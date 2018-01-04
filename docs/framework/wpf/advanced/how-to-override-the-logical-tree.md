---
title: "방법: 논리적 트리 재정의"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- overriding the logical tree [WPF]
- logical tree [WPF], overriding
ms.assetid: 0ae4d074-8113-4b06-b4fa-e0f39d4967a6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e487220f8b06515f3d37f7d55ab7ff6214c85d92
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-override-the-logical-tree"></a>방법: 논리적 트리 재정의
대부분의 경우에서 필요하지 않지만 고급 제어 작성자에는 논리적 트리 재정의 옵션이 있습니다.  
  
## <a name="example"></a>예  
 이 예제에서는 설명 서브 클래스 하는 방법 <xref:System.Windows.Controls.StackPanel> 이 경우 패널 하나만 포함 하 고 단일 자식 요소를 렌더링만 하는 동작을 적용 하는 논리적 트리를 재정의 하 합니다. 이는 실제적으로 원하는 동작이 아닐 수 있지만 요소의 정상적인 논리적 트리를 재정의하기 위한 시나리오를 보여 주는 수단으로 여기에 표시됩니다.  
  
 [!code-csharp[LogicalOverride#SingletonPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 논리적 트리에 대한 자세한 내용은 [WPF의 트리](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)를 참조하세요.
