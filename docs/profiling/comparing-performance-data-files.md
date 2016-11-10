---
title: "Comparing Performance Data Files"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "profiling tools, comparing profiling tools report files"
  - "profiling tools reports, comparing"
ms.assetid: e6fda144-f21d-4912-9d16-1b8d3555a210
caps.latest.revision: 12
ms.author: "mikejo"
manager: "ghogen"
translation.priority.ht: 
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
translation.priority.mt: 
  - "cs-cz"
  - "pl-pl"
  - "pt-br"
  - "tr-tr"
---
# Comparing Performance Data Files
Profiling Tools data files comparison functionality allows you to select two report files (.VSP /or .VSPS) files and generate a report that shows the differences, performance regressions, and improvements that occurred from one profiling session to the other.  
  
 A comparison report of data files from [!INCLUDE[vsprvs](../codequality/includes/vsprvs_md.md)] Profiling Tools compares the results of an analysis in one profiling data file to the results of a baseline analysis in another data file. Both data files must have been generated by using the same profiling method. The report of the analyzed comparisons is saved as a .vsps file.  
  
 The comparison report view presents a table view of the changed data. The table presents the delta, or change from the baseline. The delta is calculated by determining the difference between the old value, the baseline value, and the result value from the new analysis.  
  
 Comparisons of profiler data can be based on the functions in the code, modules in the application, lines, instruction pointers (IPs), and types.  
  
 Profiling data that is available for comparison includes the information that is displayed in the columns. For definitions of these column names, see [Performance Report Views](../profiling/performance-report-views.md).  
  
 A threshold can be set to reduce noise and filter out any data in the comparison table view of the rows that have not changed by a specified amount.  
  
## In This Section  
 [How to: Compare Performance Data Files](../profiling/how-to--compare-performance-data-files.md)