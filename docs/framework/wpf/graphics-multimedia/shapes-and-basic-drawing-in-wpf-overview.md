---
title: WPF에서 Shape 및 기본 그리기 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shapes [WPF], about shapes
- basic drawing [WPF]
- vector drawing [WPF], overview
- vectors [WPF], drawing
- Shape objects [WPF]
ms.assetid: 66d7a6d6-e3b6-47bc-8dfe-8a1b26f7d901
ms.openlocfilehash: 47df352c3b001f088f34ea057b34698efc4f4b53
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48778103"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a><span data-ttu-id="1c969-102">WPF에서 Shape 및 기본 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="1c969-102">Shapes and Basic Drawing in WPF Overview</span></span>
<span data-ttu-id="1c969-103">이 항목에서는 사용 하 여 그리는 방법에 대해 간략히 설명 <xref:System.Windows.Shapes.Shape> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-103">This topic gives an overview of how to draw with <xref:System.Windows.Shapes.Shape> objects.</span></span> <span data-ttu-id="1c969-104">A <xref:System.Windows.Shapes.Shape> 유형의 <xref:System.Windows.UIElement> 화면에 도형을 그릴 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-104">A <xref:System.Windows.Shapes.Shape> is a type of <xref:System.Windows.UIElement> that enables you to draw a shape to the screen.</span></span> <span data-ttu-id="1c969-105">UI 요소 이므로 <xref:System.Windows.Shapes.Shape> 내에서 개체를 사용할 수 있습니다 <xref:System.Windows.Controls.Panel> 요소 및 대부분의 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-105">Because they are UI elements, <xref:System.Windows.Shapes.Shape> objects can be used inside <xref:System.Windows.Controls.Panel> elements and most controls.</span></span>  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="1c969-106">는 그래픽 및 렌더링 서비스에 대한 여러 계층의 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-106"> offers several layers of access to graphics and rendering services.</span></span> <span data-ttu-id="1c969-107">최상위 계층 <xref:System.Windows.Shapes.Shape> 개체는 쉽게 사용 하 여 레이아웃 및 참여 등 여러 유용한 기능을 제공 하는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 이벤트 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-107">At the top layer, <xref:System.Windows.Shapes.Shape> objects are easy to use and provide many useful features, such as layout and participation in the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] event system.</span></span>  
  
  
<a name="shapes"></a>   
## <a name="shape-objects"></a><span data-ttu-id="1c969-108">Shape 개체</span><span class="sxs-lookup"><span data-stu-id="1c969-108">Shape Objects</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="1c969-109">다양 한 쉬운 준비 <xref:System.Windows.Shapes.Shape> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-109"> provides a number of ready-to-use <xref:System.Windows.Shapes.Shape> objects.</span></span>  <span data-ttu-id="1c969-110">모든 도형 개체에서 상속 된 <xref:System.Windows.Shapes.Shape> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-110">All shape objects inherit from the <xref:System.Windows.Shapes.Shape> class.</span></span> <span data-ttu-id="1c969-111">사용 가능한 도형 개체를 포함 <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>를 <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>를 <xref:System.Windows.Shapes.Polyline>, 및 <xref:System.Windows.Shapes.Rectangle>합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-111">Available shape objects include <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="1c969-112"><xref:System.Windows.Shapes.Shape> 개체에는 다음 공용 속성을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-112"><xref:System.Windows.Shapes.Shape> objects share the following common properties.</span></span>  
  
-   <span data-ttu-id="1c969-113"><xref:System.Windows.Shapes.Shape.Stroke%2A>: 도형의 윤곽선을 그리는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-113"><xref:System.Windows.Shapes.Shape.Stroke%2A>: Describes how the shape's outline is painted.</span></span>  
  
-   <span data-ttu-id="1c969-114"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: 도형의 윤곽선 두께 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-114"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Describes the thickness of the shape's outline.</span></span>  
  
-   <span data-ttu-id="1c969-115"><xref:System.Windows.Shapes.Shape.Fill%2A>: 도형의 내부가 그려지는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-115"><xref:System.Windows.Shapes.Shape.Fill%2A>: Describes how the interior of the shape is painted.</span></span>  
  
-   <span data-ttu-id="1c969-116">장치 독립적 픽셀 단위로 측정된 좌표 및 꼭지점을 지정하는 데이터 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-116">Data properties to specify coordinates and vertices, measured in device-independent pixels.</span></span>  
  
 <span data-ttu-id="1c969-117">파생 되므로 <xref:System.Windows.UIElement>, 패널 및 대부분의 컨트롤 내에서 셰이프 개체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-117">Because they derive from <xref:System.Windows.UIElement>, shape objects can be used inside panels and most controls.</span></span> <span data-ttu-id="1c969-118"><xref:System.Windows.Controls.Canvas> 패널은 자식 개체의 절대 위치 지정을 지원 하기 때문에 복잡 한 그리기를 만들기 위한 특히 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-118">The <xref:System.Windows.Controls.Canvas> panel is a particularly good choice for creating complex drawings because it supports absolute positioning of its child objects.</span></span>  
  
 <span data-ttu-id="1c969-119"><xref:System.Windows.Shapes.Line> 클래스를 사용 하면 두 점 사이의 선을 그릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-119">The <xref:System.Windows.Shapes.Line> class enables you to draw a line between two points.</span></span> <span data-ttu-id="1c969-120">다음 예제에서는 선 좌표 및 스트로크 속성을 지정하는 여러 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-120">The following example shows several ways to specify line coordinates and stroke properties.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 <span data-ttu-id="1c969-121">다음 이미지는 렌더링 된 표시 <xref:System.Windows.Shapes.Line>합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-121">The following image shows the rendered <xref:System.Windows.Shapes.Line>.</span></span>  
  
 <span data-ttu-id="1c969-122">![선 그림](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-line2.gif "shape_ovw_line2")</span><span class="sxs-lookup"><span data-stu-id="1c969-122">![Line illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-line2.gif "shape_ovw_line2")</span></span>  
  
 <span data-ttu-id="1c969-123">있지만 합니다 <xref:System.Windows.Shapes.Line> 클래스는 제공을 <xref:System.Windows.Shapes.Shape.Fill%2A> 속성을 설정 하므로 효과가 없음를 <xref:System.Windows.Shapes.Line> 영역이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-123">Although the <xref:System.Windows.Shapes.Line> class does provide a <xref:System.Windows.Shapes.Shape.Fill%2A> property, setting it has no effect because a <xref:System.Windows.Shapes.Line> has no area.</span></span>  
  
 <span data-ttu-id="1c969-124">또 다른 일반적인 도형은 <xref:System.Windows.Shapes.Ellipse>합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-124">Another common shape is the <xref:System.Windows.Shapes.Ellipse>.</span></span>  <span data-ttu-id="1c969-125">만들기는 <xref:System.Windows.Shapes.Ellipse> 셰이프를 정의 하 여 <xref:System.Windows.FrameworkElement.Width%2A> 고 <xref:System.Windows.FrameworkElement.Height%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-125">Create an <xref:System.Windows.Shapes.Ellipse> by defining the shape's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span> <span data-ttu-id="1c969-126">원을 그리려면 지정는 <xref:System.Windows.Shapes.Ellipse> 해당 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 값이 같으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-126">To draw a circle, specify an <xref:System.Windows.Shapes.Ellipse> whose <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> values are equal.</span></span>  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 <span data-ttu-id="1c969-127">다음 이미지는 렌더링 된 예를 보여 줍니다. <xref:System.Windows.Shapes.Ellipse>합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-127">The following image shows an example of a rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="1c969-128">![타원 그림](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span><span class="sxs-lookup"><span data-stu-id="1c969-128">![Ellipse illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span></span>  
  
<a name="paths"></a>   
## <a name="using-paths-and-geometries"></a><span data-ttu-id="1c969-129">경로 및 기하 도형 사용</span><span class="sxs-lookup"><span data-stu-id="1c969-129">Using Paths and Geometries</span></span>  
 <span data-ttu-id="1c969-130"><xref:System.Windows.Shapes.Path> 클래스를 사용 하면 곡선 및 복잡 한 도형을 그릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-130">The <xref:System.Windows.Shapes.Path> class enables you to draw curves and complex shapes.</span></span> <span data-ttu-id="1c969-131">이러한 곡선 및 도형은 사용 하 여 설명 됩니다 <xref:System.Windows.Media.Geometry> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-131">These curves and shapes are described using <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="1c969-132">사용 하는 <xref:System.Windows.Shapes.Path>, 만든를 <xref:System.Windows.Media.Geometry> 를 설정 하는 데 사용 합니다 <xref:System.Windows.Shapes.Path> 개체의 <xref:System.Windows.Shapes.Path.Data%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-132">To use a <xref:System.Windows.Shapes.Path>, you create a <xref:System.Windows.Media.Geometry> and use it to set the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Path.Data%2A> property.</span></span>  
  
 <span data-ttu-id="1c969-133">여러 가지 <xref:System.Windows.Media.Geometry> 개체에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-133">There are a variety of <xref:System.Windows.Media.Geometry> objects to choose from.</span></span> <span data-ttu-id="1c969-134">합니다 <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, 및 <xref:System.Windows.Media.EllipseGeometry> 클래스는 비교적 간단한 도형을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-134">The <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, and <xref:System.Windows.Media.EllipseGeometry> classes describe relatively simple shapes.</span></span> <span data-ttu-id="1c969-135">보다 복잡 한 도형을 만들거나 곡선을 사용 하 여를 <xref:System.Windows.Media.PathGeometry>입니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-135">To create more complex shapes or create curves, use a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
<a name="pathgeometry"></a>   
### <a name="pathgeometry-and-pathsegments"></a><span data-ttu-id="1c969-136">PathGeometry 및 PathSegments</span><span class="sxs-lookup"><span data-stu-id="1c969-136">PathGeometry and PathSegments</span></span>  
 <span data-ttu-id="1c969-137"><xref:System.Windows.Media.PathGeometry> 개체는 하나 이상의 이루어져 <xref:System.Windows.Media.PathFigure> 객체; 각 <xref:System.Windows.Media.PathFigure> 다른 "그림" 또는 도형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-137"><xref:System.Windows.Media.PathGeometry> objects are comprised of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="1c969-138">각 <xref:System.Windows.Media.PathFigure> 자체는 하나 이상의 구성 <xref:System.Windows.Media.PathSegment> 각각이 그림 또는 도형의 연결 된 부분을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-138">Each <xref:System.Windows.Media.PathFigure> is itself comprised of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="1c969-139">세그먼트 형식은 다음과 같습니다: <xref:System.Windows.Media.LineSegment>하십시오 <xref:System.Windows.Media.BezierSegment>, 및 <xref:System.Windows.Media.ArcSegment>합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-139">Segment types include the following: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>, and <xref:System.Windows.Media.ArcSegment>.</span></span>  
  
 <span data-ttu-id="1c969-140">다음 예제에서는 <xref:System.Windows.Shapes.Path> 정방형 베 지 어 곡선을 그리는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-140">In the following example, a <xref:System.Windows.Shapes.Path> is used to draw a quadratic Bezier curve.</span></span>  
  
 [!code-xaml[geometrysample#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="1c969-141">다음 그림에서는 렌더링된 도형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-141">The following image shows the rendered shape.</span></span>  
  
 <span data-ttu-id="1c969-142">![경로 그림](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path2.gif "shape_ovw_path2")</span><span class="sxs-lookup"><span data-stu-id="1c969-142">![Path illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path2.gif "shape_ovw_path2")</span></span>  
  
 <span data-ttu-id="1c969-143">에 대 한 자세한 내용은 <xref:System.Windows.Media.PathGeometry> 및 다른 <xref:System.Windows.Media.Geometry> 클래스를 참조 합니다 [기 하 도형 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-143">For more information about <xref:System.Windows.Media.PathGeometry> and the other <xref:System.Windows.Media.Geometry> classes, see the [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span></span>  
  
<a name="pathdatastring"></a>   
### <a name="xaml-abbreviated-syntax"></a><span data-ttu-id="1c969-144">XAML 약식 구문</span><span class="sxs-lookup"><span data-stu-id="1c969-144">XAML Abbreviated Syntax</span></span>  
 <span data-ttu-id="1c969-145">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]를 설명 하는 특수 한 축약된 구문을 사용할 수도 있습니다는 <xref:System.Windows.Shapes.Path>합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-145">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may also use a special abbreviated syntax to describe a <xref:System.Windows.Shapes.Path>.</span></span> <span data-ttu-id="1c969-146">다음 예제에서는 약식 구문이 복잡한 도형을 그리는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-146">In the following example, abbreviated syntax is used to draw a complex shape.</span></span>  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"   
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 <span data-ttu-id="1c969-147">다음 이미지는 렌더링 된 표시 <xref:System.Windows.Shapes.Path>합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-147">The following image shows a rendered <xref:System.Windows.Shapes.Path>.</span></span>  
  
 <span data-ttu-id="1c969-148">![경로 그림](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path.PNG "shape_ovw_path")</span><span class="sxs-lookup"><span data-stu-id="1c969-148">![Path illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path.PNG "shape_ovw_path")</span></span>  
  
 <span data-ttu-id="1c969-149">합니다 <xref:System.Windows.Shapes.Path.Data%2A> 특성 문자열에 나타난 M의 좌표계에 경로의 시작점을 설정 하는 "moveto" 명령으로 시작 된 <xref:System.Windows.Controls.Canvas>합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-149">The <xref:System.Windows.Shapes.Path.Data%2A> attribute string begins with the "moveto" command, indicated by M, which establishes a start point for the path in the coordinate system of the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="1c969-150"><xref:System.Windows.Shapes.Path> 데이터 매개 변수 대/소문자를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-150"><xref:System.Windows.Shapes.Path> data parameters are case-sensitive.</span></span> <span data-ttu-id="1c969-151">대문자 M은 새로운 현재 점의 절대 위치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-151">The capital M indicates an absolute location for the new current point.</span></span> <span data-ttu-id="1c969-152">소문자 m은 상대 좌표를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-152">A lowercase m would indicate relative coordinates.</span></span> <span data-ttu-id="1c969-153">첫 번째 세그먼트는 2개의 제어점 (100,25) 및 (400,350)을 사용하여 그린, (100,200)에서 시작하고 (400,175)에서 끝나는 입방형 3차원 곡선입니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-153">The first segment is a cubic Bezier curve beginning at (100,200) and ending at (400,175), drawn using the two control points (100,25) and (400,350).</span></span> <span data-ttu-id="1c969-154">이 세그먼트에서 C 명령으로 표시 됩니다는 <xref:System.Windows.Shapes.Path.Data%2A> 문자열 특성.</span><span class="sxs-lookup"><span data-stu-id="1c969-154">This segment is indicated by the C command in the <xref:System.Windows.Shapes.Path.Data%2A> attribute string.</span></span> <span data-ttu-id="1c969-155">마찬가지로 대문자 C는 절대 경로를 나타내고 소문자 c는 상대 경로를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-155">Again, the capital C indicates an absolute path; the lowercase c would indicate a relative path.</span></span>  
  
 <span data-ttu-id="1c969-156">두 번째 세그먼트는 절대 가로 "lineto" 명령 H로 시작합니다. 이 명령은 이전 하위 경로의 엔드포인트(400,175)에서 새 엔드포인트(280,175)까지 그리는 선을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-156">The second segment begins with an absolute horizontal "lineto" command H, which specifies a line drawn from the preceding subpath's endpoint (400,175) to a new endpoint (280,175).</span></span> <span data-ttu-id="1c969-157">지정 된 값은 가로 "lineto" 명령이 이기 때문에 *x*-조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-157">Because it is a horizontal "lineto" command, the value specified is an *x*-coordinate.</span></span>  
  
 <span data-ttu-id="1c969-158">전체 경로 구문에 대 한 참조를 <xref:System.Windows.Shapes.Path.Data%2A> 참조 및 [PathGeometry를 사용 하 여 도형 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-158">For the complete path syntax, see the <xref:System.Windows.Shapes.Path.Data%2A> reference and [Create a Shape by Using a PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  
  
<a name="fillpaint"></a>   
## <a name="painting-shapes"></a><span data-ttu-id="1c969-159">도형 그리기</span><span class="sxs-lookup"><span data-stu-id="1c969-159">Painting Shapes</span></span>  
 <span data-ttu-id="1c969-160"><xref:System.Windows.Media.Brush> 개체는 도형의 그리는 데 사용 됩니다 <xref:System.Windows.Shapes.Shape.Stroke%2A> 고 <xref:System.Windows.Shapes.Shape.Fill%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-160"><xref:System.Windows.Media.Brush> objects are used to paint a shape's <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="1c969-161">다음 예제에서는, 스트로크 및 채우기는 <xref:System.Windows.Shapes.Ellipse> 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-161">In the following example, the stroke and fill of an <xref:System.Windows.Shapes.Ellipse> are specified.</span></span> <span data-ttu-id="1c969-162">브러시 속성에 대한 유효한 입력은 키워드 또는 16진수 색 값일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-162">Note that valid input for brush properties can be either a keyword or hexadecimal color value.</span></span> <span data-ttu-id="1c969-163">속성을 사용할 수 있는 색 키워드에 대 한 자세한 내용은 참조는 <xref:System.Windows.Media.Colors> 클래스는 <xref:System.Windows.Media> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-163">For more information about available color keywords, see properties of the <xref:System.Windows.Media.Colors> class in the <xref:System.Windows.Media> namespace.</span></span>  
  
```xaml
<Canvas Background="LightGray">   
   <Ellipse  
      Canvas.Top="50"  
      Canvas.Left="50"  
      Fill="#FFFFFF00"  
      Height="75"  
      Width="75"  
      StrokeThickness="5"  
      Stroke="#FF0000FF"/>  
</Canvas>  
```  
  
 <span data-ttu-id="1c969-164">다음 이미지는 렌더링 된 표시 <xref:System.Windows.Shapes.Ellipse>합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-164">The following image shows the rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="1c969-165">![타원](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span><span class="sxs-lookup"><span data-stu-id="1c969-165">![An ellipse](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span></span>  
  
 <span data-ttu-id="1c969-166">명시적으로 만들려면 속성 요소 구문을 사용할 수는 또는 <xref:System.Windows.Media.SolidColorBrush> 단색으로 도형을 그리기 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-166">Alternatively, you can use property element syntax to explicitly create a <xref:System.Windows.Media.SolidColorBrush> object to paint the shape with a solid color.</span></span>  
  
```xaml
<!-- This polygon shape uses pre-defined color values for its Stroke and  
     Fill properties.   
     The SolidColorBrush's Opacity property affects the fill color in   
     this case by making it slightly transparent (opacity of 0.4) so   
     that it blends with any underlying color. -->  
  
<Polygon  
    Points="300,200 400,125 400,275 300,200"  
    Stroke="Purple"   
    StrokeThickness="2">  
    <Polygon.Fill>  
       <SolidColorBrush Color="Blue" Opacity="0.4"/>  
    </Polygon.Fill>  
</Polygon>  
```  
  
 <span data-ttu-id="1c969-167">다음 그림은 렌더링된 도형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-167">The following illustration shows the rendered shape.</span></span>  
  
 <span data-ttu-id="1c969-168">![SolidColorBrush 그림](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span><span class="sxs-lookup"><span data-stu-id="1c969-168">![SolidColorBrush illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span></span>  
  
 <span data-ttu-id="1c969-169">그라데이션, 이미지, 패턴 등으로 도형의 스트로크나 채우기를 그릴 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-169">You can also paint a shape's stroke or fill with gradients, images, patterns, and more.</span></span> <span data-ttu-id="1c969-170">자세한 내용은 참조는 [단색 및 그라데이션 개요 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-170">For more information, see the [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
<a name="stretchableshapessection"></a>   
## <a name="stretchable-shapes"></a><span data-ttu-id="1c969-171">확장 가능한 도형</span><span class="sxs-lookup"><span data-stu-id="1c969-171">Stretchable Shapes</span></span>  
 <span data-ttu-id="1c969-172">합니다 <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, 및 <xref:System.Windows.Shapes.Rectangle> 모든 클래스는 <xref:System.Windows.Shapes.Shape.Stretch%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-172">The <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle> classes all have a <xref:System.Windows.Shapes.Shape.Stretch%2A> property.</span></span> <span data-ttu-id="1c969-173">이 속성을 결정 하는 방법을 <xref:System.Windows.Shapes.Shape> 개체의 콘텐츠 (그릴 모양)을 채우도록 확장 되는 <xref:System.Windows.Shapes.Shape> 개체의 레이아웃 공간.</span><span class="sxs-lookup"><span data-stu-id="1c969-173">This property determines how a <xref:System.Windows.Shapes.Shape> object's contents (the shape to be drawn) is stretched to fill the <xref:System.Windows.Shapes.Shape> object's layout space.</span></span> <span data-ttu-id="1c969-174">A <xref:System.Windows.Shapes.Shape> 개체의 레이아웃 공간은 공간의 크기를 <xref:System.Windows.Shapes.Shape> 에서 할당 하는 레이아웃 시스템으로 인해 명시적 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 설정 또는 때문에 해당 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 및 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-174">A <xref:System.Windows.Shapes.Shape> object's layout space is the amount of space the <xref:System.Windows.Shapes.Shape> is allocated by the layout system, because of either an explicit <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> setting or because of its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> settings.</span></span> <span data-ttu-id="1c969-175">Windows Presentation Foundation의 레이아웃에 대 한 자세한 내용은 참조 하세요. [레이아웃](../../../../docs/framework/wpf/advanced/layout.md) 개요.</span><span class="sxs-lookup"><span data-stu-id="1c969-175">For additional information on layout in Windows Presentation Foundation, see [Layout](../../../../docs/framework/wpf/advanced/layout.md) overview.</span></span>  
  
 <span data-ttu-id="1c969-176">Stretch 속성은 다음 값 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-176">The Stretch property takes one of the following values:</span></span>  
  
-   <span data-ttu-id="1c969-177"><xref:System.Windows.Media.Stretch.None>: <xref:System.Windows.Shapes.Shape> 개체의 콘텐츠가 확장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-177"><xref:System.Windows.Media.Stretch.None>: The <xref:System.Windows.Shapes.Shape> object's contents are not stretched.</span></span>  
  
-   <span data-ttu-id="1c969-178"><xref:System.Windows.Media.Stretch.Fill>: <xref:System.Windows.Shapes.Shape> 개체의 콘텐츠가 레이아웃 공간을 채우도록 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-178"><xref:System.Windows.Media.Stretch.Fill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to fill its layout space.</span></span>  <span data-ttu-id="1c969-179">가로 세로 비율은 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-179">Aspect ratio is not preserved.</span></span>  
  
-   <span data-ttu-id="1c969-180"><xref:System.Windows.Media.Stretch.Uniform>: <xref:System.Windows.Shapes.Shape> 개체의 콘텐츠가 원래 가로 세로 비율을 유지 하면서 레이아웃 공간에 맞게 가능한 만큼 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-180"><xref:System.Windows.Media.Stretch.Uniform>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched as much as possible to fill its layout space while preserving its original aspect ratio.</span></span>  
  
-   <span data-ttu-id="1c969-181"><xref:System.Windows.Media.Stretch.UniformToFill>: <xref:System.Windows.Shapes.Shape> 개체의 내용을 원래 가로 세로 비율을 유지 하면서 레이아웃 공간을 완전히 채우도록 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-181"><xref:System.Windows.Media.Stretch.UniformToFill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to completely fill its layout space while preserving its original aspect ratio.</span></span>  
  
 <span data-ttu-id="1c969-182">인 경우는 <xref:System.Windows.Shapes.Shape> 개체의 콘텐츠가 확장는 <xref:System.Windows.Shapes.Shape> 확장 후 개체의 윤곽선을 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-182">Note that, when a <xref:System.Windows.Shapes.Shape> object's contents are stretched, the <xref:System.Windows.Shapes.Shape> object's outline is painted after the stretching.</span></span>  
  
 <span data-ttu-id="1c969-183">다음 예제에서는 <xref:System.Windows.Shapes.Polygon> (1, 1)를 (0, 1)를 (0, 0)에서 아주 작은 삼각형을 그리는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-183">In the following example, a <xref:System.Windows.Shapes.Polygon> is used to draw a very small triangle from (0,0) to (0,1) to (1,1).</span></span> <span data-ttu-id="1c969-184"><xref:System.Windows.Shapes.Polygon> 개체의 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 100으로 설정 됩니다 하 고 해당 stretch 속성은 Fill로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-184">The <xref:System.Windows.Shapes.Polygon> object's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> are set to 100, and its stretch property is set to Fill.</span></span> <span data-ttu-id="1c969-185">결과적으로 <xref:System.Windows.Shapes.Polygon> 개체의 콘텐츠 (삼각형)는 큰 공간을 채우도록 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-185">As a result, the <xref:System.Windows.Shapes.Polygon> object's contents (the triangle) are stretched to fill the larger space.</span></span>  
  
```xaml
<Polygon  
  Points="0,0 0,1 1,1"  
  Fill="Blue"  
  Width="100"  
  Height="100"  
  Stretch="Fill"  
  Stroke="Black"  
  StrokeThickness="2" />  
```

```csharp
PointCollection myPointCollection = new PointCollection();  
myPointCollection.Add(new Point(0,0));  
myPointCollection.Add(new Point(0,1));  
myPointCollection.Add(new Point(1,1));  
  
Polygon myPolygon = new Polygon();  
myPolygon.Points = myPointCollection;  
myPolygon.Fill = Brushes.Blue;  
myPolygon.Width = 100;  
myPolygon.Height = 100;  
myPolygon.Stretch = Stretch.Fill;  
myPolygon.Stroke = Brushes.Black;  
myPolygon.StrokeThickness = 2;  
```

<a name="transforms"></a>   
## <a name="transforming-shapes"></a><span data-ttu-id="1c969-186">도형 변환</span><span class="sxs-lookup"><span data-stu-id="1c969-186">Transforming Shapes</span></span>  
 <span data-ttu-id="1c969-187"><xref:System.Windows.Media.Transform> 클래스에는 2 차원 평면에서 도형을 변환 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-187">The <xref:System.Windows.Media.Transform> class provides the means to transform shapes in a two-dimensional plane.</span></span>  <span data-ttu-id="1c969-188">다양 한 유형의 변환에는 회전 (<xref:System.Windows.Media.RotateTransform>), 크기 조정 (<xref:System.Windows.Media.ScaleTransform>), 기울이기 (<xref:System.Windows.Media.SkewTransform>), 및 변환 (<xref:System.Windows.Media.TranslateTransform>).</span><span class="sxs-lookup"><span data-stu-id="1c969-188">The different types of transformation include rotation (<xref:System.Windows.Media.RotateTransform>), scale (<xref:System.Windows.Media.ScaleTransform>), skew (<xref:System.Windows.Media.SkewTransform>), and translation (<xref:System.Windows.Media.TranslateTransform>).</span></span>  
  
 <span data-ttu-id="1c969-189">도형에 적용하는 일반적인 변환은 회전입니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-189">A common transform to apply to a shape is a rotation.</span></span>  <span data-ttu-id="1c969-190">도형을 회전 하려면 만듭니다는 <xref:System.Windows.Media.RotateTransform> 지정 하 고 해당 <xref:System.Windows.Media.RotateTransform.Angle%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-190">To rotate a shape, create a <xref:System.Windows.Media.RotateTransform> and specify its <xref:System.Windows.Media.RotateTransform.Angle%2A>.</span></span> <span data-ttu-id="1c969-191"><xref:System.Windows.Media.RotateTransform.Angle%2A> 45의 요소를 회전 45도 시계 방향으로; 90 요소를 회전 90도 시계 방향으로; 등입니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-191">An <xref:System.Windows.Media.RotateTransform.Angle%2A> of 45 rotates the element 45 degrees clockwise; an angle of 90 rotates the element 90 degrees clockwise; and so on.</span></span> <span data-ttu-id="1c969-192">설정 된 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 속성 요소가 회전 되는 시점을 제어 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="1c969-192">Set the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties if you want to control the point about which the element is rotated.</span></span> <span data-ttu-id="1c969-193">이러한 속성 값은 변환할 요소의 좌표 공간으로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-193">These property values are expressed in the coordinate space of the element being transformed.</span></span> <span data-ttu-id="1c969-194"><xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 기본값이 0입니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-194"><xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> have default values of zero.</span></span> <span data-ttu-id="1c969-195">마지막으로 적용 된 <xref:System.Windows.Media.RotateTransform> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-195">Finally, apply the <xref:System.Windows.Media.RotateTransform> to the element.</span></span> <span data-ttu-id="1c969-196">변환이 레이아웃에 영향을 줄에 사용 하지 않으려는 경우 도형의 설정 <xref:System.Windows.UIElement.RenderTransform%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-196">If you don't want the transform to affect layout, set the shape's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 <span data-ttu-id="1c969-197">다음 예제에서는 <xref:System.Windows.Media.RotateTransform> 도형의 왼쪽된 위 모퉁이 (0, 0)에 대 한 도형을 45도 회전 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-197">In the following example, a <xref:System.Windows.Media.RotateTransform> is used to rotate a shape 45 degrees about the shape's top left corner (0,0).</span></span>  
  
 [!code-xaml[transformssample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 <span data-ttu-id="1c969-198">다음 예제에서는 다른 모양이 45도 회전되지만 이번에는 점 (25,50)을 기준으로 회전됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-198">In the next example, another shape is rotated 45 degrees, but this time it's rotated about the point (25,50).</span></span>  
  
 [!code-xaml[transformssample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 <span data-ttu-id="1c969-199">다음 그림에서는 두 변환을 적용한 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-199">The following illustration shows the results of applying the two transforms.</span></span>  
  
 <span data-ttu-id="1c969-200">![여러 중심점을 사용한 45도 회전](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="1c969-200">![45 degree rotations with different center points](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
  
 <span data-ttu-id="1c969-201">이전 예제에서는 각 도형 개체에 단일 변환이 적용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-201">In the previous examples, a single transform was applied to each shape object.</span></span> <span data-ttu-id="1c969-202">여러 변환 셰이프 (또는 다른 UI 요소)를 적용 하려면 사용을 <xref:System.Windows.Media.TransformGroup>입니다.</span><span class="sxs-lookup"><span data-stu-id="1c969-202">To apply multiple transforms to a shape (or any other UI element), use a <xref:System.Windows.Media.TransformGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c969-203">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c969-203">See Also</span></span>  
 [<span data-ttu-id="1c969-204">2차원 그래픽 및 이미징</span><span class="sxs-lookup"><span data-stu-id="1c969-204">2D Graphics and Imaging</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [<span data-ttu-id="1c969-205">단색 및 그라데이션을 사용한 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="1c969-205">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [<span data-ttu-id="1c969-206">Geometry 개요</span><span class="sxs-lookup"><span data-stu-id="1c969-206">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="1c969-207">연습: 내 첫 WPF 데스크톱 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="1c969-207">Walkthrough: My first WPF desktop application</span></span>](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)  
 [<span data-ttu-id="1c969-208">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="1c969-208">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
