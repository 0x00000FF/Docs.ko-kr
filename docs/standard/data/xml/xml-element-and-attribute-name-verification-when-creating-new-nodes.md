---
title: "새 노드를 만들 때 XML 요소 및 특성 이름 확인 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
caps.latest.revision: 5
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 5
---
# 새 노드를 만들 때 XML 요소 및 특성 이름 확인
XML DOM\(문서 개체 모델\)에서는 새 요소 노드나 특성 노드를 만들 때 해당 이름의 유효성을 확인합니다.  이름에 잘못된 문자가 있으면 예외가 throw됩니다.  이름이 유효하고 올바르게 인코딩되었는지 확인하려면 **XmlConvert** 클래스를 사용하여 이름을 인코딩한 다음 응용 프로그램 수준에서 다시 디코딩해야 합니다.  **XmlWriter**에는 추가 작업을 수행하여 제대로 구성된 XML이 만들어지는지 확인하는 메서드가 있습니다.  
  
## 참고 항목  
 [XML DOM\(문서 개체 모델\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)