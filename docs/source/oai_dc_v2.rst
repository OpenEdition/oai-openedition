.. _oai_dc_v2:

oai_dc format (v2 beta)
========================================

.. warning::

      This documentation concerns version 2 beta of the OpenEdition OAI-PMH repository. This version is subject to change until version 2.0 is released. 

      **NOT FOR USE IN PRODUCTION**



.. contents:: Table of Contents
   :depth: 2

The ``oai_dc`` format provides the following elements, according to  `OpenAIRE Guidelines for Literature Repositories v3 <https://guidelines.openaire.eu/en/latest/literature/index_guidelines-lit_v3.html>`_.

1. dc:identifier
-------------------
Identifier of the document. Repeatable.

1.1. Handle
^^^^^^^^^^^^
- ``dc:identifier`` provides the Handle of the document, prefixed by the Handle resolver URL ``https://hdl.handle.net/``
- Available for all platforms. 
- Available for all records.
- The Handle identifier is also used as OAI-PMH identifier ``record/header/identifier``

**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/jsak&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:identifier>https://hdl.handle.net/20.500.13089/jsak</dc:identifier>


1.2. DOI
^^^^^^^^^^

- ``dc:identifier`` provides the DOI of the document, prefixed by the DOI resolver URL ``https://doi.org/``
- Available for all platforms. 
- Some records from OpenEdition Books and OpenEdition Journals may have no DOI.


**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/jsak&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:identifier>https://doi.org/10.4000/remi.5530</dc:identifier>


1.3. URL
^^^^^^^^^
- ``dc:identifier`` provides without prefix the URL of the document.
- Available for all platforms. 
- All records have an URL.

**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/jsak&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:identifier>http://journals.openedition.org/remi/5530</dc:identifier>

1.4. ISBN
^^^^^^^^^^

- ``dc:identifier`` with ``info:eu-repo/semantics/altIdentifier/isbn/`` prefix provides ISBN of the digital and print version of the book.
- Available for books (OpenEdition Books) and journals issues (OpenEdition Journals).

**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/31o4&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:
    
    <dc:identifier>info:eu-repo/semantics/altIdentifier/isbn/978-2-8218-7547-0</dc:identifier>
    <dc:identifier>info:eu-repo/semantics/altIdentifier/isbn/978-3-86395-122-1</dc:identifier>

2. dc:title
-----------------

Title of the document. Non-repeatable.

3. dc:creator
-----------------
- Author(s), scientific and academic editor of the document. Repeatable.

**Example of a book:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/31o8&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:creator>Groth, Stefan</dc:creator>

For archeological note, ``dc:creator`` may also contain archaeological project directors.

**Example:** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/9xim&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:creator>Racinet, Philippe</dc:creator>
    <dc:creator>Jonvel, Richard</dc:creator>


4. dc:contibutor
-----------------

- Other contributors: translators, collaborators (For archeological note and article). 

**Example (translator):** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/k5wx&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:contributor>Mannoni, Olivier</dc:contributor>


**Example (collaborators):** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/9wrn&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:contributor>Perrault, Christophe</dc:contributor>
    <dc:contributor>Prat, Béatrice</dc:contributor>
    <dc:contributor>Rué, Mathieu</dc:contributor>
    <dc:contributor>Caillat, Pierre</dc:contributor>



.. _dcrights:

5. dc:rights
-----------------

5.1. License
^^^^^^^^^^^^^^^

- ``dc:rights`` contains license information.
- Available for all records.


5.2. OpenAIRE Access Level
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

* Following `OpenAIRE 3.0 guidelines (Access Level) <https://guidelines.openaire.eu/en/latest/literature/field_accesslevel.html>`_, an extra ``dc.rights`` element with a prefix ``info:eu-repo/semantics/`` provides the publication access level with the following vocabulary:

  * ``info:eu-repo/semantics/embargoedAccess``
  * ``info:eu-repo/semantics/restrictedAccess``
  * ``info:eu-repo/semantics/openAccess``

* Available for all records.

**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/1i54&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:rights>info:eu-repo/semantics/openAccess</dc:rights>
    <dc:rights>https://creativecommons.org/licenses/by-sa/4.0/</dc:rights>  




6. dc:date
-----------------

- ``dc:date`` provides without prefix the year of publication of the document.
- ``dc:date`` with prefix ``info:eu-repo/date/publication/`` provides the publishing date of the document on OpenEdition platform. 
- For OpenEdition Journals, and according to `OpenAIRE 3.0 guidelines (Embargo End Date) <https://guidelines.openaire.eu/en/latest/literature/field_embargoenddate.html#dc-date-embargo>`_, if ``dc:rights = "info:eu-repo/semantics/embargoedAccess"``, then an extra ``dc.date`` element with a prefix ``info:eu-repo/date/embargoEnd/`` will provide the end date of embargo (availability date of the document in open access):

**Example (book published in 1990, published on OpenEditon Books on 28/08/2022):** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/5div&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:date>1990</dc:date>
    <dc:date>info:eu-repo/date/publication/2022-08-28</dc:date>	

**Example (journal article with embargoed access):** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/k213&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:rights>info:eu-repo/semantics/embargoedAccess</dc:rights>
    <dc:date>2023</dc:date>
    <dc:date>info:eu-repo/date/publication/2023-11-28</dc:date>
    <dc:date>info:eu-repo/date/embargoEnd/2027-01-01</dc:date>


7. dc:publisher
-----------------

- ``dc:publisher`` provides the publisher name. Repeatable.

**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/1x9t&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:
    
    <dc:publisher>Casa de Velázquez</dc:publisher>
    <dc:publisher>Éditions Rue d’Ulm</dc:publisher>

8. dc:language
-----------------
- Document language. RFC1766 format. 

**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/1x9t&metadataPrefix=oai_dc


.. code-block:: xml
    :linenos:
    
    <dc:language>fr</dc:language>


.. _dctype_v2:

9. dc:type
-----------------

9.1. OpenEdition Types
^^^^^^^^^^^^^^^^^^^^^^

- ``dc:type`` provides the document type according to the list of types available in this section: :ref:`types_v2`. 
- Available for all records. 


**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/11r0i&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:type>call for papers</dc:type>
 


9.2. OpenAIRE Types
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

* According to `OpenAIRE 3.0 guidelines (Publication Type) <https://guidelines.openaire.eu/en/latest/literature/field_publicationtype.html>`_, an extra ``dc.type`` element with a prefix ``info:eu-repo/semantics/`` provide the publication type with the following vocabulary:

  * ``info:eu-repo/semantics/article``
  * ``info:eu-repo/semantics/review``
  * ``info:eu-repo/semantics/book``
  * ``info:eu-repo/semantics/bookpart``
  * ``info:eu-repo/semantics/other``

* Available for all records. 

**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/hpx1&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:
    
    <dc:type>info:eu-repo/semantics/review</dc:type>


10. dc:subject
-----------------

- ``dc:subject`` may contains keywords. In this case, an ``xml:lang`` attribute specifies the language of the keyword.
- Available for OpenEdition Journals, OpenEdition Books and Calenda.

**Example:** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/d85h&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:subject xml:lang="en">Belgium</dc:subject>
    <dc:subject xml:lang="en">migration</dc:subject>
    <dc:subject xml:lang="en">commuting</dc:subject>
    <dc:subject xml:lang="en">community detection</dc:subject>
    <dc:subject xml:lang="en">interaction fields</dc:subject>
    <dc:subject xml:lang="en">provinces</dc:subject>
    <dc:subject xml:lang="en">Census11</dc:subject>
    <dc:subject xml:lang="fr">Belgique</dc:subject>
    <dc:subject xml:lang="fr">migration</dc:subject>
    <dc:subject xml:lang="fr">détection de communautés</dc:subject>
    <dc:subject xml:lang="fr">champs d’interactions</dc:subject>
    <dc:subject xml:lang="fr">navettes</dc:subject>
    <dc:subject xml:lang="fr">provinces</dc:subject>
    <dc:subject xml:lang="fr">Census11</dc:subject>


11. dc:description
--------------------------------

``dc:description`` contains abstracts of the document if available, an excerpt (usualy the first lines) otherwise. Abstacts may be available in several languages. In this case, and ``xml:lang`` attribute specifies the language of the description.

**Example:** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/l8zw&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:description xml:lang="fr">L’archipel des Marquises (Polynésie française) construit son projet de développement territorial, y figurent deux projets d’excellence : l’inscription de l’archipel sur la liste du patrimoine mondial de l’UNESCO et la création d’une aire marine protégée. Dans ce contexte, un programme de recherche partenarial et participatif portant sur le patrimoine lié à la mer aux Marquises (PALIMMA) a contribué à identifier les connaissances présentes dans la bibliographie et à construire des données avec la population. Il s’agissait de déterminer quels étaient les patrimoines liés à la mer pour les Marquisiens, les éventuelles menaces afférentes et les pistes de gestion. Au-delà de la production de connaissance, ce programme, porté par la société marquisienne, a participé à la construction des territoires, à renforcer la capacité des populations à intervenir dans les débats et à la construction de liens entre individus et institutions.</dc:description>
    <dc:description xml:lang="en">Marquesas islands archipelago aimes to built its territorial development project in particular thanks to become listed as a world heritage site by UNESCO and the establishment of a marine protected area. In this context, a research programme was carried out. It was a partenarial and partipatory research about maritime heritage in Marquesas (PALIMMA). The objectives were to identify knowledge in the bibliography and to built data with the population (what heritage, what threats and what managerial solutions). Beyond knowledge production, this research programme, with marquisian local community, showed how important it is in ordrer to reach a balanced territorial development, to foster the empowerment of local population and to build relationships between individuals and institutions. A research program like PALIMMA can help to aim those objectives.</dc:description>

12. dc:relation
----------------------------

According to `OpenAIRE 3.0 guidelines (Publication Reference) <https://guidelines.openaire.eu/en/latest/literature/field_publicationreference.html>`_, 

- ``dc.relation`` element with a prefix ``info:eu-repo/semantics/reference/issn/`` provides ISSNs of the online journal and of the print version (if available).

For chapters published in a book and articles published in a journal issue :

- ``dc.relation`` element with a prefixe ``https://hdl.handle.net/`` provides the Handle of the parent book or journal issue.
- ``dc.relation`` element with a prefixe ``https://doi.org/`` provides the DOI of the parent book or journal issue.
- ``dc.relation`` element with a prefixe ``info:eu-repo/semantics/altIdentifier/isbn/`` provides the online and print ISBN of the parent book or journal issue.


**Example (journal article):** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/gh7p&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:relation>info:eu-repo/semantics/reference/issn/1627-4873</dc:relation>
    <dc:relation>info:eu-repo/semantics/reference/issn/1960-601X</dc:relation>


**Example (book chapter):** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/7kfl&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:relation>https://hdl.handle.net/20.500.13089/81qu</dc:relation>
    <dc:relation>https://doi.org/10.4000/books.pur.29424</dc:relation>
    <dc:relation>info:eu-repo/semantics/altIdentifier/isbn/978-2-7535-4677-6</dc:relation>
    <dc:relation>info:eu-repo/semantics/altIdentifier/isbn/978-2-7535-0687-9</dc:relation>

 
13. dc:format
-----------------

- mime type of all records is ``text/html``

**Example:** https://metadata.openedition.org/oai?verb=GetRecord&identifier=oai:revues.org:geocarrefour/10121&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:format>text/html</dc:format>

14. dc:source
-----------------
Unused


15. dc:coverage
-----------------
Unused



