---
title: '방법: 프로그래밍 방식으로 요소를 텍스트에 삽입'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Text Animation sample [WPF]
- elements [WPF], inserting into text
- inserting elements into text [WPF]
- TextPointer objects [WPF]
- text [WPF], inserting elements
ms.assetid: 97bd950a-25ac-4e42-a311-94b6420d4136
ms.openlocfilehash: 460524a88427ef5fa822461a7bb985426fefea53
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693190"
---
# <a name="how-to-insert-an-element-into-text-programmatically"></a><span data-ttu-id="3972b-102">방법: 프로그래밍 방식으로 요소를 텍스트에 삽입</span><span class="sxs-lookup"><span data-stu-id="3972b-102">How to: Insert an Element Into Text Programmatically</span></span>
<span data-ttu-id="3972b-103">다음 예제에는 두 개 사용 하는 방법을 보여 줍니다 <xref:System.Windows.Documents.TextPointer> 적용할 텍스트 내의 범위를 지정 하는 개체는 <xref:System.Windows.Documents.Span> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3972b-103">The following example shows how to use two <xref:System.Windows.Documents.TextPointer> objects to specify a range within text to apply a <xref:System.Windows.Documents.Span> element to.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3972b-104">예제</span><span class="sxs-lookup"><span data-stu-id="3972b-104">Example</span></span>  
 [!code-csharp[FlowMiscSnippets_procedural_snip#InsertInlineIntoTextExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowMiscSnippets_procedural_snip/CSharp/InsertInlineIntoTextExample.cs#insertinlineintotextexamplewholepage)]
 [!code-vb[FlowMiscSnippets_procedural_snip#InsertInlineIntoTextExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowMiscSnippets_procedural_snip/VisualBasic/InsertInlineIntoTextExample.vb#insertinlineintotextexamplewholepage)]  
  
 <span data-ttu-id="3972b-105">아래 그림은 이 예제가 어떻게 보이는지 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3972b-105">The illustration below shows what this example looks like.</span></span>  
  
 <span data-ttu-id="3972b-106">![텍스트 범위에 적용된 Span 요소](../../../../docs/framework/wpf/advanced/media/flow-insertelementintotextprogrammatically.png "Flow_InsertElementIntoTextProgrammatically")</span><span class="sxs-lookup"><span data-stu-id="3972b-106">![A Span element applied to a range of text](../../../../docs/framework/wpf/advanced/media/flow-insertelementintotextprogrammatically.png "Flow_InsertElementIntoTextProgrammatically")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3972b-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="3972b-107">See also</span></span>
- [<span data-ttu-id="3972b-108">유동 문서 개요</span><span class="sxs-lookup"><span data-stu-id="3972b-108">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)
