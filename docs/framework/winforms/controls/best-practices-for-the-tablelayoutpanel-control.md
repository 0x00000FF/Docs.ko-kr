---
title: "TableLayoutPanel 컨트롤에 대한 유용한 정보"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- layout [Windows Forms]
- TableLayoutPanel control [Windows Forms], best practices
- forms [Windows Forms], best practices
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- layout [Windows Forms], AutoSize
- layout [Windows Forms], best practices
- best practices [Windows Forms], tableLayoutPanel control
- sizing [Windows Forms], automatic
- automatic sizing
ms.assetid: b6706efb-d7a4-45ec-8cf4-08fa993e3afb
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8f2c5a16ea1f07f7688c9df14bdb6b29350f3acf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a><span data-ttu-id="a236f-102">TableLayoutPanel 컨트롤에 대한 유용한 정보</span><span class="sxs-lookup"><span data-stu-id="a236f-102">Best Practices for the TableLayoutPanel Control</span></span>
<span data-ttu-id="a236f-103"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 Windows Forms에서 사용 하기 전에 신중 하 게 고려해 야 하는 강력한 레이아웃 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a236f-103">The <xref:System.Windows.Forms.TableLayoutPanel> control provides powerful layout features that you should consider carefully before using on your Windows Forms.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="a236f-104">권장 사항</span><span class="sxs-lookup"><span data-stu-id="a236f-104">Recommendations</span></span>  
 <span data-ttu-id="a236f-105">다음 권장 사항을 사용 하는 데 도움이 됩니다는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 해당 최대한 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a236f-105">The following recommendations will help you use the <xref:System.Windows.Forms.TableLayoutPanel> control to its best advantage.</span></span>  
  
### <a name="targeted-use"></a><span data-ttu-id="a236f-106">사용 대상된</span><span class="sxs-lookup"><span data-stu-id="a236f-106">Targeted Use</span></span>  
 <span data-ttu-id="a236f-107">사용 된 <xref:System.Windows.Forms.TableLayoutPanel> 제한적으로 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a236f-107">Use the <xref:System.Windows.Forms.TableLayoutPanel> control sparingly.</span></span> <span data-ttu-id="a236f-108">하지 크기 조정 가능한 레이아웃을 필요로 하는 모든 상황에서 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a236f-108">You should not use it in all situations that require a resizable layout.</span></span> <span data-ttu-id="a236f-109">다음 목록에는 설명의 사용에서 가장 많이 향상 되는 레이아웃은 <xref:System.Windows.Forms.TableLayoutPanel> 제어:</span><span class="sxs-lookup"><span data-stu-id="a236f-109">The following list describes layouts that benefit most from the use of the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>  
  
-   <span data-ttu-id="a236f-110">서로 비례적으로 크기를 조정 하는 폼의 여러 부분이 있고 있는 레이아웃입니다.</span><span class="sxs-lookup"><span data-stu-id="a236f-110">Layouts in which there are multiple parts of the form that resize proportionally to each other.</span></span>  
  
-   <span data-ttu-id="a236f-111">추가 되거나 삭제 된 사용자 지정 가능한 필드가 있는 데이터 항목 형식과 같은 런타임에 동적으로 생성 되거나 수정 될 레이아웃 기본 설정을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a236f-111">Layouts that will be modified or generated dynamically at run time, such as data entry forms that have user-customizable fields added or subtracted based on preferences.</span></span>  
  
-   <span data-ttu-id="a236f-112">전반적인 고정 크기로 유지 해야 하는 레이아웃입니다.</span><span class="sxs-lookup"><span data-stu-id="a236f-112">Layouts that should remain at an overall fixed size.</span></span> <span data-ttu-id="a236f-113">예를 들어 800 x 600 보다 작게 유지 해야 하는 대화 상자를 할 수 있습니다 하지만 지역화 된 문자열을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a236f-113">For example, you may have a dialog box that should remain smaller than 800 x 600, but you need to support localized strings.</span></span>  
  
 <span data-ttu-id="a236f-114">다음 목록은 레이아웃을 사용 하 여 상당히 유용 하지 않습니다는 <xref:System.Windows.Forms.TableLayoutPanel> 제어:</span><span class="sxs-lookup"><span data-stu-id="a236f-114">The following list describes layouts that do not benefit greatly from using the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>  
  
-   <span data-ttu-id="a236f-115">간단한 데이터 입력 폼 단일 열과 레이블 및 텍스트 입력 영역으로 이루어진 단일 열입니다.</span><span class="sxs-lookup"><span data-stu-id="a236f-115">Simple data entry forms with a single column of labels and a single column of text-entry areas.</span></span>  
  
-   <span data-ttu-id="a236f-116">큰 단일 폼 크기를 조정 하면 사용 가능한 모든 공간을 채워야 하는 영역을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a236f-116">Forms with a single large display area that should fill all the available space when a resize occurs.</span></span> <span data-ttu-id="a236f-117">이 예는 단일 표시 하는 폼 <xref:System.Windows.Forms.PropertyGrid> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a236f-117">An example of this is a form that displays a single <xref:System.Windows.Forms.PropertyGrid> control.</span></span> <span data-ttu-id="a236f-118">이 경우 폼의 크기를 조정할 때 확장 해야만 수행 되기 때문에 앵커를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a236f-118">In this case, use anchoring, because nothing else should expand when the form is resized.</span></span>  
  
 <span data-ttu-id="a236f-119">선택 신중 하 게 제어 하에 있이 필요는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a236f-119">Choose carefully which controls need to be in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="a236f-120">앵커를 사용 하 여 30% 증가 하려고 텍스트 공간이 있는 경우 사용 하 여 고려는 <xref:System.Windows.Forms.Control.Anchor%2A> 속성에만 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a236f-120">If you have room for your text to grow by 30% using anchoring, consider using the <xref:System.Windows.Forms.Control.Anchor%2A> property only.</span></span> <span data-ttu-id="a236f-121">레이아웃에 필요한 공간을 예측할 수 경우 활용 <xref:System.Windows.Forms.Control.Dock%2A> 및 <xref:System.Windows.Forms.Control.Anchor%2A> 남아 있는 공간에 대 한 세부 정보를 예측 하는 것 보다 쉽습니다 및 <xref:System.Windows.Forms.Control.AutoSize%2A> 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a236f-121">If you can estimate the space required by your layout, use of <xref:System.Windows.Forms.Control.Dock%2A> and <xref:System.Windows.Forms.Control.Anchor%2A> is easier than estimating the details of remaining space and <xref:System.Windows.Forms.Control.AutoSize%2A> behavior.</span></span>  
  
 <span data-ttu-id="a236f-122">일반적으로 사용 하 여 레이아웃을 디자인 하는 경우는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 디자인을 가능한 한 단순하게 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a236f-122">In general, when designing your layout with the <xref:System.Windows.Forms.TableLayoutPanel> control, keep the design as simple as possible.</span></span>  
  
### <a name="use-the-document-outline-window"></a><span data-ttu-id="a236f-123">문서 개요 창을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="a236f-123">Use the Document Outline Window</span></span>  
 <span data-ttu-id="a236f-124">문서 개요 창 컨트롤의 z 순서와 부모-자식 관계를 조작 하는 데 사용할 수 있는 레이아웃의 트리 보기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a236f-124">The Document Outline window gives you a tree view of your layout, which you can use to manipulate the z-order and parent-child relationships of your controls.</span></span> <span data-ttu-id="a236f-125">**보기 메뉴**선택, **다른 창**을 선택한 후 **문서 개요**합니다.</span><span class="sxs-lookup"><span data-stu-id="a236f-125">From the **View menu**, select **Other Windows**, then select **Document Outline**.</span></span>  
  
### <a name="avoid-nesting"></a><span data-ttu-id="a236f-126">중첩을 하지 마십시오</span><span class="sxs-lookup"><span data-stu-id="a236f-126">Avoid Nesting</span></span>  
 <span data-ttu-id="a236f-127">다른 중첩 하지 마십시오 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 내에 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a236f-127">Avoid nesting other <xref:System.Windows.Forms.TableLayoutPanel> controls within a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="a236f-128">중첩 된 레이아웃을 디버깅 하는 것은 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a236f-128">Debugging nested layouts can be difficult.</span></span>  
  
### <a name="avoid-visual-inheritance"></a><span data-ttu-id="a236f-129">시각적 상속을 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="a236f-129">Avoid Visual Inheritance</span></span>  
 <span data-ttu-id="a236f-130"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 Windows Forms 디자이너에서 시각적 상속을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a236f-130">The <xref:System.Windows.Forms.TableLayoutPanel> control does not support visual inheritance in the Windows Forms Designer.</span></span> <span data-ttu-id="a236f-131">A <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 파생된 클래스에서 "잠겨 있음" 디자인 타임에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a236f-131">A <xref:System.Windows.Forms.TableLayoutPanel> control in a derived class appears as "locked" at design time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a236f-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a236f-132">See Also</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>
