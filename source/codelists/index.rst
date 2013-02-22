.. _codeLists:

Extensions to ISO19115 Codelists
================================

Annex B of the ISO19115 standard contains the codelists used in the standard. The MCP extends some of these codelists. For each codelist extended in the MCP, this section of the manual describes:

- the original codes and definitions
- the new codes and definitions

.. |ok| image:: icons/button_ok.png

CI_DateTypeCode (Annex B.5.2 in ISO19115)
-----------------------------------------

.. index:: extended code list for gmd:CI_DateTypeCode

===  ===============================  ======================  ==================================================================================================  ====
No.  Name                             Domain Code             Definition                                                                                          New 
===  ===============================  ======================  ==================================================================================================  ====
1    CI_DateTypeCode                  DateTypeCd              identification of when a given event occurred                                          
2    creation                         001                     date identifies when the resource was brought into existence                         
3    publication                      002                     date identifies when the resource was issued                                         
4    revision                         003                     date identifies when the resource was examined or re-examined and improved or amended
5    unknown                          004                     it is unknown what the date identifies                                                              |ok|
===  ===============================  ======================  ==================================================================================================  ====

Metadata about changes to this codelist
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

- **Rationale**: Sometimes it is unknown what the date refers to. Rather than pick an event at random, it is better to flag that it is unknown what event the date refers to.
- **Proposer**: AODCJF Technical Committee
- **Date proposed**: 2006
- **Date confirmed by MCP Governance Committee**: 2010
- **Included in MCP Version**: 1.2 onwards

CI_RoleCode (Annex B.5.5 in ISO19115)
-------------------------------------

.. index:: extended code list for gmd:CI_RoleCode

===  ===============================  ======================  ==============================================================================================================================================  ====
No.  Name                             Domain Code             Definition                                                                                                                                      New 
===  ===============================  ======================  ==============================================================================================================================================  ====
1    CI_RoleCode                      RoleCd                  function performed by the responsible party                                   
2    resourceProvider                 001                     party that supplies the resource                                              
3    custodian                        002                     party that accepts accountability and responsibility for the data and ensures appropriate care and maintenance of the resource
4    owner                            003                     party that owns the resource
5    user                             004                     party who uses the resource
6    distributor                      005                     party who distributes the resource
7    originator                       006                     party who created the resource    
8    pointOfContact                   007                     party who can be contacted for acquiring knowledge about or acquisition of the resource
9    principalInvestigator            008                     key party responsible for gathering information and conducting research                
10   publisher                        009                     party who published the resource                                                       
11   author                           010                     party who authored the resource                                                        
12   coinvestigator                   011                     one of the key parties responsible for gathering information and conducting research                                                            |ok|
13   licensor                         012                     party responsible for licensing                                                                                                                 |ok|
14   researchassistant                013                     party who helped gather information and conduct research                                                                                        |ok|
15   IPowner                          014                     party who owns the intellectual property                                                                                                        |ok|
16   moralRightsOwner                 015                     party who owns the moral rights                                                                                                                 |ok|
17   metadataContact                  016                     party who can be contacted about the metadata                                                                                                   |ok|
===  ===============================  ======================  ==============================================================================================================================================  ====

Metadata about changes to this codelist
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This metadata relates to codes 12-17:

- **Rationale**: ISO19115 role codes do not fully describe the range of roles that were found when adding metadata about research projects. These 6 additional codes cover some of the most important omissions.
- **Proposer**: BlueNet Staff (Kate Roberts)
- **Date proposed**: 2010
- **Date confirmed by MCP Governance Committee**: 2010
- **Included in MCP Version**: 1.4 onwards

.. _MD_MaintenanceFrequencyCode:

MD_MaintenanceFrequencyCode (Annex B.5.18 in ISO19115)
------------------------------------------------------

See :ref:`samplingFrequency` for UML diagram and details of a new element that uses this extended code list.

.. index:: extended code list for gmd:MD_MaintenanceFrequencyCode

===  ===============================  ======================  ====================================================================================================================================================================================  ====
No.  Name                             Domain Code             Definition                                                                                                                                                                            New 
===  ===============================  ======================  ====================================================================================================================================================================================  ====
1    MD_MaintenanceFrequencyCode      MaintFreqCd             frequency with which modifications and deletions are made to the data after it is first produced
2    continual                        001                     data is repeatedly and frequently updated                                     
3    daily                            002                     data is updated each day                                                  
4    weekly                           003                     data is updated on a weekly basis                   
5    fortnightly                      004                     data is updated every two weeks               
6    monthly                          005                     data is updated every month        
7    quarterly                        006                     data is updated every three months  
8    biannually                       007                     data is updated twice each year                                                        
9    annually                         008                     data is updated every year                                                             
10   asNeeded                         009                     data is updated as deemed necessary                                                    
11   irregular                        010                     data is updated in intervals that are uneven in duration                               
12   notPlanned                       011                     there are no plans to update the data 
13   unknown                          012                     frequency of maintenance for the data is unknown 
14   hourly                           013                     data is updated every hour                                                                                                                                                            |ok|
===  ===============================  ======================  ====================================================================================================================================================================================  ====

Metadata about changes to this codelist
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This metadata relates to code 14:

- **Rationale**: As this code list is now used for :ref:`samplingFrequency` as well as maintenanceFrequency, an hourly interval was required.
- **Proposer**: AODCJF                     
- **Date proposed**: 2006
- **Date confirmed by MCP Governance Committee**: 2010
- **Included in MCP Version**: 1.2 onwards

MD_ScopeCode (Annex B.5.25 in ISO19115)
---------------------------------------

.. index:: extended code list for gmd:MD_ScopeCode

===  ===============================  ======================  ====================================================================================================================================================================================  ====
No.  Name                             Domain Code             Definition                                                                                                                                                                            New 
===  ===============================  ======================  ====================================================================================================================================================================================  ====
1    MD_ScopeCode                     ScopeCd                 class of information to which the referencing entity applies                  
2    attribute                        001                     information applies to the attribute class                                    
3    attributeType                    002                     information applies to the characteristic of a feature                    
4    collectionHardware               003                     information applies to the collection hardware class
5    collectionSession                004                     information applies to the collection session
6    dataset                          005                     information applies to the dataset 
7    series                           006                     information applies to the series 
8    nonGeographicDataset             007                     information applies to non-geographic data                                             
9    dimensionGroup                   008                     information applies to a dimension group                                               
10   feature                          009                     information applies to a feature                                                       
11   featureType                      010                     information applies to a feature type                                                  
12   propertyType                     011                     information applies to a property type
13   fieldSession                     012                     information applies to a field session
14   software                         013                     information applies to a computer program or routine
15   service                          014                     information applies to a capability which a service provider entity makes available to a service user entity through a set of interfaces that define a behaviour, such as a use case
16   model                            015                     information applies to a copy or imitation of an existing or hypothetical object
17   tile                             016                     information applies to a tile, a spatial subset of geographic data
18   observed                         017                     information applies to observed data                                                                                                                                                  |ok|
19   derived                          018                     information applies to derived data                                                                                                                                                   |ok|
20   publication                      019                     information applies to publications                                                                                                                                                   |ok|
21   dataObject                       020                     information applies to data objects                                                                                                                                                   |ok|
22   project                          021                     information applies to a project                                                                                                                                                      |ok|
===  ===============================  ======================  ====================================================================================================================================================================================  ====

Metadata about changes to this codelist
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This metadata relates to codes 18-20:

- **Rationale**: ISO19115 scope codes do not fully describe the scope of metadata records from the Marine Research projects. These 3 additional scope codes cover some of the most important omissions.
- **Proposer**: AODCJF                     
- **Date proposed**: 2006
- **Date confirmed by MCP Governance Committee**: 2010
- **Included in MCP Version**: 1.2 onwards

This metadata relates to code 21:

- **Rationale**: ISO19115 scope codes do not describe data objects. 
- **Proposer**: Craig Jones, AODN and IMOS eMii
- **Date proposed**: 2012
- **Date confirmed by MCP Governance Committee**: Unknown
- **Included in MCP Version**: 1.4 onwards

This metadata relates to code 22:

- **Rationale**: ISO19115 scope codes do not describe projects. 
- **Proposer**: GeoScience Australia (already include in GA codelist http://asdd.ga.gov.au/asdd/profileinfo/GAScopeCodeList.xml)
- **Date proposed**: ????
- **Date confirmed by MCP Governance Committee**: Unknown
- **Included in MCP Version**: 1.4 onwards

MCP Codelists and Enumerations
==============================

The MCP adds two new Codelists and one Enumeration to support the new elements that have been added. The codelists and enumerations are shown without explanation in the MCP UML diagrams. Full descriptions are given in the following sections.

.. _MD_CurrencyTypeCode:

MD_CurrencyTypeCode
-------------------

.. index:: code list for mcp:MD_CurrencyTypeCode

See :ref:`temporalExtent` for UML diagram and details of elements that use this code list.

===  ===============================  ======================  ====================================================================================================================================================================================
No.  Name                             Domain Code             Definition                                                                                                                                                                          
===  ===============================  ======================  ====================================================================================================================================================================================
1    MD_CurrencyTypeCode              CurrCd                  Defines the temporal currency of the resource
2    mostRecent                       001                     resource currency is most recent                                              
3    historical                       002                     resource currency is historical                                           
4    predicted                        003                     resource currency is predicted                       
5    unknown                          004                     resource currency is unknown                 
===  ===============================  ======================  ====================================================================================================================================================================================

Metadata about changes to this codelist
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Metadata refers to codes 1-5:       

- **Rationale**: Provide MD_CurrencyTypeCode with controlled vocabulary.
- **Proposer**: AODCJF                     
- **Date proposed**: 2006
- **Date confirmed by MCP Governance Committee**: 2010
- **Included in MCP Version**: 1.2 onwards

.. _MD_TemporalAggregationUnitCode:

MD_TemporalAggregationUnitCode
------------------------------

.. index:: code list for mcp:MD_TemporalAggregationUnitCode

See :ref:`temporalExtent` for UML diagram and details of elements that use this code list.

===  ===============================  ======================  ====================================================================================================================================================================================
No.  Name                             Domain Code             Definition                                                                                                                                                                          
===  ===============================  ======================  ====================================================================================================================================================================================
1    MD_TemporalAggregationUnitCode   AgUnitCd                temporal aggregation of the resource                                          
2    day                              001                     aggregation unit is day                                                       
3    multi-day                        002                     aggregation unit is multi-day                                             
4    week                             003                     aggregation unit is week                             
5    month                            004                     aggregation unit is month                    
6    multi-month                      005                     aggregation unit is multi-month    
7    year                             006                     aggregation unit is year           
8    multi-year                       007                     aggregation unit is multi-year                                                         
9    none                             008                     aggregation unit is none                                                               
===  ===============================  ======================  ====================================================================================================================================================================================

Metadata about changes to this codelist
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Metadata refers to codes 1-9:       

- **Rationale**: Provide MD_TemporalAggregation with controlled vocabulary.
- **Proposer**: AODCJF                     
- **Date proposed**: 2006
- **Date confirmed by MCP Governance Committee**: 2010
- **Included in MCP Version**: 1.2 onwards

DP_TypeCode
-----------

.. index:: code list for mcp:DP_TypeCode

See :ref:`dataParameters` for details.

===  ===============================  ======================  ====================================================================================================================================================================================
No.  Name                             Domain Code             Definition                                                                                                                                                                          
===  ===============================  ======================  ====================================================================================================================================================================================
1    DP_TypeCode                      DPTypeCd                type of parameter or unit                                         
2    shortName                        001                     the short name by which the parameter or unit is known                        
3    longName                         002                     the long name by which the parameter or unit is known                     
4    code                             003                     the code by which the parameter or unit is known     
5    other                            004                     the parameter or unit is known by this name for some other reason
===  ===============================  ======================  ====================================================================================================================================================================================

Metadata about changes to this codelist
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Metadata refers to codes 1-5:       

- **Rationale**: Provide DP_TypeCode with controlled vocabulary.
- **Proposer**: BlueNet staff (Kate Roberts)
- **Date proposed**: 2010
- **Date confirmed by MCP Governance Committee**: 2010
- **Included in MCP Version**: 1.4 onwards

CommonsTypeCode <<Enumeration>>
-------------------------------

.. index:: code list for mcp:commonsType attribute

See :ref:`MD_Commons` for details.

===  ===============================  ======================  ====================================================================================================================================================================================
No.  Name                             Domain Code             Definition                                                                                                                                                                          
===  ===============================  ======================  ====================================================================================================================================================================================
1    commonsType                      CommonsTypeCode         Specifies the type of commons license that will be described by the MD_Commons class
2    Creative Commons                 001                     Creative Commons license (see http://creativecommons.org)                     
3    Data Commons                     002                     Data Commons license (see http://bluenet3.antcrc.utas.edu.au/datacommons) - possibly deprecated?
===  ===============================  ======================  ====================================================================================================================================================================================

Metadata about changes to this codelist
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Metadata refers to codes 2-3:       

- **Rationale**: Provide list of commons licensing schemas that can be described by MD_Commons.
- **Proposer**: BlueNet Project (Kate Roberts)
- **Date proposed**: 2010
- **Date confirmed by MCP Governance Committee**: 2010
- **Included in MCP Version**: 1.4 onwards

