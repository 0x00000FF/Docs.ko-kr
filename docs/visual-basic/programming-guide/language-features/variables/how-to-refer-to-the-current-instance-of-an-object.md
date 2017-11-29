---
title: "방법: 개체의 현재 인스턴스 참조(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 33ea612253b00e12f47258189da4ac7d8d98ade5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a>방법: 개체의 현재 인스턴스 참조(Visual Basic)
*현재 인스턴스가* 는 코드가 현재 실행 중인 개체입니다.  
  
 사용 된 `Me` 키워드를 현재 인스턴스를 참조 합니다.  
  
### <a name="to-refer-to-the-current-instance"></a>현재 인스턴스 참조 하려면  
  
-   사용 하 여는 `Me` 키워드 일반적으로 사용 되는 개체 변수의 이름입니다.  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     하지만 `Me` 개체 처럼 동작 변수를 선언할 수 없거나 값을 할당할 합니다. `Me`항상 현재 인스턴스를 참조 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [개체 변수](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [개체 변수 할당](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [Me, My, MyBase 및 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
