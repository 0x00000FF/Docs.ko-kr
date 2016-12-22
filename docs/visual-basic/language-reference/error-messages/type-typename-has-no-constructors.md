---
title: "Type &#39;&lt;typename&gt;&#39; has no constructors | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30251"
  - "vbc30251"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30251"
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Type &#39;&lt;typename&gt;&#39; has no constructors
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

형식이 `Sub New()` 호출을 지원하지 않습니다.  컴파일러 또는 이진 파일이 손상되었기 때문일 수 있습니다.  
  
 **오류 ID:** BC30251  
  
### 이 오류를 해결하려면  
  
1.  형식이 다른 프로젝트 또는 참조되는 파일에 있으면 해당 프로젝트나 파일을 다시 설치합니다.  
  
2.  형식이 같은 프로젝트에 있으면 해당 형식이 포함된 어셈블리를 다시 컴파일합니다.  
  
3.  그래도 오류가 다시 발생하면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러를 다시 설치합니다.  
  
4.  오류가 계속 발생하면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.  
  
## 참고 항목  
 [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [의견 보내기](/visual-studio/ide/talk-to-us)