.. _dataParameters:

Data Parameters (mcp:dataParameters)
====================================

Rationale
---------

ISO19115 has classes for describing the data parameters of coverages (continuously varying data usually represented by grids) and features (usually discrete data represented as points, lines and polygons etc) in the Content Information package (see section A.2.8 of the ISO19115 standard). However, the package does not provide:

#. a simple, unified description of data parameters. The metadata author is forced instead to split the description of data parameters between a class for coverages and a separate, related standard for features (ISO19110)
#. a simple way of handling the different aliases that often need to be described when entering metadata about data parameters 
#. encapsulation of the data parameter metadata - not just names and units but instruments, analyses and platforms associated with the parameter    
#. vocabulary support for looking up data parameter terms

The intention of this package is to address points 1-3 and provide a basis for point 4 when vocabulary services that provide these terms are standardized and more widely available.

UML
---

.. image:: dataParameters_uml.png

*UML Diagram of DataParameters package*

Data Dictionary
---------------

.. index:: mcp:dataParameters
.. index:: mcp:DP_DataParameters
.. index:: mcp:dataParameter
.. index:: mcp:DP_DataParameter
.. index:: mcp:parameterName
.. index:: mcp:parameterUnits
.. index:: mcp:parameterMinimumValue
.. index:: mcp:parameterMaximumValue
.. index:: mcp:parameterDeterminationInstrument
.. index:: mcp:parameterAnalysisMethod
.. index:: mcp:platform

===  ===================================  ==============================================================================================================  ========================  ===============  ==================================  ===============================
No.  Name/Role Name                       Definition                                                                                                      Condition/ Obligation     Max. Occurrence  Data Type                           Domain
===  ===================================  ==============================================================================================================  ========================  ===============  ==================================  ===============================
940  DP_DataParameters                    Container for description of data set data parameters                                                           Note 1                    Note 2           Aggregated Class                    Line 68                        
941  DP_DataParameter                     Container for description of a data set parameter                                                               Note 1                    Note 2           Class                               Lines 942-948
942  parameterName                        Name of Parameter                                                                                               M                         N                Class                               DP_Term        
943  parameterUnits                       Units of Parameter                                                                                              M                         N                Class                               DP_Term        
944  parameterMinimumValue                Minimum Value of Parameter                                                                                      O                         1                CharacterString                     FreeText
945  parameterMaximumValue                Maximum Value of Parameter                                                                                      O                         1                CharacterString                     FreeText
946  parameterDeterminationInstrument     Name and information about an instrument used in the determination of an observed or measured parameter         O                         N                Class                               DP_Term
947  parameterAnalysisMethod              Name and information about an analysis method used in the determination of an observed or measured parameter    O                         N                Class                               DP_Term
948  platform                             Name and information about a platform used to observe or measure a parameter                                    O                         N                Class                               DP_Term
===  ===================================  ==============================================================================================================  ========================  ===============  ==================================  ===============================

.. include:: ../common_notes.rst

.. index:: mcp:term
.. index:: mcp:type
.. index:: mcp:usedInDataset
.. index:: mcp:vocabularyTermURL
.. index:: mcp:vocabularyTermPublisher
.. index:: mcp:vocabularyServiceURL
.. index:: mcp:vocabularyVersion
.. index:: mcp:vocabularyPublisher
.. index:: mcp:vocabularyRelationship
.. index:: mcp:termDefinition
.. index:: mcp:DP_Term
.. index:: mcp:DP_TypeCode

===  ===========================  =============================================================================================================  ===============================================  ===============  ==================================  ===============================
No.  Name/Role Name               Definition                                                                                                     Condition/ Obligation                            Max. Occurrence  Data Type                           Domain
===  ===========================  =============================================================================================================  ===============================================  ===============  ==================================  ===============================
949  DP_Term                      Container for the description of terms used to express the parameter                                           Note 1                                           Note 2           Class << DataType >>                Lines 950-959
950  term                         Word used to describe a thing or express a concept that is considered a data parameter                         M                                                1                CharacterString                     FreeText
951  type                         Type of term (from codelist)                                                                                   M                                                1                CodeList                            DP_TypeCode
952  usedInDataset                Flag to indicate whether the parameter is used in the dataset                                                  M                                                1                Boolean                                         
953  vocabularyTermURL            URL of vocabulary term                                                                                         C / type equal to "shortName" or "longName"      1                Class                               URL      
954  vocabularyTermPublisher      Citation of publishing authority regulating or managing vocabulary term                                        O                                                1                Class                               CI_Citation 
955  vocabularyServiceURL         URL for the service that exposes the vocabulary scheme in which the term resides                               M                                                1                Class                               URL      
956  vocabularyVersion            Version of the vocabulary in which the term resides                                                            O                                                1                CharacterString                     FreeText
957  vocabularyPublisher          Citation of publishing authority regulating or managing the vocabulary in which the term resides               O                                                1                Class                               CI_Citation 
958  vocabularyRelationship       Information about the relationship between this term and another term(s) from a vocabulary                     O                                                N                Class                               DP_VocabularyRelationship
959  termDefinition               Definition of the term if not available from vocabulary service                                                C / type equal to "localCode" or "localSynonym"  1                CharacterString                     FreeText
===  ===========================  =============================================================================================================  ===============================================  ===============  ==================================  ===============================

.. include:: ../common_notes.rst

.. index:: mcp:relationshipType
.. index:: mcp:relatedTermURL
.. index:: mcp:relatedTerm
.. index:: mcp:DP_VocabularyRelationship
.. index:: mcp:DP_RelationshipTypeCode  

===  ===========================  =============================================================================================================  ==============  ========  ==================================  ===============================
No.  Name/Role Name               Definition                                                                                                     Cond/ Oblig     Max. Occ  Data Type                           Domain
===  ===========================  =============================================================================================================  ==============  ========  ==================================  ===============================
960  DP_VocabularyRelationship    Container for the description of relationship between term and term or terms from a vocabulary                 Note 1          Note 2    Class <<DataType >>                 Lines 961-963
961  relationshipType             Type of relationship between two terms (described using skos)                                                  M               1         CodeList                            DP_RelationshipTypeCode
962  relatedTermURL               URL of related vocabulary term                                                                                 M               1         Class                               URL      
963  relatedTerm                  Related term name or label                                                                                     M               1         CharacterString                     FreeText
===  ===========================  =============================================================================================================  ==============  ========  ==================================  ===============================

.. include:: ../common_notes.rst

XML Example
-----------

An XML example of the data parameter package:

::
 
  <mcp:dataParameters>
    <mcp:DP_DataParameters>
      <mcp:dataParameter>
        <mcp:DP_DataParameter>
          <mcp:parameterName>
            <mcp:DP_Term>
              <mcp:term>
                  <gco:CharacterString>Temperature of the water body</gco:CharacterString>
              </mcp:term>
              <mcp:type>
                <mcp:DP_TypeCode 
                  codeList="http://schemas.aodn.org.au/mcp-2.0/resources/CodeList/gmxCodelists.xml#DP_TypeCo
                            de"
                  codeListValue="longName">longName</mcp:DP_TypeCode>
              </mcp:type>
              <mcp:usedInDataset>
                <gco:Boolean>1</gco:Boolean>
              </mcp:usedInDataset>
              <mcp:vocabularyTermURL>
                <gmd:URL>http://vocab.nerc.ac.uk/collection/P01/current/TEMPPR01</gmd:URL>
              </mcp:vocabularyTermURL>
              <mcp:vocabularyPublisher>
                <gmd:CI_Citation>
                  <gmd:title>
                    <gco:CharacterString>AODN Discovery Parameter Vocabulary</gco:CharacterString>
                  </gmd:title>
                  <gmd:date>
                    <gmd:CI_Date>
                      <gmd:date>
                        <gco:Date>2015-09-01</gco:Date>
                      </gmd:date>
                      <gmd:dateType>
                        <gmd:CI_DateTypeCode
                          codeList="http://www.ngdc.noaa.gov/metadata/published/xsd/schema/resources/Codelis
                                    t/gmxCodelists.xml#CI_DateTypeCode"
                          codeListValue="creation">creation</gmd:CI_DateTypeCode>
                      </gmd:dateType>
                    </gmd:CI_Date>
                  </gmd:date>
                  <gmd:citedResponsibleParty>
                    <gmd:CI_ResponsibleParty>
                      <gmd:organisationName>
                        <gco:CharacterString>eMarine Information Infrastructure (eMII)</gco:CharacterString>
                      </gmd:organisationName>
                      <gmd:role>
                        <gmd:CI_RoleCode
                          codeList="http://www.isotc211.org/2005/resources/Codelist/gmxCodelists.xml#CI_Role
                                    Code"
                          codeListValue="publisher">publisher</gmd:CI_RoleCode>
                      </gmd:role>
                    </gmd:CI_ResponsibleParty>
                  </gmd:citedResponsibleParty>
                </gmd:CI_Citation>
              </mcp:vocabularyPublisher>
              <mcp:vocabularyVersion>
                <gco:CharacterString>1.0</gco:CharacterString>
              </mcp:vocabularyVersion>
              <mcp:vocabularyServiceURL>
                <gmd:URL>http://vocabs.ands.org.au/repository/api/lda/aodn/aodn-discoveryparameter-vocabular
                         y/version-1-0/concept</gmd:URL>
              </mcp:vocabularyServiceURL>
              <mcp:termDefinition>
                <gco:CharacterString>The degree of hotness of the water column expressed against a standard 
                                     scale. Includes both IPTS-68 and ITS-90 scales.</gco:CharacterString>
              </mcp:termDefinition>
              <mcp:vocabularyRelationship>
                <mcp:DP_VocabularyRelationship>
                  <mcp:relationshipType>
                    <mcp:DP_RelationshipTypeCode
                      codeList="http://schemas.aodn.org.au/mcp-2.0/resources/Codelist/gmxCodelists.xml#DP_Re
                                lationshipTypeCode"
                      codeListValue="skos:exactMatch">skos:closeMatch</mcp:DP_RelationshipTypeCode>
                  </mcp:relationshipType>
                  <mcp:relatedTermURL>
                    <gmd:URL>http://gcmdservices.gsfc.nasa.gov/kms/concept/61594015-4ab4-4b38-ae4f-e31a4757b
                             065</gmd:URL>
                  </mcp:relatedTermURL>
                  <mcp:relatedTerm>
                    <gco:CharacterString>Water Temperature</gco:CharacterString>
                  </mcp:relatedTerm>
                </mcp:DP_VocabularyRelationship>
              </mcp:vocabularyRelationship>
            </mcp:DP_Term>
          </mcp:parameterName>
          <mcp:parameterUnits>
            <mcp:DP_Term>
              <mcp:term>
                <gco:CharacterString>degrees celsius</gco:CharacterString>
              </mcp:term>
              <mcp:type>
                <mcp:DP_TypeCode
                  codeList="http://schemas.aodn.org.au/mcp-2.0/resources/CodeList/gmxCodelists.xml#DP_TypeCo
                            de"
                  codeListValue="longName">longName</mcp:DP_TypeCode>
              </mcp:type>
              <mcp:usedInDataset>
                <gco:Boolean>1</gco:Boolean>
              </mcp:usedInDataset>
              <mcp:vocabularyTermURL>
                <gmd:URL>http://vocab.nerc.ac.uk/collection/P06/current/UPAA</gmd:URL>
              </mcp:vocabularyTermURL>
              <mcp:vocabularyPublisher>
                <gmd:CI_Citation>
                  ..
                </gmd:CI_Citation>
              </mcp:vocabularyPublisher>
              <mcp:vocabularyVersion>
                <gco:CharacterString>1.0</gco:CharacterString>
              </mcp:vocabularyVersion>
              <mcp:vocabularyServiceURL>
                <gmd:URL>http://vocabs.ands.org.au/repository/api/lda/aodn/aodn-units-of-measure-vocabulary/
                         version-1-0/concept</gmd:URL>
              </mcp:vocabularyServiceURL>
              <mcp:termDefinition>
                <gco:CharacterString>Some defn for degrees celsius</gco:CharacterString>
              </mcp:termDefinition>
            </mcp:DP_Term>
          </mcp:parameterUnits>
          <mcp:parameterMinimumValue>
            <gco:CharacterString>2.1</gco:CharacterString>
          </mcp:parameterMinimumValue>
          <mcp:parameterMaximumValue>
            <gco:CharacterString>18.2</gco:CharacterString>
          </mcp:parameterMaximumValue>
        </mcp:DP_DataParameter>
      </mcp:dataParameter>
    </mcp:DP_DataParameters>
  </mcp:dataParameters>

Metadata about this package
---------------------------

**Change**

- **Proposer**: BlueNet Project (Kate Roberts)
- **Date proposed**: 2010
- **Date accepted by MCP Governance Committee**: 2010
- **MCP Version**: 1.4 onwards
- **Brief decription of changes**: Original proposal

**Change**

- **Proposer**: AODN (Kim Finney, Craig Jones et. al.)
- **Date proposed**: March 2013
- **Date accepted by MCP Governance Committee**: Not yet accepted
- **MCP Version**: 2.0 onwards
- **Brief decription of changes**: Move from describing parameter names and units to parameter terms where terms relate not just to parameter names and unit names, but platforms, analysis methods, instruments etc). Added mcp:vocabularyTermURL, mcp:vocabularyTermDefinitionURL, mcp:vocabularyRelationship, mcp:DP_VocabularyRelationship, mcp:parameterDeterminationInstrument, mcp:parameterAnalysisMethod, mcp:platform - to provide more information about platform, analysis methods and instruments used for data parameters and explicit links to vocabulary and vocabulary of definitions

**Change**

- **Proposer**: AODN (Kim Finney, Craig Jones et. al.)
- **Date proposed**: November 2015
- **Date accepted by MCP Governance Committee**: Not yet accepted
- **MCP Version**: 2.0 onwards
- **Brief decription of changes**: Move term metadata to DP_Term, make vocabularyTermURL optional for local codes and synonyms, rename localDefinition to termDefinition, remove parameterDescription, add term publisher and make it clear what is term and vocabulary metadata

