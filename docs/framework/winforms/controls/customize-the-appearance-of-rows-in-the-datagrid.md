---
title: DataGridView 컨트롤에서 행 모양 사용자 지정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- rows [Windows Forms], customizing in DataGridView control
- DataGridView control [Windows Forms], customizing rows
ms.assetid: d40b53d2-7e7c-48c5-8570-6e79d15c3bbb
ms.openlocfilehash: 099b2104e7a4887aa846c4d65273db2dd4f60559
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744032"
---
# <a name="how-to-customize-the-appearance-of-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="414c4-102">방법: Windows Forms DataGridView 컨트롤에서 행 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="414c4-102">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="414c4-103"><xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> 및 <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> 이벤트를 하나 또는 둘 다 처리하여 <xref:System.Windows.Forms.DataGridView> 행의 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="414c4-103">You can control the appearance of <xref:System.Windows.Forms.DataGridView> rows by handling one or both of the <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> and <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> events.</span></span> <span data-ttu-id="414c4-104">이들 이벤트는 <xref:System.Windows.Forms.DataGridView> 컨트롤이 나머지 부분을 그리게 하는 동안 원하는 부분만 그릴 수 있도록 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="414c4-104">These events are designed so that you can paint only what you want to while letting the <xref:System.Windows.Forms.DataGridView> control paint the rest.</span></span> <span data-ttu-id="414c4-105">예를 들어 사용자 지정 배경을 그리려면 <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> 이벤트를 처리하고 개별 셀이 자체 전경 콘텐츠를 그리도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="414c4-105">For example, if you want to paint a custom background, you can handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> event and let the individual cells paint their own foreground content.</span></span> <span data-ttu-id="414c4-106">또는 셀이 자신을 그리고 <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> 이벤트에 대한 처리기에서 사용자 지정 전경 콘텐츠를 추가하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="414c4-106">Alternately, you can let the cells paint themselves and add custom foreground content in a handler for the <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="414c4-107">셀 그리기를 사용하지 않도록 설정하고 <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> 이벤트 처리에서 직접 모든 부분을 그릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="414c4-107">You can also disable cell painting and paint everything yourself in a <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> event handler.</span></span>  
  
 <span data-ttu-id="414c4-108">다음 코드 예제에서는 여러 열에 걸쳐 있는 그라데이션 선택 배경 및 일부 사용자 지정 전경 콘텐츠를 제공하려고 두 이벤트 모두에 대한 처리기를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="414c4-108">The following code example implements handlers for both events in order to provide a gradient selection background and some custom foreground content that spans multiple columns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="414c4-109">예</span><span class="sxs-lookup"><span data-stu-id="414c4-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewRowPainting#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/CS/datagridviewrowpainting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewRowPainting#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/VB/datagridviewrowpainting.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="414c4-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="414c4-110">Compiling the Code</span></span>  
 <span data-ttu-id="414c4-111">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="414c4-111">This example requires:</span></span>  
  
- <span data-ttu-id="414c4-112">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="414c4-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="414c4-113">참조</span><span class="sxs-lookup"><span data-stu-id="414c4-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>
- [<span data-ttu-id="414c4-114">Windows Forms DataGridView 컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="414c4-114">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="414c4-115">DataGridView 컨트롤 아키텍처</span><span class="sxs-lookup"><span data-stu-id="414c4-115">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
