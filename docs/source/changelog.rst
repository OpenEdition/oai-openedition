.. _changelog:

Changelog 
============================================

**2025-07-17**

*Release 2.1.2*

* ``oai_openaire`` and ``mods``: fix  inversion of creator and contributor ``givenName`` and ``familyName`` (bug introduced for Journals and Books in release 2.1.0)


**2025-05-12**

*Release 2.1.1*

* fix ``ResumptionToken`` issue: urlencoded resumptionToken is now valid
* ``oai_openaire``: ``creator/nameIdentifier@schemeUri`` and  ``contributor/nameIdentifier@schemeUri``: provide identifier resolver
* ``oai_openaire``: fix double ``datacite:rights``
* ``ListSets``: add ``dc:type`` that specify which record identifiers are available



**2025-04-29**

*Release 2.1.0*

* add Person Identifiers if available (IdRef, Orcid, Isni, Viaf, BNF):

  * ``mods``: ``name/nameIdentifier`` element 
  * ``oai_openaire``: ``creator/nameIdentifier`` and  ``contributor/nameIdentifier`` 


**2025-02-14**

*Release 2.0.2*

* remove "Announcement / News" type documents for journals
* when abstract is not available provide excerpt in:

  * ``description`` (``oai_dc`` and ``oai_openaire`` formats)
  * ``abstract`` (``mods`` format)

* ``mods`` format: add attribute ``abstract@type``. Possible values: ``summary``, ``abstract``

**2025-01-28**

*Release 2.0.1*

* ``oai_openaire`` format: update  ``datacite:identifier@identifierType`` attribute value to ``datacite:identifier@identifierType="HANDLE"`` (was ``datacite:identifier@identifierType="Handle"``)
* remove invalid ``request@cursor`` attribute
* remove invalid extra ``request`` attribute when ``@resumptionToken`` is used
* fix ``resumptionToken`` value: avoid characters ``&``, ``=``
* fix incorrect error messages (GetRecord -> badArgument)

**2024-11-20**

* OAI-PMH v2 is released to 2.0.0
* OAI-PMH v1 is declared as deprecated


**2024-06-14**

* first version of repository OAI-PMH v2 beta


**2022-02-15**

* fix error on ``dc:date`` and ``dcterms:issued``
* add ``dcterms.created``

**2018-10-26**

* 1st release


