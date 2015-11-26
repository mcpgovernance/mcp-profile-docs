.. _introduction:

Introduction
============

.. index:: type 1 and type 2 profiles of ISO19115

The MCP is a `type 2` profile of :term:`ISO19115` implemented in :term:`XML` using :term:`ISO19139`. This means that:

#. Any element of ISO19115 can be used in the MCP
#. New elements have been added using the approved extension procedures for ISO19115 and the XML implementation of ISO19139
#. Controlled vocabularies for certain metadata elements (also known as code lists) and rules for validating metadata records from ISO19115 have been extended and new controlled vocabularies and rules for checking validity have been added

`Type 1` profiles of :term:`ISO19115` are simpler than `type 2` profiles because they do not add new elements. Examples of `type 1` profiles are the ANZLIC Metadata profile and the WMO (World Meteorological Organisation) profile version 1.2.

XML Fragments
-------------

This manual uses fragments of XML to describe the MCP. Some familiarity with the following XML concepts is required:

- namespaces
- elements and attributes
- schemas

The basic concepts and ideas behind XML can be found at http://www.w3schools.com/xml and other places on the internet. 

For brevity and to help understanding, fragments of XML will be written as follows:

- using a different font and background
- indented where possible to help reading 
- where an XML element, including the start tag, end tag and content, is too long to show on a single line, it shall break across more than one line automatically
- content not relevant to the purpose of the fragment will be replaced by an ellipsis (...)

XML Conventions
---------------

These conventions reuse and extend the conventions set out in the 
`WMO Core Metadata Profile v1-2 Manual <http://wis.wmo.int/2010/metadata/version_1-2/>`_ by Jeremy Tandy. The conventions are as follows:

- The schema documents (see :term:`XSD`) and codelists for the Marine Community Profile extend those used for ISO19139 and ISO19136. They are available online at http://schemas.aodn.org.au/mcp-2.0.
- The schema documents for ISO19139 are included with the MCP schema documents. They are also available from the `ISO TC211 website <http:///www.isotc211.org/2005>`_ (see also :term:`ISO TC211`). 
- A number of different namespaces are used to separate metadata elements into packages for easier management or to include XML implementations of other standards such as GML. The result is that an MCP metadata record will incorporate multiple namespaces as follows:

 - The namespace identifier for mcp shall be: http://schemas.aodn.org.au/mcp-2.0
 - The namespace identifier for dwc shall be: http://rs.tdwg.org/dwc/terms/ 
 - The namespace identifier for gmd shall be: http://www.isotc211.org/2005/gmd
 - The namespace identifier for gco shall be: http://www.isotc211.org/2005/gco
 - The namespace identifier for gmx shall be: http://www.isotc211.org/2005/gmx
 - The namespace identifier for gml shall be: http://www.opengis.net/gml
 - The namespace identifier for xlink shall be: http://www.w3.org/1999/xlink
 - The namespace identifier for xsi shall be: http://www.w3.org/2001/XMLSchema-instance

- The root element when shown shall be mcp:MD_Metadata
- The root element should have an attribute called xsi:schemaLocation which contains a value or set of values hinting at the physical location of schemas which may be used for validation. Since this attribute provides only a hint validating parsers are allowed to ignore it and use other means of locating the relevant schemas.
- An example of the complete namespace declaration for an MCP metadata record is:

::

 <mcp:MD_Metadata 
  xmlns:mcp="http://schemas.aodn.org.au/mcp-2.0"
  xmlns:dwc="http://rs.tdwg.org/dwc/terms/"
  xmlns:gmd="http://www.isotc211.org/2005/gmd"
  xmlns:gco="http://www.isotc211.org/2005/gco"
  xmlns:gml="http://www.opengis.net/gml"
  xmlns:gmx="http://www.isotc211.org/2005/gmx"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xmlns:xlink="http://www.w3.org/1999/xlink"
  gco:isoType="gmd:MD_Metadata"
  xsi:schemaLocation="
    http://schemas.aodn.org.au/mcp-2.0 
    http://schemas.aodn.org.au/mcp-2.0/schema.xsd 
    http://www.isotc211.org/2005/gmx
    http://www.isotc211.org/2005/gmx/gmx.xsd">
   (...)
 </mcp:MD_Metadata>

*Example of complete namespace declaration for an MCP metadata record*

.. index:: namespaces with prefixes are recommended and preferred

.. note:: The example of the complete namespace declaration of an MCP metadata record shown above has explicit namespace prefixes for each namespace used in the document. This is the recommended and preferred practice for MCP metadata records.

- Codelist elements from the mcp namespace should use the appropriate URL for the codeList attribute. For mcp elements the codelist URL is http://schemas.aodn.org.au/mcp-2.0/schema/resources/Codelist/gmxCodelists.xml. The name of the codelist element should be attached to the URL. For example, for the codelist element, mcp:MD_TemporalAggregationUnitCode, the codelist URL must be: http://schemas.aodn.org.au/mcp-2.0/schema/resources/Codelist/gmxCodelists.xml#MD_TemporalAggregationUnitCode. An example of a codelist element from an MCP metadata record is:

::
 
 <mcp:MD_TemporalAggregationUnitCode 
    codeList="http://schemas.aodn.org.au/mcp-2.0/schema/resources/Codelist/gmxCodelists.xml#MD_TemporalAggregationUnitCode"
    codeListValue="multi-day">multi-day</mcp:MD_TemporalAggregationUnitCode>

*Example of a codelist element from an MCP 2.0 metadata record*

- Codelist elements from other namespaces such as those with the gmd prefix can use either the mcp codelist URL http://schemas.aodn.org.au/mcp-2.0/schema/resources/Codelist/gmxCodelists.xml or one of the official ISO19115/19139 codelist URLs: http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO_19139_Schemas/resources/codelist/ML_gmxCodelists.xml. It is preferable to use the official ISO19115/19139 codelist URL.

MCP XML Schemas (XSDs)
----------------------

.. index:: Schema XSDs for the MCP

The schema documents (see :term:`XSD`) and codelists for the Marine Community Profile are available online at http://schemas.aodn.org.au/mcp-2.0.

As the MCP is under development and contributing organisations develop and change metadata elements, code lists and content rules, an experimental version of the MCP exists at http://schemas.aodn.org.au/mcp-2.1-experimental.

MCP Implementations
-------------------

The following versions of the MCP have been implemented as plugin metadata schemas for version 2.8.x of GeoNetwork opensource (see :term:`GeoNetwork`):

- Version 2.0 (described by this document) 
- Version 2.1 experimental (this document plus experimental extensions under development by users of the MCP) 
- Version 1.4  
- Version 1.5 experimental (=1.4 + experimental extensions) 

.. index:: Implementations of the MCP, GeoNetwork 2.8.x (ANZMEST)

You can obtain a complete release of GeoNetwork version 2.8 with the MCP configured and ready to use in the ANZMEST package of GeoNetwork 2.8 for AU/NZ users at http://anzlicmet.bluenet.utas.edu.au.
