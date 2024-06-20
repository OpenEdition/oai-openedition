.. _sets_v2:

Sets description (v2 beta)
========================================

.. warning::

      This documentation concerns version 2 beta of the OpenEdition OAI-PMH repository. This version is subject to change until version 2.0 is released. 

      **NOT FOR USE IN PRODUCTION**

.. contents:: Table of Contents
   :depth: 2

Available sets
-------------------------

One set for each platform:

* ``journals``: records from OpenEdition Journals
* ``books``: records from OpenEdition Books
* ``blogs``: records from Hypotheses
* ``events``: records from Calenda

One set for each "publication" (Journal, Blog, Book Publisher)

* ``journals:[journalID]``: records from a specific journal. Ex. ``journals:chs``
* ``books:[publisherID]``: records from a specific book publisher. Ex. ``books:pur``
* ``blogs:[blogID]``: records from a specific blog. Ex. ``blogs:cpa``
* Not applicable for Calenda

.. _findaset:

Find a set
--------------

There are several ways to find the identifier of a set:

From OAI ListSets 
^^^^^^^^^^^^^^^^^^^
The complete list of Sets is available in the repository using the OAI verb ``ListSets``. The repository displays 100 sets per page. Use the ``resumptionToken`` parameter to display the next page. 

* https://metadata.openedition.org/oai?verb=ListSets
* https://metadata.openedition.org/oai?verb=ListSets&resumptionToken=cursor%3D100%26cursorMark%3DAoEnT0oucmllZg%3D%3D


From publication URL
^^^^^^^^^^^^^^^^^^^^^
You can infer the set identifier of a publication (journal, blog...)  from its URL.

**Examples**

============================================ ========================
URL                                          Set
============================================ ========================
https://journals.openedition.org/vertigo     ``journals:vertigo``
https://books.openedition.org/editionsmsh    ``books:editionsmsh``
https://sms.hypotheses.org                   ``blogs:sms``
============================================ ========================


From Kbart Coverage List
^^^^^^^^^^^^^^^^^^^^^^^^
For OpenEdition Journals publications, the [journalID] is available in our Kbart coverage list: https://www.openedition.org/journal-title-list.html?kbart=1 (title_id column)

Set = ``journals:[journalID]``

Sample queries
-------------------

* https://metadata.openedition.org/oai?verb=ListRecords&metadataPrefix=oai_dc&set=journals
* https://metadata.openedition.org/oai?verb=ListRecords&metadataPrefix=oai_dc&set=books
* https://metadata.openedition.org/oai?verb=ListRecords&metadataPrefix=oai_dc&set=blogs
* https://metadata.openedition.org/oai?verb=ListRecords&metadataPrefix=oai_dc&set=events
* https://metadata.openedition.org/oai?verb=ListRecords&metadataPrefix=oai_dc&set=openaire

--------------------------------------

* https://metadata.openedition.org/oai?verb=ListRecords&metadataPrefix=oai_dc&set=journals:ejpap
* https://metadata.openedition.org/oai?verb=ListRecords&metadataPrefix=oai_dc&set=books:pur
* https://metadata.openedition.org/oai?verb=ListRecords&metadataPrefix=oai_dc&set=blogs:histoirebnf



