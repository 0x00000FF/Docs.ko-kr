---
title: '방법: 페이지 함수 호출'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- calling page functions [WPF]
- page functions [WPF], calling
- functions [WPF], calling
ms.assetid: a4808397-c6d5-406a-83e0-0091f0c15ae4
ms.openlocfilehash: 288edec51a690be844aaa913c368496648a7811b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375170"
---
# <a name="how-to-call-a-page-function"></a><span data-ttu-id="bcabd-102">방법: 페이지 함수 호출</span><span class="sxs-lookup"><span data-stu-id="bcabd-102">How to: Call a Page Function</span></span>
<span data-ttu-id="bcabd-103">페이지 함수를 호출 하는 방법을 보여 주는이 예제는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="bcabd-103">This example shows how to call a page function from a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcabd-104">예제</span><span class="sxs-lookup"><span data-stu-id="bcabd-104">Example</span></span>  
 <span data-ttu-id="bcabd-105">사용 하 여 페이지 함수를 이동할 수는 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]마찬가지로 페이지를 탐색할 때 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcabd-105">You can navigate to a page function using a [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], just as you can when you navigate to a page.</span></span> <span data-ttu-id="bcabd-106">다음 예제에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcabd-106">This is shown in the following example.</span></span>  
  
 [!code-csharp[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#navigatetoapagefunctionlikeapagecodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#navigatetoapagefunctionlikeapagecodebehind)]  
  
 <span data-ttu-id="bcabd-107">데이터를 페이지 함수에 전달해야 하는 경우 인스턴스를 만든 다음 속성을 설정하여 데이터를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcabd-107">If you need to pass data to the page function, you can create an instance of it and pass the data by setting a property.</span></span> <span data-ttu-id="bcabd-108">또는 다음 예에 표시된 대로 기본이 아닌 생성자를 사용하여 데이터를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcabd-108">Or, as the following example shows, you can pass the data using a non-default constructor.</span></span>  
  
 [!code-xaml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#callapagefunctioncodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#callapagefunctioncodebehind)]  
  
## <a name="see-also"></a><span data-ttu-id="bcabd-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="bcabd-109">See also</span></span>
- <xref:System.Windows.Navigation.PageFunction%601>
