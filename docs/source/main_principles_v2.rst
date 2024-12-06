.. _main_principles_v2:

Main Principles
==================================

.. contents:: Table of Contents
   :depth: 2


The OpenEdition repository follows the version 2.0 of the OAI-PMH protocol available on the Open Archives Initiative website: http://www.openarchives.org/OAI/openarchivesprotocol.html

.. note::

      What's new in this version?

      - The repository uses Handles as identifiers
      - It supports deleted records
      - It is compatible with OpenAIRE v4
      - It provides metadata in the following formats:

        * ``oai_dc``: Dublin Core, following `OpenAIRE Guidelines for Literature Repositories v3 <https://guidelines.openaire.eu/en/latest/literature/index_guidelines-lit_v3.html>`_
        * ``oai_openaire``: `OpenAIRE Guidelines for Literature Repository Managers v4 <https://openaire-guidelines-for-literature-repository-managers.readthedocs.io/en/v4.0.0/>`_
        * ``mods``: `Metadata Object Description Schema <https://www.loc.gov/standards/mods/>`_ 
        * ``mets``: `Metadata Encoding and Transmission Standard <https://www.loc.gov/standards/mets/>`_

      Migration steps from v1 to v2

      - june-october 2024: OpenEdition OAI-PMH v2 is tested by partners.
      - november 2024: v2.0 is released and usable in production environment. v1 is declared Deprecated.
      - november 2024-june 2025: v1 and v2 continue to run in parallel, while harvesters upgrade to version 2.
      - june 2025: v1 is removed.


.. _oe_identifier:

OpenEdition Identifiers
----------------------------------

Handle and DOI
^^^^^^^^^^^^^^^^^^^^^^^^^

- OpenEdition uses 2 PID system (Handle and DOI) for the documents published on the 4 platforms:

  - `OpenEdition Books <https://books.openedition.org>`_
  - `OpenEdition Journals <https://journals.openedition.org>`_
  - `Hypotheses <https://hypotheses.org>`_
  - `Calenda <https://calenda.org>`_

- The Handle system covers 100% of the documents
- The DOI system covers 100% of documents for Hypotheses and Calenda and around 90% for OpenEdition Books and Journals
- Since the OAI-PMH protocol needs identifiers for all records, the OAI-PMH identifier system is Handle.

Retrieving Handle, DOI and URL
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Handle, DOI and URL and other metadata can be retrieved from the metadata service witch return metadata (format `CSL-data.json <https://github.com/citation-style-language/schema/blob/master/schemas/input/csl-data.json>`_) on each document from:

- Handle: ``https://metadata.openedition.org/handle/[HANDLE]?format=json``
- DOI: ``https://metadata.openedition.org/doi/[DOI]?format=json``
- Content Id: ``https://metadata.openedition.org/contentid/[CONTENTID]?format=json``

**Journal article example:** https://journals.openedition.org/rdr/1789

- Retrieving metadata:

+------------+-----------------------------------------------------------------------+
| Handle     | https://metadata.openedition.org/handle/20.500.13089/jlrc?format=json |
+------------+-----------------------------------------------------------------------+
| DOI        | https://metadata.openedition.org/doi/10.4000/rdr.1789?format=json     |
+------------+-----------------------------------------------------------------------+
| Content ID | https://metadata.openedition.org/contentid/OJ.rdr.1789?format=json    |
+------------+-----------------------------------------------------------------------+

- Several Citation format for each document (argument ``format (default="mla")``):

+---------------+--------------------------------------------------------------------------+
| CSL-data.json | https://metadata.openedition.org/handle/20.500.13089/jlrc?format=json    |
+---------------+--------------------------------------------------------------------------+
| Text MLA      | https://metadata.openedition.org/handle/20.500.13089/jlrc?format=mla     |
+---------------+--------------------------------------------------------------------------+
| Text APA      | https://metadata.openedition.org/handle/20.500.13089/jlrc?format=apa     |
+---------------+--------------------------------------------------------------------------+
| Text Chicago  | https://metadata.openedition.org/handle/20.500.13089/jlrc?format=chicago |
+---------------+--------------------------------------------------------------------------+

- Content ID can be deduced from the url and conversely:

+----------------------+-------------------------------------------------+-----------------------+
| Platform             | URL                                             | ContentId             |
+======================+=================================================+=======================+
| OpenEdition Journals | https://journals.openedition.org/rdr/1789       | OJ.rdr.1789           |
+----------------------+-------------------------------------------------+-----------------------+
| OpenEdition Books    | https://books.openedition.org/momeditions/18666 | OB.momeditions.18666  |
+----------------------+-------------------------------------------------+-----------------------+
| Hypotheses           | https://sms.hypotheses.org/43068                | HO.sms.43068          |
+----------------------+-------------------------------------------------+-----------------------+
| Calenda              | https://calenda.org/1170768                     | CO.calendaorg.1170768 |
+----------------------+-------------------------------------------------+-----------------------+

More information about CSL format:

- https://citationstyles.org/
- https://github.com/citation-style-language/schema
- json schema used in OpenEdition metadata service: https://github.com/citation-style-language/schema/blob/master/schemas/input/csl-data.json

.. _identifier_v2:

OAI-PMH Identifiers
----------------------------------

- Identifiers used in the repository are of the `handle <https://www.handle.net/>`_ type.
- They resolve to the resource using the Handle resolver: https://hdl.handle.net/XXX

Example:

https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/k1x3&metadataPrefix=oai_dc returns:


.. code-block:: xml
    :linenos:

    <?xml version="1.0" encoding="UTF-8"?>
    <record>
      <header>
        <identifier>20.500.13089/k1x3</identifier>
        <datestamp>2019-05-21T16:57:47Z</datestamp>
        <setSpec>journals</setSpec>
        <setSpec>journals:rfp</setSpec>
      </header>

The resource is available at https://hdl.handle.net/20.500.13089/k1x3

Deleted Records
----------------------------------

The repository supports the notion of deleted records. Deleted records are persistent, meaning the information is still availaible over time in the repository.


Example: 
https://metadata.openedition.org/oai?verb=ListRecords&set=journals:ges&metadataPrefix=oai_dc


.. code-block:: xml
    :linenos:

    <OAI-PMH xmlns="http://www.openarchives.org/OAI/2.0/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.openarchives.org/OAI/2.0/ http://www.openarchives.org/OAI/2.0/OAI-PMH.xsd">
      <responseDate>2024-06-10T06:24:24Z</responseDate>
      <request verb="ListRecords" set="journals:ges" metadataPrefix="oai_dc" cursor="0">https://metadata.openedition.org/oai</request>
      <ListRecords>
        <record>
          [...]
        </record>
        <record>
          <header status="deleted">
            <identifier>20.500.13089/vmnb</identifier>
            <datestamp>2024-01-19T12:06:50Z</datestamp>
            <setSpec>journals</setSpec>
            <setSpec>journals:ges</setSpec>
          </header>
        </record>

Note that Handles of deleted records still resolve to a landing page with metadata of the deleted resource. Example: https://hdl.handle.net/20.500.13089/vmnb

More information on deleted records at OAI-PMH website: https://www.openarchives.org/OAI/openarchivesprotocol.html#DeletedRecords


Selective Harvesting
------------------------------

The repository allows selective harvesting, by set and by date. 

Selective harvesting by set
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

* For retrieving the document metadata from the Publications de l’École française de Rome only, you will have to query the ``books:efr`` set: https://metadata.openedition.org/oai/?verb=ListRecords&metadataPrefix=oai_dc&set=books:efr
* For retrieving metadata from all OpenEdition Journals documents, you will have to query the ``journals`` set: https://metadata.openedition.org/oai/?verb=ListRecords&metadataPrefix=oai_dc&set=journals


More info about available sets: :ref:`sets_v2` 


Selective harvesting by date
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The repository allows harvesting by date, i.e. harvesting of records added or updated before or after a specified date

The parameters to use are ``from`` and ``until``. Allowed date formats are ``dd-mm-yyyy`` and ``dd-mm-yyyyThh:mm:ssZ``.

**Example**

https://metadata.openedition.org/oai/?verb=ListRecords&metadataPrefix=oai_dc&from=2017-03-13T16:47:48Z will retrieve a list of records added or updated since the 13 march 2017 at 4.47 pm.

.. _rToken_v2:

resumptionToken
----------------------------------

The repository uses the `resumptionToken <http://www.openarchives.org/OAI/openarchivesprotocol.html#FlowControl>`_ system. Therefore, it is not possible to retrieve all documents with a single ``ListRecords``, ``ListIdentifiers`` or ``ListSets`` request.

For instance, for retrieving the metadata of all documents from the journal Revista Crítica de Ciências Sociais, you will use the query:

https://metadata.openedition.org/oai/?verb=ListRecords&set=journals:rccs&metadataPrefix=oai_dc

The repository will return a list of the first 100 documents + a ``resumptionToken`` element at the end of the response.

.. code-block:: xml
    :linenos:

    <?xml version="1.0" encoding="UTF-8"?>
    <OAI-PMH xmlns="http://www.openarchives.org/OAI/2.0/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.openarchives.org/OAI/2.0/ http://www.openarchives.org/OAI/2.0/OAI-PMH.xsd">
      <responseDate>2024-06-09T19:39:32Z</responseDate>
      <request verb="ListRecords" set="journals:rccs" metadataPrefix="oai_dc" cursor="0">https://metadata.openedition.org/oai</request>
      <ListRecords>
        <record>
          [...]
        </record>
        <record>
          [...]
        </record>
        [...]

        <resumptionToken cursor="0" completeListSize="1075">set%3Djournals%3Arccs%26metadataPrefix%3Doai_dc%26cursor%3D100%26cursorMark%3DAoErT0oucmNjcy44NjI%3D</resumptionToken>
      </ListRecords>


For retrieving the next 10 documents, you will pass the content of the ``resumptionToken`` element as an argument of a new URL request:

https://metadata.openedition.org/oai?verb=ListRecords&resumptionToken=set%3Djournals%3Arccs%26metadataPrefix%3Doai_dc%26cursor%3D100%26cursorMark%3DAoErT0oucmNjcy44NjI%3D
and so on.


The OAI-PMH documentation available at http://www.openarchives.org/OAI/openarchivesprotocol.html gives a more detailed insight of the resumptionToken parameter.



