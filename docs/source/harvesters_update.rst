.. _harvesters_update:

Updating harvesters from v1 to v2
==================================

.. contents:: Table of Contents
   :depth: 2


As explained in :ref:`OAI v2 / Main principles <main_principles_v2>`, the OAI-PMH repository V2 uses new identifiers (Handle). Identifiers used un OAI-PMH V1 are no longer used.

For Instance, the following document https://journals.openedition.org/vertigo/44488 have these representations in OAI V1 and V2:

- OAI-PMH V1: https://oai.openedition.org/?verb=GetRecord&identifier=oai:revues.org:vertigo/44488&metadataPrefix=oai_dc
- OAI-PMH-V2: https://metadata.openedition.org/oai?verb=GetRecord&identifier=20.500.13089/126nm&metadataPrefix=oai_dc

As a result, Harvesters should delete the existing OpenEdition metadata in their system and harvest the V2 repository as new records.

Please contact us if we can help you with the migration process: referencement@openedition.org



