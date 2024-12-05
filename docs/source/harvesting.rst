Harvesting
======================

.. warning::

   Version 1 of the OAI-PMH repository is DEPRECIATED. Please refer to the warning on the :ref:`home page <home>`.



.. contents:: Table of Contents
   :depth: 2

The openedition repository follows the version 2.0 of the OAI-PMH protocol available on the Open Archives Initiative website: http://www.openarchives.org/OAI/openarchivesprotocol.html


Selective Harvesting
------------------------------

The repository allows selective harvesting, by set and by date. 

Selective harvesting by set
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

* For retrieving the document metadata from the Publications de l’École française de Rome only, you will have to query the ``books:efr`` set: https://oai.openedition.org/?verb=ListRecords&metadataPrefix=oai_dc&set=books:efr
* For retrieving metadata from all OpenEdition Journals documents, you will have to query the ``journals`` set: https://oai.openedition.org/?verb=ListRecords&metadataPrefix=oai_dc&set=journals


More info about available sets: :ref:`sets` 


Selective harvesting by date
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The repository allows harvesting by date, i.e. harvesting of records added or updated before or after a specified date

The parameters to use are ``from`` and ``until``. Allowed date formats are ``dd-mm-yyyy`` and ``dd-mm-yyyyThh:mm:ssZ``.

**Example**

https://oai.openedition.org/?verb=ListRecords&metadataPrefix=oai_dc&from=2017-03-13T16:47:48Z will retrieve a list of records added or updated since the 13 march 2017 at 4.47 pm.

.. _rToken:

resumptionToken
----------------------------------

The repository uses the `resumptionToken <http://www.openarchives.org/OAI/openarchivesprotocol.html#FlowControl>`_ system. Therefore, it is not possible to retrieve all documents with a single ``ListRecords``, ``ListIdentifiers`` or 
``ListSets`` request.

For instance, for retrieving the metadata of all documents from the journal Revista Crítica de Ciências Sociais, you will use the query:

https://oai.openedition.org/?verb=ListRecords&set=journals:rccs&metadataPrefix=oai_dc

The repository will return a list of the first 10 documents + a ``resumptionToken`` element at the end of the response.

.. code-block:: xml
    :linenos:

    <?xml version="1.0" encoding="UTF-8"?>
    <OAI-PMH xmlns="http://www.openarchives.org/OAI/2.0/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.openarchives.org/OAI/2.0/ http://www.openarchives.org/OAI/2.0/OAI-PMH.xsd">
      <responseDate>2018-10-12T07:11:17Z</responseDate>
      <request verb="ListRecords" metadataPrefix="oai_dc" set="journals:rccs">https://oai.openedition.org/</request>
      <ListRecords xmlns:oai_dc="http://www.openarchives.org/OAI/2.0/oai_dc/" xmlns:dc="http://purl.org/dc/elements/1.1/"> 
        <record>
          [...]
        </record>
        <record>
          [...]
        </record>
        [...]
        
        <resumptionToken completeListSize="830">metadataPrefix%3Doai_dc%26set%3Djournals%253Arccs%26until%3D2018-10-12T07%253A11%253A17Z%26cursor%3D10</resumptionToken>
      </ListRecords>
    </OAI-PMH>


For retrieving the next 10 documents, you will pass the content of the ``resumptionToken`` element as an argument of a new URL request:

https://oai.openedition.org/?verb=ListRecords&resumptionToken=metadataPrefix%3Doai_dc%26set%3Djournals%253Arccs%26until%3D2018-10-12T07%253A11%253A17Z%26cursor%3D10

and so on.


The OAI-PMH documentation available at http://www.openarchives.org/OAI/openarchivesprotocol.html gives a more detailed insight of the resumptionToken parameter.


Deleted Records
----------------------------------

The repository does not provide information about deleted records.


