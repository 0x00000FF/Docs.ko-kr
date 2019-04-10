---
title: '방법: WPF 애플리케이션에 시작 화면 추가'
ms.date: 08/18/2018
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 3120ee64d65822d323800a89466c6b707169aaaa
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59307504"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a><span data-ttu-id="3b893-102">방법: WPF 애플리케이션에 시작 화면 추가</span><span class="sxs-lookup"><span data-stu-id="3b893-102">How to: Add a Splash Screen to a WPF Application</span></span>

<span data-ttu-id="3b893-103">이 항목에서는 시작 창 또는 *시작 화면*을 Windows Presentation Foundation(WPF) 응용 프로그램에 추가하는 방법을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="3b893-103">This topic shows how to add a startup window, or *splash screen*, to a Windows Presentation Foundation (WPF) application.</span></span>

## <a name="to-add-an-existing-image-as-a-splash-screen"></a><span data-ttu-id="3b893-104">기존 이미지를 시작 화면으로 추가하려면</span><span class="sxs-lookup"><span data-stu-id="3b893-104">To add an existing image as a splash screen</span></span>

1. <span data-ttu-id="3b893-105">시작 화면으로 사용하려는 이미지를 찾거나 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3b893-105">Create or find an image that you want to use for the splash screen.</span></span> <span data-ttu-id="3b893-106">Windows Imaging 구성 요소(WIC)에서 지원되는 모든 이미지 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b893-106">You can use any image format that is supported by the Windows Imaging Component (WIC).</span></span> <span data-ttu-id="3b893-107">예를 들어, BMP, GIF, JPEG, PNG 또는 TIFF 형식으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b893-107">For example, you can use the BMP, GIF, JPEG, PNG, or TIFF format.</span></span>

2. <span data-ttu-id="3b893-108">WPF 응용 프로그램 프로젝트에 해당 이미지 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3b893-108">Add the image file to the WPF Application project.</span></span>

3. <span data-ttu-id="3b893-109">**솔루션 탐색기**에서 이미지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b893-109">In **Solution Explorer**, select the image.</span></span>

4. <span data-ttu-id="3b893-110">속성 창에서 **빌드 작업** 속성의 드롭다운 화살표를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3b893-110">In the Properties window, click the drop-down arrow for the **Build Action** property.</span></span>

5. <span data-ttu-id="3b893-111">드롭 다운 목록에서 **SplashScreen**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b893-111">Select **SplashScreen** from the drop-down list.</span></span>

6. <span data-ttu-id="3b893-112">**F5** 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3b893-112">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="3b893-113">시작 화면 이미지가 화면 중앙에 나타난 다음 메인 응용 프로그램 창이 나타나면 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="3b893-113">The splash screen image appears in the center of the screen, and then fades when the main application window appears.</span></span>

## <a name="to-exclude-the-splash-screen-from-build"></a><span data-ttu-id="3b893-114">빌드에서 시작 화면을 제외하려면</span><span class="sxs-lookup"><span data-stu-id="3b893-114">To exclude the splash screen from build</span></span>

1. <span data-ttu-id="3b893-115">**솔루션 탐색기**에서 시작 화면 이미지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b893-115">In **Solution Explorer**, select the splash screen image.</span></span>

2. <span data-ttu-id="3b893-116">**속성** 창에서 **빌드 작업**을 **None**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b893-116">In the **Properties** window, set the **Build Action** to **None**.</span></span>

## <a name="to-remove-the-splash-screen-from-an-application"></a><span data-ttu-id="3b893-117">응용 프로그램에서 시작 화면을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="3b893-117">To remove the splash screen from an application</span></span>

<span data-ttu-id="3b893-118">**솔루션 탐색기**에서 시작 화면 이미지를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="3b893-118">In **Solution Explorer**, delete the splash screen image.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b893-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="3b893-119">See also</span></span>

- <xref:System.Windows.SplashScreen>
- [<span data-ttu-id="3b893-120">방법: 프로젝트에 기존 항목 추가</span><span class="sxs-lookup"><span data-stu-id="3b893-120">How to: Add Existing Items to a Project</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))
