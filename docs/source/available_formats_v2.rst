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

_tei_v2:

TEI full text and Raw full text for partners
------------------------------------------------------

.. note :: Access to Full text in TEI and Raw text format is only available for authorized IP address (OpenEdition partners)

OpenEdition provide partners an access to full text in TEI (`Text Encoding Initiative <http://www.tei-c.org/>`_) format and Raw text format for documents published on OpenEdition Journals and OpenEdition Books. 

Link to TEI structured full text and to Raw text (actually BASICTEI format) is retrivable from OAI in ``oai_openaire`` format, following the url available in 2 elements ``<oaire:file mimeType="application/tei+xml">``

* First element provides the URL of XML-TEI Full text (suitable for republication and text and data mining)
* Second element provides the URL of the "basicTEI" format witch provide metadata of the document in TeiHeader and raw text in the body section of the TEI document (suitable for text indexing). 

More information in detailed documentation of :ref:`oaire:file <oairefile>`.

If you need access to OpenEdition’s TEI as a partner, please email us at contact+oai@openedition.org.


**Example**

https://metadata.openedition.org/oai2?verb=GetRecord&identifier=20.500.13089/d8ae&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <oaire:file accessRightsURI="http://purl.org/coar/access_right/c_16ec" mimeType="application/tei+xml" objectType="fulltext">https://journals.openedition.org/belgeo/tei/57360</oaire:file>
    <oaire:file accessRightsURI="http://purl.org/coar/access_right/c_16ec" mimeType="application/tei+xml" objectType="fulltext">https://journals.openedition.org/belgeo/basictei/57360</oaire:file>

   


