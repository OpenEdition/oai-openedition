METS format
=================


.. warning::

   Version 1 of the OAI-PMH repository is DEPRECIATED. Please refer to the warning on the :ref:`home page <home>`.


.. contents:: Table of Contents
   :depth: 2

The ``mets`` (Metadata Encoding and Transmission Standard) format is available for books and journal issues (more info about types :ref:`types_v1`). The aim of this format is to describe the metadata and the complete structure of the volume (book or journal issue). 

The ``mets`` format is documented on the Library of Congress website: http://www.loc.gov/standards/mets/.

The list of available records in mets format can be found through OAI: https://oai.openedition.org/?verb=ListIdentifiers&metadataPrefix=mets (use :ref:`rToken` to retrieve the complete list).

In OpenEdition OAI, a ``mets`` record is divided into 3 main parts : one ``mets:structMap``, one ``mets:fileSec`` and several ``mets:dmdSec``.


.. _metsstructmap_v1:

1. mets:structMap
---------------------

The ``mets:structMap`` element describes the tree structure of the volume.

``mets:div`` elements are nested to describe the hierarchial organisation of the volume, parts, texts. Each ``mets:div`` element is qualified with the following attributes:

* ``TYPE``:  :ref:`List of document types <types_v1>` 
* ``ORDER``: sequence number whitch defines the order of the documents relative to the parent ``div`` element.
* ``DMDID``: refer to the ``ID`` of the relevant ``mets:dmdSec`` element.
* ``LABEL``: descriptive label 

Each ``mets:div`` element refering to a document file have one or several ``mets:fptr`` child element, with a ``FILEID`` refer to the ``ID`` of the relevant ``mets:file`` element.

**example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:books.openedition.org:puv/2002&metadataPrefix=mets

.. code-block:: xml
    :linenos:

    <mets:div LABEL="Voix de femmes" TYPE="part" DMDID="MD_OB_puv_2054" ID="SM_OB_puv_2054" ORDER="3">
        <mets:div LABEL="Le harem des voyageuses et des résidentes : un Ailleurs radical" TYPE="chapter" DMDID="MD_OB_puv_2055" ID="SM_OB_puv_2055" ORDER="1">
            <mets:fptr FILEID="F_OB_puv_basictei_2055"/>
            <mets:fptr FILEID="F_OB_puv_tei_2055"/>
            <mets:fptr FILEID="F_OB_puv_xhtml_2055"/>
            <mets:fptr FILEID="F_OB_puv_pdf_2055"/>
        </mets:div>
        <mets:div LABEL="Le voyage de Blanche Lee Childe (1881-1882) ou les conservatismes à l’épreuve des altérités" TYPE="chapter" DMDID="MD_OB_puv_2056" ID="SM_OB_puv_2056" ORDER="2">
            <mets:fptr FILEID="F_OB_puv_basictei_2056"/>
            <mets:fptr FILEID="F_OB_puv_tei_2056"/>
            <mets:fptr FILEID="F_OB_puv_xhtml_2056"/>
            <mets:fptr FILEID="F_OB_puv_pdf_2056"/>
        </mets:div>
    </mets:div>


2. mets:fileSec
----------------------


The ``mets:fileSec`` (File Section)  element is a main element contaning ``mets:file`` elements, one for each available format of each document described in the ``mets:structMap`` section.

The ``mets:file`` element have a child node ``mets:FLocat`` with an attribute ``xlink:href`` providing the url of the ressource.

.. note :: ``mets:structMap/mets:div/mets:fptr/@FILEID`` match ``mets:fileSec/mets:fileGrp/mets:file/@ID``

**example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:books.openedition.org:puv/2002&metadataPrefix=mets

.. code-block:: xml
    :linenos:

    <mets:fileGrp ID="FG_OB_puv_2055">
        <mets:file ID="F_OB_puv_xhtml_2055" MIMETYPE="text/html">
            <mets:FLocat LOCTYPE="URL" xlink:href="http://books.openedition.org/puv/2055"/>
        </mets:file>
        <mets:file ID="F_OB_puv_pdf_2055" MIMETYPE="application/pdf">
            <mets:FLocat LOCTYPE="URL" xlink:href="http://books.openedition.org/puv/pdf/2055"/>
        </mets:file>
        <mets:file ID="F_OB_puv_tei_2055" MIMETYPE="text/xml">
            <mets:FLocat LOCTYPE="URL" xlink:href="http://books.openedition.org/puv/tei/2055"/>
        </mets:file>
        <mets:file ID="F_OB_puv_basictei_2055" MIMETYPE="text/xml">
            <mets:FLocat LOCTYPE="URL" xlink:href="http://books.openedition.org/puv/basictei/2055"/>
        </mets:file>
    </mets:fileGrp>


3. mets:dmdSec
--------------------------

Each ``mets:div`` element used in the ``mets:strucMap`` is described in a ``mets:dmdSec`` (Descriptive Metadata Section) in dcterms. The metadata provided are the same as the metadata provided in :ref:`qdc`.

The ``mets:dmdSec`` have an ``ID`` attribute matching the ``DMDID`` of ``mets:div`` elements available in ``mets:structMap``.

.. note :: ``mets:structMap/mets:div/@DMDID`` match ``mets:mets/mets:dmdSec/@ID``

**example:** https://oai.openedition.org/?verb=GetRecord&identifier=oai:books.openedition.org:puv/2002&metadataPrefix=mets

.. code-block:: xml
    :linenos:


    <mets:dmdSec ID="MD_OB_puv_2055">
        <mets:mdWrap MDTYPE="DC" LABEL="Dublin Core Descriptive Metadata" MIMETYPE="text/xml">
            <mets:xmlData>
                <dcterms:title>Le harem des voyageuses et des résidentes : un Ailleurs radical</dcterms:title>
                <dcterms:type>chapter</dcterms:type>
                <dcterms:creator>Lançon, Daniel</dcterms:creator>
                <dcterms:subject xml:lang="fr" scheme="keywords">Orientalisme</dcterms:subject>
                <dcterms:subject xml:lang="fr" scheme="keywords">littérature</dcterms:subject>
                <dcterms:subject xml:lang="fr" scheme="keywords">francophonie</dcterms:subject>
                <dcterms:subject xml:lang="fr" scheme="keywords">écriture</dcterms:subject>
                <dcterms:subject scheme="ISI">Literature, Romance</dcterms:subject>
                <dcterms:subject scheme="BISAC">LIT004150</dcterms:subject>
                <dcterms:subject scheme="BIC">DSB</dcterms:subject>
                <dcterms:description>Le xixe siècle marque l’apogée de la traite en terre d’islam ; traite qui est à l’origine même du système du harem. Sans doute deux millions de personnes ont-elles été concernées en Égypte par ce commerce dont plus de la moitié provenait de la vallée du Haut-Nil (actuels Soudan et Éthiopie-Somalie). Pour la seule année 1867, trente mille esclaves furent exportés du Soudan vers l’Égypte via le Nil ou la mer Rouge, en majeure partie des jeunes filles. Dans le même temps, plusieurs centaines de ...</dcterms:description>
                <dcterms:publisher>Presses universitaires de Vincennes</dcterms:publisher>
                <dcterms:language scheme="RFC1766">fr</dcterms:language>
                <dcterms:issued scheme="W3CDTF">2015-03-10</dcterms:issued>
                <dcterms:identifier scheme="URI">http://books.openedition.org/puv/2055</dcterms:identifier>
                <dcterms:extent>111-123</dcterms:extent>
                <dcterms:identifier scheme="URN">urn:eisbn:9782842928728</dcterms:identifier>
                <dcterms:identifier scheme="URN">urn:isbn:9782842924256</dcterms:identifier>
                <dcterms:accessRights>info:eu-repo/semantics/restrictedAccess</dcterms:accessRights>
                <dcterms:hasFormat scheme="TEI">http://books.openedition.org/puv/tei/2055</dcterms:hasFormat>
                <dcterms:hasFormat scheme="BASICTEI">http://books.openedition.org/puv/basictei/2055</dcterms:hasFormat>
            </mets:xmlData>
        </mets:mdWrap>
    </mets:dmdSec>

