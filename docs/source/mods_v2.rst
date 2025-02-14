.. _mods_v2:

mods format
========================================


.. contents:: Table of Contents
   :depth: 2

The ``mods`` format provides the following elements, according to  `Metadata Object Description Schema (MODS) 3.8 <https://www.loc.gov/standards/mods/>`_.

1. mods:identifier
----------------------------
- Identifier of the document. Repeatable with distinct types.

1.1. Handle
^^^^^^^^^^^^^^^

- ``mods:identifier`` with attribute ``type="hdl"`` provides the Handle of the document.
- Available for all records. 


**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/jsak&metadataPrefix=mods

.. code-block:: xml
    :linenos:

    <mods:identifier type="hdl">20.500.13089/jsak</mods:identifier>


1.2. DOI
^^^^^^^^^^^^^^^

- ``mods:identifier`` with attribute ``type="doi"`` provides the DOI of the document.
- Available for all platforms. 
- Some records from OpenEdition Books and OpenEdition Journals may have no DOI.


**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/jsak&metadataPrefix=mods

.. code-block:: xml
    :linenos:

    <mods:identifier type="doi">10.4000/remi.5530</mods:identifier>

1.3. ISBN
^^^^^^^^^^

- ``mods:identifier`` with attribute ``type="eisbn"`` or ``type="pisbn"`` provides respectively the dig    ital ISBN and print ISBN of the document.
- Available for books (OpenEdition Books) and journals issues (OpenEdition Journals).

**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/31o4&metadataPrefix=mods

.. code-block:: xml
    :linenos:

    <mods:identifier type="eisbn" typeURI="http://id.loc.gov/vocabulary/identifiers/isbn">978-2-8218-7547-0</mods:identifier>
    <mods:identifier type="pisbn" typeURI="http://id.loc.gov/vocabulary/identifiers/isbn">978-3-86395-122-1</mods:identifier>


2. mods:location
--------------------------------

- ``mods:location/mods:url`` provides the URL of the document.
- Available for all records. 

**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/jsak&metadataPrefix=mods

.. code-block:: xml
    :linenos:

    <mods:location>
      <mods:url>https://journals.openedition.org/remi/5530</mods:url>
    </mods:location>


3. mods:title
---------------------------

- ``mods:title`` without attribute provides the main Title of the document.
- ``mods:subTitle`` without attribute provides the subtitle of the document.
- ``mods:titleInfo[@type="translated"]/mods:title`` provides the translated titles of the document. The ``xml:lang`` attribute precise the language. 


**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/gd0i&metadataPrefix=mods

.. code-block:: xml
    :linenos:

    <mods:titleInfo>
      <mods:title>Qu’est-ce que le travail quand on n’a pas d’emploi ?</mods:title>
      <mods:subTitle>Le travail non salarié à l’aune des projections d’avenir des chômeurs</mods:subTitle>
    </mods:titleInfo>
    <mods:titleInfo type="translated">
      <mods:title xml:lang="en">What’s work when you’re unemployed ? Non-wage work in the light of future projections for the unemployed</mods:title>
      <mods:title xml:lang="de">Was ist Arbeit, wenn man keinen Arbeitsplatz hat ? Selbständige Arbeit, gemessen an den Zukunftsprojektionen von Arbeitssuchenden</mods:title>
      <mods:title xml:lang="es">¿Qué es el trabajo cuando no se tiene empleo ? El trabajo no asalariado según las proyecciones de futuro de los desempleados</mods:title>
    </mods:titleInfo>


4. mods:name
-------------------------
- Author, scientific and academic editor, archaeological project director, translator or other type of contributor. Repeatable.
- Roles are defined using marcrelator reference: https://www.loc.gov/marc/relators/relaterm.html. Used terms are :

  - ``aut``: Author
  - ``pbd``: Publishing director
  - ``edt``: Editor
  - ``trl``: Translator
  - ``ctb``: Contributor
  - ``orm``: Organizer

- For OpenEdition Journals, OpenEdition Books and Calenda, given name (``mods:namePart[@type="given"]``) and family name (``mods:namePart[@type="family"]``) are distincts.
- For Hypotheses blog posts, there is no distinction.

**Example of a book:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/31o8&metadataPrefix=mods

.. code-block:: xml
    :linenos:

    <mods:name type="personal">
      <mods:role>
        <mods:roleTerm authority="marcrelator">aut</mods:roleTerm>
      </mods:role>
      <mods:namePart type="given">Stefan</mods:namePart>
      <mods:namePart type="family">Groth</mods:namePart>
    </mods:name>


**Example of a blog post:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/11r1e&metadataPrefix=mods

.. code-block:: xml
    :linenos:

    <mods:name type="personal">
      <mods:role>
        <mods:roleTerm authority="marcrelator">aut</mods:roleTerm>
      </mods:role>
      <mods:namePart>Olivier Jacquot</mods:namePart>
    </mods:name>


.. _modstype_v2:

5. mods:typeOfResource
---------------------------------

- ``mods:typeOfResource`` with attribute ``authority="openedition"`` provides the document type according to the list of types available in this section: :ref:`types_v2`. 
- ``mods:typeOfResource`` with attribute ``authorityURI="http://purl.org/coar/resource_type/"`` provides the document type according to the list of types available at http://purl.org/coar/resource_type/. ``ValueURI`` attribute precise the term URI. 
- Available for all records. 


**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/11r0i&metadataPrefix=mods

.. code-block:: xml
    :linenos:

    <mods:typeOfResource authorityURI="http://purl.org/coar/resource_type/" valueURI="http://purl.org/coar/resource_type/c_18cf">text</mods:typeOfResource>
    <mods:typeOfResource authority="openedition">call for papers</mods:typeOfResource>

6. mods:language
-----------------
- Document language. Repeatable

**Example:** 
https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/11r0i&metadataPrefix=mods


.. code-block:: xml
    :linenos:

    <mods:language>
      <mods:languageTerm type="code" authority="iso639-1">fr</mods:languageTerm>
    </mods:language>
    <mods:language>
      <mods:languageTerm type="code" authority="iso639-1">en</mods:languageTerm>
    </mods:language>

7. mods:accessCondition (access rights)
---------------------------------------------------

- Access right of the resource.
- ``mods:accessCondition`` with attribute ``type="restriction on access"`` provides the access right of the document according to the list of types available at http://purl.org/coar/access_right/. ``ValueURI`` attribute precise the term URI. 
- Available for all records. 

**Example:** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/1i54&metadataPrefix=mods

.. code-block:: xml
    :linenos:

    <mods:accessCondition type="restriction on access" auhorityURI="http://purl.org/coar/access_right/" valueURI="http://purl.org/coar/access_right/c_abf2">open access</mods:accessCondition>

8. mods:accessCondition (license)
-------------------------------------------------

- ``mods:accessCondition`` with attribute ``type="license"`` provides the license of the document. When availabe (i.e. CC License), ``ValueURI`` attribute precise the license URI. 
- 
- Available for all records.

**Example:** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/1i54&metadataPrefix=mods

.. code-block:: xml
    :linenos:

    <mods:accessCondition type="license" valueURI="https://creativecommons.org/licenses/by-sa/4.0/">CC-BY-SA-4.0</mods:accessCondition>


9. mods:abstract
--------------------------------

``mods:abstract`` contains abstracts of the document if available (attribute ``type="summary"``), an excerpt (usualy the first lines) otherwise (attribute ``type="excerpt"``). Abstacts may be available in several languages. In this case, and ``xml:lang`` attribute specifies the language of the description.

**Example ("summary"):** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/l8zw&metadataPrefix=mods

.. code-block:: xml
    :linenos:

    <mods:abstract xml:lang="fr" type="summary">L’archipel des Marquises (Polynésie française) construit son projet de développement territorial, y figurent deux projets d’excellence : l’inscription de l’archipel sur la liste du patrimoine mondial de l’UNESCO et la création d’une aire marine protégée. Dans ce contexte, un programme de recherche partenarial et participatif portant sur le patrimoine lié à la mer aux Marquises (PALIMMA) a contribué à identifier les connaissances présentes dans la bibliographie et à construire des données avec la population. Il s’agissait de déterminer quels étaient les patrimoines liés à la mer pour les Marquisiens, les éventuelles menaces afférentes et les pistes de gestion. Au-delà de la production de connaissance, ce programme, porté par la société marquisienne, a participé à la construction des territoires, à renforcer la capacité des populations à intervenir dans les débats et à la construction de liens entre individus et institutions.</mods:abstract>
    <mods:abstract xml:lang="en" type="summary">Marquesas islands archipelago aimes to built its territorial development project in particular thanks to become listed as a world heritage site by UNESCO and the establishment of a marine protected area. In this context, a research programme was carried out. It was a partenarial and partipatory research about maritime heritage in Marquesas (PALIMMA). The objectives were to identify knowledge in the bibliography and to built data with the population (what heritage, what threats and what managerial solutions). Beyond knowledge production, this research programme, with marquisian local community, showed how important it is in ordrer to reach a balanced territorial development, to foster the empowerment of local population and to build relationships between individuals and institutions. A research program like PALIMMA can help to aim those objectives.</mods:abstract>

**Example ("excerpt"):** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/13ad5&metadataPrefix=mods

.. code-block:: xml
    :linenos:

    <mods:abstract type="excerpt" >Le 11 février 2025 est la 10e Journée internationale des femmes et filles de sciences. Créée par l'ONU en 2015, cette journée vise à encourager la participation des femmes à la recherche scientifique, en tant que chercheuses et en tant qu’étudiantes, à travers de nombreuses actions d’information et de médiation. Mondes Sociaux a choisi cette occasion pour éclairer certains aspects de l’histoire de la place des femmes à l’université et dans les disciplines scientifiques. Longtemps interdite d’accès...</mods:abstract>



10. mods:subject 
---------------------------

- ``mods:subject`` contains keywords. An ``xml:lang`` attribute specifies the language of the keyword.
- Available for OpenEdition Journals and OpenEdition Books and Calenda. 

**Example:** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/d85h&metadataPrefix=mods

.. code-block:: xml
    :linenos:

    <mods:subject xml:lang="en">
      <mods:topic>Belgium</mods:topic>
      <mods:topic>migration</mods:topic>
      <mods:topic>commuting</mods:topic>
      <mods:topic>community detection</mods:topic>
      <mods:topic>interaction fields</mods:topic>
      <mods:topic>provinces</mods:topic>
      <mods:topic>Census11</mods:topic>
    </mods:subject>
    <mods:subject xml:lang="fr">
      <mods:topic>Belgique</mods:topic>
      <mods:topic>migration</mods:topic>
      <mods:topic>détection de communautés</mods:topic>
      <mods:topic>champs d’interactions</mods:topic>
      <mods:topic>navettes</mods:topic>
      <mods:topic>provinces</mods:topic>
      <mods:topic>Census11</mods:topic>
    </mods:subject>



11. mods.originInfo
-----------------------------------


11.1 mods:dateIssued
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

- ``mods:dateIssued`` provides without prefix the year of publication of the document.

11.2 mods:dateOther
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
- ``mods:dateOther`` with attribute ``type="published_on_openedition"`` provides the publishing date of the document on OpenEdition platform. 
- For OpenEdition Journals, if ``mods:accessCondition[@type="restriction on access"] = embargoed access``, an extra ``mods:dateOther`` element with attribute ``type="available"`` provides the end date of embargo (availability date of the document in open access):

11.3 mods:publisher
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
- ``mods:publisher`` provides the publisher name. Repeatable.

11.4 mods.place
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
- For books, ``mods.place`` provides the publication place.

**Example (Journal article):** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/d85h&metadataPrefix=mods

.. code-block:: xml
    :linenos:

    <mods:originInfo>
      <mods:dateIssued encoding="w3cdtf">2017</mods:dateIssued>
      <mods:dateOther encoding="w3cdtf" type="published_on_openedition">2018-04-11</mods:dateOther>
      <mods:publisher>Société Royale Belge de Géographie</mods:publisher>
      <mods:publisher>National Committee of Geography of Belgium</mods:publisher>
    </mods:originInfo>


**Example (Journal article with embargo):** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/k213&metadataPrefix=mods

.. code-block:: xml
    :linenos:

    <mods:accessCondition type="restriction on access" auhorityURI="http://purl.org/coar/access_right/" valueURI="http://purl.org/coar/access_right/c_f1cf">embargoed access</mods:accessCondition>

    <mods:originInfo>
      <mods:dateIssued encoding="w3cdtf">2023</mods:dateIssued>
      <mods:dateOther encoding="w3cdtf" type="published_on_openedition">2023-11-28</mods:dateOther>
      <mods:dateOther encoding="w3cdtf" type="available">2027-01-01</mods:dateOther>
      <mods:publisher>ENS Éditions</mods:publisher>
    </mods:originInfo>

**Example (Book):** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/5div&metadataPrefix=mods

.. code-block:: xml
    :linenos:

    <mods:originInfo>
      <mods:dateIssued encoding="w3cdtf">1990</mods:dateIssued>
      <mods:dateOther encoding="w3cdtf" type="published_on_openedition">2022-08-28</mods:dateOther>
      <mods:place>
        <mods:placeTerm>Lyon</mods:placeTerm>
      </mods:place>
      <mods:publisher>Presses universitaires de Lyon</mods:publisher>
    </mods:originInfo>

12. mods:relatedItem[@type="host"]
---------------------------------------------------

- ``mods:relatedItem[@type="host"]`` provides information on the publication context:

  - For articles, it describes the journal and issue in which the article was published.
  - For book chapters, it describes the book in which the chapter was published.
  - For blog posts, it describes the blogin which the post was published.
  - For Calenda events, it describes the platform Calenda.

12.1 mods:title
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

- ``mods:titleInfo/mods:title`` provides the title of the Journal, Blog, Book

12.2 mods:identifier
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
- For journal articles, blog posts, Calenda events: 

  - ``mods:identifier[@type="eissn"]`` provides the digital ISSN of the Journal, Blog or site.
  - ``mods:identifier[@type="pissn"]`` provides the print ISSN of the Journal.

- For book chapters: 

  - ``mods:identifier[@type="eisbn"]`` provides the digital ISBN of the Book.
  - ``mods:identifier[@type="pisbn"]`` provides the print ISSN of the Book.

- For book chapters and journal articles :
 
  - ``mods:identifier[@type="doi"]`` provides the DOI of the jook or journal issue.
  - ``mods:identifier[@type="hdl"]`` provides the Handle of the book or journal issue.


12.3 mods:part
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
- For books chapters and journal articles ``mods:part`` provides pagination.
- For journal articles ``mods:part`` provides also the volume, issue, as shown in the example below..


**Example (Journal article):** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/gioa&metadataPrefix=mods

.. code-block:: xml
    :linenos:

    <mods:relatedItem type="host">
      <mods:titleInfo>
        <mods:title>Géomorphologie : relief, processus, environnement</mods:title>
      </mods:titleInfo>
      <mods:identifier type="eissn" typeURI="http://id.loc.gov/vocabulary/identifiers/issn">1957-777X</mods:identifier>
      <mods:identifier type="pissn" typeURI="http://id.loc.gov/vocabulary/identifiers/issn">1266-5304</mods:identifier>
      <mods:identifier type="doi">10.4000/geomorphologie.7878</mods:identifier>
      <mods:identifier type="hdl">20.500.13089/gizl</mods:identifier>
      <mods:part>
        <mods:detail type="volume">
          <mods:number>16</mods:number>
        </mods:detail>
        <mods:detail type="issue">
          <mods:number>2</mods:number>
        </mods:detail>
        <mods:extent unit="pages">
          <mods:start>215</mods:start>
          <mods:end>222</mods:end>
          <mods:list>215-222</mods:list>
        </mods:extent>
      </mods:part>
    </mods:relatedItem>


**Example (Book chapter):** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/11ppk&metadataPrefix=mods

.. code-block:: xml
    :linenos:

    <mods:relatedItem type="host">
      <mods:titleInfo>
        <mods:title>Renouveler les médiations du patrimoine en bibliothèque</mods:title>
      </mods:titleInfo>
      <mods:identifier type="eisbn" typeURI="http://id.loc.gov/vocabulary/identifiers/isbn">978-2-37546-171-6</mods:identifier>
      <mods:identifier type="pisbn" typeURI="http://id.loc.gov/vocabulary/identifiers/isbn">978-2-37546-170-9</mods:identifier>
      <mods:identifier type="doi">10.4000/11pqr</mods:identifier>
      <mods:identifier type="handle">20.500.13089/11pqr</mods:identifier>
      <mods:part>
        <mods:extent unit="pages">
          <mods:start>21</mods:start>
          <mods:end>28</mods:end>
          <mods:list>21-28</mods:list>
        </mods:extent>
      </mods:part>
    </mods:relatedItem>

**Example (Blog post):** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/11sem&metadataPrefix=mods

.. code-block:: xml
    :linenos:

    <mods:relatedItem type="host">
      <mods:titleInfo>
        <mods:title>Mondes sociaux</mods:title>
      </mods:titleInfo>
      <mods:identifier type="eissn" typeURI="http://id.loc.gov/vocabulary/identifiers/issn">2428-1387</mods:identifier>
    </mods:relatedItem>

**Example (Calenda event):** https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/11pm5&metadataPrefix=mods

.. code-block:: xml
    :linenos:

    <mods:relatedItem type="host">
      <mods:titleInfo>
        <mods:title>Calenda</mods:title>
      </mods:titleInfo>
      <mods:identifier type="eissn" typeURI="http://id.loc.gov/vocabulary/identifiers/issn">2107-5646</mods:identifier>
    </mods:relatedItem>



