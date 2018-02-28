---
title: "XML 문서 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ea67841e44d8d88d2effec92eb1668142c1510f2
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="xml-document-creation"></a>XML 문서 만들기
XML 문서를 만드는 방법에는 두 가지가 있습니다. 하나는 매개 변수 없이 **XmlDocument**를 만드는 방법이고 다른 방법은 **XmlDocument**를 만들어 XmlNameTable를 매개 변수로 전달하는 것입니다. 다음 예제에서는 매개 변수를 사용하지 않고 비어 있는 새 **XmlDocument**를 만드는 방법을 보여줍니다.  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 문서를 만든 후에는 **Load** 메서드를 사용하여 문자열, 스트림, URL, 텍스트 판독기 또는 **XmlReader** 파생 클래스의 데이터와 함께 로드할 수 있습니다. 또한 문자열에서 XML을 읽는 **LoadXML** 메서드라는 다른 로드 메서드도 있습니다. 다양한 **Load** 메서드에 대한 자세한 내용은 [DOM에 XML 문서 읽어오기](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md)를 참조하세요.  
  
 **XmlNameTable**이라는 클래스가 있습니다. 이 클래스는 원자화된 문자열 개체를 포함하는 테이블입니다. 이 테이블을 사용하면 XML 파서에서 쉽게 XML 문서의 반복되는 모든 요소 및 특성 이름에 같은 문자열 개체를 사용할 수 있습니다. **XmlNameTable**은 문서가 생성될 때 위와 같이 자동으로 생성되며 문서가 로드되면 특성 및 요소 이름과 함께 로드됩니다. 이름 테이블이 포함된 문서가 이미 있고 해당 이름이 다른 문서에도 유용하다면 **XmlNameTable**이 매개 변수인 **Load** 메서드를 사용하여 새 문서를 만들 수 있습니다. 이 메서드로 문서를 만들면 해당 문서는 다른 문서의 모든 특성 및 요소를 이미 로드한 기존의 **XmlNameTable**을 사용합니다. 이를 사용하여 요소 및 특성 이름을 효율적으로 비교할 수 있습니다. **XmlNameTable**에 대한 자세한 내용은 [XmlNameTable을 사용한 개체 비교](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md)를 참조하세요. 참조에 대한 내용은 <xref:System.Xml.XmlNameTable>을 확인하세요.  
  
## <a name="see-also"></a>참고 항목  
 [XML DOM(문서 개체 모델)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
