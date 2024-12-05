.. _qdc:

QDC format
===================


.. warning::

   Version 1 of the OAI-PMH repository is DEPRECIATED. Please refer to the warning on the :ref:`home page <home>`.


.. contents:: Table of Contents
   :depth: 2

The ``qdc`` format provides the following elements:

1. dcterms:title
-----------------

Title of the document. Non-repeatable.

2. dcterms:alternative
------------------------------------
Alternative title (translated title). Repeatable. An ``xml:lang`` attribute specifies the language of the alternative title.

Available for OpenEdition Journals and OpenEdition Books.

**Example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:histoire-education/2589&metadataPrefix=qdc

.. code-block:: xml
    :linenos:

    <dcterms:alternative xml:lang="en">The Society for Promoting the Employment of Women in London (1859-late XIXth century): vocational and commercial training for “the surplus woman”</dcterms:alternative>
    <dcterms:alternative xml:lang="de">Der „Verein für Frauenerwerb“ in London (1859 bis Ende des 19. Jahrhunderts) : die kaufmännische Berufsausbildung als Hilfe für „überschüssige Frauen“</dcterms:alternative>

3. dcterms:creator
--------------------------
Author(s) of the document. Repeatable.

Unavailable for Calenda.

.. note :: For Journal Issues and Books, ``dcterms.creator`` provides authors of the issue or the book AND authors of the child articles or chapters.

**Example of a book with multiple authors at chapter level:** 
https://oai.openedition.org/?verb=GetRecord&identifier=oai:books.openedition.org:gup/348&metadataPrefix=qdc

For archeological note, ``dcterms:creator`` may also contain archaeological project directors.

**Example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:archeomed/7020&metadataPrefix=qdc

.. code-block:: xml
    :linenos:

    <dcterms:type>archaeological note</dcterms:type>
    <dcterms:creator>Racinet, Philippe</dcterms:creator>
    <dcterms:creator>Jonvel, Richard</dcterms:creator>

See https://journals.openedition.org/archeomed/7020?lang=en for roles of each ``dcterms:creator``.

4. dcterms:contibutor
---------------------------

Scientific and academic editor of the document. Available for OpenEdition Journals and OpenEdition Books. 

**Example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:books.openedition.org:cvz/3321&metadataPrefix=qdc

.. code-block:: xml
    :linenos:

    <dcterms:contributor>Alvarez Roblin, David</dcterms:contributor>
    <dcterms:contributor>Biaggini, Olivier</dcterms:contributor>

For archeological note and article, ``dcterms:contributor`` may also contain collaborators.

**Example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:archeomed/11348&metadataPrefix=qdc

.. code-block:: xml
    :linenos:

    <dcterms:contributor>Perrault, Christophe</dcterms:contributor>
    <dcterms:contributor>Prat, Béatrice</dcterms:contributor>
    <dcterms:contributor>Rué, Mathieu</dcterms:contributor>
    <dcterms:contributor>Caillat, Pierre</dcterms:contributor>

See https://journals.openedition.org/archeomed/11348?lang=en for roles of each ``dcterms:contributor``.



5. dcterms:issued
------------------------
Publication date of the document on OpenEdition platform. 

If an article was previously published in another format (for instance a print version), the ``dcterms:issued`` element won't provide the date of the previous publishing but only the publishing date of the document on OpenEdition.

**Example:** 
https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:remi/8732&metadataPrefix=qdc

.. code-block:: xml
    :linenos:
    
    <dcterms:issued xsi:type="dcterms:W3CDTF">2017-09-01</dcterms:issued>


.. _dctermscreated:

6. dcterms:created
------------------------
First publication date.

The ``dcterms:created`` element provides the first publication date (year only) of the document, regardless of the format (prior digital publication, prior print publication, 1st publication on OpenEdition, etc.)

**Example:** 
https://oai.openedition.org/?verb=GetRecord&identifier=oai:books.openedition.org:gup/348&metadataPrefix=qdc

.. code-block:: xml
    :linenos:

    <dcterms:created xsi:type="dcterms:W3CDTF">2013</dcterms:created>


.. _dctermsaccessrights:


7. dcterms:accessRights
---------------------------------

Available for the 4 OpenEdition platforms: OpenEdition Books, OpenEdition Journals, Hypothèses et Calenda.

The ``dcterms:accessRights`` element can match the following values :

* ``info:eu-repo/semantics/embargoedAccess`` : articles and journal issues under embargo
* ``info:eu-repo/semantics/openAccess`` : open access document (article, journal issue, book, book section, blog post, event...). At least the html format is freely accessible. The other formats (pdf, epub) may be.
* ``info:eu-repo/semantics/restrictedAccess`` : book and book section in restricted acces.

**Example:** 
https://oai.openedition.org/?verb=GetRecord&identifier=oai:books.openedition.org:ariadnaediciones/158&metadataPrefix=qdc

.. code-block:: xml
    :linenos:
    
    <dcterms:accessRights>info:eu-repo/semantics/openAccess</dcterms:accessRights>


8. dcterms:available
-------------------------

Applicable for OpenEdition Jounals. If ``dcterms:accessRights = "info:eurepo/semantics/embargoedAccess"``, then the ``dcterms:available`` element will provide the end date of embargo (availability date of the document in open access):

**Example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:rfp/5246&metadataPrefix=qdc

.. code-block:: xml
    :linenos:
    
    <dcterms:accessRights>info:eu-repo/semantics/embargoedAccess</dcterms:accessRights>
    <dcterms:available xsi:type="dcterms:W3CDTF">2022-01-01</dcterms:available>


9. dcterms:publisher
-----------------------------

``dcterms:publisher`` provides the publisher name.

For OpenEdition Journals and Hypotheses documents ``dcterms:publisher`` provides also the journal or blog title

**Example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:studifrancesi/2636&metadataPrefix=qdc

.. code-block:: xml
    :linenos:
    
    <dcterms:publisher>Rosenberg &amp; Sellier</dcterms:publisher>
    <dcterms:publisher>Studi Francesi</dcterms:publisher>


10. dcterms:identifier
--------------------------------
Identifier of the document. Repeatable.

10.1. URI
^^^^^^^^^
``dcterms:identifier`` with an attribute ``scheme="URI"`` provides the URI of the document.

**Example:** 
https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:remi/5530&metadataPrefix=qdc

.. code-block:: xml
    :linenos:

    <dcterms:identifier scheme="URI">http://journals.openedition.org/remi/5530</dcterms:identifier>

10.2. DOI
^^^^^^^^^^
Available for OpenEdition Journals and OpenEdition Books.

``dcterms:identifier`` with an attribute ``scheme="URN"`` and a ``urn:doi`` prefix provides the DOI of the document.

**Example:** 
https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:remi/5530&metadataPrefix=qdc

.. code-block:: xml
    :linenos:

    <dcterms:identifier scheme="URN">urn:doi:10.4000/remi.5530</dcterms:identifier>

10.3. ISBN
^^^^^^^^^^
Available for OpenEdition Books.

``dcterms:identifier`` with an attribute ``scheme="URN"`` and a ``urn:isbn`` or ``urn:eisbn`` prefix provides respectively ISBN of the print and electronic version of the book.

**Example:** 
https://oai.openedition.org/?verb=GetRecord&identifier=oai:books.openedition.org:gup/348&metadataPrefix=qdc

.. code-block:: xml
    :linenos:
    
    <dcterms:identifier scheme="URN">urn:eisbn:9782821875470</dcterms:identifier>
    <dcterms:identifier scheme="URN">urn:isbn:9783863951221</dcterms:identifier> 

For OAI records of a book chapter, the ISBN and eISBN provided refer to the parent book of that chapter.

**Example:** 
https://oai.openedition.org/?verb=GetRecord&identifier=oai:books.openedition.org:gup/367&metadataPrefix=qdc

.. code-block:: xml
    :linenos:
    
    <dcterms:identifier scheme="URN">urn:eisbn:9782821875470</dcterms:identifier>
    <dcterms:identifier scheme="URN">urn:isbn:9783863951221</dcterms:identifier>

11. dcterms:isPartOf
----------------------------

Available for OpenEdition Journals.

``dcterms:isPartOf`` with an attribute ``scheme="URN"`` and a ``urn:issn`` or ``urn:eissn`` prefix provides respectively ISSN of the print and electronic version of the journal in which the document was published.

**Example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:geocarrefour/10121&metadataPrefix=qdc

.. code-block:: xml
    :linenos:

    <dcterms:isPartOf scheme="URN">urn:issn:1627-4873</dcterms:isPartOf>
    <dcterms:isPartOf scheme="URN">urn:eissn:1960-601X</dcterms:isPartOf>

12. dcterms:hasFormat
----------------------------

Available for OpenEdition Journals and OpenEdition Books.

OpenEdition provide partners an access to full text in TEI (`Text Encoding Initiative <http://www.tei-c.org/>`_) format and Raw text format for documents published on OpenEdition Journals and OpenEdition Books. 

Link to TEI structured full text and to Raw text is retrivable in ``dcterms:hasFormat``.

* ``<dcterms:hasFormat scheme="TEI">``: link to structured  XML-TEI Full text (suitable for republication and text and dat mining)
* ``<dcterms:hasFormat scheme="BASICTEI">``: link to full text in the "basicTEI" format witch provide metadata of the document in TeiHeader and raw text in the body section (suitable for text indexing). 

.. note :: Access to Full text in TEI and Raw text format is only available for authorized IP address (OpenEdition partners). More infos :ref:`tei_v1`  

**Example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:geocarrefour/10121&metadataPrefix=qdc

.. code-block:: xml
    :linenos:

    <dcterms:hasFormat scheme="TEI">http://journals.openedition.org/geocarrefour/tei/10121</dcterms:hasFormat>
    <dcterms:hasFormat scheme="BASICTEI">http://journals.openedition.org/geocarrefour/basictei/10121</dcterms:hasFormat>


13. dcterms:language
----------------------------------
Document language. RFC1766 format. 

**Example:** 
https://oai.openedition.org/?verb=GetRecord&identifier=oai:books.openedition.org:cfee/1081&metadataPrefix=qdc

.. code-block:: xml
    :linenos:
    
    <dcterms:language xsi:type="dcterms:RFC1766">en</dcterms:language>

.. _dctermstype:

14. dcterms:type
-------------------------

Available for all platforms. 

``dcterms:type`` provides the document type according to the list of types available in this section: :ref:`types_v1`. 


**Example:** 
https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:lectures/27329&metadataPrefix=qdc

.. code-block:: xml
    :linenos:
    
    <dcterms:type>review</dcterms:type>


15. dcterms:rights
---------------------------

Available for OpenEdition Journals and OpenEdition Books. ``dcterms:rights`` may contain license information if provided by the publisher.

**Example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:books.openedition.org:ariadnaediciones/158&metadataPrefix=qdc

.. code-block:: xml
    :linenos:
    
    <dcterms:rights>CC BY-SA 3.0</dcterms:rights>


16. dcterms:extent
-------------------------
Available for OpenEdition Journals and OpenEdition Books.

``dcterms:extent`` may provide the number of pages or the pages range in print edition of the document.

**Page range example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:ethnomusicologie/1513&metadataPrefix=qdc

.. code-block:: xml
    :linenos:
    
    <dcterms:extent>240-241</dcterms:extent>

**Number of pages example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:books.openedition.org:purh/7891&metadataPrefix=qdc

.. code-block:: xml
    :linenos:
    
    <dcterms:extent>132</dcterms:extent>


17. dcterms:spatial
---------------------------
Available for OpenEdition Journals and OpenEdition Books.

``dcterms:spatial`` may contain spatial topics of the document.

**Example:** 
https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:balkanologie/717&metadataPrefix=qdc

.. code-block:: xml
    :linenos:
    
    <dcterms:spatial>Bulgarie</dcterms:spatial>
    <dcterms:spatial>Turquie</dcterms:spatial>


18. dcterms:temporal
-------------------------
Available for OpenEdition Journals and OpenEdition Books.

``dcterms:temporal`` may contain temporal characteristics of the document.

**Example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:dam/460&metadataPrefix=qdc

.. code-block:: xml
    :linenos:
    
    <dcterms:temporal>âge du Bronze</dcterms:temporal>
    <dcterms:temporal>Néolithique</dcterms:temporal>

19. dcterms:subject
---------------------------

19.1 Keywords
^^^^^^^^^^^^^^^^^^

Available for OpenEdition Journals and OpenEdition Books. 
``dcterms:subject`` with a attribute ``scheme="keywords"`` may contains keywords. An ``xml:lang`` attribute specifies the language of the keyword.

**Example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:belgeo/20507&metadataPrefix=qdc

.. code-block:: xml
    :linenos:
    
    <dcterms:subject xml:lang="fr" scheme="keywords">détection de communautés</dcterms:subject>
    <dcterms:subject xml:lang="fr" scheme="keywords">champs d’interactions</dcterms:subject>
    <dcterms:subject xml:lang="fr" scheme="keywords">migration</dcterms:subject>
    <dcterms:subject xml:lang="fr" scheme="keywords">navettes</dcterms:subject>
    <dcterms:subject xml:lang="fr" scheme="keywords">provinces</dcterms:subject>
    <dcterms:subject xml:lang="fr" scheme="keywords">Belgique</dcterms:subject>
    <dcterms:subject xml:lang="fr" scheme="keywords">Census11</dcterms:subject>
    <dcterms:subject xml:lang="en" scheme="keywords">community detection</dcterms:subject>
    <dcterms:subject xml:lang="en" scheme="keywords">interaction fields</dcterms:subject>
    <dcterms:subject xml:lang="en" scheme="keywords">migration</dcterms:subject>
    <dcterms:subject xml:lang="en" scheme="keywords">commuting</dcterms:subject>
    <dcterms:subject xml:lang="en" scheme="keywords">provinces</dcterms:subject>
    <dcterms:subject xml:lang="en" scheme="keywords">Belgium</dcterms:subject>
    <dcterms:subject xml:lang="en" scheme="keywords">Census11</dcterms:subject>

19.2 Other Subjects
^^^^^^^^^^^^^^^^^^^^^^
For OpenEdition Books only, ``dcterms:subject`` may also contains terms from `BISAC <https://bisg.org/page/BISACSubjectCodes>`_, `BIC <https://ns.editeur.org/bic_categories>`_, `ISI <https://en.wikipedia.org/wiki/Institute_for_Scientific_Information>`_ classification. The ``scheme`` attribute specifies the classification.

**Example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:books.openedition.org:pum/21469&metadataPrefix=qdc

.. code-block:: xml
    :linenos:
    
    <dcterms:subject xml:lang="fr" scheme="keywords">environnement</dcterms:subject>
    <dcterms:subject xml:lang="fr" scheme="keywords">protection</dcterms:subject>
    <dcterms:subject xml:lang="fr" scheme="keywords">gestion</dcterms:subject>
    <dcterms:subject xml:lang="fr" scheme="keywords">politique gouvernementale</dcterms:subject>
    <dcterms:subject scheme="ISI">Environmental Studies</dcterms:subject>
    <dcterms:subject scheme="ISI">Political Science</dcterms:subject>
    <dcterms:subject scheme="BISAC">POL044000</dcterms:subject>
    <dcterms:subject scheme="BIC">RND</dcterms:subject>

 
20. dctems:abstract
--------------------------------

``dcterms:abstract`` provides abstracts of the document. Abstacts may be available in several languages specified by the ``xml:lang`` attribute.

**Example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:cipango/1688&metadataPrefix=qdc

.. code-block:: xml
    :linenos:

    <dcterms:abstract xml:lang="fr">Cet article se penche sur la crise de 2001 au sujet des manuels d’histoire suite à l’homologation du manuel révisionniste de la Société pour la rédaction de nouveaux manuels d’histoire (« Tsukuru-kai »). Notre propos n’est pas de revenir sur le contenu de ce manuel, mais d’examiner les réactions qu’il suscita en Corée du Sud, où il était considéré comme la pointe de l’iceberg d’un problème touchant tous les manuels d’histoire japonais, ainsi que la riposte que ces critiques coréennes provoquèrent dans les milieux proches du manuel révisionniste. Au-delà des accusations réciproques de « déformer » l’histoire, l’analyse comparative des sujets de controverse dans les principaux manuels des deux pays révèle que les divergences sont bien moindres que les frictions diplomatiques engendrées par cette crise ne le suggéraient. La comparaison avec les éditions suivantes des manuels montre en outre que de part et d’autre, certaines leçons ont été tirées afin d’éviter qu’une crise de l’ampleur de 2001 ne se reproduise.</dcterms:abstract>
    <dcterms:abstract xml:lang="en">This paper deals with the history textbook crisis of 2001 following the authorization of the revisionist textbook from the Society for History Textbook Reform. Our purpose is not to delve into that textbook but to examine both the reactions it sparked in South Korea, where it was deemed to be the tip of the iceberg of a wider problem affecting all Japanese history textbooks, and the response that supporters of the revisionist textbook gave to South Korean criticisms. Beyond the mutual charges of “distorting” history, the comparative analysis of the controversial issues reveals far less discrepancies than the diplomatic row triggered by that crisis may have suggested. Comparison with succeeding editions of the textbooks indicates that both sides have drawn the conclusions to avoid a similar crisis.</dcterms:abstract>

21. dctems:description
--------------------------------

``dcterms:descripton`` provides an excerpt of the document, usualy the first lines. ``dcterms:descripton`` is used only in the lack of ``dcterms:abstract``.

**Example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:appareil/1493&metadataPrefix=qdc

.. code-block:: xml
    :linenos:

    <dcterms:description>Le livre de Michel Serres présente plusieurs difficultés de lecture : le désordre semble régner, des interruptions succèdent à d’autres interruptions. Les textes littéraires, scientifiques et philosophiques qui servent de base aux analyses sont cachés par des couches de plus en plus complexes : des greffes d’autres textes, des images, des métaphores, etc. Peut-être peut-on trouver une raison à ceci dans le fait que Serres ne se borne pas à faire une théorie du parasite. Il cherche plutôt à mo...</dcterms:description>



22. dcterms:bibliographicalCitation
---------------------------------------------

Available for OpenEdition Journals, for ``issue`` documents only (see :ref:`types_v1`). 

.. note :: Only covers a small part of journal issues.

Elements ``dcterms:bibliographicalCitation.issue`` and ``dcterms:bibliographicalCitation.volume`` provides the issue number ans the volume number.

**Example with issue only:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:beo/787&metadataPrefix=qdc

.. code-block:: xml
    :linenos:
    
    <dcterms:bibliographicCitation.issue>61</dcterms:bibliographicCitation.issue>

 
**Example with issue and volume:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:ejas/7622&metadataPrefix=qdc

.. code-block:: xml
    :linenos:

    <dcterms:bibliographicCitation.volume>4</dcterms:bibliographicCitation.volume>
    <dcterms:bibliographicCitation.issue>2</dcterms:bibliographicCitation.issue>

