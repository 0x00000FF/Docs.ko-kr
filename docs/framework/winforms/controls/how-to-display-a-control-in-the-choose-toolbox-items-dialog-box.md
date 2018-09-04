---
title: '방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시'
ms.date: 03/30/2017
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
ms.openlocfilehash: fdda72d60b0f18e76b03e9b7f05060a09763a3f7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43527625"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="9a243-102">방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시</span><span class="sxs-lookup"><span data-stu-id="9a243-102">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>
<span data-ttu-id="9a243-103">개발 하 고 컨트롤을 배포할 해당 컨트롤에 표시 되도록 할 수 있습니다 합니다 **도구 상자 항목 선택** 마우스 오른쪽 단추로 클릭할 때 표시 되는 대화 상자를 **도구 상자** 선택한  **항목 선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="9a243-103">As you develop and distribute controls, you may want those controls to appear in the **Choose Toolbox Items** dialog box, which is displayed when you right-click the **Toolbox** and select **Choose Items**.</span></span> <span data-ttu-id="9a243-104">AssemblyFoldersEx 등록 절차를 사용 하 여이 대화 상자에서 표시할 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a243-104">You can enable your control to appear in this dialog box by using the AssemblyFoldersEx registration procedure.</span></span>  
  
### <a name="to-display-your-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="9a243-105">도구 상자 항목 선택 대화 상자에서 컨트롤을 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="9a243-105">To display your control in the Choose Toolbox Items dialog box</span></span>  
  
-   <span data-ttu-id="9a243-106">컨트롤 어셈블리를 전역 어셈블리 캐시에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a243-106">Install your control assembly to the global assembly cache.</span></span> <span data-ttu-id="9a243-107">자세한 내용은 참조 하세요. [방법: 전역 어셈블리 캐시에 어셈블리 설치](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)</span><span class="sxs-lookup"><span data-stu-id="9a243-107">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)</span></span>  
  
     <span data-ttu-id="9a243-108">또는</span><span class="sxs-lookup"><span data-stu-id="9a243-108">-or-</span></span>  
  
-   <span data-ttu-id="9a243-109">AssemblyFoldersEx 등록 절차를 사용 하 여 컨트롤 및 해당 연결 된 디자인 타임 어셈블리를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a243-109">Register your control and its associated design-time assemblies by using the AssemblyFoldersEx registration procedure.</span></span> <span data-ttu-id="9a243-110">AssemblyFoldersEx는 타사 공급 업체에서 지원 되는 프레임 워크의 각 버전에 대 한 경로 저장 하는 위치는 레지스트리 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="9a243-110">AssemblyFoldersEx is a registry location where third-party vendors store paths for each version of the framework that they support.</span></span> <span data-ttu-id="9a243-111">참조 어셈블리를 찾는이 레지스트리 위치에 디자인 타임 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a243-111">Design-time resolution can look in this registry location to find reference assemblies.</span></span> <span data-ttu-id="9a243-112">레지스트리 스크립트를 도구 상자에 표시 하려는 컨트롤을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a243-112">The registry script can specify the controls you want to appear in the Toolbox.</span></span> <span data-ttu-id="9a243-113">자세한 내용은 [사용자 지정 컨트롤 및 디자인 타임 어셈블리 (Visual Studio 2013) 배포](https://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)합니다.</span><span class="sxs-lookup"><span data-stu-id="9a243-113">For more information, see [Deploying a Custom Control and Design-time Assemblies (Visual Studio 2013)](https://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a243-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a243-114">See Also</span></span>  
 [<span data-ttu-id="9a243-115">도구 상자 항목 선택 대화 상자(Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="9a243-115">Choose Toolbox Items Dialog Box (Visual Studio)</span></span>](https://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [<span data-ttu-id="9a243-116">사용자 지정 컨트롤 및 디자인 타임 어셈블리 (Visual Studio 2013) 배포</span><span class="sxs-lookup"><span data-stu-id="9a243-116">Deploying a Custom Control and Design-time Assemblies (Visual Studio 2013)</span></span>](https://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)  
 [<span data-ttu-id="9a243-117">디자인 타임에 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="9a243-117">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [<span data-ttu-id="9a243-118">방법: 전역 어셈블리 캐시에 어셈블리 설치</span><span class="sxs-lookup"><span data-stu-id="9a243-118">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
 [<span data-ttu-id="9a243-119">연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기</span><span class="sxs-lookup"><span data-stu-id="9a243-119">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
