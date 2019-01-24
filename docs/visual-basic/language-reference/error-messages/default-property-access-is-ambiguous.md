---
title: 기본 속성 액세스가 상속 된 인터페이스 멤버 사이 모호 &#39; &lt;defaultpropertyname&gt; &#39; 인터페이스 &#39; &lt;interfacename1&gt; &#39; 및 &#39; &lt;defaultpropertyname&gt; &#39; 인터페이스의 &#39; &lt;interfacename2&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: 1fae63506a35eb046676214a2b6c52977f24645d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518646"
---
# <a name="default-property-access-is-ambiguous-between-the-inherited-interface-members-39ltdefaultpropertynamegt39-of-interface-39ltinterfacename1gt39-and-39ltdefaultpropertynamegt39-of-interface-39ltinterfacename2gt39"></a>기본 속성 액세스가 상속 된 인터페이스 멤버 사이 모호 &#39; &lt;defaultpropertyname&gt; &#39; 인터페이스 &#39; &lt;interfacename1&gt; &#39; 및 &#39; &lt;defaultpropertyname&gt; &#39; 인터페이스의 &#39; &lt;interfacename2&gt;&#39;
인터페이스는 각각 같은 이름의 기본 속성을 선언 하는 두 인터페이스에서 상속 됩니다. 컴파일러는 한정자 없이이 기본 속성에 대 한 액세스를 확인할 수 없습니다. 다음은 이에 대한 예입니다.  
  
```  
Public Interface Iface1  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface2  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface3  
    Inherits Iface1, Iface2  
End Interface  
Public Class testClass  
    Public Sub accessDefaultProperty()  
        Dim testObj As Iface3  
        Dim testInt As Integer = testObj(1)  
    End Sub  
End Class  
```  
  
 지정 하는 경우 `testObj(1)`, 컴파일러에서 기본 속성을 확인 하려고 합니다. 그러나 두 가지 가능한 기본 속성 상속 된 인터페이스 때문 하므로 컴파일러가이 오류를 알립니다.  
  
 **오류 ID:** BC30686  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   동일한 이름 가진 모든 멤버를 상속 하지 않습니다. 앞의 예제에서 경우 `testObj` 의 멤버는 필요 하지 않습니다 예를 들어, `Iface2`를 다음과 같이 선언 합니다.  
  
    ```  
    Dim testObj As Iface1  
    ```  
  
     또는  
  
-   클래스에서 상속 하는 인터페이스를 구현 합니다. 그런 다음 각 다른 이름의 상속 된 속성을 구현할 수 있습니다. 그러나 그 중 하나만 구현 하는 클래스의 기본 속성을 수 있습니다. 다음은 이에 대한 예입니다.  
  
    ```  
    Public Class useIface3  
        Implements Iface3  
        Default Public Property prop1(ByVal arg As Integer) As Integer Implements Iface1.prop  
            ' Insert code to define Get and Set procedures for prop1.  
        End Property  
        Public Property prop2(ByVal arg As Integer) As Integer Implements Iface2.prop  
            ' Insert code to define Get and Set procedures for prop2.  
        End Property  
    End Class  
    ```  
  
## <a name="see-also"></a>참고자료
- [인터페이스](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
