OAI_DC format
===================

.. contents:: Table of Contents
   :depth: 2

The ``oai_dc`` format provides the following elements:

1. dc:title
-----------------

Title of the document. Non-repeatable.

2. dc:creator
-----------------
Author(s) of the document. Repeatable.

Unavailable for Calenda.

For Journal Issues and Books, ``dc.creator`` provides authors of the issue or the book AND authors of the child articles or chapters.

**Example of a book with multiple authors at chapter level:** 
https://oai.openedition.org/?verb=GetRecord&identifier=oai:books.openedition.org:gup/348&metadataPrefix=oai_dc

For archeological note, ``dc:contributor`` may also contain archaeological project directors.

**Example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:archeomed/7020&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:type>archaeological note</dc:type>
    <dc:creator>Racinet, Philippe</dc:creator>
    <dc:creator>Jonvel, Richard</dc:creator>

See https://journals.openedition.org/archeomed/7020?lang=en for roles of each ``dc:creator``.

3. dc:contibutor
-----------------

Scientific and academic editor of the document. Available for OpenEdition Journals and OpenEdition Books. 

**Example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:books.openedition.org:cvz/3321&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:contributor>Alvarez Roblin, David</dc:contributor>
    <dc:contributor>Biaggini, Olivier</dc:contributor>

For archeological note and article, ``dc:contributor`` may also contain collaborators.

**Example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:archeomed/11348&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:contributor>Perrault, Christophe</dc:contributor>
    <dc:contributor>Prat, Béatrice</dc:contributor>
    <dc:contributor>Rué, Mathieu</dc:contributor>
    <dc:contributor>Caillat, Pierre</dc:contributor>

See https://journals.openedition.org/archeomed/11348?lang=en for roles of each ``dc:contributor``.


.. _dcrights:

4. dc:rights
-----------------

4.1. License
^^^^^^^^^^^^^^^

Available for OpenEdition Journals and OpenEdition Books. 
``dc:rights`` may contain license information if provided by the publisher.


4.2. OpenAIRE Access Level (OpenEdition Journals and Openedition Books)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

For OpenEdition Journals and OpenEdition Books, and according to `OpenAIRE 3.0 guidelines (Access Level) <https://guidelines.openaire.eu/en/latest/literature/field_accesslevel.html>`_, an extra ``dc.rights`` element with a prefix ``info:eu-repo/semantics/`` will provide the publication type with the following vocabulary:

* ``info:eu-repo/semantics/embargoedAccess``
* ``info:eu-repo/semantics/restrictedAccess``
* ``info:eu-repo/semantics/openAccess``

**Example:** 
https://oai.openedition.org/?verb=GetRecord&identifier=oai:books.openedition.org:ariadnaediciones/158&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:
    
    <dc:rights>CC BY-SA 3.0</dc:rights>
    <dc:rights>info:eu-repo/semantics/openAccess</dc:rights>




5. dc:date
-----------------
Publishing date of the document on OpenEdition platform. 

If an article was previously published in another format (for instance a print version), the ``dc:date`` element won't provide the date of the previous publishing but only the publishing date of the document on OpenEdition.

For OpenEdition Journals, and according to `OpenAIRE 3.0 guidelines (Embargo End Date) <https://guidelines.openaire.eu/en/latest/literature/field_embargoenddate.html#dc-date-embargo>`_, if ``dc:rights = "info:eu-repo/semantics/embargoedAccess"``, then an extra ``dc.date`` element with a prefix ``info:eu-repo/date/embargoEnd/`` will provide the end date of embargo (availability date of the document in open access):

**Example:** 
https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:remi/8732&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:rights>info:eu-repo/semantics/embargoedAccess</dc:rights>
    <dc:date>info:eu-repo/date/embargoEnd/2021-01-01</dc:date>

6. dc:publisher
-----------------

``dc:publisher`` provides the publisher name.

For OpenEdition Journals and Hypotheses documents ``dc:publisher`` provides also the journal or blog title

**Example:** 
https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:studifrancesi/2636&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:
    
    <dc:publisher>Rosenberg &amp; Sellier</dc:publisher>
    <dc:publisher>Studi Francesi</dc:publisher>


7. dc:identifier
-------------------
Identifier of the document. Repeatable.

7.1. URL
^^^^^^^^^
``dc:identifier`` provides without prefix the URL of the document.

**Example:** 
https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:remi/5530&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:identifier>http://journals.openedition.org/remi/5530</dc:identifier>

7.2. DOI
^^^^^^^^^^
Available for OpenEdition Journals and OpenEdition Books.

``dc:identifier`` with ``urn:doi`` prefix provides the DOI of the document.

**Example:** 
https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:remi/5530&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:identifier>urn:doi:10.4000/remi.5530</dc:identifier>

7.3. ISBN
^^^^^^^^^^
Available for OpenEdition Books.

``dc:identifier`` with ``urn:isbn`` and ``urn:eisbn`` prefix provides respectively ISBN of the print and electronic version of the book.

**Example:** 
https://oai.openedition.org/?verb=GetRecord&identifier=oai:books.openedition.org:gup/348&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:
    
    <dc:identifier>urn:eisbn:9782821875470</dc:identifier>
    <dc:identifier>urn:isbn:9783863951221</dc:identifier>

For OAI records of a book chapter, the ISBN and eISBN provided refer to the parent book of that chapter.

**Example:** 
https://oai.openedition.org/?verb=GetRecord&identifier=oai:books.openedition.org:gup/367&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:
    
    <dc:identifier>urn:eisbn:9782821875470</dc:identifier>
    <dc:identifier>urn:isbn:9783863951221</dc:identifier>

8. dc:language
-----------------
Document language. RFC1766 format. 

**Example:** 
https://oai.openedition.org/?verb=GetRecord&identifier=oai:books.openedition.org:cfee/1081&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:
    
    <dc:language>en</dc:language>


.. _dctype:

9. dc:type
-----------------

9.1. OpenEdition Types
^^^^^^^^^^^^^^^^^^^^^^
Available for all platforms. 

``dc:type`` provides the document type according to the list of types available in this section: :ref:`types`. 

**Example:** 
https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:lectures/27329&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:
    
    <dc:type>review</dc:type>


9.2. OpenAIRE Types (OpenEdition Journals and Openedition Books)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

For OpenEdition Journals and OpenEdition Books, and according to `OpenAIRE 3.0 guidelines (Publication Type) <https://guidelines.openaire.eu/en/latest/literature/field_publicationtype.html>`_, an extra ``dc.type`` element with a prefix ``info:eu-repo/semantics/`` will provide the publication type with the following vocabulary:

* ``info:eu-repo/semantics/article``
* ``info:eu-repo/semantics/review``
* ``info:eu-repo/semantics/book``
* ``info:eu-repo/semantics/bookpart``
* ``info:eu-repo/semantics/other``

**Example:** 
https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:lectures/27329&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:
    
    <dc:type>info:eu-repo/semantics/review</dc:type>

10. dc:coverage
-----------------
Available for OpenEdition Journals and OpenEdition Books.

``dc:coverage`` may contain spatial topics of the document.

**Example:** 
https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:balkanologie/717&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:
    
    <dc:coverage>Bulgarie</dc:coverage>
    <dc:coverage>Turquie</dc:coverage>


11. dc:subject
-----------------

11.1 Keywords
^^^^^^^^^^^^^^^^^^

Available for OpenEdition Journals and OpenEdition Books. 
``dc:subject`` may contains keywords. In this case, an ``xml:lang`` attribute specifies the language of the keyword.

**Example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:belgeo/20507&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:subject xml:lang="fr">détection de communautés</dc:subject>
    <dc:subject xml:lang="fr">champs d’interactions</dc:subject>
    <dc:subject xml:lang="fr">migration</dc:subject>
    <dc:subject xml:lang="fr">navettes</dc:subject>
    <dc:subject xml:lang="fr">provinces</dc:subject>
    <dc:subject xml:lang="fr">Belgique</dc:subject>
    <dc:subject xml:lang="fr">Census11</dc:subject>
    <dc:subject xml:lang="en">community detection</dc:subject>
    <dc:subject xml:lang="en">interaction fields</dc:subject>
    <dc:subject xml:lang="en">migration</dc:subject>
    <dc:subject xml:lang="en">commuting</dc:subject>
    <dc:subject xml:lang="en">provinces</dc:subject>
    <dc:subject xml:lang="en">Belgium</dc:subject>
    <dc:subject xml:lang="en">Census11</dc:subject>


11.2 Other Subjects
^^^^^^^^^^^^^^^^^^^^^^
For OpenEdition Books only, ``dc:subject`` may also contains terms from `BISAC <https://bisg.org/page/BISACSubjectCodes>`_, `BIC <https://ns.editeur.org/bic_categories>`_, `ISI <https://en.wikipedia.org/wiki/Institute_for_Scientific_Information>`_ classification.

**Example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:books.openedition.org:pum/21469&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:subject xml:lang="fr">environnement</dc:subject>
    <dc:subject xml:lang="fr">protection</dc:subject>
    <dc:subject xml:lang="fr">gestion</dc:subject>
    <dc:subject xml:lang="fr">politique gouvernementale</dc:subject>
    <dc:subject>Environmental Studies</dc:subject> <!-- from ISI -->
    <dc:subject>Political Science</dc:subject>     <!-- from ISI -->
    <dc:subject>POL044000</dc:subject>             <!-- From BISAC -->
    <dc:subject>RND</dc:subject>                   <!-- From BIC -->



12. dc:source
-----------------
Unused

13. dc:description
--------------------------------

``dc:description`` contains abstracts of the document if available, an excerpt (usualy the first lines) otherwise. Abstacts may be available in several languages. In this case, and ``xml:lang`` attribute specifies the language of the description.

**Example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:tem/4515&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:description xml:lang="fr">L’archipel des Marquises (Polynésie française) construit son projet de développement territorial, y figurent deux projets d’excellence : l’inscription de l’archipel sur la liste du patrimoine mondial de l’UNESCO et la création d’une aire marine protégée. Dans ce contexte, un programme de recherche partenarial et participatif portant sur le patrimoine lié à la mer aux Marquises (PALIMMA) a contribué à identifier les connaissances présentes dans la bibliographie et à construire des données avec la population. Il s’agissait de déterminer quels étaient les patrimoines liés à la mer pour les Marquisiens, les éventuelles menaces afférentes et les pistes de gestion. Au-delà de la production de connaissance, ce programme, porté par la société marquisienne, a participé à la construction des territoires, à renforcer la capacité des populations à intervenir dans les débats et à la construction de liens entre individus et institutions.</dc:description>
    <dc:description xml:lang="en">Marquesas islands archipelago aimes to built its territorial development project in particular thanks to become listed as a world heritage site by UNESCO and the establishment of a marine protected area. In this context, a research programme was carried out. It was a partenarial and partipatory research about maritime heritage in Marquesas (PALIMMA). The objectives were to identify knowledge in the bibliography and to built data with the population (what heritage, what threats and what managerial solutions). Beyond knowledge production, this research programme, with marquisian local community, showed how important it is in ordrer to reach a balanced territorial development, to foster the empowerment of local population and to build relationships between individuals and institutions. A research program like PALIMMA can help to aim those objectives.</dc:description>

14. dc:relation
----------------------------

For OpenEdition Journals, and according to `OpenAIRE 3.0 guidelines (Publication Reference) <https://guidelines.openaire.eu/en/latest/literature/field_publicationreference.html>`_, ``dc.relation`` element with a prefix ``info:eu-repo/semantics/reference/issn/`` will provide ISSNs of the online journal and of the print version (if available).

**Example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:geocarrefour/10121&metadataPrefix=oai_dc

.. code-block:: xml
    :linenos:

    <dc:relation>info:eu-repo/semantics/reference/issn/1627-4873</dc:relation>
    <dc:relation>info:eu-repo/semantics/reference/issn/1960-601X</dc:relation>

 
