---
title: "Windows Forms 컨트롤 렌더링"
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
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- OnPaintBackground method [Windows Forms], invoking in Windows Forms custom controls
- custom controls [Windows Forms], graphics resources
- custom controls [Windows Forms], invalidation and painting
ms.assetid: aae8e1e6-4786-432b-a15e-f4c44760d302
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 587c9c8fb0bf634a2491acb1ae0b2f60979fa899
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="rendering-a-windows-forms-control"></a><span data-ttu-id="8fafb-102">Windows Forms 컨트롤 렌더링</span><span class="sxs-lookup"><span data-stu-id="8fafb-102">Rendering a Windows Forms Control</span></span>
<span data-ttu-id="8fafb-103">렌더링은 사용자의 화면에 시각적 표시를 만드는 프로세스를 말합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-103">Rendering refers to the process of creating a visual representation on a user's screen.</span></span> <span data-ttu-id="8fafb-104">Windows Forms를 사용 하 여 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] (새 Windows 그래픽 라이브러리) 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-104">Windows Forms uses [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] (the new Windows graphics library) for rendering.</span></span> <span data-ttu-id="8fafb-105">에 대 한 액세스를 제공 하는 관리 되는 클래스 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 에 <xref:System.Drawing?displayProperty=nameWithType> 네임 스페이스 및 그 하위 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-105">The managed classes that provide access to [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] are in the <xref:System.Drawing?displayProperty=nameWithType> namespace and its subnamespaces.</span></span>  
  
 <span data-ttu-id="8fafb-106">다음 요소가 컨트롤 렌더링에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-106">The following elements are involved in control rendering:</span></span>  
  
-   <span data-ttu-id="8fafb-107">기본 클래스에서 제공 하는 그리기 기능 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-107">The drawing functionality provided by the base class <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="8fafb-108">필수 요소는 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 그래픽 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-108">The essential elements of the [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] graphics library.</span></span>  
  
-   <span data-ttu-id="8fafb-109">그리기 영역의 기 하 도형을 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-109">The geometry of the drawing region.</span></span>  
  
-   <span data-ttu-id="8fafb-110">그래픽 리소스를 해제 하기 위한 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-110">The procedure for freeing graphics resources.</span></span>  
  
## <a name="drawing-functionality-provided-by-control"></a><span data-ttu-id="8fafb-111">그리기 컨트롤에서 제공 하는 기능</span><span class="sxs-lookup"><span data-stu-id="8fafb-111">Drawing Functionality Provided by Control</span></span>  
 <span data-ttu-id="8fafb-112">기본 클래스 <xref:System.Windows.Forms.Control> 통해 그리기 기능을 제공 해당 <xref:System.Windows.Forms.Control.Paint> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-112">The base class <xref:System.Windows.Forms.Control> provides drawing functionality through its <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="8fafb-113">컨트롤에서 발생 된 <xref:System.Windows.Forms.Control.Paint> 표시를 업데이트 해야 할 때마다 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-113">A control raises the <xref:System.Windows.Forms.Control.Paint> event whenever it needs to update its display.</span></span> <span data-ttu-id="8fafb-114">.NET Framework의 이벤트에 대 한 자세한 내용은 참조 [이벤트 처리 및 발생](../../../../docs/standard/events/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-114">For more information about events in the .NET Framework, see [Handling and Raising Events](../../../../docs/standard/events/index.md).</span></span>  
  
 <span data-ttu-id="8fafb-115">이벤트 데이터에 대 한 클래스는 <xref:System.Windows.Forms.Control.Paint> 이벤트 <xref:System.Windows.Forms.PaintEventArgs>, 컨트롤을 그리는 데 필요한 데이터를 보유-graphics 개체 및 그릴 영역을 나타내는 사각형 개체에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-115">The event data class for the <xref:System.Windows.Forms.Control.Paint> event, <xref:System.Windows.Forms.PaintEventArgs>, holds the data needed for drawing a control — a handle to a graphics object and a rectangle object that represents the region to draw in.</span></span> <span data-ttu-id="8fafb-116">이러한 개체에 표시 되는 다음 코드 조각에서 굵게 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-116">These objects are shown in bold in the following code fragment.</span></span>  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   Implements IDisposable  
  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property  
   ' Other properties and methods.  
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs, IDisposable {  
public System.Drawing.Rectangle ClipRectangle {get;}  
public System.Drawing.Graphics Graphics {get;}  
// Other properties and methods.  
...  
}  
```  
  
 <span data-ttu-id="8fafb-117"><xref:System.Drawing.Graphics>그리기 기능을 캡슐화 하는 관리 되는 클래스에 대 한 설명에 설명 된 대로 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 이 항목의 뒷부분에 나오는 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-117"><xref:System.Drawing.Graphics> is a managed class that encapsulates drawing functionality, as described in the discussion of [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] later in this topic.</span></span> <span data-ttu-id="8fafb-118"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 의 인스턴스가 <xref:System.Drawing.Rectangle> 구조체이 고 컨트롤을 그릴 수 있는 사용 가능한 영역을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-118">The <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is an instance of the <xref:System.Drawing.Rectangle> structure and defines the available area in which a control can draw.</span></span> <span data-ttu-id="8fafb-119">컨트롤 개발자를 계산할 수는 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 를 사용 하는 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 이 항목의 뒷부분에 나오는 기 하 도형에 대 한 설명에 설명 된 대로 컨트롤의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-119">A control developer can compute the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> using the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of a control, as described in the discussion of geometry later in this topic.</span></span>  
  
 <span data-ttu-id="8fafb-120">재정의 하 여 컨트롤 렌더링 논리를 제공 해야는 <xref:System.Windows.Forms.Control.OnPaint%2A> 에서 상속 된 메서드 <xref:System.Windows.Forms.Control>합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-120">A control must provide rendering logic by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="8fafb-121"><xref:System.Windows.Forms.Control.OnPaint%2A>그래픽 개체 및 통해 그릴 사각형에 대 한 액세스를 가져옵니다는 <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> 및 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 의 속성은 <xref:System.Windows.Forms.PaintEventArgs> 인스턴스가 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-121"><xref:System.Windows.Forms.Control.OnPaint%2A> gets access to a graphics object and a rectangle to draw in through the <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> properties of the <xref:System.Windows.Forms.PaintEventArgs> instance passed to it.</span></span>  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 <span data-ttu-id="8fafb-122"><xref:System.Windows.Forms.Control.OnPaint%2A> 메서드는 기본 <xref:System.Windows.Forms.Control> 클래스는 그리기 기능을 구현 하지 않는 있지만에 등록 된 이벤트 대리자를 호출는 <xref:System.Windows.Forms.Control.Paint> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-122">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base <xref:System.Windows.Forms.Control> class does not implement any drawing functionality but merely invokes the event delegates that are registered with the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="8fafb-123">재정의 하는 경우 <xref:System.Windows.Forms.Control.OnPaint%2A>, 일반적으로 호출 해야 합니다는 <xref:System.Windows.Forms.Control.OnPaint%2A> 수신 하는 등록 된 대리자에는 기본 클래스의 메서드는 <xref:System.Windows.Forms.Control.Paint> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-123">When you override <xref:System.Windows.Forms.Control.OnPaint%2A>, you should typically invoke the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class so that registered delegates receive the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="8fafb-124">하지만 전체 화면을 그리는 컨트롤의 기본 클래스를 호출 하지 않아야 <xref:System.Windows.Forms.Control.OnPaint%2A>마찬가지로 깜빡임을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-124">However, controls that paint their entire surface should not invoke the base class's <xref:System.Windows.Forms.Control.OnPaint%2A>, as this introduces flicker.</span></span> <span data-ttu-id="8fafb-125">재정의에 대 한 예제는 <xref:System.Windows.Forms.Control.OnPaint%2A> 이벤트 참조는 [하는 방법: Windows Forms 컨트롤을 표시 진행률 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-125">For an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> event, see the [How to: Create a Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8fafb-126">호출 하지 말고 <xref:System.Windows.Forms.Control.OnPaint%2A> 직접 제어;에서 대신 호출할는 <xref:System.Windows.Forms.Control.Invalidate%2A> 메서드 (에서 상속 되며, <xref:System.Windows.Forms.Control>) 또는 일부 다른 메서드를 호출 하는 <xref:System.Windows.Forms.Control.Invalidate%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-126">Do not invoke <xref:System.Windows.Forms.Control.OnPaint%2A> directly from your control; instead, invoke the <xref:System.Windows.Forms.Control.Invalidate%2A> method (inherited from <xref:System.Windows.Forms.Control>) or some other method that invokes <xref:System.Windows.Forms.Control.Invalidate%2A>.</span></span> <span data-ttu-id="8fafb-127"><xref:System.Windows.Forms.Control.Invalidate%2A> 메서드 호출 <xref:System.Windows.Forms.Control.OnPaint%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-127">The <xref:System.Windows.Forms.Control.Invalidate%2A> method in turn invokes <xref:System.Windows.Forms.Control.OnPaint%2A>.</span></span> <span data-ttu-id="8fafb-128"><xref:System.Windows.Forms.Control.Invalidate%2A> 메서드는 오버 로드 하 고 제공 된 인수에 따라 <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, 일부 또는 전체 화면 영역의 컨트롤을 다시 그립니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-128">The <xref:System.Windows.Forms.Control.Invalidate%2A> method is overloaded, and, depending on the arguments supplied to <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, a control redraws either some or all of its screen area.</span></span>  
  
 <span data-ttu-id="8fafb-129">기본 <xref:System.Windows.Forms.Control> 그리기에 사용 되는 다른 메서드를 정의 하는 클래스-는 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="8fafb-129">The base <xref:System.Windows.Forms.Control> class defines another method that is useful for drawing — the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method.</span></span>  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <span data-ttu-id="8fafb-130"><xref:System.Windows.Forms.Control.OnPaintBackground%2A>배경을 칠하는 (있고, 따라서 셰이프) 창 동안 빠른 되도록 보장 하 고 <xref:System.Windows.Forms.Control.OnPaint%2A> 세부 정보를 그리는 및 개별 그리기 요청은 하나에 결합 되므로 느릴 수 <xref:System.Windows.Forms.Control.Paint> 되어야 하는 모든 영역을 검사 하는 이벤트 다시 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-130"><xref:System.Windows.Forms.Control.OnPaintBackground%2A> paints the background (and thereby the shape) of the window and is guaranteed to be fast, while <xref:System.Windows.Forms.Control.OnPaint%2A> paints the details and might be slower because individual paint requests are combined into one <xref:System.Windows.Forms.Control.Paint> event that covers all areas that have to be redrawn.</span></span> <span data-ttu-id="8fafb-131">호출 하려는 경우는 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 예를 들어, 컨트롤에 대 한 그라데이션 색 배경을 그리는 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="8fafb-131">You might want to invoke the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> if, for instance, you want to draw a gradient-colored background for your control.</span></span>  
  
 <span data-ttu-id="8fafb-132">반면 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 이벤트와 비슷한 명명법 개이고으로 동일한 인수를 사용는 `OnPaint` 메서드를 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> true 이벤트 메서드가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-132">While <xref:System.Windows.Forms.Control.OnPaintBackground%2A> has an event-like nomenclature and takes the same argument as the `OnPaint` method, <xref:System.Windows.Forms.Control.OnPaintBackground%2A> is not a true event method.</span></span> <span data-ttu-id="8fafb-133">없는 `PaintBackground` 이벤트 및 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 이벤트 대리자를 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-133">There is no `PaintBackground` event and <xref:System.Windows.Forms.Control.OnPaintBackground%2A> does not invoke event delegates.</span></span> <span data-ttu-id="8fafb-134">재정의 하는 경우는 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 메서드, 파생된 클래스를 호출 하는 데 필요 하지 않습니다.는 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 기본 클래스의 메서드.</span><span class="sxs-lookup"><span data-stu-id="8fafb-134">When overriding the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method, a derived class is not required to invoke the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method of its base class.</span></span>  
  
## <a name="gdi-basics"></a><span data-ttu-id="8fafb-135">GDI + 기본 사항</span><span class="sxs-lookup"><span data-stu-id="8fafb-135">GDI+ Basics</span></span>  
 <span data-ttu-id="8fafb-136"><xref:System.Drawing.Graphics> 클래스는 텍스트를 표시 하기 위한 메서드 뿐 아니라 원, 삼각형, 호 및 타원, 같은 다양 한 셰이프를 그리기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-136">The <xref:System.Drawing.Graphics> class provides methods for drawing various shapes such as circles, triangles, arcs, and ellipses, as well as methods for displaying text.</span></span> <span data-ttu-id="8fafb-137"><xref:System.Drawing?displayProperty=nameWithType> 네임 스페이스 및 그 하위 네임 스페이스 셰이프 (원, 사각형, 타원, 및 기타), 색, 글꼴, 브러시, 등과 같은 그래픽 요소를 캡슐화 하는 클래스가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-137">The <xref:System.Drawing?displayProperty=nameWithType> namespace and its subnamespaces contain classes that encapsulate graphics elements such as shapes (circles, rectangles, arcs, and others), colors, fonts, brushes, and so on.</span></span> <span data-ttu-id="8fafb-138">에 대 한 자세한 내용은 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], 참조 [관리 되는 그래픽 클래스를 사용 하 여](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-138">For more information about [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], see [Using Managed Graphics Classes](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md).</span></span> <span data-ttu-id="8fafb-139">필수 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 에 나와 [하는 방법: Windows Forms 컨트롤을 표시 진행률 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-139">The essentials of [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] are also described in the [How to: Create a Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
## <a name="geometry-of-the-drawing-region"></a><span data-ttu-id="8fafb-140">기 하 도형 그리기 영역의</span><span class="sxs-lookup"><span data-stu-id="8fafb-140">Geometry of the Drawing Region</span></span>  
 <span data-ttu-id="8fafb-141"><xref:System.Windows.Forms.Control.ClientRectangle%2A> 사용자의 화면에 컨트롤에 사용할 수 있는 사각형 영역을 지정 하는 컨트롤의 속성 동안는 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 속성 <xref:System.Windows.Forms.PaintEventArgs> 그리고 실제로 있는 영역을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-141">The <xref:System.Windows.Forms.Control.ClientRectangle%2A> property of a control specifies the rectangular region available to the control on the user's screen, while the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of <xref:System.Windows.Forms.PaintEventArgs> specifies the area that is actually painted.</span></span> <span data-ttu-id="8fafb-142">(기억 그리기가 수행 됩니다는 <xref:System.Windows.Forms.Control.Paint> 사용 이벤트 메서드를 한 <xref:System.Windows.Forms.PaintEventArgs> 인스턴스).</span><span class="sxs-lookup"><span data-stu-id="8fafb-142">(Remember that painting is done in the <xref:System.Windows.Forms.Control.Paint> event method that takes a <xref:System.Windows.Forms.PaintEventArgs> instance as its argument).</span></span> <span data-ttu-id="8fafb-143">컨트롤의 표시 변경의 경우 작은 섹션의 경우 처럼 컨트롤에서 사용 가능한 영역의 부분만 그릴 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-143">A control might need to paint only a portion of its available area, as is the case when a small section of the control's display changes.</span></span> <span data-ttu-id="8fafb-144">컨트롤 개발자 이런 경우, 그리고 전달 하는 실제 사각형을 계산 해야 <xref:System.Windows.Forms.Control.Invalidate%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-144">In those situations, a control developer must compute the actual rectangle to draw in and pass that to <xref:System.Windows.Forms.Control.Invalidate%2A>.</span></span> <span data-ttu-id="8fafb-145">오버 로드 된 버전의 <xref:System.Windows.Forms.Control.Invalidate%2A> 사용 하는 <xref:System.Drawing.Rectangle> 또는 <xref:System.Drawing.Region> 인수를 사용 하 여 인수에 지정 된 생성의 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 속성 <xref:System.Windows.Forms.PaintEventArgs>합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-145">The overloaded versions of <xref:System.Windows.Forms.Control.Invalidate%2A> that take a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.Region> as an argument use that argument to generate the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
 <span data-ttu-id="8fafb-146">다음 코드 조각 표시 방법을 `FlashTrackBar` 사용자 지정 컨트롤에 그릴 사각형 영역을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-146">The following code fragment shows how the `FlashTrackBar` custom control computes the rectangular area to draw in.</span></span> <span data-ttu-id="8fafb-147">`client` 변수 나타냅니다는 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-147">The `client` variable denotes the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property.</span></span> <span data-ttu-id="8fafb-148">전체 샘플을 참조 하십시오. [하는 방법: Windows Forms 컨트롤을 표시 진행률 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-148">For a complete sample, see [How to: Create a Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a><span data-ttu-id="8fafb-149">그래픽 리소스를 해제</span><span class="sxs-lookup"><span data-stu-id="8fafb-149">Freeing Graphics Resources</span></span>  
 <span data-ttu-id="8fafb-150">그래픽 개체는 시스템 리소스를 사용 하기 때문에 비용이 많이 드는입니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-150">Graphics objects are expensive because they use system resources.</span></span> <span data-ttu-id="8fafb-151">인스턴스를 포함 하는 이러한 개체는 <xref:System.Drawing.Graphics?displayProperty=nameWithType> 클래스의 인스턴스 뿐만 아니라 <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>, 및 기타 그래픽 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-151">Such objects include instances of the <xref:System.Drawing.Graphics?displayProperty=nameWithType> class as well as instances of <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>, and other graphics classes.</span></span> <span data-ttu-id="8fafb-152">에 필요 하 고 해제 하는 경우에 그래픽 리소스를 만드는 것이 중요 하기를 사용 하 여 작업을 마치는 곧 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-152">It is important that you create a graphics resource only when you need it and release it soon as you are finished using it.</span></span> <span data-ttu-id="8fafb-153">구현 하는 형식을 만드는 경우는 <xref:System.IDisposable> 인터페이스를 호출 해당 <xref:System.IDisposable.Dispose%2A> 메서드 했으면 된 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-153">If you create a type that implements the <xref:System.IDisposable> interface, call its <xref:System.IDisposable.Dispose%2A> method when you are finished with it in order to free resources.</span></span>  
  
 <span data-ttu-id="8fafb-154">다음 코드 조각 표시 방법을 `FlashTrackBar` 사용자 지정 컨트롤을 만들고 해제는 <xref:System.Drawing.Brush> 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-154">The following code fragment shows how the `FlashTrackBar` custom control creates and releases a <xref:System.Drawing.Brush> resource.</span></span> <span data-ttu-id="8fafb-155">전체 소스 코드에 대 한 참조 [하는 방법: Windows Forms 컨트롤을 표시 진행률 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8fafb-155">For the complete source code, see [How to: Create a Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="8fafb-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8fafb-156">See Also</span></span>  
 [<span data-ttu-id="8fafb-157">방법: 진행률을 보여 주는 Windows Forms 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="8fafb-157">How to: Create a Windows Forms Control That Shows Progress</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)
