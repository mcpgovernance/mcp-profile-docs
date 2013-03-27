.. _dataParameters:

Data Parameters (mcp:dataParameters)
====================================

Rationale
---------

ISO19115 has classes for describing the data parameters of coverages (continuously varying data usually represented by grids) and features (usually discrete data represented as points, lines and polygons etc) in the Content Information package (see section A.2.8 of the ISO19115 standard). However, the package does not provide:

- a simple, unified description of data parameters. The metadata author is forced instead to split the description of data parameters between a class for coverages and a separate, related standard for features (ISO19110)
- a simple way of handling the different aliases that often need to be described when entering metadata about data parameter names
- vocabulary support for looking up data parameter names where these names have been standardized

The intention of this new package is to address the first two shortcomings and provide a basis for the third (vocabulary support) when vocabulary services that provide these parameters are standardized and widely available.

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

===  ===================================  =======================================================================================================  ========================  ===============  ==================================  ===============================
No.  Name/Role Name                       Definition                                                                                               Condition/ Obligation     Max. Occurrence  Data Type                           Domain
===  ===================================  =======================================================================================================  ========================  ===============  ==================================  ===============================
940  DP_DataParameters                    Container for description of data set data parameters                                                    Note 1                    Note 2           Aggregated Class                    Line 68                        
941  DP_DataParameter                     Container for description of a data set parameter                                                        Note 1                    Note 2           Class                               Lines 942-949
942  parameterName                        Name of Parameter                                                                                        M                         N                Class                               DP_InfoType        
943  parameterUnits                       Units of Parameter                                                                                       M                         N                Class                               DP_InfoType        
944  parameterMinimumValue                Minimum Value of Parameter                                                                               O                         1                CharacterString                     FreeText
945  parameterMaximumValue                Maximum Value of Parameter                                                                               O                         1                CharacterString                     FreeText
946  parameterDescription                 Parameter Description                                                                                    O                         1                CharacterString                     FreeText
947  parameterDeterminationInstrument     Name and information about an instrument used in the determination of an observed or measured parameter  O                         N                Class                               DP_InfoType
948  parameterAnalysisMethod              Name and information about an analysis used in the determination of an observed or measured parameter    O                         N                Class                               DP_InfoType
949  platform                             Name and information about a platform used to observe or measure a parameter                             O                         N                Class                               DP_InfoType
===  ===================================  =======================================================================================================  ========================  ===============  ==================================  ===============================

.. include:: ../common_notes.rst

.. index:: mcp:name
.. index:: mcp:type
.. index:: mcp:vocabularyTermUrl
.. index:: mcp:vocabularyTermDefinitionUrl
.. index:: mcp:vocabularyListUrl
.. index:: mcp:vocabularyListVersion
.. index:: mcp:vocabularyListAuthority
.. index:: mcp:localDefinition
.. index:: mcp:DP_TypeCode

===  ===========================  ====================================================================================  ========================  ===============  ==================================  ===============================
No.  Name/Role Name               Definition                                                                            Condition/ Obligation     Max. Occurrence  Data Type                           Domain
===  ===========================  ====================================================================================  ========================  ===============  ==================================  ===============================
950  DP_InfoType                  Container for the description of terms used to express the parameter                  Note 1                    Note 2           Class <<DataType>>                  Lines 951-969
951  name                         Name of the term                                                                      M                         1                CharacterString                     FreeText
952  type                         Type of term                                                                          M                         1                CodeList                            DP_TypeCode
953  usedinDataset                Flag to indicate whether the parameter is used in the dataset                         M                         1                CodeList                            DP_TypeCode
954  vocabularyTermUrl            URL identifying the term in the vocabulary                                            C                         1                Class                               URL      
955  vocabularyTermDefinitionUrl  URL identifying the definiton in the vocabulary                                       O                         1                Class                               URL      
956  vocabularyListURL            URL of the vocabulary service that provides this term                                 O                         1                Class                               URL         
957  vocabularyListVersion        Version of the vocabulary that this term belongs to                                   O                         1                CharacterString                     FreeText
958  vocabularyListAuthority      Citation of authority regulating or managing vocabulary specified at 950              O                         1                Class                               CI_Citation 
959  localDefinition              Definition of the term if not available from a vocabulary service                     C                         1                CharacterString                     FreeText
===  ===========================  ====================================================================================  ========================  ===============  ==================================  ===============================

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
            <mcp:DP_ParameterName>
              <mcp:name>
                <gco:CharacterString>t</gco:CharacterString> 
              </mcp:name> 
              <mcp:type>
                <mcp:DP_TypeCode 
            codeList="http://bluenet3.antcrc.utas.edu.au/mcp-1.4/resources/Codelist/gmxCodelists.xml#DP_TypeCode" 
            codeListValue="shortName">shortName</mcp:DP_TypeCode> 
              </mcp:type> 
              <mcp:usedInDataset>
                <gco:Boolean>1</gco:Boolean> 
              </mcp:usedInDataset> 
              <mcp:vocabularyTermURL>
                <gmd:URL>http://www.imos.org.au/vocabserver?code=temperature&vocab=oceanography</gmd:URL> 
              </mcp:vocabularyListURL> 
              <mcp:vocabularyListURL>
                <gmd:URL>http://www.imos.org.au/vocabserver?vocab=oceanography</gmd:URL> 
              </mcp:vocabularyListURL> 
              <mcp:vocabularyListVersion>
                <gco:CharacterString>3.6</gco:CharacterString> 
              </mcp:vocabularyListVersion> 
            </mcp:DP_ParameterName> 
          </mcp:parameterName> 
          <mcp:parameterUnit>
            <mcp:DP_ParameterUnit>
              <mcp:name>
                <gco:CharacterString>degrees celsius</gco:CharacterString> 
              </mcp:name> 
              <mcp:type>
                <mcp:DP_TypeCode 
            codeList="http://bluenet3.antcrc.utas.edu.au/mcp-1.4/resources/Codelist/gmxCodelists.xml#DP_TypeCode"
            codeListValue="longName">longName</mcp:DP_TypeCode> 
              </mcp:type> 
              <mcp:usedInDataset>
                <gco:Boolean>1</gco:Boolean> 
              </mcp:usedInDataset> 
              <mcp:localDefinition>
                <gco:CharacterString>Degrees celsius according to Anders Celsius ie. the scale is inverted with 0 indicating the boiling point of water and 100 representing the freezing point of water - its our local definition of degrees celsius</gco:CharacterString> 
              </mcp:vocabularyListVersion> 
            </mcp:DP_ParameterUnit>
          </mcp:parameterUnit> 
          <mcp:parameterMinimumValue>
            <gco:CharacterString>0.1</gco:CharacterString> 
          </mcp:parameterMinimumValue> 
          <mcp:parameterMaximumValue>
            <gco:CharacterString>22.5</gco:CharacterString> 
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

- **Proposer**: BlueNet Project (Kate Roberts)
- **Date proposed**: 2010
- **Date accepted by MCP Governance Committee**: 2010
- **MCP Version**: 1.4 onwards
- **Brief decription of changes**: Original proposal

- **Proposer**: AODN (Kim Finney, Craig Jones et al)
- **Date proposed**: March 2013
- **Date accepted by MCP Governance Committee**: 2010
- **MCP Version**: 1.5 onwards
- **Brief decription of changes**: Added mcp:vocabularyTermUrl, mcp:vocabularyTermDefinitionUrl, mcp:parameterDeterminationInstrument, mcp:parameterAnalysisMethod, mcp:platform - to provide more information about platform, analysis methods and instruments used for data parameters and explicit links to vocabulary and vocabulary of definitions

