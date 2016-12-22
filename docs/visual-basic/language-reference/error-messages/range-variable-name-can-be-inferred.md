---
title: "Range variable name can be inferred only from a simple or qualified name with no arguments | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc36599"
  - "bc36599"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36599"
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Range variable name can be inferred only from a simple or qualified name with no arguments
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

하나 이상의 인수를 사용하는 프로그래밍 요소가 LINQ 쿼리에 포함되었습니다.  컴파일러가 해당 프로그래밍 요소에서 범위 변수를 유추할 수 없습니다.  
  
 **오류 ID:** BC36599  
  
### 이 오류를 해결하려면  
  
1.  다음 코드와 같이 프로그래밍 요소에 명시적 변수 이름을 지정합니다.  
  
```  
Dim query = From var1 In collection1   
            Select VariableAlias = SampleFunction(var1), var1  
```  
  
## 참고 항목  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)