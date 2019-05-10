---
title: '방법: 두 가지 컨트롤의 속성 바인딩'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 332e8e0dfa30ff7aff27c95652f07446baf6511a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754044"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="66d4f-102">방법: 두 가지 컨트롤의 속성 바인딩</span><span class="sxs-lookup"><span data-stu-id="66d4f-102">How to: Bind the Properties of Two Controls</span></span>
<span data-ttu-id="66d4f-103">사용 하 여 다른의 인스턴스화된 한 컨트롤의 속성을 바인딩하는 방법을 보여 주는이 예제는 <xref:System.Windows.Data.Binding.ElementName%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="66d4f-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66d4f-104">예제</span><span class="sxs-lookup"><span data-stu-id="66d4f-104">Example</span></span>  
 <span data-ttu-id="66d4f-105">다음 예제에서는 바인딩하는 방법을 보여줍니다를 <xref:System.Windows.Controls.Panel.Background%2A> 의 속성을 <xref:System.Windows.Controls.Canvas> 에 <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>합니다.<xref:System.Windows.Controls.ContentControl.Content%2A></span><span class="sxs-lookup"><span data-stu-id="66d4f-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span></span> <span data-ttu-id="66d4f-106">속성을 <xref:System.Windows.Controls.ComboBox>:</span><span class="sxs-lookup"><span data-stu-id="66d4f-106">property of a <xref:System.Windows.Controls.ComboBox>:</span></span>  
  
 [!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="66d4f-107">이 예를 렌더링하면 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66d4f-107">When this example is rendered it looks like the following:</span></span>  
  
![녹색 값을 사용 하 여 상자를 선택 하 고 녹색 사각형 콤보를 보여주는 스크린샷.](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> <span data-ttu-id="66d4f-109">바인딩 대상 속성 (이 예는 <xref:System.Windows.Controls.Panel.Background%2A> 속성) 종속성 속성 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66d4f-109">The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="66d4f-110">자세한 내용은 [데이터 바인딩 개요](data-binding-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66d4f-110">For more information, see [Data Binding Overview](data-binding-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66d4f-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="66d4f-111">See also</span></span>

- [<span data-ttu-id="66d4f-112">바인딩 소스 지정</span><span class="sxs-lookup"><span data-stu-id="66d4f-112">Specify the Binding Source</span></span>](how-to-specify-the-binding-source.md)
- [<span data-ttu-id="66d4f-113">방법 항목</span><span class="sxs-lookup"><span data-stu-id="66d4f-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
