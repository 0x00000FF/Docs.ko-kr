---
title: "잉크 저장"
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
- ISF (Ink Serialized Format)
- storing ink [WPF]
- ink [WPF], storing
- retrieving ink [WPF]
- Ink Serialized Format (ISF)
ms.assetid: a3f6d16b-d682-4680-9965-907332b4d2b8
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 244a4bfa5def1319438d66a52120e36aab0e753b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="storing-ink"></a>잉크 저장
<xref:System.Windows.Ink.StrokeCollection.Save%2A> 메서드 잉크도 잉크 직렬화 형식 ISF ()를 저장 하기 위한 지원을 제공 합니다. 에 대 한 생성자는 <xref:System.Windows.Ink.StrokeCollection> 클래스 잉크 데이터를 읽기 위한 지원을 제공 합니다.  
  
## <a name="ink-storage-and-retrieval"></a>잉크 저장 및 검색  
 이 섹션에서는 저장 하 고에 잉크를 검색 하는 방법을 설명의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 플랫폼입니다.  
  
 다음 예제에서는 구현 파일 저장 대화 상자에 있는 사용자에 게 표시 하 고에서 잉크를 저장 하는 단추 클릭 이벤트 처리기는 <xref:System.Windows.Controls.InkCanvas> 를 파일로 합니다.  
  
 [!code-csharp[DigitalInkTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#12)]
 [!code-vb[DigitalInkTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#12)]  
  
 다음 예제에서는 잉크에이 파일에서 읽고 파일 열기 대화 상자에 있는 사용자에 게 표시 단추 클릭 이벤트 처리기를 구현 하는 <xref:System.Windows.Controls.InkCanvas> 요소입니다.  
  
 [!code-csharp[DigitalInkTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#13)]
 [!code-vb[DigitalInkTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#13)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.InkCanvas>  
 [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md)
