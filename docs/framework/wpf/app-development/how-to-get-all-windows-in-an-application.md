---
title: "방법: 응용 프로그램의 모든 창 가져오기"
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
helpviewer_keywords: window objects [WPF], getting
ms.assetid: f120f06e-993b-4a97-9657-af0d1986981f
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fdb1baad8b779b6ef0443a05e5f6575b552b1c19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-all-windows-in-an-application"></a><span data-ttu-id="ee801-102">방법: 응용 프로그램의 모든 창 가져오기</span><span class="sxs-lookup"><span data-stu-id="ee801-102">How to: Get all Windows in an Application</span></span>
<span data-ttu-id="ee801-103">이 예제에서는 모두 가져오기 위한 <xref:System.Windows.Window> 응용 프로그램의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ee801-103">This example shows how to get all <xref:System.Windows.Window> objects in an application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee801-104">예</span><span class="sxs-lookup"><span data-stu-id="ee801-104">Example</span></span>  
 <span data-ttu-id="ee801-105">모든 인스턴스화할 <xref:System.Windows.Window> 개체를 볼 수 있는지 여부를 여부를 자동으로에서 관리 되는 창 참조의 컬렉션에 추가 됩니다 <xref:System.Windows.Application>에서 노출 하 고 <xref:System.Windows.Application.Windows%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="ee801-105">Every instantiated <xref:System.Windows.Window> object, whether visible or not, is automatically added to a collection of window references that is managed by <xref:System.Windows.Application>, and exposed from <xref:System.Windows.Application.Windows%2A>.</span></span>  
  
 <span data-ttu-id="ee801-106">열거할 수 <xref:System.Windows.Application.Windows%2A> 다음 코드를 사용 하 여 인스턴스화된 모든 windows 얻으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee801-106">You can enumerate <xref:System.Windows.Application.Windows%2A> to get all instantiated windows using the following code:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetAllWindows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/CustomWindow.xaml.cs#getallwindows)]
 [!code-vb[HOWTOWindowManagementSnippets#GetAllWindows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/customwindow.xaml.vb#getallwindows)]
