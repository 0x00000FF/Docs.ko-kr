---
title: 기본 양식의 모양 수정 효과
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms [Windows Forms]
- inherited forms [Windows Forms], modifications to base form
- Windows Forms, base form appearance
- base forms
- inheritance [Windows Forms], forms
ms.assetid: 1c3f2b29-a05c-4c6f-aa1a-4e66b94f343a
ms.openlocfilehash: adaf9224fd340c6ea4342e2591806a7c877e83ff
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43746174"
---
# <a name="effects-of-modifying-a-base-form39s-appearance"></a><span data-ttu-id="d3f0a-102">기본 양식의 모양 수정 효과</span><span class="sxs-lookup"><span data-stu-id="d3f0a-102">Effects of Modifying a Base Form&#39;s Appearance</span></span>
<span data-ttu-id="d3f0a-103">응용 프로그램을 개발하는 동안 프로젝트(또는 다른 프로젝트)에 있는 다른 양식을 상속하는 기본 양식의 모양을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f0a-103">During application development, you may often need to change the appearance of the base form from which other forms in the project (or in other projects) are inheriting.</span></span>  
  
 <span data-ttu-id="d3f0a-104">디자인 타임에서 기본 양식의 모양 변경(속성 설정 또는 컨트롤의 더하기와 빼기)은 기본 양식을 포함하는 프로젝트를 빌드할 때 상속된 양식에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3f0a-104">At design time, changes to the base form's appearance (be it the setting of properties or the addition and subtraction of controls) are reflected on inherited forms when the project containing the base form is built.</span></span> <span data-ttu-id="d3f0a-105">단순히 기본 양식에 대한 변경 내용을 저장하기에는 충분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f0a-105">It is not sufficient for you to simply save the changes to the base form.</span></span> <span data-ttu-id="d3f0a-106">프로젝트를 빌드하려면 **빌드** 메뉴에서 **빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f0a-106">To build a project, choose **Build** from the **Build** menu.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3f0a-107">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f0a-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="d3f0a-108">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f0a-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="d3f0a-109">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3f0a-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
 <span data-ttu-id="d3f0a-110">런타임 시 기본 양식에 대한 수정은 이미 인스턴스화된 상속된 양식에 아무 영향도 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f0a-110">Modifications made to the base form at run time have no affect on inherited forms that are already instantiated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3f0a-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3f0a-111">See Also</span></span>  
 [<span data-ttu-id="d3f0a-112">base</span><span class="sxs-lookup"><span data-stu-id="d3f0a-112">base</span></span>](~/docs/csharp/language-reference/keywords/base.md)  
 [<span data-ttu-id="d3f0a-113">방법: Windows Forms 상속</span><span class="sxs-lookup"><span data-stu-id="d3f0a-113">How to: Inherit Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 [<span data-ttu-id="d3f0a-114">Windows Forms 시각적 개체 상속</span><span class="sxs-lookup"><span data-stu-id="d3f0a-114">Windows Forms Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)
