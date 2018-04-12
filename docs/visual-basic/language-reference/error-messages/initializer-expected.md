---
title: 이니셜라이저가 필요합니다.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 46ff91ec240212571f7ec9f26e82d9d128263545
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="initializer-expected"></a>이니셜라이저가 필요합니다.
초기화 목록의 비어 있는 경우 다음 예제와 같이 개체 이니셜라이저를 사용 하 여 클래스의 인스턴스를 선언 하려고 했습니다.  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 다음 예제와 같이 이니셜라이저 목록에서 하나 이상의 필드 또는 속성 초기화 되어야 합니다.  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 **오류 ID:** BC30996  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  하나 이상의 필드 또는 이니셜라이저의 속성을 초기화 하거나 개체 이니셜라이저를 사용 하지 마십시오.  
  
## <a name="see-also"></a>참고 항목  
 [개체 이니셜라이저: 명명된 형식과 익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [방법: 개체 이니셜라이저를 사용하여 개체 선언](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
