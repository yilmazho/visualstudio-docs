---
title: "Compiler Error CS1733"
ms.custom: na
ms.date: "10/13/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CS1733"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1733"
ms.assetid: 2188aabe-404d-4a95-a11a-736dbd848508
caps.latest.revision: 8
ms.author: "billchi"
manager: "douge"
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
# Compiler Error CS1733
Expected expression.  
  
 This error is produced whenever the compiler is expecting an expression on the line where the error occurred. In the following example, the trailing comma in the initializer indicates to the compiler that another expression will follow.  
  
### To correct this error  
  
-   Provide the missing expression.  
  
-   Remove the tokens that are causing the compiler to expect an expression.  
  
## Example  
 The following example produces CS1733 because of the trailing comma:  
  
```  
// cs1733.cs  
using System.Collections.Generic;  
public class Test  
{  
    public static void Main()  
    {  
        List<int> list = new List<int>() {{ 1, 2, }};// CS1733  
    }      
}  
```