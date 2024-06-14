.. _formats_v2:

Available Formats (v2 beta)
=====================================
.. warning::

      This documentation concerns version 2 beta of the OpenEdition OAI-PMH repository. This version is subject to change until version 2.0 is released. 

      **NOT FOR USE IN PRODUCTION**


.. contents:: Table of Contents
   :depth: 2

Metadata in OAI
-------------------

Records are available in the following metadata formats:

* ``oai_dc``: Dublin Core, following `OpenAIRE Guidelines for Literature Repositories v3 <https://guidelines.openaire.eu/en/latest/literature/index_guidelines-lit_v3.html>`_
* ``oai_openaire``: `OpenAIRE Guidelines for Literature Repository Managers v4 <https://openaire-guidelines-for-literature-repository-managers.readthedocs.io/en/v4.0.0/>`_
* ``mods``: `Metadata Object Description Schema <https://www.loc.gov/standards/mods/>`_ 
* ``mets``: `Metadata Encoding and Transmission Standard <https://www.loc.gov/standards/mets/>`_

The METS format is available only for journal issues and books. It is not available for blogs, Calenda events.

.. _tei_v2:

TEI full text and Raw full text for partners
------------------------------------------------------

TODO 

.. note :: Access to Full text in TEI and Raw text format is only available for authorized IP address (OpenEdition partners)

OpenEdition provide partners an access to full text in TEI (`Text Encoding Initiative <http://www.tei-c.org/>`_) format and Raw text format for documents published on OpenEdition Journals and OpenEdition Books. 

Link to TEI structured full text and to Raw text (actually BASICTEI format) is retrivable from OAI in ``qdc`` format, following the url available in these elements:

* ``<dcterms:hasFormat scheme="TEI">``: link to structured  XML-TEI Full text (suitable for republication and text and data mining)
* ``<dcterms:hasFormat scheme="BASICTEI">``: link to full text in the "basicTEI" format witch provide metadata of the document in TeiHeader and raw text in the body section of the TEI document (suitable for text indexing). 

If you need access to OpenEdition’s TEI as a partner, please email us at contact+oai@openedition.org.


**Example**

https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:terrain/16916&metadataPrefix=qdc

.. code-block:: xml
    :linenos:

    <?xml version="1.0" encoding="UTF-8"?>
    <OAI-PMH xmlns="http://www.openarchives.org/OAI/2.0/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.openarchives.org/OAI/2.0/ http://www.openarchives.org/OAI/2.0/OAI-PMH.xsd">
      <responseDate>2018-10-11T20:34:26Z</responseDate>
      <request verb="GetRecord" identifier="oai:revues.org:terrain/16916" metadataPrefix="qdc">https://oai.openedition.org/</request>
      <GetRecord xmlns:qdc="http://epubs.cclrc.ac.uk/xmlns/qdc/" xmlns:dcterms="http://purl.org/dc/terms/">
        <record>
          <header>
            <identifier>oai:revues.org:terrain/16916</identifier>
            <datestamp>2018-10-09T10:04:10Z</datestamp>
            <setSpec>journals</setSpec>
            <setSpec>journals:terrain</setSpec>
            <setSpec>openaire</setSpec>
          </header>
          <metadata>
            <qdc:qualifieddc xmlns:dcterms="http://purl.org/dc/terms/" xmlns:qdc="http://epubs.cclrc.ac.uk/xmlns/qdc/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://purl.org/dc/terms/ http://dublincore.org/schemas/xmls/qdc/2006/01/06/dcterms.xsd http://epubs.cclrc.ac.uk/xmlns/qdc/ http://epubs.cclrc.ac.uk/xsd/qdc.xsd">
              <dcterms:title>Y a-t-il une différence entre « Roms » et « Roumains » ?</dcterms:title>
              
              [...]
          
              <dcterms:hasFormat scheme="TEI">http://journals.openedition.org/terrain/tei/16916</dcterms:hasFormat>
              <dcterms:hasFormat scheme="BASICTEI">http://journals.openedition.org/terrain/basictei/16916</dcterms:hasFormat>
            </qdc:qualifieddc>
          </metadata>
        </record>
      </GetRecord>
    </OAI-PMH>



