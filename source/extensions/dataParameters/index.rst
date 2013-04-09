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
.. index:: mcp:parameterDescription
.. index:: mcp:parameterDeterminationInstrument
.. index:: mcp:parameterAnalysisMethod
.. index:: mcp:platform

===  ===================================  ==============================================================================================================  ========================  ===============  ==================================  ===============================
No.  Name/Role Name                       Definition                                                                                                      Condition/ Obligation     Max. Occurrence  Data Type                           Domain
===  ===================================  ==============================================================================================================  ========================  ===============  ==================================  ===============================
940  DP_DataParameters                    Container for description of data set data parameters                                                           Note 1                    Note 2           Aggregated Class                    Line 68                        
941  DP_DataParameter                     Container for description of a data set parameter                                                               Note 1                    Note 2           Class                               Lines 942-949
942  parameterName                        Name of Parameter                                                                                               M                         N                Class                               DP_Term        
943  parameterUnits                       Units of Parameter                                                                                              M                         N                Class                               DP_Term        
944  parameterMinimumValue                Minimum Value of Parameter                                                                                      O                         1                CharacterString                     FreeText
945  parameterMaximumValue                Maximum Value of Parameter                                                                                      O                         1                CharacterString                     FreeText
946  parameterDescription                 Parameter Description                                                                                           O                         1                CharacterString                     FreeText
947  parameterDeterminationInstrument     Name and information about an instrument used in the determination of an observed or measured parameter         O                         N                Class                               DP_Term
948  parameterAnalysisMethod              Name and information about an analysis method used in the determination of an observed or measured parameter    O                         N                Class                               DP_Term
949  platform                             Name and information about a platform used to observe or measure a parameter                                    O                         N                Class                               DP_Term
===  ===================================  ==============================================================================================================  ========================  ===============  ==================================  ===============================

.. include:: ../common_notes.rst

.. index:: mcp:term
.. index:: mcp:type
.. index:: mcp:usedInDataset
.. index:: mcp:vocabularyRelationship
.. index:: mcp:localDefinition
.. index:: mcp:DP_Term
.. index:: mcp:DP_TypeCode

===  ===========================  =============================================================================================================  ========================  ===============  ==================================  ===============================
No.  Name/Role Name               Definition                                                                                                     Condition/ Obligation     Max. Occurrence  Data Type                           Domain
===  ===========================  =============================================================================================================  ========================  ===============  ==================================  ===============================
950  DP_Term                      Container for the description of terms used to express the parameter                                           Note 1                    Note 2           Class <<DataType>>                  Lines 951-954
951  term                         Word used to describe a thing or express a concept related to data parameter                                   M                         1                CharacterString                     FreeText
952  type                         Type of term (from codelist)                                                                                   M                         1                CodeList                            DP_TypeCode
953  usedInDataset                Flag to indicate whether the parameter is used in the dataset                                                  M                         1                Boolean                                         
953  vocabularyRelationship       Information about relationship between this term and term or terms from a vocabulary                           O                         N                Class                               DP_VocabularyRelationship
954  localDefinition              Definition of the term if not available from a vocabulary service                                              O                         1                CharacterString                     FreeText
===  ===========================  =============================================================================================================  ========================  ===============  ==================================  ===============================

.. include:: ../common_notes.rst

.. index:: mcp:vocabularyTermURL
.. index:: mcp:vocabularyTermDefinitionURL
.. index:: mcp:vocabularyListURL
.. index:: mcp:vocabularyListVersion
.. index:: mcp:vocabularyListAuthority
.. index:: mcp:DP_VocabularyRelationship
.. index:: mcp:DP_RelationshipTypeCode  

===  ===========================  =============================================================================================================  ==============  ========  ==================================  ===============================
No.  Name/Role Name               Definition                                                                                                     Cond/ Oblig     Max. Occ  Data Type                           Domain
===  ===========================  =============================================================================================================  ==============  ========  ==================================  ===============================
960  DP_VocabularyRelationship    Container for the description of relationship between term and term or terms from a vocabulary                 Note 1          Note 2    Class <<DataType>>                  Lines 961-966
961  relationshipType             Type of relationship between term and vocabulary term (from skos)                                              M               1         CodeList                            DP_RelationshipTypeCode
962  vocabularyTermURL            URL of vocabulary term                                                                                         M               1         Class                               URL      
963  vocabularyTermDefinitionURL  URL identifying the definition of the vocabulary term                                                          O               1         Class                               URL      
964  vocabularyTermDefinition     Definition extracted from vocabularyTermDefinitionURL                                                          O               1         CharacterString                     FreeText 
965  vocabularyListURL            URL of the vocabulary service that provides vocabulary term at 962                                             M               1         Class                               URL         
966  vocabularyListVersion        Version of the vocabulary that provides vocabulary term at 962                                                 O               1         CharacterString                     FreeText
966  vocabularyListAuthority      Citation of authority regulating or managing vocabulary specified at 965                                       O               1         Class                               CI_Citation 
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
                <gco:CharacterString>t</gco:CharacterString> 
              </mcp:term> 
              <mcp:type>
                <mcp:DP_TypeCode 
            codeList="http://bluenet3.antcrc.utas.edu.au/mcp-1.4/resources/Codelist/gmxCodelists.xml#DP_TypeCode" 
            codeListValue="shortName">shortName</mcp:DP_TypeCode> 
              </mcp:type> 
              <mcp:usedInDataset>
                <gco:Boolean>1</gco:Boolean> 
              </mcp:usedInDataset>
              <mcp:vocabularyRelationship>
                <mcp:DP_VocabularyRelationship>
                  <mcp:relationshipType>
                    <mcp:DP_RelationshipTypeCode
            codeList="http://bluenet3.antcrc.utas.edu.au/mcp-1.4/resources/Codelist/gmxCodelists.xml#DP_RelationshipTypeCode" 
            codeListValue="skos:exactmatch">skos:exactmatch</mcp:DP_RelationshipTypeCode>
                  </mcp:relationshipType>
                  <mcp:vocabularyTermURL>
                   <gmd:URL>http://www.imos.org.au/vocabserver?code=temperature&vocab=oceanography</gmd:URL> 
                  </mcp:vocabularyTermURL> 
                  <mcp:vocabularyListURL>
                   <gmd:URL>http://www.imos.org.au/vocabserver?vocab=oceanography</gmd:URL> 
                  </mcp:vocabularyListURL> 
                  <mcp:vocabularyListVersion>
                    <gco:CharacterString>3.6</gco:CharacterString> 
                  </mcp:vocabularyListVersion> 
                </mcp:DP_VocabularyRelationship>
              </mcp:vocabularyRelationship>
            </mcp:DP_Term> 
          </mcp:parameterName> 
          <mcp:parameterUnit>
            <mcp:DP_Term>
              <mcp:term>
                <gco:CharacterString>degrees celsius</gco:CharacterString> 
              </mcp:term> 
              <mcp:type>
                <mcp:DP_TypeCode 
            codeList="http://bluenet3.antcrc.utas.edu.au/mcp-1.4/resources/Codelist/gmxCodelists.xml#DP_TypeCode"
            codeListValue="longName">longName</mcp:DP_TypeCode> 
              </mcp:type> 
              <mcp:usedInDataset>
                <gco:Boolean>1</gco:Boolean> 
              </mcp:usedInDataset> 
              <mcp:vocabularyRelationship>
                <mcp:DP_VocabularyRelationship>
                  <mcp:relationshipType>
                    <mcp:DP_RelationshipTypeCode
            codeList="http://bluenet3.antcrc.utas.edu.au/mcp-1.4/resources/Codelist/gmxCodelists.xml#DP_RelationshipTypeCode" 
            codeListValue="skos:exactmatch">skos:exactmatch</mcp:DP_RelationshipTypeCode>
                  </mcp:relationshipType>
                  <mcp:vocabularyTermURL>
                   <gmd:URL>http://www.imos.org.au/vocabserver?code=degreescelsius&vocab=oceanography_units</gmd:URL> 
                  </mcp:vocabularyTermURL> 
                  <mcp:vocabularyListURL>
                   <gmd:URL>http://www.imos.org.au/vocabserver?vocab=oceanography_units</gmd:URL> 
                  </mcp:vocabularyListURL> 
                  <mcp:vocabularyListVersion>
                    <gco:CharacterString>2.1</gco:CharacterString> 
                  </mcp:vocabularyListVersion> 
                </mcp:DP_VocabularyRelationship>
              </mcp:vocabularyRelationship>
            </mcp:DP_Term>
          </mcp:parameterUnit> 
          <mcp:parameterMinimumValue>
            <gco:CharacterString>2.1</gco:CharacterString> 
          </mcp:parameterMinimumValue> 
          <mcp:parameterMaximumValue>
            <gco:CharacterString>18.2</gco:CharacterString> 
          </mcp:parameterMaximumValue> 
          <mcp:parameterDescription>
            <gco:CharacterString>The temperature observed by the CTD on its depth profile</gco:CharacterString> 
          </mcp:parameterDescription> 
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

- **Proposer**: AODN (Kim Finney, Craig Jones et al)
- **Date proposed**: March 2013
- **Date accepted by MCP Governance Committee**: Not yet accepted
- **MCP Version**: 1.5 onwards
- **Brief decription of changes**: Move from describing parameter names and units to parameter terms where terms relate not just to parameter names and unit names, but platforms, analysis methods, instruments etc). Added mcp:vocabularyTermURL, mcp:vocabularyTermDefinitionURL, mcp:vocabularyRelationship, mcp:DP_VocabularyRelationship, mcp:parameterDeterminationInstrument, mcp:parameterAnalysisMethod, mcp:platform - to provide more information about platform, analysis methods and instruments used for data parameters and explicit links to vocabulary and vocabulary of definitions

