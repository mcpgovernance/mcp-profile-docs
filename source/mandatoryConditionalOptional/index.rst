.. _mandatoryConditionalOptional:

Mandatory, Conditional and Optional Elements for Marine Geographic Datasets
===========================================================================

**Mandatory metadata elements** are elements that must appear in any MCP metadata record. 

**Conditional metadata elements** are elements that are mandatory if a certain condition exists. For example, it is mandatory to have a metadata language element if the language encoding is not one of the common ISO10646-1/Unicode character sets such as UTF-8.

**Optional metadata elements** are elements that don't need to be present but are recommended to maximize interoperability.

Mandatory Metadata Elements for Marine Geographic Datasets
----------------------------------------------------------

**About the Dataset**:

===   ====================================  ===============================================================================================================================================================================================
No.   Name                                  XPath              
===   ====================================  ===============================================================================================================================================================================================
D1    Citation Title                        mcp:MD_Metadata/gmd:identificationInfo/mcp:MD_DataIdentification/gmd:citation/gmd:CI_Citation/gmd:title
D2    Citation Date                         mcp:MD_Metadata/gmd:identificationInfo/mcp:MD_DataIdentification/gmd:citation/gmd:CI_Citation/gmd:date
D3    Abstract                              mcp:MD_Metadata/gmd:identificationInfo/mcp:MD_DataIdentification/gmd:abstract
D5    Language                              mcp:MD_Metadata/gmd:identificationInfo/mcp:MD_DataIdentification/gmd:language
D6    Topic Category                        mcp:MD_Metadata/gmd:identificationInfo/mcp:MD_DataIdentification/gmd:topicCategory
D7    Bounding Box                          mcp:MD_Metadata/gmd:identificationInfo/mcp:MD_DataIdentification/gmd:extent/gmd:EX_Extent/gmd:geographicElement/gmd:EX_GeographicBoundingBox
D8    Temporal Extent                       mcp:MD_Metadata/gmd:identificationInfo/mcp:MD_DataIdentification/gmd:extent/gmd:EX_Extent/gmd:geographicElement/mcp:EX_TemporalExtent
===   ====================================  ===============================================================================================================================================================================================

*Rationale for making D7 and D8 mandatory*: In earlier versions of the MCP documentation (eg. http://www.aodc.gov.au/files/MarineCommunityProfilev1.4.pdf), D7 and D8 were made conditional on the hierarchyLevel being set to 'dataset'. However the subject (and the title of this section) in previous documentation has always been about 'Metadata Elements for Marine Geographic *Datasets*'. Given that we are referring to 'datasets', this condition would appear to be trivially satisfied and we can safely make elements D7 and D8 mandatory.


**About the Metadata record**:

===   ====================================  ===============================================================================================================================================================================================
No.   Name                                  XPath              
===   ====================================  ===============================================================================================================================================================================================
M1    File Identifier                       mcp:MD_Metadata/gmd:fileIdentifier
M2    Standard Name                         mcp:MD_Metadata/gmd:metadataStandardName
M3    Standard Version                      mcp:MD_Metadata/gmd:metadataStandardVersion
M4    Date Stamp                            mcp:MD_Metadata/gmd:dateStamp
M5    Revision Date                         mcp:MD_Metadata/mcp:revisionDate
M6    Point of Contact                      mcp:MD_Metadata/gmd:contact/gmd:CI_ResponsibleParty
===   ====================================  ===============================================================================================================================================================================================

*Rationale for making M2 and M3 and Mandatory*: The MCP is implemented in both a production version and an experimental version. Implementations need to be able to distinguish between these versions of the MCP.

Conditional Metadata Elements for Marine Geographic Datasets
------------------------------------------------------------

**About the Dataset**:

===   ====================================  =================================================================================  ===============================================================================================
No.   Name                                  XPath                                                                              Condition
===   ====================================  =================================================================================  ===============================================================================================
CD3   Character Set                         mcp:MD_Metadata/gmd:identificationInfo/mcp:MD_DataIdentification/gmd:characterSet                                                              Documented if ISO 10646-1/Unicode (eg. UTF-8) not used and not defined by the encoding standard
===   ====================================  =================================================================================  ===============================================================================================

**About the Metadata record**:

===   ====================================  ================================  ===============================================================================================
No.   Name                                  XPath                             Condition
===   ====================================  ================================  ===============================================================================================
CM1   Character Set                         mcp:MD_Metadata/gmd:characterSet  Documented if ISO 10646-1/Unicode (eg. UTF-8) not used and not defined by the encoding standard
CM2   Language                              mcp:MD_Metadata/gmd:language      Documented if not defined by the encoding standard
===   ====================================  ================================  ===============================================================================================


Optional Metadata Elements for Marine Geographic Datasets
---------------------------------------------------------

All optional elements refer to the dataset.

===   ====================================  ===============================================================================================================================================================================================
No.   Name                                  XPath              
===   ====================================  ===============================================================================================================================================================================================
OD1   Responsible Party                     mcp:MD_Metadata/gmd:identificationInfo/mcp:MD_DataIdentification/gmd:pointOfContact/gmd:CI_ResponsibleParty
OD2   Spatial Resolution                    mcp:MD_Metadata/gmd:identificationInfo/mcp:MD_DataIdentification/gmd:spatialResolution/gmd:MD_Resolution/gmd:equivalentScale
OD3   Distribution Format                   mcp:MD_Metadata/gmd:distributionInfo/gmd:MD_Distribution/gmd:distributionFormat/gmd:MD_Format
OD4   Online Resource                       mcp:MD_Metadata/gmd:distributionInfo/gmd:MD_Distribution/gmd:transferOptions/gmd:MD_DigitalTransferOptions/gmd:onLine/gmd:CI_OnlineResource
OD5   Reference System                      mcp:MD_Metadata/gmd:referenceSystemInfo/gmd:MD_ReferenceSystem 
OD6   Spatial Representation Type           mcp:MD_Metadata/gmd:identificationInfo/mcp:MD_DataIdentification/gmd:spatialRepresentationType
OD7   Keywords                              mcp:MD_Metadata/gmd:identificationInfo/mcp:MD_DataIdentification/gmd:keywords
OD8   Lineage                               mcp:MD_Metadata/gmd:dataQualityInfo/gmd:DQ_DataQuality/gmd:lineage/gmd:LI_Lineage/gmd:statement
===   ====================================  ===============================================================================================================================================================================================
