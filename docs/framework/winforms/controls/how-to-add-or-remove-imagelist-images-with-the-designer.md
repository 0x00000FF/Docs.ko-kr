---
title: "방법: 디자이너를 사용하여 ImageList 이미지 추가 또는 제거"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ce14d6f060482eb521e9812a127c6b27431121c0
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="46b2c-102">방법: 디자이너를 사용하여 ImageList 이미지 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="46b2c-102">How to: Add or Remove ImageList Images with the Designer</span></span>
<span data-ttu-id="46b2c-103">이미지를 추가할 수는 <xref:System.Windows.Forms.ImageList> 여러 가지 방법으로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b2c-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="46b2c-104">연결 된 스마트 태그를 사용 하 여 이미지를 매우 신속 하 게 추가할 수는 <xref:System.Windows.Forms.ImageList>에 다른 여러 속성을 설정 하는 경우 또는 <xref:System.Windows.Forms.ImageList>, 속성 창 사용 하 여 이미지를 추가 하는 편리한 방법을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b2c-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="46b2c-105">코드를 사용 하 여 이미지를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b2c-105">You can also add images by using code.</span></span> <span data-ttu-id="46b2c-106">코드를 사용 하 여 이미지를 추가 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: Windows Forms ImageList 구성 요소와 이미지 추가 또는 제거](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="46b2c-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="46b2c-107">채울 일반적으로 <xref:System.Windows.Forms.ImageList> 구성 요소를 이미지로 전에 컨트롤과 연결 되어 있지만이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46b2c-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46b2c-108">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b2c-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="46b2c-109">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="46b2c-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="46b2c-110">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46b2c-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="46b2c-111">추가 하거나 속성 창을 사용 하 여 이미지를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="46b2c-111">To add or remove images by using the Properties window</span></span>  
  
1.  <span data-ttu-id="46b2c-112">선택 된 <xref:System.Windows.Forms.ImageList> 구성 요소를 폼에 추가 하거나 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b2c-112">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>  
  
2.  <span data-ttu-id="46b2c-113">속성 창에서 줄임표 단추를 클릭 합니다. (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 옆에 <xref:System.Windows.Forms.ImageList.Images%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="46b2c-113">In the Properties window, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
3.  <span data-ttu-id="46b2c-114">에 **이미지 컬렉션 편집기**, 클릭 **추가** 또는 **제거** 를 추가 하거나 목록에서 이미지를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b2c-114">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>  
  
### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="46b2c-115">스마트 태그를 사용 하 여 이미지 추가 또는 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="46b2c-115">To add or remove images using the smart tag</span></span>  
  
1.  <span data-ttu-id="46b2c-116">선택 된 <xref:System.Windows.Forms.ImageList> 구성 요소를 폼에 추가 하거나 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b2c-116">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>  
  
2.  <span data-ttu-id="46b2c-117">스마트 태그 문자 모양을 클릭 (![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span><span class="sxs-lookup"><span data-stu-id="46b2c-117">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span></span>  
  
3.  <span data-ttu-id="46b2c-118">에 **ImageList 작업** 대화 상자에서 **이미지 선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="46b2c-118">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>  
  
4.  <span data-ttu-id="46b2c-119">에 **이미지 컬렉션 편집기** 클릭 **추가** 또는 **제거** 를 추가 하거나 목록에서 이미지를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b2c-119">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46b2c-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46b2c-120">See Also</span></span>  
 [<span data-ttu-id="46b2c-121">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="46b2c-121">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="46b2c-122">연습: Windows Forms 컨트롤에서 스마트 태그를 사용하여 일반 작업 수행</span><span class="sxs-lookup"><span data-stu-id="46b2c-122">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)  
 [<span data-ttu-id="46b2c-123">ImageList 구성 요소</span><span class="sxs-lookup"><span data-stu-id="46b2c-123">ImageList Component</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
