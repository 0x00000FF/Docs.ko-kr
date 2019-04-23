---
title: Visual Basic의 Me, My, MyBase 및 MyClass
ms.date: 07/20/2015
f1_keywords:
- MyClass
- vb.Me
- MyBase
- vb.MyBase
- Me
- vb.MyClass
- vb.This
- vb.My
helpviewer_keywords:
- My object
- self-reference [Visual Basic], Me keyword
- MyClass keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], referring to the current instance of an object
- Me keyword [Visual Basic]
- self-reference
- current instance [Visual Basic], Me keyword
- MyBase keyword [Visual Basic], relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
ms.openlocfilehash: a8df6e48fd5bce9bb28d8aef7e031f36741ad0ad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58813394"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Visual Basic의 Me, My, MyBase 및 MyClass
`Me`를 `My`, `MyBase`, 및 `MyClass` Visual Basic에는 비슷한 이름 이지만 다른 목적으로 합니다. 이 항목에서는 구별할 수 있도록 이러한 각 엔터티를 설명 합니다.  
  
## <a name="me"></a>Me  
 `Me` 키워드를 클래스 또는 구조 코드는 현재 실행 중인 특정 인스턴스를 참조할 수 있습니다. `Me` 개체 변수 또는 현재 인스턴스를 참조 하는 구조 변수 처럼 동작 합니다. 사용 하 여 `Me` 프로시저 다른 클래스, 구조체 또는 모듈에는 클래스 또는 구조체의 현재 실행 중인 인스턴스에 대 한 정보를 전달 하는 데 특히 유용 합니다.  
  
 예를 들어, 모듈의 다음 절차를 있다고 가정 합니다.  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 이 프로시저를 호출 하는의 현재 인스턴스를 전달 합니다 <xref:System.Windows.Forms.Form> 다음 문을 사용 하 여 인수로 클래스입니다.  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My  
 합니다 `My` 다양 한 쉽고 직관적인 액세스를 제공 하는 기능 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 클래스, Visual Basic 사용자의 컴퓨터, 응용 프로그램, 설정, 리소스 및 등을 사용 하 여 상호 작용 하도록 허용 합니다.  
  
## <a name="mybase"></a>MyBase  
 `MyBase` 키워드는 클래스의 현재 인스턴스의 기본 클래스를 참조 하는 개체 변수 처럼 동작 합니다. `MyBase` 파생된 클래스에서 섀도 처리 되거나 재정의 되는 기본 클래스 멤버 액세스를 주로 사용 됩니다. `MyBase.New` 파생된 클래스 생성자에서 기본 클래스 생성자를 명시적으로 호출 됩니다.  
  
## <a name="myclass"></a>MyClass  
 `MyClass` 키워드 원래 구현 된 클래스의 현재 인스턴스를 참조 하는 개체 변수 처럼 동작 합니다. `MyClass` 비슷합니다 `Me`, 되지만에 대 한 모든 메서드 호출이 메서드 것 처럼 처리 됩니다 `NotOverridable`합니다.  
  
## <a name="see-also"></a>참고자료

- [상속 기본 사항](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
