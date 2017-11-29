---
title: "방법: 컨트롤 렌더링 클래스 사용"
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
- cpp
helpviewer_keywords:
- professional appearance [Windows Forms], rendering Windows Forms controls
- visual themes [Windows Forms], applying to Windows Forms controls
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: c0125e34-cd74-4c35-818c-3e40f462b0a3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ff10cd12889750e3d32fcfce080d472f40bb9c2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-a-control-rendering-class"></a><span data-ttu-id="e90d4-102">방법: 컨트롤 렌더링 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="e90d4-102">How to: Use a Control Rendering Class</span></span>
<span data-ttu-id="e90d4-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Forms.ComboBoxRenderer> 드롭 다운 화살표는 콤보 상자 컨트롤을 렌더링 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e90d4-103">This example demonstrates how to use the <xref:System.Windows.Forms.ComboBoxRenderer> class to render the drop-down arrow of a combo box control.</span></span> <span data-ttu-id="e90d4-104">이 예제에서는 이루어져는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드는 간단한 사용자 지정 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="e90d4-104">The example consists of the <xref:System.Windows.Forms.Control.OnPaint%2A> method of a simple custom control.</span></span> <span data-ttu-id="e90d4-105"><xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> 속성은 응용 프로그램 창의 클라이언트 영역에서 비주얼 스타일을 사용 하는지 여부를 결정 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e90d4-105">The <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> property is used to determine whether visual styles are enabled in the client area of application windows.</span></span> <span data-ttu-id="e90d4-106">비주얼 스타일은 활성 상태인 경우 하면 <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> 메서드는 비주얼 스타일; 있는 드롭다운 화살표를 렌더링 하는 그렇지 않은 경우는 <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> 메서드는 기본 Windows 스타일에 있는 드롭다운 화살표를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="e90d4-106">If visual styles are active, then the <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> method will render the drop-down arrow with visual styles; otherwise, the <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> method will render the drop-down arrow in the classic Windows style.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e90d4-107">예제</span><span class="sxs-lookup"><span data-stu-id="e90d4-107">Example</span></span>  
 [!code-cpp[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/cpp/form1.cpp#10)]
 [!code-csharp[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e90d4-108">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="e90d4-108">Compiling the Code</span></span>  
 <span data-ttu-id="e90d4-109">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e90d4-109">This example requires:</span></span>  
  
-   <span data-ttu-id="e90d4-110">파생 되는 사용자 지정 컨트롤은 <xref:System.Windows.Forms.Control> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e90d4-110">A custom control derived from the <xref:System.Windows.Forms.Control> class.</span></span>  
  
-   <span data-ttu-id="e90d4-111">A <xref:System.Windows.Forms.Form> 사용자 지정 컨트롤을 호스팅하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="e90d4-111">A <xref:System.Windows.Forms.Form> that hosts the custom control.</span></span>  
  
-   <span data-ttu-id="e90d4-112">에 대 한 참조는 <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, 및 <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e90d4-112">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e90d4-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e90d4-113">See Also</span></span>  
 [<span data-ttu-id="e90d4-114">비주얼 스타일을 사용하여 컨트롤 렌더링</span><span class="sxs-lookup"><span data-stu-id="e90d4-114">Rendering Controls with Visual Styles</span></span>](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)
