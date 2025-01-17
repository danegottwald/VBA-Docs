---
title: TextFrame2.AutoSize property (Office)
ms.prod: office
api_name:
- Office.TextFrame2.AutoSize
ms.assetid: f5d6da56-bd8a-2485-6176-1ddafb19629d
ms.date: 01/25/2019
ms.localizationpriority: medium
---


# TextFrame2.AutoSize property (Office)

Returns or sets a value that indicates whether the size of the specified shape is changed automatically to fit text within its boundaries. Read/write.


## Syntax

_expression_.**AutoSize**

_expression_ An expression that returns a **[TextFrame2](Office.TextFrame2.md)** object.


## Remarks

The value of the **AutoSize** property can be one of the following **[MsoAutoSize](office.msoautosize.md)** constants:

- **msoAutoSizeMixed**
- **msoAutoSizeNone**
- **msoAutoSizeShapeToFitText**
- **msoAutoSizeTextToFitShape**

## Example

The following code shows how to adjust the size of the title text on slide one to fit the text frame that contains it.


```vb
Dim pptSlide As Slide 
 Set pptSlide = ActivePresentation.Slides(1) 
With pptSlide.Shapes(1) 
 If .TextFrame2.TextRange.Characters.Count < 50 Then 
 .TextFrame2.AutoSize = msoAutoSizeTextToFitShape 
 End If 
End With
```


## See also

- [TextFrame2 object members](overview/Library-Reference/textframe2-members-office.md)



[!include[Support and feedback](~/includes/feedback-boilerplate.md)]