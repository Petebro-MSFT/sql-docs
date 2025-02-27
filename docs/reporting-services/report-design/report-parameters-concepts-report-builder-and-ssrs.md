---
title: "Report parameters concepts in paginated reports | Microsoft Docs"
description: Find out how to add parameters to link related paginated reports, to control a report appearance, to filter report data, or to narrow the scope in Report Builder. 
ms.date: 03/01/2017
ms.service: reporting-services
ms.subservice: report-design


ms.topic: conceptual
ms.assetid: b0aa2159-4e49-4713-8824-5ef9a9edbc62
author: maggiesMSFT
ms.author: maggies
---
# Report parameters concepts in paginated reports (Report Builder)

[!INCLUDE[ssrs-appliesto](../../includes/ssrs-appliesto.md)] [!INCLUDE [ssrs-appliesto-ssrs-rb](../../includes/ssrs-appliesto-ssrs-rb.md)] [!INCLUDE [ssrs-appliesto-pbi-rb](../../includes/ssrs-appliesto-pbi-rb.md)] [!INCLUDE [ssrb-applies-to-ssdt-yes](../../includes/ssrb-applies-to-ssdt-yes.md)]

  You can add parameters to a paginated report to link related reports, to control the report appearance, to filter report data, or to narrow the scope of a report to specific users or locations.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 Report parameters are created in the following ways:  
  
-   Automatically, when you define dataset query that contains query variables. For each query variable, a corresponding dataset query parameter and report parameter with the same names are created. A query parameter can be a reference to a query variable or to an input parameter for a stored procedure.  
  
-   Automatically, when you add a reference to a shared dataset that contains query parameters.  
  
-   Manually, when you create report parameters in the Report Data pane. Parameters are one of the built-in collections that you can include in an expression in a report. Because expressions are used to define values throughout a report definition, you can use parameters to control report appearance or to pass values to related subreports or reports that also use parameters.  
  
 For more information, see [Report Parameters &#40;Report Builder and Report Designer&#41;](../../reporting-services/report-design/report-parameters-report-builder-and-report-designer.md).  
  
 Parameters are frequently used to filter report data both before and after the data is returned to the report. For more information, see [Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](../../reporting-services/report-design/filter-group-and-sort-data-report-builder-and-ssrs.md).  
  
 When you design a report, report parameters are saved in the report definition. When you publish a report, report parameters are saved and managed separately from the report definition. After you save the report to the report server, you can do the following:  
  
-   Change report parameter values directly on the report server independently from the report definition.  
  
-   Create multiple linked reports in which each linked report is a link to the report definition with a separate set of parameter values that can be managed independently on the report server.  
  
 If you plan to create report snapshots, histories, or subscriptions to a published report, you must understand how report parameters affect the design requirements for the report.  
  
## See Also  
 [Reporting Services Concepts (SSRS)](../reporting-services-concepts-ssrs.md)
 [Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](../../reporting-services/report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)   
 [Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../../reporting-services/tutorial-add-a-parameter-to-your-report-report-builder.md)  
  
  
