---
title: '방법: 페이지에서 창 너비 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- width of windows [WPF], setting from a page
- windows [WPF], setting width from a page
- pages [WPF], setting window width from
ms.assetid: 31601c92-7889-472a-b07e-bf675ad21c92
ms.openlocfilehash: fee6d4c9ae9dae03e81cc4be56576763cb59958b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62006722"
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a><span data-ttu-id="13d83-102">방법: 페이지에서 창 너비 설정</span><span class="sxs-lookup"><span data-stu-id="13d83-102">How to: Set the Width of a Window from a Page</span></span>
<span data-ttu-id="13d83-103">이 예제에서 창의 너비를 설정 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.Page>합니다.</span><span class="sxs-lookup"><span data-stu-id="13d83-103">This example illustrates how to set the width of the window from a <xref:System.Windows.Controls.Page>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13d83-104">예제</span><span class="sxs-lookup"><span data-stu-id="13d83-104">Example</span></span>  
 <span data-ttu-id="13d83-105">A <xref:System.Windows.Controls.Page> 설정 하 여 해당 호스트 창의 너비를 설정할 수 있습니다 <xref:System.Windows.Controls.Page.WindowWidth%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="13d83-105">A <xref:System.Windows.Controls.Page> can set the width of its host window by setting <xref:System.Windows.Controls.Page.WindowWidth%2A>.</span></span> <span data-ttu-id="13d83-106">이 속성을 사용 하면를 <xref:System.Windows.Controls.Page> 를 호스팅하는 창의 유형에 대 한 명시적 정보가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13d83-106">This property allows the <xref:System.Windows.Controls.Page> to not have explicit knowledge of the type of window that hosts it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13d83-107">사용 하 여 창 너비를 설정 하려면 <xref:System.Windows.Controls.Page.WindowWidth%2A>, <xref:System.Windows.Controls.Page> 창의 자식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13d83-107">To set the width of a window using <xref:System.Windows.Controls.Page.WindowWidth%2A>, a <xref:System.Windows.Controls.Page> must be the child of a window.</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
