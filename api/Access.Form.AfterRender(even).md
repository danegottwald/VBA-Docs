---
title: Form.AfterRender event (Access)
keywords: vbaac10.chm13680
f1_keywords:
- vbaac10.chm13680
ms.prod: access
api_name:
- Access.Form.AfterRender
ms.assetid: 3232d72f-4dd4-9797-d9cb-5ac616c68c71
ms.date: 03/08/2019
ms.localizationpriority: medium
---


# Form.AfterRender event (Access)

Occurs after the object represented by the _chartObject_ argument has been rendered.


## Syntax

_expression_.**AfterRender** (_drawObject_, _chartObject_)

_expression_ A variable that represents a **[Form](Access.Form.md)** object.


## Parameters

|Name|Required/Optional|Data type|Description|
|:-----|:-----|:-----|:-----|
| _drawObject_|Required|**Object**|A **ChChartDraw** object. Use the methods and properties of this object to draw objects on the chart.|
| _chartObject_|Required|**Object**|The object that has just been rendered. Use the **TypeName** function to determine what type of object has just been rendered.|

## Return value

Nothing


## Example

The following example demonstrates the syntax for a subroutine that traps the **AfterRender** event.

```vb
Private Sub Form_AfterRender( _ 
 ByVal drawObject As Object, ByVal chartObject As Object) 
 MsgBox TypeName(chartObject) & " has been rendered." 
End Sub
```




[!include[Support and feedback](~/includes/feedback-boilerplate.md)]