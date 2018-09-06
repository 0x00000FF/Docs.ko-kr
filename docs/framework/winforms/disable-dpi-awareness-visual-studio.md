---
title: Visual Studio에서 인식 되는 DPI를 사용 하지 않도록 설정
description: HDPI 모니터에 Windows Forms 디자이너 및 DPI를 인식 하지 못하는 프로세스로 Visual Studio를 실행 하는 방법의 제한 사항에 설명 합니다.
ms.date: 08/14/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 65c997e12aa033b3b08d32c8ab76372e3c52a803
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43748118"
---
# <a name="disable-dpi-awareness-in-visual-studio"></a><span data-ttu-id="6a63a-103">Visual Studio에서 인식 되는 DPI를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="6a63a-103">Disable DPI-awareness in Visual Studio</span></span>

<span data-ttu-id="6a63a-104">Visual Studio는 dpi 인식 응용 프로그램에 자동으로 표시 배율을 즉 인치당입니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-104">Visual Studio is a dots per inch (DPI) aware application, which means the display scales automatically.</span></span> <span data-ttu-id="6a63a-105">응용 프로그램에서 DPI에서 인식 되지 않으면 알 경우 운영 체제에 비트맵으로 응용 프로그램을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-105">If an application states that it's not DPI-aware, the operating system scales the application as a bitmap.</span></span> <span data-ttu-id="6a63a-106">이 동작은 DPI 가상화를 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-106">This behavior is also called DPI virtualization.</span></span> <span data-ttu-id="6a63a-107">응용 프로그램이 여전히 100% 배율 조정 또는 96dpi에서 실행 되 고 있는지 것으로 생각 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-107">The application still thinks that it's running at 100% scaling, or 96 dpi.</span></span>

## <a name="windows-forms-designer-on-hdpi-monitors"></a><span data-ttu-id="6a63a-108">HDPI 모니터에 Windows Forms 디자이너</span><span class="sxs-lookup"><span data-stu-id="6a63a-108">Windows Forms Designer on HDPI monitors</span></span>

<span data-ttu-id="6a63a-109">합니다 **Windows Forms 디자이너** Visual Studio에 없는 확장 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-109">The **Windows Forms Designer** in Visual Studio doesn't have scaling support.</span></span> <span data-ttu-id="6a63a-110">이 인해 표시 문제에서 몇 가지 형태를 열면 합니다 **Windows Forms 디자이너** hdpi 모니터 인치당 높은에서.</span><span class="sxs-lookup"><span data-stu-id="6a63a-110">This causes display issues when you open some forms in the **Windows Forms Designer** on high dots per inch (HDPI) monitors.</span></span> <span data-ttu-id="6a63a-111">예를 들어 다음 그림에 나와 있는 것 처럼 중복 컨트롤 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-111">For examples, controls can appear to overlap as shown in the following image:</span></span>

![HDPI 모니터에서 Windows Forms 디자이너](media/disable-dpi-awareness-visual-studio/win-forms-designer-hdpi.png)

<span data-ttu-id="6a63a-113">Visual Studio 2017 버전 15.8 및 나중에 폼을 여는 경우에 **Windows Forms 디자이너** HDPI 모니터를에서 Visual Studio 디자이너의 맨 위에 있는 노란색 표시줄 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-113">In Visual Studio 2017 version 15.8 and later, when you open a form in the **Windows Forms Designer** on an HDPI monitor, Visual Studio displays a yellow informational bar at the top of the designer:</span></span>

![DPI를 인식 하지 못하는 모드에서 다시 시작 하려면 Visual Studio의 정보 표시줄](media/disable-dpi-awareness-visual-studio/scaling-gold-bar.png)

<span data-ttu-id="6a63a-115">메시지 읽고 **기본 디스플레이에 크기 조정 (192dpi) 200%로 설정 됩니다. 디자이너 창에서 렌더링 문제를 발생할 수 있습니다이 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6a63a-115">The message reads **Scaling on your main display is set to 200% (192 dpi). This might cause rendering problems in the designer window.**</span></span>

<span data-ttu-id="6a63a-116">디자이너에서 작동 하지 않는 경우 폼의 레이아웃을 조정할 필요가 없습니다 정보 표시줄을 무시 하 고 다른 형식의 디자이너 또는 코드 편집기에서 작업을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-116">If you aren't working in the designer and don't need to adjust the layout of your form, you can ignore the informational bar and continue working in the code editor or in other types of designers.</span></span> <span data-ttu-id="6a63a-117">만 **Windows Forms 디자이너** 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-117">Only the **Windows Forms Designer** is affected.</span></span> <span data-ttu-id="6a63a-118">작업할 필요가 없는 경우는 **Windows Forms 디자이너**, 다음 섹션에서는 도움이 [문제를 해결](#to-resolve-the-problem)합니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-118">If you do need to work in the **Windows Forms Designer**, the next section helps you [resolve the problem](#to-resolve-the-problem).</span></span>

## <a name="to-resolve-the-problem"></a><span data-ttu-id="6a63a-119">문제를 해결 하려면</span><span class="sxs-lookup"><span data-stu-id="6a63a-119">To resolve the problem</span></span>

<span data-ttu-id="6a63a-120">표시 문제를 해결 하는 방법은 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-120">There are three options to resolve the display problem.</span></span>

### <a name="restart-visual-studio-as-a-dpi-unaware-process"></a><span data-ttu-id="6a63a-121">DPI를 인식 하지 못하는 프로세스로 Visual Studio를 다시 시작</span><span class="sxs-lookup"><span data-stu-id="6a63a-121">Restart Visual Studio as a DPI-unaware process</span></span>

<span data-ttu-id="6a63a-122">DPI를 인식 하지 못하는 프로세스로 노란색 정보 모음에서 옵션을 선택 하면 Visual Studio를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-122">You can restart Visual Studio as a DPI-unaware process by selecting the option on the yellow informational bar.</span></span> <span data-ttu-id="6a63a-123">이 기본 방법은 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-123">This is the preferred way of resolving the problem.</span></span>

<span data-ttu-id="6a63a-124">Visual Studio DPI를 인식 하지 못하는 프로세스로 실행 되 면 디자이너 레이아웃 문제가 해결 되 면 있지만 글꼴 희미하게 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-124">When Visual Studio runs as a DPI-unaware process, the designer layout issues are resolved, but fonts may appear blurry.</span></span> <span data-ttu-id="6a63a-125">Visual Studio는 DPI를 인식 하지 못하는 프로세스로 실행 될 때 다른 노란색 정보 메시지를 표시 **Visual Studio DPI를 인식 하지 못하는 프로세스로 실행 됩니다. WPF 및 XAML 디자이너를 제대로 표시 되지 않을 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6a63a-125">Visual Studio displays a different yellow informational message when it runs as a DPI-unaware process that says **Visual Studio is running as a DPI-unaware process. WPF and XAML designers might not display correctly.**</span></span> <span data-ttu-id="6a63a-126">정보 표시줄 하는 옵션도 제공 **DPI 인식 프로세스로 Visual Studio를 다시 시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-126">The informational bar also provides an option to **Restart Visual Studio as a DPI-aware process**.</span></span>

> [!NOTE]
> - <span data-ttu-id="6a63a-127">DPI를 인식 하지 못하는 프로세스로 다시 시작 하는 옵션을 선택 하면 Visual Studio 도구 창 도킹 되지 않았는지 있었습니다, 해당 도구 창의 위치 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-127">If you had undocked tool windows in Visual Studio when you selected the option to restart as a DPI-unaware process, the position of those tool windows may change.</span></span>
> - <span data-ttu-id="6a63a-128">있는 경우 또는 Visual Basic 기본 프로필을 사용 하는 경우는 **만들어질 때 새 프로젝트 저장** 옵션의 선택을 취소 **도구** > **옵션**  >  **프로젝트 및 솔루션**, DPI를 인식 하지 못하는 프로세스로 다시 시작 될 때 Visual Studio 프로젝트를 다시 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-128">If you use the default Visual Basic profile, or if you have the **Save new projects when created** option deselected in **Tools** > **Options** > **Projects and Solutions**, Visual Studio cannot reopen your project when it restarts as a DPI-unaware process.</span></span> <span data-ttu-id="6a63a-129">아래에서 선택 하 여 프로젝트를 열 수는 있지만 **파일** > **최근 프로젝트 및 솔루션**합니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-129">However, you can open the project by selecting it under **File** > **Recent Projects and Solutions**.</span></span>

<span data-ttu-id="6a63a-130">작업 완료 되 면 DPI 인식 프로세스로 Visual Studio를 다시 시작 해야 합니다 **Windows Forms 디자이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-130">It's important to restart Visual Studio as a DPI-aware process when you're finished working in the **Windows Forms Designer**.</span></span> <span data-ttu-id="6a63a-131">DPI를 인식 하지 못하는 프로세스로 실행 중인 경우 글꼴 흐리게 수 및와 같은 문제를 다른 디자이너에 표시 될 수 있습니다 합니다 **XAML 디자이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-131">When it's running as a DPI-unaware process, fonts can look blurry and you may see issues in other designers such as the **XAML Designer**.</span></span> <span data-ttu-id="6a63a-132">닫고 DPI를 인식 하지 못하는 모드에서 실행 되는 경우에 Visual Studio를 다시 열 경우 됩니다 DPI 인식 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-132">If you close and reopen Visual Studio when it's running in DPI-unaware mode, it becomes DPI-aware again.</span></span> <span data-ttu-id="6a63a-133">클릭할 수도 있습니다는 **DPI 인식 프로세스로 Visual Studio를 다시 시작** 정보 표시줄에 대 한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-133">You can also click the **Restart Visual Studio as a DPI-aware process** option in the informational bar.</span></span>

### <a name="add-a-registry-entry"></a><span data-ttu-id="6a63a-134">레지스트리 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-134">Add a registry entry</span></span>

<span data-ttu-id="6a63a-135">레지스트리를 수정 하 여 DPI를 인식 하지 못하는으로 Visual Studio를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-135">You can mark Visual Studio as DPI-unaware by modifying the registry.</span></span> <span data-ttu-id="6a63a-136">열기 **레지스트리 편집기** 항목을 추가 합니다 **실행 NT\CurrentVersion\AppCompatFlags\Layers** 하위 키:</span><span class="sxs-lookup"><span data-stu-id="6a63a-136">Open **Registry Editor** and add an entry to the **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers** subkey:</span></span>

<span data-ttu-id="6a63a-137">**항목**: %ProgramFiles (x86) %\Microsoft Visual Studio\2017\your-edition\Common7\IDE\devenv.exe</span><span class="sxs-lookup"><span data-stu-id="6a63a-137">**Entry**: %ProgramFiles(x86)%\Microsoft Visual Studio\2017\your-edition\Common7\IDE\devenv.exe</span></span>

<span data-ttu-id="6a63a-138">**형식**: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6a63a-138">**Type**: REG_SZ</span></span>

<span data-ttu-id="6a63a-139">**값**: DPIUNAWARE</span><span class="sxs-lookup"><span data-stu-id="6a63a-139">**Value**: DPIUNAWARE</span></span>

> [!NOTE]
> <span data-ttu-id="6a63a-140">Visual Studio는 레지스트리 항목을 제거할 때까지 DPI를 인식 하지 못하는 모드로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-140">Visual Studio remains in DPI-unaware mode until you remove the registry entry.</span></span>

### <a name="set-your-display-scaling-setting-to-100"></a><span data-ttu-id="6a63a-141">디스플레이 설정을 100%로 크기 조정 설정</span><span class="sxs-lookup"><span data-stu-id="6a63a-141">Set your display scaling setting to 100%</span></span>

<span data-ttu-id="6a63a-142">Windows 10에서 100%로 설정 크기 조정 하 여 표시를 설정 하려면 다음을 입력 **설정 표시** 작업 표시줄을 선택 하 고 검색 상자에에서 **표시 설정 변경**합니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-142">To set your display scaling setting to 100% in Windows 10, type **display settings** in the task bar search box, and then select **Change display settings**.</span></span> <span data-ttu-id="6a63a-143">에 **설정을** 창에서 **텍스트, 앱 및 기타 항목의 크기를 변경** 에 **100%** 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-143">In the **Settings** window, set **Change the size of text, apps, and other items** to **100%**.</span></span>

<span data-ttu-id="6a63a-144">100%로 크기 조정 디스플레이 설정 적절 하지 않을, 있으므로 사용자 인터페이스를 사용할 수 있으려면 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="6a63a-144">Setting your display scaling to 100% may be undesirable, because it can make the user interface too small to be usable.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a63a-145">참고자료</span><span class="sxs-lookup"><span data-stu-id="6a63a-145">See also</span></span>

- [<span data-ttu-id="6a63a-146">Windows Forms의 자동 크기 조정</span><span class="sxs-lookup"><span data-stu-id="6a63a-146">Automatic scaling in Windows Forms</span></span>](automatic-scaling-in-windows-forms.md)