---
title: 세 가지 범주의 그래픽 서비스
ms.date: 03/30/2017
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2-D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
ms.openlocfilehash: f7aa4de8a0d646c441d0921fb2561ef5a9480f4e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711232"
---
# <a name="three-categories-of-graphics-services"></a><span data-ttu-id="5f8d9-102">세 가지 범주의 그래픽 서비스</span><span class="sxs-lookup"><span data-stu-id="5f8d9-102">Three Categories of Graphics Services</span></span>
<span data-ttu-id="5f8d9-103">Windows Forms의 그래픽 제공은 다음 세 가지 광범위 한 범주에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d9-103">The graphics offerings in Windows Forms fall into the following three broad categories:</span></span>  
  
-   <span data-ttu-id="5f8d9-104">2 차원 (2-d) 벡터 그래픽</span><span class="sxs-lookup"><span data-stu-id="5f8d9-104">Two-dimensional (2-D) vector graphics</span></span>  
  
-   <span data-ttu-id="5f8d9-105">이미징</span><span class="sxs-lookup"><span data-stu-id="5f8d9-105">Imaging</span></span>  
  
-   <span data-ttu-id="5f8d9-106">입력 체계</span><span class="sxs-lookup"><span data-stu-id="5f8d9-106">Typography</span></span>  
  
## <a name="2-d-vector-graphics"></a><span data-ttu-id="5f8d9-107">2 차원 벡터 그래픽</span><span class="sxs-lookup"><span data-stu-id="5f8d9-107">2-D Vector Graphics</span></span>  
 <span data-ttu-id="5f8d9-108">2 차원 벡터 그래픽은 기본 형식입니다. 선, 곡선 및 도형; 등 좌표계의 점 집합으로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d9-108">Two-dimensional vector graphics are primitives; such as lines, curves, and figures; that are specified by sets of points on a coordinate system.</span></span> <span data-ttu-id="5f8d9-109">예를 들어 직선 두 끝점으로 지정 된 및 사각형 왼쪽 위 구석에 해당 하 고 너비와 높이 지정 하는 숫자의 쌍의 위치를 제공 하는 지점으로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d9-109">For example, a straight line is specified by its two endpoints, and a rectangle is specified by a point giving the location of its upper-left corner and a pair of numbers giving its width and height.</span></span> <span data-ttu-id="5f8d9-110">간단한 경로 직선으로 연결 된 점의 배열에 의해 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d9-110">A simple path is specified by an array of points that are connected by straight lines.</span></span> <span data-ttu-id="5f8d9-111">베 지 어 스플라인을 지정 되는 정교한 곡선에서 4 개의 제어점입니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d9-111">A Bézier spline is a sophisticated curve specified by four control points.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="5f8d9-112">클래스 및 구조체는 기본 형식 자체에 대 한 정보를 저장 하는, 기본 형식 그리는 방법에 대 한 정보를 저장 하는 클래스 및 드로잉을 실제로 수행 하는 클래스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d9-112">provides classes and structures that store information about the primitives themselves, classes that store information about how the primitives will be drawn, and classes that actually do the drawing.</span></span> <span data-ttu-id="5f8d9-113">예를 들어 합니다 <xref:System.Drawing.Rectangle> 구조; 사각형의 크기와 위치를 저장 합니다 <xref:System.Drawing.Pen> 선 색, 선 두께 및 선 스타일에 대 한 정보를 저장 하는 클래스 및 <xref:System.Drawing.Graphics> 클래스에 선, 사각형, 경로 그리기 위한 메서드 및 다른 수치입니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d9-113">For example, the <xref:System.Drawing.Rectangle> structure stores the location and size of a rectangle; the <xref:System.Drawing.Pen> class stores information about line color, line width, and line style; and the <xref:System.Drawing.Graphics> class has methods for drawing lines, rectangles, paths, and other figures.</span></span> <span data-ttu-id="5f8d9-114">또한 여러 <xref:System.Drawing.Brush> 하는 방법에 대 한 정보를 저장 하는 클래스 수치 닫히고 경로 색 또는 패턴을 사용 하 여 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d9-114">There are also several <xref:System.Drawing.Brush> classes that store information about how closed figures and paths will be filled with colors or patterns.</span></span>  
  
 <span data-ttu-id="5f8d9-115">그래픽 명령 시퀀스는 벡터 이미지 메타 파일에 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d9-115">You can record a vector image, which is a sequence of graphics commands, in a metafile.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="5f8d9-116">제공 된 <xref:System.Drawing.Imaging.Metafile> 기록, 표시 및 메타 파일을 저장 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d9-116">provides the <xref:System.Drawing.Imaging.Metafile> class for recording, displaying, and saving metafiles.</span></span> <span data-ttu-id="5f8d9-117">사용 하 여 합니다 <xref:System.Drawing.Imaging.MetafileHeader> 고 <xref:System.Drawing.Imaging.MetaHeader> 클래스 메타 파일 헤더에 저장 된 데이터를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d9-117">With the <xref:System.Drawing.Imaging.MetafileHeader> and <xref:System.Drawing.Imaging.MetaHeader> classes, you can inspect the data stored in a metafile header.</span></span>  
  
## <a name="imaging"></a><span data-ttu-id="5f8d9-118">이미징</span><span class="sxs-lookup"><span data-stu-id="5f8d9-118">Imaging</span></span>  
 <span data-ttu-id="5f8d9-119">특정 종류의 그림 어렵거나 벡터 그래픽 기술을 사용 하 여 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d9-119">Certain kinds of pictures are difficult or impossible to display with the techniques of vector graphics.</span></span> <span data-ttu-id="5f8d9-120">예를 들어, 도구 모음 단추에서 사진과 아이콘으로 표시 되는 그림은 선 및 곡선 컬렉션으로 지정 하기 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d9-120">For example, the pictures on toolbar buttons and the pictures that appear as icons are difficult to specify as collections of lines and curves.</span></span> <span data-ttu-id="5f8d9-121">붐비는 야구 경기장 고해상도 디지털 사진 벡터 기법을 사용 하 여 만들려는 훨씬 더 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d9-121">A high-resolution digital photograph of a crowded baseball stadium is even more difficult to create with vector techniques.</span></span> <span data-ttu-id="5f8d9-122">이 유형의 이미지는 화면에 있는 각 점의 색을 나타내는 숫자의 배열 하는 비트맵으로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d9-122">Images of this type are stored as bitmaps, which are arrays of numbers that represent the colors of individual dots on the screen.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="5f8d9-123">제공 된 <xref:System.Drawing.Bitmap> 표시, 조작 및 비트맵 저장에 대 한 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d9-123">provides the <xref:System.Drawing.Bitmap> class for displaying, manipulating, and saving bitmaps.</span></span>  
  
## <a name="typography"></a><span data-ttu-id="5f8d9-124">입력 체계</span><span class="sxs-lookup"><span data-stu-id="5f8d9-124">Typography</span></span>  
 <span data-ttu-id="5f8d9-125">입력 체계에는 다양 한 글꼴, 크기 및 스타일의에서 텍스트 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d9-125">Typography is the display of text in a variety of fonts, sizes, and styles.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="5f8d9-126">이 복잡 한 작업에 대 한 광범위 한 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d9-126">provides extensive support for this complex task.</span></span> <span data-ttu-id="5f8d9-127">새로운 기능 중 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 텍스트를 제공 하는 하위 픽셀 앤티 앨리어싱 렌더링 되는 LCD 화면의 부드러운 모양으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d9-127">One of the new features in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] is subpixel antialiasing, which gives text rendered on an LCD screen a smoother appearance.</span></span>  
  
 <span data-ttu-id="5f8d9-128">또한 Windows Forms 제공 옵션을 사용 하 여 텍스트를 그릴 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 기능에서 해당 <xref:System.Windows.Forms.TextRenderer> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d9-128">In addition, Windows Forms offers the option to draw text with [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] capabilities in its <xref:System.Windows.Forms.TextRenderer> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f8d9-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="5f8d9-129">See also</span></span>
- [<span data-ttu-id="5f8d9-130">그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="5f8d9-130">Graphics Overview</span></span>](graphics-overview-windows-forms.md)
- [<span data-ttu-id="5f8d9-131">GDI + 관리 코드 정보</span><span class="sxs-lookup"><span data-stu-id="5f8d9-131">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)
- [<span data-ttu-id="5f8d9-132">관리되는 그래픽 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="5f8d9-132">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)
