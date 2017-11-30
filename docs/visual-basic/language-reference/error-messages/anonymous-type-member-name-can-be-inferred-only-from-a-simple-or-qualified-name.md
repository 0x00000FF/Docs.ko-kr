---
title: "익명 형식 멤버 이름은 인수가 없는 단순한 이름 또는 정규화된 이름에서만 유추할 수 있습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36556
- bc36556
helpviewer_keywords: BC36556
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7068928a17ee5fdb7bf6b5e0a40aaa7e5ef32f11
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="anonymous-type-member-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>익명 형식 멤버 이름은 인수가 없는 단순한 이름 또는 정규화된 이름에서만 유추할 수 있습니다.
복잡 한 식은 익명 형식 멤버 이름을 유추할 수 없습니다.  
  
```vb  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 익명 형식 수 및 멤버 이름 및 형식을 유추할 수 없습니다.는 원본에 대 한 자세한 내용은 참조 [하는 방법: 익명 형식 선언에서 속성 이름 유추 및 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)합니다.  
  
 **오류 ID:** BC36556  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   다음 코드와 같이 식을 멤버 이름에 할당 합니다.  
  
    ```  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [방법: 익명 형식 선언에서 속성 이름 및 형식 유추](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
