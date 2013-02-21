.. _MD_Commons:

Commons Licensing Constraints (mcp:MD_Commons)
==============================================

Rationale
---------

ISO19115 has a number of constraint classes that can be used to describe rights to information and restrictions on access and use: MD_Security, MD_LegalConstraints (see section A.2.3 of the ISO19115 standard for details). However, the majority of the elements used in these classes are free text and there are no specific elements that can be used to handle licenses that are delivered and described on the internet. The intention of these new classes is to fill this gap by providing purpose built elements that describe both the internet delivered licenses and any additional constraints that the common forms of these licenses may require (eg. attribution constraints).

UML
---

.. image:: MD_Commons_uml.png

*UML Diagram of MD_Commons class*

Data Dictionary
---------------

This table makes use of lines 67-68 from table B.2.3 (Constraint information) in the ISO19115 standard. Lines 901 onwards are new elements from the MCP.

.. index:: mcp:MD_Commons
.. index:: mcp:jurisdictionLink
.. index:: mcp:licenseLink
.. index:: mcp:imageLink
.. index:: mcp:licenseName
.. index:: mcp:attributionConstraints
.. index:: mcp:derivativeConstraints
.. index:: mcp:collectiveWorksConstraints
.. index:: mcp:otherConstraints
.. index:: mcp:commonsType

===  ===========================  ====================================================================================  ========================  ===============  ==================================  ===============================
No.  Name/Role Name               Definition                                                                            Condition/ Obligation     Max. Occurrence  Data Type                           Domain
===  ===========================  ====================================================================================  ========================  ===============  ==================================  ===============================
67   MD_Constraints               Restrictions on the access and use of a resource or metadata                          Note 1                    Note 2           Aggregated Class                    Line 68                        
68   useLimitation                Limitation affecting fitness for use of the resource or metadata                      O                         N                CharacterString                     FreeText
901  MD_Commons                   Commons license restrictions on resource or metadata                                  Note 1                    Note 2           Specified Class (MD_Constraints)    Lines 902-911 and 68
902  jurisdictionLink             Link to licensing jurisdiction information                                            M                         1                Class                               URL                
903  licenseLink                  Link to licensing information                                                         M                         1                Class                               URL                
904  imageLink                    Link to visual license representation (as image)                                      M                         1                Class                               URL                
905  licenseName                  Name of the license                                                                   M                         1                CharacterString                     FreeText
906  attributionConstraints       How, when and who resource or metadata should be attributed to                        O                         N                CharacterString                     FreeText
907  derivativeConstraints        Constraints on products that may be derived from resource or metadata                 O                         N                CharacterString                     FreeText
908  commercialUseConstraints     Constraints on making use of resource or metadata commercially                        O                         N                CharacterString                     FreeText
909  collectiveWorksConstraints   Constraints on including this resource or metadata in a collective work               O                         N                CharacterString                     FreeText
910  otherConstraints             Any other constraint not captured specific constraint fields                          O                         N                CharacterString                     FreeText
911  commonsType                  Type of commons licensing scheme described                                            M                         1                Enumeration                         CommonsTypeCode <<Enumeration>>
===  ===========================  ====================================================================================  ========================  ===============  ==================================  ===============================

.. include:: ../common_notes.rst

XML Example
-----------

.. index:: Creative Commons example in mcp:MD_Commons

An XML example of a resource constraint that uses a Creative Commons license.

::
 
     <gmd:resourceConstraints>
        <mcp:MD_Commons mcp:commonsType="Creative Commons" gco:isoType="gmd:MD_Constraints">
            <gmd:useLimitation>
                <gco:CharacterString>The data used to test this vehicle 
        should not be used for navigation purposes</gco:CharacterString>
            </gmd:useLimitation>
            <mcp:jurisdictionLink>
                <gmd:URL>http://creativecommons.org/international/au/</gmd:URL>
            </mcp:jurisdictionLink>
            <mcp:licenseLink>
                <gmd:URL>http://creativecommons.org/licenses/by-sa/3.0/au/</gmd:URL>
            </mcp:licenseLink>
            <mcp:imageLink>
                <gmd:URL>http://i.creativecommons.org/l/by-sa/3.0/au/88x31.png</gmd:URL>
            </mcp:imageLink>
            <mcp:licenseName>
                <gco:CharacterString>Attribution-ShareAlike 3.0 Australia</gco:CharacterString>
            </mcp:licenseName>
            <mcp:attributionConstraints>
                <gco:CharacterString>Attribute as: Butte J, A horse drawn, 
        cabbage leaf powered, Marine bicycle, Heath Robinson Monthly,
        UK Oceanographics Inc</gco:CharacterString>
            </mcp:attributionConstraints>
            <mcp:otherConstraints>
                <gco:CharacterString>Note attribution and share alike
                      provisions of CC license</gco:CharacterString>
            </mcp:otherConstraints>
        </mcp:MD_Commons>
     </gmd:resourceConstraints>

Metadata about this element
---------------------------

- **Proposer**: BlueNet Project (Kate Roberts)
- **Date proposed**: 2010
- **Date accepted by MCP Governance Committee**: 2010
- **MCP Version**: 1.4 onwards

