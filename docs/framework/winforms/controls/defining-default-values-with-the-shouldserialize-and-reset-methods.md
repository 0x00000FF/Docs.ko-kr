---
title: ShouldSerialize 및 Reset 메서드를 사용하여 기본값 정의
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property methods
- ShouldPersist method
ms.assetid: 7b6c5e00-3771-46b4-9142-5a80d5864a5e
ms.openlocfilehash: f1f5a668c5d4f52ef7dd9f60a31c04f2173165f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090617"
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a><span data-ttu-id="b78ce-102">ShouldSerialize 및 Reset 메서드를 사용하여 기본값 정의</span><span class="sxs-lookup"><span data-stu-id="b78ce-102">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>
<span data-ttu-id="b78ce-103">`ShouldSerialize` 및 `Reset` 가지가 선택적 속성에 대해 제공할 수 있는 속성에는 없는 경우는 간단한 기본 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b78ce-103">`ShouldSerialize` and `Reset` are optional methods that you can provide for a property, if the property does not a have simple default value.</span></span> <span data-ttu-id="b78ce-104">속성의 기본값에 하는 경우 적용 해야 합니다 <xref:System.ComponentModel.DefaultValueAttribute> 대신 특성 클래스 생성자에 기본값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b78ce-104">If the property has a simple default value, you should apply the <xref:System.ComponentModel.DefaultValueAttribute> and supply the default value to the attribute class constructor instead.</span></span> <span data-ttu-id="b78ce-105">이러한 메커니즘 중 하나는 디자이너에서 다음 기능을 사용할 수 있습니다:</span><span class="sxs-lookup"><span data-stu-id="b78ce-105">Either of these mechanisms enables the following features in the designer:</span></span>  
  
-   <span data-ttu-id="b78ce-106">속성이는 기본값에서 수정 된 경우 속성 브라우저에 시각적 표시를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b78ce-106">The property provides visual indication in the property browser if it has been modified from its default value.</span></span>  
  
-   <span data-ttu-id="b78ce-107">사용자 속성을 마우스 오른쪽 단추로 클릭 하 고 선택할 수 **재설정** 속성을 기본값으로 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b78ce-107">The user can right-click on the property and choose **Reset** to restore the property to its default value.</span></span>  
  
-   <span data-ttu-id="b78ce-108">디자이너는 더 효율적인 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b78ce-108">The designer generates more efficient code.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b78ce-109">적용 중 하나는 <xref:System.ComponentModel.DefaultValueAttribute> 바꾸거나 `Reset` *PropertyName* 및 `ShouldSerialize` *PropertyName* 메서드.</span><span class="sxs-lookup"><span data-stu-id="b78ce-109">Either apply the <xref:System.ComponentModel.DefaultValueAttribute> or provide `Reset`*PropertyName* and `ShouldSerialize`*PropertyName* methods.</span></span> <span data-ttu-id="b78ce-110">둘 다 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b78ce-110">Do not use both.</span></span>  
  
 <span data-ttu-id="b78ce-111">합니다 `Reset` *PropertyName* 메서드 다음 코드 조각에 표시 된 대로 속성을 해당 기본값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b78ce-111">The `Reset`*PropertyName* method sets a property to its default value, as shown in the following code fragment.</span></span>  
  
```vb  
Public Sub ResetMyFont()  
   MyFont = Nothing  
End Sub  
```  
  
```csharp  
public void ResetMyFont() {  
   MyFont = null;  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="b78ce-112">속성에 없는 경우를 `Reset` 메서드를 사용 하 여 표시 되지를 <xref:System.ComponentModel.DefaultValueAttribute>, 해당 선언에서 제공 되는 기본 값이 없는 `Reset` 바로 가기 메뉴에서는 해당 속성을 사용할 옵션는 **속성** Visual Studio에서 Windows Forms 디자이너의 창.</span><span class="sxs-lookup"><span data-stu-id="b78ce-112">If a property does not have a `Reset` method, is not marked with a <xref:System.ComponentModel.DefaultValueAttribute>, and does not have a default value supplied in its declaration, the `Reset` option for that property is disabled in the shortcut menu of the **Properties** window of the Windows Forms Designer in Visual Studio.</span></span>  
  
 <span data-ttu-id="b78ce-113">Visual Studio와 같은 디자이너를 사용 합니다 `ShouldSerialize` *PropertyName* 속성이 기본값에서 변경 되었는지 여부를 확인 하 고 속성을 경우에만 폼에 코드를 작성 방법 변경 되 면 되므로 보다 효율적인 코드 세대입니다.</span><span class="sxs-lookup"><span data-stu-id="b78ce-113">Designers such as Visual Studio use the `ShouldSerialize`*PropertyName* method to check whether a property has changed from its default value and write code into the form only if a property is changed, thus allowing for more efficient code generation.</span></span> <span data-ttu-id="b78ce-114">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="b78ce-114">For example:</span></span>  
  
```vb  
'Returns true if the font has changed; otherwise, returns false.  
' The designer writes code to the form only if true is returned.  
Public Function ShouldSerializeMyFont() As Boolean  
   Return Not (thefont Is Nothing)  
End Function  
```  
  
```csharp  
// Returns true if the font has changed; otherwise, returns false.  
// The designer writes code to the form only if true is returned.  
public bool ShouldSerializeMyFont() {  
   return thefont != null;  
}  
```  
  
 <span data-ttu-id="b78ce-115">전체 코드 예제와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b78ce-115">A complete code example follows.</span></span>  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.Windows.Forms  
Imports System.Drawing  
  
Public Class MyControl  
   Inherits Control  
  
   ' Declare an instance of the Font class  
   ' and set its default value to Nothing.  
   Private thefont As Font = Nothing  
  
   ' The MyFont property.   
   Public Property MyFont() As Font  
      ' Note that the Font property never  
      ' returns null.  
      Get  
         If Not (thefont Is Nothing) Then  
            Return thefont  
         End If  
         If Not (Parent Is Nothing) Then  
            Return Parent.Font  
         End If  
         Return Control.DefaultFont  
      End Get  
      Set  
         thefont = value  
      End Set  
   End Property  
  
   Public Function ShouldSerializeMyFont() As Boolean  
      Return Not (thefont Is Nothing)  
   End Function  
  
   Public Sub ResetMyFont()  
      MyFont = Nothing  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Windows.Forms;  
using System.Drawing;  
  
public class MyControl : Control {  
   // Declare an instance of the Font class  
   // and set its default value to null.  
   private Font thefont = null;  
  
   // The MyFont property.      
   public Font MyFont {  
      // Note that the MyFont property never  
      // returns null.  
      get {  
         if (thefont != null) return thefont;  
         if (Parent != null) return Parent.Font;  
         return Control.DefaultFont;  
      }  
      set {  
         thefont = value;  
      }  
   }  
  
   public bool ShouldSerializeMyFont() {  
      return thefont != null;  
   }  
  
   public void ResetMyFont() {  
      MyFont = null;  
   }  
}  
```  
  
 <span data-ttu-id="b78ce-116">개인 변수의 값으로 액세스 하는 경우에이 경우에서는 `MyFont` 속성은 `null`, 속성 브라우저에 표시 되지 `null`대신 표시 합니다 <xref:System.Windows.Forms.Control.Font%2A> 있지 않으면 부모 `null`, 또는 기본 <xref:System.Windows.Forms.Control.Font%2A> 에 정의 된 값 <xref:System.Windows.Forms.Control>합니다.</span><span class="sxs-lookup"><span data-stu-id="b78ce-116">In this case, even when the value of the private variable accessed by the `MyFont` property is `null`, the property browser does not display `null`; instead, it displays the <xref:System.Windows.Forms.Control.Font%2A> property of the parent, if it is not `null`, or the default <xref:System.Windows.Forms.Control.Font%2A> value defined in <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="b78ce-117">에 대 한 기본값에 따라서 `MyFont` 간단히 설정할 수 없습니다 및 <xref:System.ComponentModel.DefaultValueAttribute> 이 속성에 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b78ce-117">Thus the default value for `MyFont` cannot be simply set, and a <xref:System.ComponentModel.DefaultValueAttribute> cannot be applied to this property.</span></span> <span data-ttu-id="b78ce-118">대신 합니다 `ShouldSerialize` 및 `Reset` 에 대 한 메서드를 구현 해야 합니다 `MyFont` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b78ce-118">Instead, the `ShouldSerialize` and `Reset` methods must be implemented for the `MyFont` property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b78ce-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="b78ce-119">See also</span></span>

- [<span data-ttu-id="b78ce-120">Windows Forms 컨트롤의 속성</span><span class="sxs-lookup"><span data-stu-id="b78ce-120">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="b78ce-121">속성 정의</span><span class="sxs-lookup"><span data-stu-id="b78ce-121">Defining a Property</span></span>](defining-a-property-in-windows-forms-controls.md)
- [<span data-ttu-id="b78ce-122">속성 변경 이벤트</span><span class="sxs-lookup"><span data-stu-id="b78ce-122">Property-Changed Events</span></span>](property-changed-events.md)
