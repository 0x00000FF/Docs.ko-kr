---
title: '방법: 페이지 함수에서 반환'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- returning from page functions [WPF]
- page functions [WPF], returning from
- functions [WPF], returning from
ms.assetid: 87804905-7e8f-417b-b0e3-5622da686396
ms.openlocfilehash: 85ca9632a6f5b5df08fa6ac042d56ebbc70d427d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718548"
---
# <a name="how-to-return-from-a-page-function"></a><span data-ttu-id="8f4b1-102">방법: 페이지 함수에서 반환</span><span class="sxs-lookup"><span data-stu-id="8f4b1-102">How to: Return from a Page Function</span></span>
<span data-ttu-id="8f4b1-103">이 예제에서는 페이지 함수에서 결과를 반환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8f4b1-103">This example shows how to return a result from a page function.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f4b1-104">예제</span><span class="sxs-lookup"><span data-stu-id="8f4b1-104">Example</span></span>  
 <span data-ttu-id="8f4b1-105">페이지 함수에서 반환할 호출할 필요가 <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> 의 인스턴스를 전달 하 고 <xref:System.Windows.Navigation.ReturnEventArgs%601>입니다.</span><span class="sxs-lookup"><span data-stu-id="8f4b1-105">To return from a page function, you need to call <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> and pass an instance of <xref:System.Windows.Navigation.ReturnEventArgs%601>.</span></span>  
  
 [!code-xaml[HOWTOPageFunctionSnippets#PageFunctionReturnAResultXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/GetStringPageFunction.xaml#pagefunctionreturnaresultxaml1)]  
[!code-xaml[HOWTOPageFunctionSnippets#PageFunctionReturnAResultXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/GetStringPageFunction.xaml#pagefunctionreturnaresultxaml2)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#PageFunctionReturnAResultCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/GetStringPageFunction.xaml.cs#pagefunctionreturnaresultcodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#PageFunctionReturnAResultCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/GetStringPageFunction.xaml.vb#pagefunctionreturnaresultcodebehind)]  
  
## <a name="see-also"></a><span data-ttu-id="8f4b1-106">참고자료</span><span class="sxs-lookup"><span data-stu-id="8f4b1-106">See also</span></span>
- <xref:System.Windows.Navigation.PageFunction%601>
