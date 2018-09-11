---
title: '방법: 사전을 사용하여 이벤트 인스턴스 저장(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: c3a804ce1bf1f5ac8db47f0f0c1f37d1ca5f781b
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44213175"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a>방법: 사전을 사용하여 이벤트 인스턴스 저장(C# 프로그래밍 가이드)
`accessor-declarations`는 각 이벤트에 대한 필드를 할당하지 않고 사전을 통해 이벤트 인스턴스를 저장하여 많은 이벤트를 공개하는 데 사용됩니다. 이 기능은 많은 이벤트가 있지만 대부분의 이벤트가 구현되지 않을 것으로 예상하는 경우에만 유용합니다.  
  
## <a name="example"></a>예  
 [!code-csharp[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## <a name="see-also"></a>참고 항목

- [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
- [이벤트](../../../csharp/programming-guide/events/index.md)  
- [대리자](../../../csharp/programming-guide/delegates/index.md)
