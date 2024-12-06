.. _harvesters_update:

Updating harvesters from v1 to v2
==================================

.. contents:: Table of Contents
   :depth: 2

Harvest OAI-PMH V2 as a new repository
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

As explained in :ref:`OAI v2 / Main principles <main_principles_v2>`, the OAI-PMH repository V2 uses new identifiers (Handle). Identifiers used un OAI-PMH V1 are no longer used.

For Instance, the following document https://journals.openedition.org/vertigo/44488 have these representations in OAI V1 and V2:

- OAI-PMH V1: https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:vertigo/44488&metadataPrefix=oai_dc
- OAI-PMH-V2: https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/126nm&metadataPrefix=oai_dc

As a result, the easiest method for Harvesters to migrate is probably to delete the existing OpenEdition metadata in their system and harvest the V2 repository as new records.

Please contact us if we can help you with the migration process: referencement@openedition.org


Retrieve Handle from previous OAI Identifiers
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Despite this, if needed, Harvester can retrieve the new identifiers (Handle) from the previous OAI Identifiers.

Example with the OAI-PMH V1 identifier: ``oai:revues.org:vertigo/44488``

- https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:vertigo/44488&metadataPrefix=qdc returns :

.. code-block:: xml
    :linenos:

    <dcterms:identifier scheme="URN">urn:handle:20.500.13089/126nm</dcterms:identifier>

- This handle is to be used in OAI-PMH v2, for instance with the ``oai_openaire`` format: https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/126nm&metadataPrefix=oai_openaire


