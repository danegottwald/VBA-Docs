---
title: Application.DeleteReportControl method (Access)
keywords: vbaac10.chm12523
f1_keywords:
- vbaac10.chm12523
ms.prod: access
api_name:
- Access.Application.DeleteReportControl
ms.assetid: 26e30033-ab56-9cfa-3c35-f6d47caf8bd7
ms.date: 02/05/2019
ms.localizationpriority: medium
---


# Application.DeleteReportControl method (Access)

The **DeleteReportControl** method deletes a specified control from a report.


## Syntax

_expression_.**DeleteReportControl** (_ReportName_, _ControlName_)

_expression_ A variable that represents an **[Application](Access.Application.md)** object.


## Parameters

|Name|Required/Optional|Data type|Description|
|:-----|:-----|:-----|:-----|
| _ReportName_|Required|**String**|The name of the report containing the control that you want to delete.|
| _ControlName_|Required|**String**|The name of the control that you want to delete.|

## Return value

Nothing


## Remarks

The **DeleteReportControl** method is available only in form Design view or report Design view, respectively.

> [!NOTE] 
> If you are building a wizard that deletes a control from a form or report, your wizard must open the form or report in Design view before it can delete the control.


## Example

The following example creates a form with a command button and displays a message that asks if the user wants to delete the command button. If the user chooses **Yes**, the command button is deleted.

```vb
Sub DeleteCommandButton() 
 Dim frm As Form, ctlNew As Control 
 Dim strMsg As String, intResponse As Integer, _ 
 intDialog As Integer 
 
 ' Create new form and get pointer to it. 
 Set frm = CreateForm 
 ' Create new command button. 
 Set ctlNew = CreateControl(frm.Name, acCommandButton) 
 ' Restore form. 
 DoCmd.Restore 
 ' Set caption. 
 ctlNew.Caption = "New Command Button" 
 ' Size control. 
 ctlNew.SizeToFit 
 ' Prompt user to delete control. 
 strMsg = "About to delete " & ctlNew.Name &". Continue?" 
 ' Define buttons to be displayed in dialog box. 
 intDialog = vbYesNo + vbCritical + vbDefaultButton2 
 intResponse = MsgBox(strMsg, intDialog) 
 If intResponse = vbYes Then 
 ' Delete control. 
 DeleteControl frm.Name, ctlNew.Name 
 End If 
End Sub
```



[!include[Support and feedback](~/includes/feedback-boilerplate.md)]