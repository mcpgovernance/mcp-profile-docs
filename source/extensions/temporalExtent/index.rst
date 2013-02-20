.. _temporalExtent:

Temporal Extent (mcp:EX_TemporalExtent)
=======================================

Rationale
---------

ISO19115 has a temporal extent to describe a time period which is most often applied to the resource or subject of the metadata record. However, the temporal extent does not include a description of the temporal currency or aggregation in use. The intention of these new classes is to fill this gap.

UML
---

.. image:: EX_TemporalExtent_uml.png

*UML Diagram of extended EX_TemporalExtent class*

Data Dictionary
---------------

This table makes use of lines 350-351 from table B.3.1.2 (Temporal extent information) in the ISO19115 standard. Lines 920 onwards are new elements from the MCP.

.. index:: mcp:currency
.. index:: mcp:temporalAggregation
.. index:: mcp:TemporalAggregationUnitCode

===  ===========================  ====================================================================================  ========================  ===============  ==================================  ==========================================
No.  Name/Role Name               Definition                                                                            Condition/Obligation      Max. Occurrence  Data Type                           Domain
===  ===========================  ====================================================================================  ========================  ===============  ==================================  ==========================================
350  EX_TemporalExtent            Time period covered by the content of the dataset or metadata subject                 Note 1                    Note 2           Aggregated Class (EX_Extent)        Lines 351 & 920-921             
351  extent                       Date and time for the content of the dataset or metadata subject                      M                         1                Class                               TM_Primitive (B.4.5) 
920  currency                     Temporal currency for the dataset or metadata subject                                 O                         1                Class                               :ref:`MD_CurrencyTypeCode` <<CodeList>>
921  temporalAggregation          Temporal aggregation for the dataset or metadata subject                              O                         1                Class                               :ref:`MD_TemporalAggregationUnitCode` <<CodeList>
===  ===========================  ====================================================================================  ========================  ===============  ==================================  ==========================================

XML Example
-----------

An XML fragment showing an example of the mcp:EX_TemporalExtent element.

::

  <gmd:temporalElement>
    <mcp:EX_TemporalExtent gco:isoType="gmd:EX_TemporalExtent">
      <gmd:extent>
        <gml:TimePeriod gml:id="N10315">
          <gml:begin>
            <gml:TimeInstant gml:id="N1031B">
              <gml:timePosition>2012-01-01T00:45:00</gml:timePosition>
            </gml:TimeInstant>
          </gml:begin>
          <gml:end>
            <gml:TimeInstant gml:id="N10326">
              <gml:timePosition>2012-01-28T03:30:00</gml:timePosition>
            </gml:TimeInstant>
          </gml:end>
        </gml:TimePeriod>
      </gmd:extent>
      <mcp:currency>
        <mcp:MD_CurrencyTypeCode 
         codeList="http://bluenet3.antcrc.utas.edu.au/mcp-1.4/resources/Codelist/gmxCodelists.xml#MD_CurrencyTypeCode" 
         codeListValue="historical">historical</mcp:MD_CurrencyTypeCode>
      </mcp:currency>
      <mcp:temporalAggregation>
        <mcp:MD_TemporalAggregationUnitCode 
         codeList="http://bluenet3.antcrc.utas.edu.au/mcp-1.4/resources/Codelist/gmxCodelists.xml#MD_TemporalAggregationUnitCode" 
         codeListValue="week">week</mcp:MD_TemporalAggregationUnitCode>
      </mcp:temporalAggregation>
    </mcp:EX_TemporalExtent>
  </gmd:temporalElement> 

Metadata about this element
---------------------------

- **Proposer**: AODCJF Technical Committee
- **Date proposed**: 2006
- **Date accepted by MCP Governance Committee**: 2010
- **MCP Version**: 1.2 onwards

