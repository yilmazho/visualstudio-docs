---
title: "Expression Evaluator"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "expressions [Debugging SDK]"
  - "debugging [Debugging SDK], expression evaluation"
  - "expression evaluation"
ms.assetid: f9381b2f-99aa-426c-aea0-d9c15f3c859b
caps.latest.revision: 19
ms.author: "gregvanl"
manager: "ghogen"
translation.priority.mt: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# Expression Evaluator
Expression evaluators (EE) examine the syntax of a language to parse and evaluate variables and expressions at run time, allowing them to be viewed by the user when the IDE is in break mode.  
  
## Using Expression Evaluators  
 Expressions are created using the [ParseText](../extensibility/idebugexpressioncontext2--parsetext.md) method, as follows:  
  
1.  The debug engine (DE) implements the [IDebugExpressionContext2](../extensibility/idebugexpressioncontext2.md) interface.  
  
2.  The debug package gets an `IDebugExpressionContext2` object from an [IDebugStackFrame2](../extensibility/idebugstackframe2.md) interface and then calls the `IDebugStackFrame2::ParseText` method on it to get an [IDebugExpression2](../extensibility/idebugexpression2.md) object.  
  
3.  The debug package calls the [EvaluateSync](../extensibility/idebugexpression2--evaluatesync.md) method or the [EvaluateAsync](../extensibility/idebugexpression2--evaluateasync.md) method to get the value of the expression. `IDebugExpression2::EvaluateAsync` is called from the Command/Immediate window. All other UI components call `IDebugExpression2::EvaluateSync`.  
  
4.  The result of expression evaluation is an [IDebugProperty2](../extensibility/idebugproperty2.md) object, which contains the name, type, and value of the result of the expression evaluation.  
  
 During expression evaluation, the EE requires information from the symbol provider component. The symbol provider supplies the symbolic information used for identifying and understanding the parsed expression.  
  
 When asynchronous expression evaluation is complete, an asynchronous event is sent by the DE through the session debug manager (SDM) to notify the IDE that expression evaluation is complete. When synchronous expression evaluation is complete, the result of the evaluation is returned from the call to the `IDebugExpression2::EvaluateSync` method.  
  
## Implementation Notes  
 The [!INCLUDE[vsprvs](../codequality/includes/vsprvs_md.md)] debug engines expect to talk with the expression evaluator using Common Language Runtime (CLR) interfaces. As a result, an expression evaluator that works with the [!INCLUDE[vsprvs](../codequality/includes/vsprvs_md.md)] debug engines must support the CLR (a complete list of all CLR debugging interfaces can be found in debugref.doc, which is part of the [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]).  
  
## See Also  
 [Debugger Components](../extensibility/debugger-components.md)