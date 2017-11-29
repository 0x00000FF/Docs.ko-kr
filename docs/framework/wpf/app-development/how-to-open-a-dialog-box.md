---
title: "방법: 대화 상자 열기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- opening dialog boxes [WPF]
- dialog boxes [WPF], opening
ms.assetid: 6b1557d2-da98-4ef4-9f68-4089f04ab9ea
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d318f35f8f009f0f2c77210ca8b6b29bedfb7619
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-open-a-dialog-box"></a>방법: 대화 상자 열기
이 예제에는 대화 상자를 여는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 대화 상자는 인스턴스화하여 열려 있는 창을 <xref:System.Windows.Window> 호출는 <xref:System.Windows.Window.ShowDialog%2A> 메서드. <xref:System.Windows.Window.ShowDialog%2A>창을 열고 새 대화 상자가 닫힐 때까지 반환 하지 않습니다. 이러한 형식의 라고도 *모달* 창 및 사용자 입력을 제한 합니다.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewdialogboxcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewdialogboxcode)]  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 호출 <xref:System.Windows.Window.ShowDialog%2A> 모든 창과 사용자 입력된 이벤트를 제한 없이 사용할 수 있는 권한이 필요 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자 결과 반환](../../../../docs/framework/wpf/app-development/how-to-return-a-dialog-box-result.md)
