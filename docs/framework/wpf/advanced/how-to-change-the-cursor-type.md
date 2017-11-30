---
title: "방법: 커서 형식 변경"
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
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 41cd8c9cd647c7efbc4e6cf13517ed638245e51c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-change-the-cursor-type"></a><span data-ttu-id="49b9a-102">방법: 커서 형식 변경</span><span class="sxs-lookup"><span data-stu-id="49b9a-102">How to: Change the Cursor Type</span></span>
<span data-ttu-id="49b9a-103">변경 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Input.Cursor> 에서 특정 요소 및 응용 프로그램에 대 한 마우스 포인터의 합니다.</span><span class="sxs-lookup"><span data-stu-id="49b9a-103">This example shows how to change the <xref:System.Windows.Input.Cursor> of the mouse pointer for a specific element and for the application.</span></span>  
  
 <span data-ttu-id="49b9a-104">이 예제는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일 및 코드 숨김 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="49b9a-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49b9a-105">예제</span><span class="sxs-lookup"><span data-stu-id="49b9a-105">Example</span></span>  
 <span data-ttu-id="49b9a-106">구성 된 사용자 인터페이스를 만들면는 <xref:System.Windows.Controls.ComboBox> 하 고 원하는 <xref:System.Windows.Input.Cursor>, 한 쌍의 <xref:System.Windows.Controls.RadioButton> 커서 변경만 단일 요소에 적용 됩니다 또는 전체 응용 프로그램에 적용 되는 개체 및 <xref:System.Windows.Controls.Border> 새 커서에 적용 되는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="49b9a-106">The user interface is created, which consists of a <xref:System.Windows.Controls.ComboBox> to select the desired <xref:System.Windows.Input.Cursor>, a pair of <xref:System.Windows.Controls.RadioButton> objects to determine if the cursor change applies to only a single element or applies to the entire application, and a <xref:System.Windows.Controls.Border> which is the element that the new cursor is applied to.</span></span>  
  
 [!code-xaml[cursors#ChangeCursorsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 <span data-ttu-id="49b9a-107">다음 코드 숨김 만듭니다는 <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> 에서 커서 유형이 변경 될 때 호출 되는 이벤트 처리기는 <xref:System.Windows.Controls.ComboBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="49b9a-107">The following code behind creates a <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event handler which is called when the cursor type is changed in the <xref:System.Windows.Controls.ComboBox>.</span></span>  <span data-ttu-id="49b9a-108">Switch 문의 커서 이름 및 설정에 대 한 필터는 <xref:System.Windows.FrameworkElement.Cursor%2A> 속성에는 <xref:System.Windows.Controls.Border> 라는 *DisplayArea*합니다.</span><span class="sxs-lookup"><span data-stu-id="49b9a-108">A switch statement filters on the cursor name and sets the <xref:System.Windows.FrameworkElement.Cursor%2A> property on the <xref:System.Windows.Controls.Border> which is named *DisplayArea*.</span></span>  
  
 <span data-ttu-id="49b9a-109">커서 변경 "전체 Application"으로 설정 된 경우는 <xref:System.Windows.Input.Mouse.OverrideCursor%2A> 속성이로 설정 되는 <xref:System.Windows.FrameworkElement.Cursor%2A> 속성의는 <xref:System.Windows.Controls.Border> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="49b9a-109">If the cursor change is set to "Entire Application", the <xref:System.Windows.Input.Mouse.OverrideCursor%2A> property is set to the <xref:System.Windows.FrameworkElement.Cursor%2A> property of the <xref:System.Windows.Controls.Border> control.</span></span>  <span data-ttu-id="49b9a-110">이렇게 하면 커서를 전체 응용 프로그램에 대 한 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49b9a-110">This forces the cursor to change for the whole application.</span></span>  
  
 [!code-csharp[cursors#ChangeCursorsSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a><span data-ttu-id="49b9a-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49b9a-111">See Also</span></span>  
 [<span data-ttu-id="49b9a-112">입력 개요</span><span class="sxs-lookup"><span data-stu-id="49b9a-112">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)
