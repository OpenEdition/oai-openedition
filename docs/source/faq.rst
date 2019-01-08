FAQ 
===

.. contents:: Table of Contents
   :depth: 2

1. How can I get only open access ressources?
-----------------------------------------------------------

Calenda and Hypotheses
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

All the Calenda and Hypotheses documents are available in open access. You can get these documents using the set that match the platforms. More info: :ref:`sets` 

**Calenda:** http://oai.openedition.org/?verb=ListRecords&metadataPrefix=oai_dc&set=events 

**Hypotheses:** http://oai.openedition.org/?verb=ListRecords&metadataPrefix=oai_dc&set=blogs 

----------------------------------------------

For ressources from OpenEdition Journals and OpenEdition Books, you can:

use the ``openaire`` set (Journals and Books)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This set lists only open access records. More info: :ref:`sets`

**OpenAIRE:** http://oai.openedition.org/?verb=ListRecords&metadataPrefix=oai_dc&set=openaire 

use dc:rights or dcterms:accessRights while harvesting (all platforms)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

For each record, the ``dc.rights`` element  (``oai_dc`` format) and the ``dcterms:accessRights`` element (``qdc`` format) provides the access policy of the document. 

See :ref:`dcrights` and :ref:`dctermsaccessrights` for details  

**Open access document (qdc):** http://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:anthropologiesante/2918&metadataPrefix=qdc

**Restricted access document (qdc):** http://oai.openedition.org/?verb=GetRecord&identifier=oai:books.openedition.org:pufr/10095&metadataPrefix=qdc 

2. How can I harvest all documents from OpenEdition Journals?
-------------------------------------------------------------------

Use the set `journals` and the metadataPrefix `oai_dc` or `qdc` to get all documents (issues, articles, reviews): http://oai.openedition.org/?verb=ListRecords&set=journals&metadataPrefix=qdc

Use the set `journals` and metadataPrefix `mets` to get only issues (with links to each articles inside the mets `structMap` element): http://oai.openedition.org/?verb=ListRecords&set=journals&metadataPrefix=mets

See the following sections for details:

.. toctree::
   :maxdepth: 1

   sets
   oai_dc
   qdc
   mets



3. How can I harvest a specific journal or blog?
----------------------------------------------------------
Use one of a following method to find and harvest a specific set: :ref:`findaset` 


4. Sample queries?
----------------------------------------------

**Retrieving general information about the repository:**

http://oai.openedition.org/?verb=Identify

**Listing available sets:**

http://oai.openedition.org/?verb=ListSets

**Retrieving all documents metadata from all platforms, in Qualified Dublin Core format:**

http://oai.openedition.org/?verb=ListRecords&metadataPrefix=qdc

**Retrieving all metadata from Calenda added since 1 January 2013, in Qualified Dublin Core format:**

http://oai.openedition.org/?verb=ListRecords&set=events:calendaorg&from=2013-01-01&metadataPrefix=qdc

**Retrieving all documents of Journal of TEI, in METS format:**

http://oai.openedition.org/?verb=ListRecords&set=journals:jtei&metadataPrefix=mets

**Listing the documents’ identifiers of the Publications de l’École française de Rome:**

http://oai.openedition.org/?verb=ListIdentifiers&set=books:efr

**Listing the available metadata formats for a post in the academic blog The Recipes Project:**

http://oai.openedition.org/?verb=ListMetadataFormats&identifier=oai:hypotheses.org:recipes/2294


