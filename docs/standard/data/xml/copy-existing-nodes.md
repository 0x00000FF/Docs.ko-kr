---
title: "기존 노드 복사"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c026d9f825375d74d53d5cc46969ff0f713bab1c
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="copy-existing-nodes"></a>기존 노드 복사
XML DOM(문서 개체 모델)에는**SelectSingleNode**, **ChildNodes[int i]**, **Attributes[int i]** 등 노드를 선택하는 데 사용할 수 있는 여러 메서드와 속성이 있습니다. 노드를 선택하면 특정 노드 형식에 작동하는 삽입 메서드 중 하나를 사용하여 트리에 해당 노드를 삽입할 수 있습니다. 트리에 노드를 삽입하는 경우 유일한 제한 사항은 노드가 삽입된 후에도 문서가 제대로 구성되어야 한다는 것입니다. 기존 노드를 DOM 트리에 삽입할 경우 해당 노드가 원래 위치에서 제거된 후에 대상 위치에 추가됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML DOM(문서 개체 모델)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
