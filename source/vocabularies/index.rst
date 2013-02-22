.. _vocabularies:

Vocabularies used by the MCP
============================

Descriptive Keywords (gmd:keywords)
-----------------------------------

.. index:: gmd:keywords

The MCP mandates usage of the NASA Global Change Master Directory (GCMD) Science Keywords vocabulary for the descriptive keywords section of the MCP record. See http://gcmd.nasa.gov/Resources/valids/archives/keyword_list.html

Originally these keywords were only available as a web page or CSV document. More recently, these keywords have been made available through a specific web service, details of which are available at http://gcmd.gsfc.nasa.gov/Connect/docs/kms/KeywordManagementServiceAPI.pdf. 

Some implementations of the MCP still use a GCMD keyword 'picker' developed by the `Australian Institute of Marine Science <http://www.aims.gov.au>`_. Other implementations have moved to a :term:`SKOS` file developed from the keywords used in this GCMD keyword picker. 

Regardless of the method used to include GCMD science keywords in an MCP record, it is highly recommended that a description of the GCMD thesaurus used is included in the gmd:thesaurusName section of gmd:descriptiveKeywords with the following information:

- the version number of the GCMD keyword list used
- an online link to the GCMD science keyword list from which keywords have been chosen 
- a reference to the GCMD Science keyword authors (as suggested by NASA on http://gcmd.nasa.gov/Resources/valids/archives/keyword_list.html)

An example of how to do this is as follows:

::

  <gmd:descriptiveKeywords>
    <gmd:MD_Keywords>
       (...)
       <gmd:type>
         <gmd:MD_KeywordTypeCode codeList="http://bluenet3.antcrc.utas.edu.au/mcp-1.4/schema/resources/Codelist/gmxCodelists.xml#MD_KeywordTypeCode" codeListValue="discipline">discipline</gmd:MD_KeywordTypeCode>
        </gmd:type>
        <gmd:thesaurusName>
            <gmd:CI_Citation>
                <gmd:title>
                    <gco:CharacterString>Global Change Master Directory Earth Science Keywords</gco:CharacterString>
                </gmd:title>
                <gmd:date gco:nilReason="unknown"/>
                <gmd:edition>
                    <gco:CharacterString>bc44a748-f1a1-4775-9395-a4a6d8bb8df6:conceptscheme:GCMD Keywords, Version 5.3.8</gco:CharacterString>
                </gmd:edition>
                <gmd:editionDate gco:nilReason="unknown"/>
                <gmd:identifier>
                    <gmd:MD_Identifier>
                        <gmd:code>
                            <gmx:Anchor 
              xlink:href="http://yourgeonetwork.com/geonetwork/srv/en/?uuid=bc44a748-f1a1-4775-9395-a4a6d8bb8df6">
                geonetwork.thesaurus.register.discipline.bc44a748-f1a1-4775-9395-a4a6d8bb8df6</gmx:Anchor>
                        </gmd:code>
                    </gmd:MD_Identifier>
                </gmd:identifier>
                <gmd:otherCitationDetails>
                  <gco:CharacterString>Olsen, L.M., G. Major, K. Shein, 
                J. Scialdone, S. Ritz, T. Stevens, M. Morahan, A. Aleman, 
                R. Vogel, S. Leicester, H. Weir, M. Meaux, S. Grebas, 
                C.Solomon, M. Holland, T. Northcutt, R. A. Restrepo, 
                R. Bilodeau,2012. NASA/Global Change Master Directory (GCMD) 
                Earth Science Keywords</gco:CharacterString>
                </gmd:otherCitationDetails>
            </gmd:CI_Citation>
        </gmd:thesaurusName>
    </gmd:MD_Keywords>
  </gmd:descriptiveKeywords>

Geographic Extent Names
-----------------------

Geographic Extent Names for common Marine regions have been developed for the MCP by the AODCJF Technical Committee. Rather than reproduce that extent name list in this document an online link to the extent name list (in ISO19139 CT_CodelistCatalogue format) can be found `here <http://www.aodn.org.au/redmine/projects/mcp-governance/wiki/Documentation>`_.

Geographic Extent Names can be used in the following places in an MCP metadata record:

- 'Region' type keywords in gmd:descriptiveKeywords
- geographic identifiers in gmd:EX_GeographicDescription

Collection Method Vocabulary
----------------------------

A collection method vocabulary based on the NASA GCMD Instruments Keyword list (see http://gcmd.nasa.gov/Resources/valids/archives/keyword_list.html) is also suggested for use in MCP records.

.. note:: Usage of this vocabulary does not appear to be common in MCP implementations. Some additional work needs to be done to extract this list of instruments and produce a SKOS and/or ISO19139 CT_CodelistCatalog version that can be used by MCP implementations.
