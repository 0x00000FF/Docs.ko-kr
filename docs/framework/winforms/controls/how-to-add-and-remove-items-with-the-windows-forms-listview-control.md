---
title: "방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], populating
- list views [Windows Forms], adding list items
- ListView control [Windows Forms], adding list items
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8a66d0da6e010efbad77e9544267d1b6af9d1233
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control"></a>방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거
Windows Forms에 항목을 추가 하는 프로세스 <xref:System.Windows.Forms.ListView> 제어 이루어져 주로 항목을 지정 하 고 속성을 할당 합니다. 목록 항목 추가 또는 제거를 언제 든 지 수행할 수 있습니다.  
  
### <a name="to-add-items-programmatically"></a>프로그래밍 방식으로 항목을 추가 하려면  
  
1.  사용 하 여는 <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> 의 메서드는 <xref:System.Windows.Forms.ListView.Items%2A> 속성입니다.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### <a name="to-remove-items-programmatically"></a>프로그래밍 방식으로 항목을 제거 하려면  
  
1.  사용 하 여는 <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> 또는 <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> 의 메서드는 <xref:System.Windows.Forms.ListView.Items%2A> 속성입니다. <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> 단일 항목을 제거 하는 메서드, <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> 메서드 목록에서 모든 항목을 제거 합니다.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ListView>  
 [ListView 컨트롤](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [ListView 컨트롤 개요](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
