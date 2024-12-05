.. _oai_openaire_v2:

oai_openaire format
========================================

.. contents:: Table of Contents
   :depth: 2

The ``oai_openaire`` format provides the following elements, according to  `OpenAIRE Guidelines for Literature Repository Managers v4 <https://openaire-guidelines-for-literature-repository-managers.readthedocs.io/en/v4.0.0/>`_.

1. datacite:identifier
----------------------------

- ``datacite:identifier`` provides the Handle of the document
- Available for all records.
- The Handle identifier is also used as OAI-PMH identifier ``record/header/identifier``

**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/jsak&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <datacite:identifier identifierType="Handle">20.500.13089/jsak</datacite:identifier>


2. datacite:title
---------------------------

- ``datacite:title`` without attribute provides the main Title of the document.
- ``datacite:title`` with attribute ``titleType="Subtitle"`` provides the subtitle of the document.
- ``datacite:title`` with attribute ``titleType="TranslatedTitle"`` provides the translated titles of the document. 


**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/gd0i&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <datacite:titles>
      <datacite:title>Qu’est-ce que le travail quand on n’a pas d’emploi ?</datacite:title>
      <datacite:title titleType="Subtitle">Le travail non salarié à l’aune des projections d’avenir des chômeurs</datacite:title>
      <datacite:title titleType="TranslatedTitle" xml:lang="en">What’s work when you’re unemployed ? Non-wage work in the light of future projections for the unemployed</datacite:title>
      <datacite:title titleType="TranslatedTitle" xml:lang="de">Was ist Arbeit, wenn man keinen Arbeitsplatz hat ? Selbständige Arbeit, gemessen an den Zukunftsprojektionen von Arbeitssuchenden</datacite:title>
      <datacite:title titleType="TranslatedTitle" xml:lang="es">¿Qué es el trabajo cuando no se tiene empleo ? El trabajo no asalariado según las proyecciones de futuro de los desempleados</datacite:title>
    </datacite:titles>

3. datacite:creator
-------------------------
- Author(s), scientific and academic editor, archaeological project director. Repeatable.
- For OpenEdition Journals, OpenEdition Books and Calenda, ``givenName`` and ``familyName`` are distincts.
- For Hypotheses blog posts, there is no distinction.

**Example of a book:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/31o8&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <datacite:creators>
      <datacite:creator>
        <datacite:creatorName nameType="Personal">Groth, Stefan</datacite:creatorName>
        <datacite:givenName>Stefan</datacite:givenName>
        <datacite:familyName>Groth</datacite:familyName>
      </datacite:creator>
    </datacite:creators>

**Example of an archeological note:** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/9xim&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <datacite:creators>
        <datacite:creator>
          <datacite:creatorName nameType="Personal">Racinet, Philippe</datacite:creatorName>
          <datacite:givenName>Philippe</datacite:givenName>
          <datacite:familyName>Racinet</datacite:familyName>
        </datacite:creator>
        <datacite:creator>
          <datacite:creatorName nameType="Personal">Jonvel, Richard</datacite:creatorName>
          <datacite:givenName>Richard</datacite:givenName>
          <datacite:familyName>Jonvel</datacite:familyName>
        </datacite:creator>
    </datacite:creators>

**Example of a blog post:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/11r1e&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <datacite:creators>
      <datacite:creator>
        <datacite:creatorName>Olivier Jacquot</datacite:creatorName>
      </datacite:creator>
    </datacite:creators>


4. datacite:contributor
---------------------------------

- Other contributors: translators, collaborators (For archeological note and article). 

**Example (translator):** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/k5wx&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <datacite:contributors>
      <datacite:contributor contributorType="Other">
        <datacite:creatorName nameType="Personal">Mannoni, Olivier</datacite:creatorName>
        <datacite:givenName>Olivier</datacite:givenName>
        <datacite:familyName>Mannoni</datacite:familyName>
      </datacite:contributor>
    </datacite:contributors>


**Example (collaborators):** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/9wrn&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <datacite:contributors>
      <datacite:contributor contributorType="Other">
        <datacite:creatorName nameType="Personal">Perrault, Christophe</datacite:creatorName>
        <datacite:givenName>Christophe</datacite:givenName>
        <datacite:familyName>Perrault</datacite:familyName>
      </datacite:contributor>
      <datacite:contributor contributorType="Other">
        <datacite:creatorName nameType="Personal">Prat, Béatrice</datacite:creatorName>
        <datacite:givenName>Béatrice</datacite:givenName>
        <datacite:familyName>Prat</datacite:familyName>
      </datacite:contributor>
      <datacite:contributor contributorType="Other">
        <datacite:creatorName nameType="Personal">Rué, Mathieu</datacite:creatorName>
        <datacite:givenName>Mathieu</datacite:givenName>
        <datacite:familyName>Rué</datacite:familyName>
      </datacite:contributor>
      <datacite:contributor contributorType="Other">
        <datacite:creatorName nameType="Personal">Caillat, Pierre</datacite:creatorName>
        <datacite:givenName>Pierre</datacite:givenName>
        <datacite:familyName>Caillat</datacite:familyName>
      </datacite:contributor>
    </datacite:contributors>



5. oaire:fundingReference
---------------------------------

- Information about financial support. Repeatable.
- Available on OpenEdition Books and OpenEdition Journals
- ``funderIdentifiertype`` is always ``"Crossref Funder"``
- ``awardNumber`` may be precised, if information is available

**Example :** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/fx&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <oaire:fundingReferences>
      <oaire:fundingReference>
        <oaire:funderName>Coordenação de Aperfeiçoamento de Pessoal de Nível Superior</oaire:funderName>
        <oaire:funderIdentifier funderIdentifierType="Crossref Funder ID">http://dx.doi.org/10.13039/501100002322</oaire:funderIdentifier>
        <oaire:awardTitle>Programme Saint Hilaire</oaire:awardTitle>
      </oaire:fundingReference>
      <oaire:fundingReference>
        <oaire:funderName>Ministère des Affaires Étrangères</oaire:funderName>
        <oaire:funderIdentifier funderIdentifierType="Crossref Funder ID">http://dx.doi.org/10.13039/501100003388</oaire:funderIdentifier>
        <oaire:awardTitle>Programme Saint Hilaire</oaire:awardTitle>
      </oaire:fundingReference>
    </oaire:fundingReferences>



6. datacite:alternateIdentifier
---------------------------------------

- Alternative identifier of the document. Repeatable.

6.1. DOI
^^^^^^^^^^

- ``datacite:alternateIdentifier`` with attribute ``alternateIdentifierType="DOI"`` provides the DOI of the document.
- Available for all platforms. 
- Some records from OpenEdition Books and OpenEdition Journals may have no DOI.


**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/jsak&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <datacite:alternateIdentifiers>
      <datacite:alternateIdentifier alternateIdentifierType="DOI">10.4000/remi.5530</datacite:alternateIdentifier>
      [...]
    </datacite:alternateIdentifiers>


6.2. URL
^^^^^^^^^
- ``datacite:alternateIdentifier`` with attribute ``alternateIdentifierType="URL"`` provides the URL of the document.
- Available for all records. 

**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/jsak&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <datacite:alternateIdentifiers>
      <datacite:alternateIdentifier alternateIdentifierType="URL">https://journals.openedition.org/remi/5530</datacite:alternateIdentifier>
      [...]
    </datacite:alternateIdentifiers>

6.3. ISBN
^^^^^^^^^^

- ``datacite:alternateIdentifier`` with attribute ``alternateIdentifierType="ISBN"`` or  ``alternateIdentifierType="PISBN"`` provides respectively the digital ISBN and print ISBN of the document.
- Available for books (OpenEdition Books) and journals issues (OpenEdition Journals).

**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/31o4&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <datacite:alternateIdentifiers>
      [...]
      <datacite:alternateIdentifier alternateIdentifierType="ISBN">978-2-8218-7547-0</datacite:alternateIdentifier>
      <datacite:alternateIdentifier alternateIdentifierType="PISBN">978-3-86395-122-1</datacite:alternateIdentifier>
    </datacite:alternateIdentifiers>

7. datacite:relatedIdentifier
---------------------------------------

- ``datacite:relatedIdentifier`` provides identifiers of "parent" of the resource (Journal and Journal Issue for resource of OpenEdition Journals), (Book for Chapters of OpenEdition Books)


- ``datacite:relatedIdentifier`` element with attribute ``relatedIdentifierType="EISSN"`` and ``relatedIdentifierType="PISSN"`` provides respectively e-ISSN and Print ISSN of the journal.

For chapters published in a book and articles published in a journal issue :

- ``datacite:relatedIdentifier`` element with attribute ``relatedIdentifierType="Handle"`` provides the Handle of the parent book or journal issue.
- ``datacite:relatedIdentifier`` element with attribute ``relatedIdentifierType="DOI"`` provides the DOI of the parent book or journal issue.
- ``datacite:relatedIdentifier`` element with attribute ``relatedIdentifierType="ISBN"`` and ``relatedIdentifierType="PISBN"`` provides respectively the digital ISBN and Print ISBN of the parent book or journal issue.


**Example (journal article):** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/gh7p&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <datacite:relatedIdentifiers>
      <datacite:relatedIdentifier relatedIdentifierType="EISSN" relationType="IsPartOf">1960-601X</datacite:relatedIdentifier>
      <datacite:relatedIdentifier relatedIdentifierType="PISSN" relationType="IsPartOf">1627-4873</datacite:relatedIdentifier>
      <datacite:relatedIdentifier relatedIdentifierType="Handle" relationType="IsPartOf">20.500.13089/gh7p</datacite:relatedIdentifier>
      <datacite:relatedIdentifier relatedIdentifierType="DOI" relationType="IsPartOf">10.4000/geocarrefour.10012</datacite:relatedIdentifier>
    </datacite:relatedIdentifiers>


**Example (book chapter):** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/7kfl&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <datacite:relatedIdentifiers>
      <datacite:relatedIdentifier relatedIdentifierType="Handle" relationType="IsPartOf">20.500.13089/81qu</datacite:relatedIdentifier>
      <datacite:relatedIdentifier relatedIdentifierType="DOI" relationType="IsPartOf">10.4000/books.pur.29424</datacite:relatedIdentifier>
      <datacite:relatedIdentifier relatedIdentifierType="ISBN" relationType="IsPartOf">978-2-7535-4677-6</datacite:relatedIdentifier>
      <datacite:relatedIdentifier relatedIdentifierType="PISBN" relationType="IsPartOf">978-2-7535-0687-9</datacite:relatedIdentifier>
    </datacite:relatedIdentifiers>

.. note::

    For a document of type ‘chapter’, the Handle relatedIdentifier can be used with a GetRecord request to obtain detailed information about the book in which the chapter is published.


8. dc:language
-----------------
- Document language. RFC1766 format. 

**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/1x9t&metadataPrefix=oai_openaire


.. code-block:: xml
    :linenos:
    
    <dc:language>fr</dc:language>


9. dc:publisher
-----------------

- ``dc:publisher`` provides the publisher name. Repeatable.

**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/1x9t&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:
    
    <dc:publisher>Casa de Velázquez</dc:publisher>
    <dc:publisher>Éditions Rue d’Ulm</dc:publisher>


10. datacite:date
-----------------

- ``datacite:date`` with attribute ``dateType="Issued"`` provides the year of publication of the document.
- ``datacite:date`` with attribute ``dateType="Updated"`` provides the last update of the document.
- For OpenEdition Journals, if ``datacite:rights = embargoed access``, an extra ``dc.date`` element with attribute ``dateType="Available"`` provides the end date of embargo (availability date of the document in open access):

**Example (book published in 1990, published on OpenEditon Books on 28/08/2022):** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/5div&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <datacite:dates>
      <datacite:date dateType="Issued">1990</datacite:date>
      <datacite:date dateType="Updated">2024-05-23</datacite:date>
    </datacite:dates>

**Example (journal article with embargoed access):** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/k213&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <datacite:rights rightsURI="http://purl.org/coar/access_right/c_f1cf">embargoed access</datacite:rights>
    <datacite:dates>
      <datacite:date dateType="Available">2027-01-01</datacite:date>
      <datacite:date dateType="Issued">2023</datacite:date>
      <datacite:date dateType="Updated">2023-11-28</datacite:date>
    </datacite:dates>

.. _resourceType_v2:

11. oaire:resourceType
-------------------------------

- Type of resource in the `COAR Resource Type Vocabulary <https://vocabularies.coar-repositories.org/documentation/resource_types/>`_
- Available for all records. 

**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/hpx1&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <oaire:resourceType resourceTypeGeneral="literature" uri="http://purl.org/coar/resource_type/c_efa0">review</oaire:resourceType>

12. dc:description
--------------------------------

``dc:description`` contains abstracts of the document if available, an excerpt (usualy the first lines) otherwise. Abstacts may be available in several languages. In this case, and ``xml:lang`` attribute specifies the language of the description.

**Example:** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/l8zw&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <dc:description xml:lang="fr">L’archipel des Marquises (Polynésie française) construit son projet de développement territorial, y figurent deux projets d’excellence : l’inscription de l’archipel sur la liste du patrimoine mondial de l’UNESCO et la création d’une aire marine protégée. Dans ce contexte, un programme de recherche partenarial et participatif portant sur le patrimoine lié à la mer aux Marquises (PALIMMA) a contribué à identifier les connaissances présentes dans la bibliographie et à construire des données avec la population. Il s’agissait de déterminer quels étaient les patrimoines liés à la mer pour les Marquisiens, les éventuelles menaces afférentes et les pistes de gestion. Au-delà de la production de connaissance, ce programme, porté par la société marquisienne, a participé à la construction des territoires, à renforcer la capacité des populations à intervenir dans les débats et à la construction de liens entre individus et institutions.</dc:description>
    <dc:description xml:lang="en">Marquesas islands archipelago aimes to built its territorial development project in particular thanks to become listed as a world heritage site by UNESCO and the establishment of a marine protected area. In this context, a research programme was carried out. It was a partenarial and partipatory research about maritime heritage in Marquesas (PALIMMA). The objectives were to identify knowledge in the bibliography and to built data with the population (what heritage, what threats and what managerial solutions). Beyond knowledge production, this research programme, with marquisian local community, showed how important it is in ordrer to reach a balanced territorial development, to foster the empowerment of local population and to build relationships between individuals and institutions. A research program like PALIMMA can help to aim those objectives.</dc:description>


13. dc:format
-----------------

- mime type of all records is ``text/html``

**Example:** https://metadata.openedition.org/oai?verb=GetRecord&identifier=oai:revues.org:geocarrefour/10121&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <dc:format>text/html</dc:format>


.. _dataciterights:

14. datacite:subject
---------------------------

- ``dc:subject`` contains keywords. An ``xml:lang`` attribute specifies the language of the keyword.
- Available for OpenEdition Journals and OpenEdition Books and Calenda. 

**Example:** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/d85h&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <datacite:subjects>
      <datacite:subject xml:lang="en">Belgium</datacite:subject>
      <datacite:subject xml:lang="en">migration</datacite:subject>
      <datacite:subject xml:lang="en">commuting</datacite:subject>
      <datacite:subject xml:lang="en">community detection</datacite:subject>
      <datacite:subject xml:lang="en">interaction fields</datacite:subject>
      <datacite:subject xml:lang="en">provinces</datacite:subject>
      <datacite:subject xml:lang="en">Census11</datacite:subject>
      <datacite:subject xml:lang="fr">Belgique</datacite:subject>
      <datacite:subject xml:lang="fr">migration</datacite:subject>
      <datacite:subject xml:lang="fr">détection de communautés</datacite:subject>
      <datacite:subject xml:lang="fr">champs d’interactions</datacite:subject>
      <datacite:subject xml:lang="fr">navettes</datacite:subject>
      <datacite:subject xml:lang="fr">provinces</datacite:subject>
      <datacite:subject xml:lang="fr">Census11</datacite:subject>
    </datacite:subjects>


15. datacite:rights
--------------------------

- Access right of the resource.
- Available for all records. 

**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/1i54&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <datacite:rights rightsURI="http://purl.org/coar/access_right/c_abf2">open access</datacite:rights>

16. oaire:licenseCondition
------------------------------

- ``oaire:licenseCondition`` contains license information.
- Available for all records.

**Example:** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/d85h&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <oaire:licenseCondition uri="https://creativecommons.org/licenses/by/4.0/">CC-BY-4.0</oaire:licenseCondition>

.. _oairefile:


17. oaire:file
---------------------------

- ``oaire:file`` provides the URL of the HTML of the resource.
- For OpenEdition Journals and OpenEdition Books ``oaire:file`` provides also, the URL of the PDF, ePub, TEI and "Basic TEI" version of the resource.
- ``mimeType`` attribute precises the format and ``accessRightsURI`` the access right type (using the http://purl.org/coar/access_right references).

**Example (book):** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/1i54&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <oaire:file accessRightsURI="http://purl.org/coar/access_right/c_abf2" mimeType="text/html" objectType="fulltext">https://books.openedition.org/ariadnaediciones/158</oaire:file>
    <oaire:file accessRightsURI="http://purl.org/coar/access_right/c_16ec" mimeType="application/pdf" objectType="fulltext">https://books.openedition.org/ariadnaediciones/pdf/158</oaire:file>
    <oaire:file accessRightsURI="http://purl.org/coar/access_right/c_16ec" mimeType="application/epub+zip" objectType="fulltext">https://books.openedition.org/ariadnaediciones/epub/158</oaire:file>

**Example (journal article):** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/d8ae&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <oaire:file accessRightsURI="http://purl.org/coar/access_right/c_abf2" mimeType="text/html" objectType="fulltext">https://journals.openedition.org/belgeo/57360</oaire:file>
    <oaire:file accessRightsURI="http://purl.org/coar/access_right/c_16ec" mimeType="application/tei+xml" objectType="fulltext">https://journals.openedition.org/belgeo/tei/57360</oaire:file>
    <oaire:file accessRightsURI="http://purl.org/coar/access_right/c_16ec" mimeType="application/tei+xml" objectType="fulltext">https://journals.openedition.org/belgeo/basictei/57360</oaire:file>
    <oaire:file accessRightsURI="http://purl.org/coar/access_right/c_abf2" mimeType="application/pdf" objectType="fulltext">https://journals.openedition.org/belgeo/pdf/57360</oaire:file>


**Example (blog post):** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/11sem&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <oaire:file accessRightsURI="http://purl.org/coar/access_right/c_abf2" mimeType="text/html" objectType="fulltext">https://sms.hypotheses.org/43068</oaire:file>



18. oaire:citationTitle
--------------------------

- For OpenEdition Journals, Hypotheses, Calenda ``oaire:citationTitle`` contains the Title of the journal, blog, site.
- For OpenEdition Books (for chapters) ``oaire:citationTitle`` contains the Title of the book.

**Example (journal article):** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/d8ae&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <oaire:citationTitle>Belgeo</oaire:citationTitle>

**Example (book chapter):** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/11qip&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <oaire:citationTitle>Between Lines and Notarial Marks</oaire:citationTitle>

19. oaire:citationVolume
--------------------------

- For OpenEdition Journals ``oaire:citationVolume`` contains the volume of the issue.

**Example (journal article):** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/1i54&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <oaire:citationVolume>4</oaire:citationVolume>


20. oaire:citationIssue
--------------------------

- For OpenEdition Journals ``oaire:citationIssue`` contains the issue of the issue.

**Example (journal article):** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/jry1&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <oaire:citationVolume>34</oaire:citationVolume>
    <oaire:citationIssue>4</oaire:citationIssue>



21. oaire:citationStartPage / oaire:citationEndPage
--------------------------------------------------------

- For OpenEdition Journals and OpenEdition Books; ``oaire:citationStartPage`` and ``oaire:citationEndPage`` contains the pagination.

**Example (journal article):** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/jry1&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <oaire:citationStartPage>223</oaire:citationStartPage>
    <oaire:citationEndPage>230</oaire:citationEndPage>

22. datacite:geoLocation
--------------------------------------------------------

- Geolocalisation for Calenda events

**Example (Calenda event):** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/11pm5&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <datacite:geoLocations>
      <datacite:geoLocation>
        <datacite:geoLocationPlace>Aix-en-Provence</datacite:geoLocationPlace>
      </datacite:geoLocation>
    </datacite:geoLocations>

23. oaire:citationConferencePlace
--------------------------------------------------------

- Calenda events : Conference place

**Example (Calenda event):** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/11pm5&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <oaire:citationConferencePlace>Aix-en-Provence</oaire:citationConferencePlace>

24. oaire:citationConferenceDate
--------------------------------------------------------

- Calenda events : Conference date

**Example (Calenda event):** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/11pm5&metadataPrefix=oai_openaire

.. code-block:: xml
    :linenos:

    <oaire:citationConferenceDate>2024-06-04</oaire:citationConferenceDate>


