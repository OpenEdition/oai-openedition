mets format
=================

.. warning::

      This documentation concerns version 2 beta of the OpenEdition OAI-PMH repository. This version is subject to change until version 2.0 is released. 

      **NOT FOR USE IN PRODUCTION**

.. contents:: Table of Contents
   :depth: 2

The ``mets`` (Metadata Encoding and Transmission Standard) format is available for books and journal issues (more info about types :ref:`types_v2`). The aim of this format is to describe the metadata and the complete structure of the volume (book or journal issue). 

The ``mets`` format is documented on the Library of Congress website: http://www.loc.gov/standards/mets/.

The list of available records in mets format can be found through OAI: https://metadata.openedition.org/oai2?verb=ListIdentifiers&metadataPrefix=mets (use :ref:`rToken_v2` to retrieve the complete list).

In OpenEdition OAI, a ``mets`` record is divided into 3 main parts : one ``mets:structMap``, one ``mets:fileSec`` and several ``mets:dmdSec``.


.. _metsstructmap_v2:

1. mets:structMap
---------------------

The ``mets:structMap`` element describes the tree structure of the volume.

``mets:div`` elements are nested to describe the hierarchial organisation of the volume, parts, texts. Each ``mets:div`` element is qualified with the following attributes:

* ``TYPE``:  :ref:`List of document types <types_v2>` 
* ``ORDER``: sequence number whitch defines the order of the documents relative to the parent ``div`` element.
* ``DMDID``: refer to the ``ID`` of the relevant ``mets:dmdSec`` element.
* ``LABEL``: descriptive label 

Each ``mets:div`` element refering to a document file have one or several ``mets:fptr`` child element, with a ``FILEID`` refer to the ``ID`` of the relevant ``mets:file`` element.

**example:** https://metadata.openedition.org/oai2?verb=GetRecord&identifier=20.500.13089/11qs2&metadataPrefix=mets

.. code-block:: xml
    :linenos:

     <mets:div LABEL="Théâtres d&#039;Orient" TYPE="part" DMDID="MD_OB_momeditions_18766" ID="SM_OB_momeditions_18766" ORDER="4">
       <mets:div LABEL="The parodos of the Greek theatres through time: from the Classical to the Roman imperial period" TYPE="chapter" DMDID="MD_OB_momeditions_18771" ID="SM_OB_momeditions_18771" ORDER="1">
         <mets:fptr FILEID="F_OB_momeditions_basictei_18771"/>
         <mets:fptr FILEID="F_OB_momeditions_tei_18771"/>
         <mets:fptr FILEID="F_OB_momeditions_xhtml_18771"/>
         <mets:fptr FILEID="F_OB_momeditions_pdf_18771"/>
       </mets:div>
       <mets:div LABEL="Parodos ou aditus ?" TYPE="chapter" DMDID="MD_OB_momeditions_18781" ID="SM_OB_momeditions_18781" ORDER="2">
         <mets:fptr FILEID="F_OB_momeditions_basictei_18781"/>
         <mets:fptr FILEID="F_OB_momeditions_tei_18781"/>
         <mets:fptr FILEID="F_OB_momeditions_xhtml_18781"/>
         <mets:fptr FILEID="F_OB_momeditions_pdf_18781"/>
       </mets:div>
       <mets:div LABEL="Formes architecturales et fonctions de l’aditus maximus dans les théâtres du Proche‑Orient romain" TYPE="chapter" DMDID="MD_OB_momeditions_18791" ID="SM_OB_momeditions_18791" ORDER="3">
         <mets:fptr FILEID="F_OB_momeditions_basictei_18791"/>
         <mets:fptr FILEID="F_OB_momeditions_tei_18791"/>
         <mets:fptr FILEID="F_OB_momeditions_xhtml_18791"/>
         <mets:fptr FILEID="F_OB_momeditions_pdf_18791"/>
       </mets:div>
     </mets:div>



2. mets:fileSec
----------------------


The ``mets:fileSec`` (File Section)  element is a main element contaning ``mets:file`` elements, one for each available format of each document described in the ``mets:structMap`` section.

The ``mets:file`` element have a child node ``mets:FLocat`` with an attribute ``xlink:href`` providing the url of the ressource.

.. note :: ``mets:structMap/mets:div/mets:fptr/@FILEID`` match ``mets:fileSec/mets:fileGrp/mets:file/@ID``

**example:** https://metadata.openedition.org/oai2?verb=GetRecord&identifier=20.500.13089/11qs2&metadataPrefix=mets

.. code-block:: xml
    :linenos:

    <mets:fileGrp ID="FG_OB_momeditions_18881">
      <mets:file ID="F_OB_momeditions_xhtml_18881" MIMETYPE="text/html">
        <mets:FLocat LOCTYPE="URL" xlink:href="https://books.openedition.org/momeditions/18881"/>
      </mets:file>
      <mets:file ID="F_OB_momeditions_pdf_18881" MIMETYPE="application/pdf">
        <mets:FLocat LOCTYPE="URL" xlink:href="https://books.openedition.org/momeditions/pdf/18881"/>
      </mets:file>
      <mets:file ID="F_OB_momeditions_tei_18881" MIMETYPE="text/xml">
        <mets:FLocat LOCTYPE="URL" xlink:href="https://books.openedition.org/momeditions/tei/18881"/>
      </mets:file>
      <mets:file ID="F_OB_momeditions_basictei_18881" MIMETYPE="text/xml">
        <mets:FLocat LOCTYPE="URL" xlink:href="https://books.openedition.org/momeditions/basictei/18881"/>
      </mets:file>
    </mets:fileGrp>


3. mets:dmdSec
--------------------------

Each ``mets:div`` element used in the ``mets:strucMap`` is described in a ``mets:dmdSec`` (Descriptive Metadata Section) in dcterms. The metadata provided are the same as the metadata provided in :ref:`mods_v2`

The ``mets:dmdSec`` have an ``ID`` attribute matching the ``DMDID`` of ``mets:div`` elements available in ``mets:structMap``.

.. note :: ``mets:structMap/mets:div/@DMDID`` match ``mets:mets/mets:dmdSec/@ID``

**example:** https://metadata.openedition.org/oai2?verb=GetRecord&identifier=20.500.13089/11qs2&metadataPrefix=mets

.. code-block:: xml
    :linenos:

    <mets:dmdSec ID="MD_OB_momeditions_18781">
      <mets:mdWrap MDTYPE="MODS" MIMETYPE="text/xml">
        <mets:xmlData xmlns:mods="http://www.loc.gov/mods/v3"
          xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
          xsi:schemaLocation="http://www.loc.gov/mods/v3 https://www.loc.gov/standards/mods/v3/mods-3-8.xsd">
          <mods:titleInfo>
            <mods:title>Parodos ou aditus ?</mods:title>
            <mods:subTitle>L’évolution des accès aux théâtres d’Ionie à l’époque impériale</mods:subTitle>
          </mods:titleInfo>
          <mods:typeOfResource authorityURI="http://purl.org/coar/resource_type/" valueURI="http://purl.org/coar/resource_type/c_3248">book part</mods:typeOfResource>
          <mods:typeOfResource authority="openedition">chapter</mods:typeOfResource>
          <mods:language>
            <mods:languageTerm type="code" authority="iso639-1">fr</mods:languageTerm>
          </mods:language>
          <mods:identifier type="doi">10.4000/11qri</mods:identifier>
          <mods:identifier type="hdl">20.500.13089/11qri</mods:identifier>
          <mods:location>
            <mods:url>https://books.openedition.org/momeditions/18781</mods:url>
          </mods:location>
          <mods:accessCondition type="license" valueURI="https://creativecommons.org/licenses/by-nc-nd/4.0/">CC-BY-NC-ND-4.0</mods:accessCondition>
          <mods:accessCondition type="restriction on access" authorityURI="http://purl.org/coar/access_right/" valueURI="http://purl.org/coar/access_right/c_abf2">open access</mods:accessCondition>
          <mods:name type="personal">
            <mods:role>
              <mods:roleTerm authority="marcrelator">aut</mods:roleTerm>
            </mods:role>
            <mods:namePart type="given">Jeanne</mods:namePart>
            <mods:namePart type="family">Capelle</mods:namePart>
          </mods:name>
          <mods:abstract xml:lang="fr">Dans l’Ionie d’époque impériale, si certains petits théâtres conservèrent leurs parodos hellénistiques, à portes d’accès à l’orchestra (Priène, Érythrées), les accès au diazôma depuis les parodos – par des portes ouvrant dans les murs de soutènement – tendirent à les concurrencer et l’espace des parodos à rétrécir (Métropolis). Dans les plus grands théâtres, les accès furent reconfigurés. Ceux de Magnésie, Éphèse et Milet adoptèrent un modèle commun, avec des parodos surélevées, donnant désormais accès à l’estrade puis au podium, sans que soient supprimés les accès bas latéraux à l’orchestra. On adopta une solution un peu différente à Smyrne et bien plus encore à Téos, seul théâtre où l’on renonça à des accès latéraux à l’orchestra aussi bien qu’à la scène. Mais jamais des aditus de type latin ne se substituèrent aux parodos, qui, à Priène, furent même entretenues et empruntées bien après la fin des spectacles, jusqu’à l’époque tardo-byzantine, jouissant d’une exceptionnelle longévité.</mods:abstract>
          <mods:abstract xml:lang="en">In Imperial-period Ionia, although some small theatres kept their Hellenistic parodos, with doors opening onto the orchestra (Priene, Erythrai), access to the diazoma from the parodos – through doors opening in the retaining walls – tended to compete with them and the space of the parodos to shrink (Metropolis). In the largest theatres, the entrances were reconfigured. The theatres of Magnesia, Ephesus and Miletus adopted a common pattern, with raised parodos giving access to the stage and then to the podium, without removing the low side entrances to the orchestra. A slightly different solution was adopted in Smyrna and even more so in Teos, the only theatre where side access to the orchestra as well as to the stage was abandoned. Yet, the Latin-style aditus never replaced the parodos, which in Priene were even maintained and well used even after the end of the performances, right up until the late Byzantine period, enjoying exceptional longevity.</mods:abstract>
          <mods:originInfo>
            <mods:dateIssued encoding="w3cdtf">2024</mods:dateIssued>
            <mods:dateOther encoding="w3cdtf" type="published_on_openedition">2024-05-29</mods:dateOther>
            <mods:place>
              <mods:placeTerm>Lyon</mods:placeTerm>
            </mods:place>
            <mods:publisher>MOM Éditions</mods:publisher>
          </mods:originInfo>
          <mods:relatedItem type="host">
            <mods:titleInfo>
              <mods:title>Les théâtres antiques et leurs entrées</mods:title>
            </mods:titleInfo>
            <mods:identifier type="eisbn" typeURI="http://id.loc.gov/vocabulary/identifiers/isbn">978-2-35668-156-0</mods:identifier>
            <mods:identifier type="pisbn" typeURI="http://id.loc.gov/vocabulary/identifiers/isbn">978-2-35668-085-3</mods:identifier>
            <mods:identifier type="hdl">20.500.13089/11qs2</mods:identifier>
            <mods:identifier type="doi">10.4000/11qs2</mods:identifier>
            <mods:part>
              <mods:extent unit="pages">
                <mods:start>63</mods:start>
                <mods:end>93</mods:end>
                <mods:list>63-93</mods:list>
              </mods:extent>
            </mods:part>
          </mods:relatedItem>
        </mets:xmlData>
      </mets:mdWrap>
    </mets:dmdSec>

