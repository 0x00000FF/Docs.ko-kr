---
title: '연습: WPF에서 호스팅할 Direct3D9 콘텐츠 만들기'
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 286e98bc-1eaa-4b5e-923d-3490a9cca5fc
ms.openlocfilehash: 462220b526db90d3acfa90a28f9bfd56dbe813e2
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991405"
---
# <a name="walkthrough-creating-direct3d9-content-for-hosting-in-wpf"></a><span data-ttu-id="b0704-102">연습: WPF에서 호스팅할 Direct3D9 콘텐츠 만들기</span><span class="sxs-lookup"><span data-stu-id="b0704-102">Walkthrough: Creating Direct3D9 Content for Hosting in WPF</span></span>
<span data-ttu-id="b0704-103">이 연습에서는 Windows Presentation Foundation (WPF) 응용 프로그램에서 호스트 하는 데 적합 한 Direct3D9 콘텐츠를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-103">This walkthrough shows how to create Direct3D9 content that is suitable for hosting in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="b0704-104">WPF 응용 프로그램에서 Direct3D9 콘텐츠를 호스트 하는 방법에 대 한 자세한 내용은 [wpf 및 Direct3d9 상호 운용성](wpf-and-direct3d9-interoperation.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b0704-104">For more information on hosting Direct3D9 content in WPF applications, see [WPF and Direct3D9 Interoperation](wpf-and-direct3d9-interoperation.md).</span></span>

 <span data-ttu-id="b0704-105">이 연습에서는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-105">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="b0704-106">Direct3D9 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-106">Create a Direct3D9 project.</span></span>

- <span data-ttu-id="b0704-107">WPF 응용 프로그램에서 호스팅을 위한 Direct3D9 프로젝트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-107">Configure the Direct3D9 project for hosting in a WPF application.</span></span>

 <span data-ttu-id="b0704-108">작업이 완료 되 면 WPF 응용 프로그램에서 사용할 수 있도록 Direct3D9 콘텐츠를 포함 하는 DLL이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-108">When you are finished, you will have a DLL that contains Direct3D9 content for use in a WPF application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b0704-109">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="b0704-109">Prerequisites</span></span>
 <span data-ttu-id="b0704-110">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-110">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="b0704-111">Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="b0704-111">Visual Studio 2010.</span></span>

- <span data-ttu-id="b0704-112">DirectX SDK 9 이상</span><span class="sxs-lookup"><span data-stu-id="b0704-112">DirectX SDK 9 or later.</span></span>

## <a name="creating-the-direct3d9-project"></a><span data-ttu-id="b0704-113">Direct3D9 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="b0704-113">Creating the Direct3D9 Project</span></span>
 <span data-ttu-id="b0704-114">첫 번째 단계는 Direct3D9 프로젝트를 만들고 구성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-114">The first step is to create and configure the Direct3D9 project.</span></span>

#### <a name="to-create-the-direct3d9-project"></a><span data-ttu-id="b0704-115">Direct3D9 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="b0704-115">To create the Direct3D9 project</span></span>

1. <span data-ttu-id="b0704-116">C++ 이라는`D3DContent`새 Win32 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-116">Create a new Win32 Project in C++ named `D3DContent`.</span></span>

     <span data-ttu-id="b0704-117">Win32 응용 프로그램 마법사가 열리고 시작 화면이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-117">The Win32 Application Wizard opens and displays the Welcome screen.</span></span>

2. <span data-ttu-id="b0704-118">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-118">Click **Next**.</span></span>

     <span data-ttu-id="b0704-119">응용 프로그램 설정 화면이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-119">The Application Settings screen appears.</span></span>

3. <span data-ttu-id="b0704-120">**응용 프로그램 종류:** 섹션에서 **DLL** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-120">In the **Application type:** section, select the **DLL** option.</span></span>

4. <span data-ttu-id="b0704-121">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-121">Click **Finish**.</span></span>

     <span data-ttu-id="b0704-122">D3DContent 프로젝트가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-122">The D3DContent project is generated.</span></span>

5. <span data-ttu-id="b0704-123">솔루션 탐색기에서 D3DContent 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-123">In Solution Explorer, right-click the D3DContent project and select **Properties**.</span></span>

     <span data-ttu-id="b0704-124">**D3DContent 속성 페이지** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-124">The **D3DContent Property Pages** dialog box opens.</span></span>

6. <span data-ttu-id="b0704-125">**C/C++**  노드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-125">Select the **C/C++** node.</span></span>

7. <span data-ttu-id="b0704-126">**추가 포함 디렉터리** 필드에서 DirectX Include 폴더의 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-126">In the **Additional Include Directories** field, specify the location of the DirectX include folder.</span></span> <span data-ttu-id="b0704-127">이 폴더의 기본 위치는%ProgramFiles%\Microsoft DirectX SDK (*version*) \Include.입니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-127">The default location for this folder is %ProgramFiles%\Microsoft DirectX SDK (*version*)\Include.</span></span>

8. <span data-ttu-id="b0704-128">**링커** 노드를 두 번 클릭 하 여 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-128">Double-click the **Linker** node to expand it.</span></span>

9. <span data-ttu-id="b0704-129">**추가 라이브러리 디렉터리** 필드에서 DirectX 라이브러리 폴더의 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-129">In the **Additional Library Directories** field, specify the location of the DirectX libraries folder.</span></span> <span data-ttu-id="b0704-130">이 폴더의 기본 위치는%ProgramFiles%\Microsoft DirectX SDK (*version*) \Lib\x86.입니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-130">The default location for this folder is %ProgramFiles%\Microsoft DirectX SDK (*version*)\Lib\x86.</span></span>

10. <span data-ttu-id="b0704-131">**입력** 노드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-131">Select the **Input** node.</span></span>

11. <span data-ttu-id="b0704-132">**추가 종속성** 필드에 `d3d9.lib` 및 `d3dx9.lib` 파일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-132">In the **Additional Dependencies** field, add the `d3d9.lib` and `d3dx9.lib` files.</span></span>

12. <span data-ttu-id="b0704-133">솔루션 탐색기에서 라는 `D3DContent.def` 새 모듈 정의 파일 (.def)을 프로젝트에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-133">In Solution Explorer, add a new module definition file (.def) named `D3DContent.def` to the project.</span></span>

## <a name="creating-the-direct3d9-content"></a><span data-ttu-id="b0704-134">Direct3D9 콘텐츠 만들기</span><span class="sxs-lookup"><span data-stu-id="b0704-134">Creating the Direct3D9 Content</span></span>
 <span data-ttu-id="b0704-135">최상의 성능을 얻으려면 Direct3D9 콘텐츠에서 특정 설정을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-135">To get the best performance, your Direct3D9 content must use particular settings.</span></span> <span data-ttu-id="b0704-136">다음 코드에서는 최상의 성능 특성이 있는 Direct3D9 화면을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-136">The following code shows how to create a Direct3D9 surface that has the best performance characteristics.</span></span> <span data-ttu-id="b0704-137">자세한 내용은 [Direct3D9 및 WPF 상호 운용성을 위한 성능 고려 사항](performance-considerations-for-direct3d9-and-wpf-interoperability.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-137">For more information, see [Performance Considerations for Direct3D9 and WPF Interoperability](performance-considerations-for-direct3d9-and-wpf-interoperability.md).</span></span>

#### <a name="to-create-the-direct3d9-content"></a><span data-ttu-id="b0704-138">Direct3D9 콘텐츠를 만들려면</span><span class="sxs-lookup"><span data-stu-id="b0704-138">To create the Direct3D9 content</span></span>

1. <span data-ttu-id="b0704-139">솔루션 탐색기를 사용 하 여 C++ 프로젝트에 다음의 세 가지 클래스를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-139">Using Solution Explorer, add three C++ classes to the project named the following.</span></span>

     <span data-ttu-id="b0704-140">`CRenderer`(가상 소멸자 포함)</span><span class="sxs-lookup"><span data-stu-id="b0704-140">`CRenderer` (with virtual destructor)</span></span>

     `CRendererManager`

     `CTriangleRenderer`

2. <span data-ttu-id="b0704-141">코드 편집기에서 렌더러를 열고 자동으로 생성 된 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-141">Open Renderer.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.h#rendererh)]

3. <span data-ttu-id="b0704-142">코드 편집기에서 렌더러를 열고 자동으로 생성 된 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-142">Open Renderer.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderercpp)]

4. <span data-ttu-id="b0704-143">코드 편집기에서 RendererManager .h를 열고 자동으로 생성 된 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-143">Open RendererManager.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.h#renderermanagerh)]

5. <span data-ttu-id="b0704-144">코드 편집기에서 RendererManager .cpp를 열고 자동으로 생성 된 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-144">Open RendererManager.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanagercpp)]

6. <span data-ttu-id="b0704-145">코드 편집기에서 TriangleRenderer을 열고 자동으로 생성 된 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-145">Open TriangleRenderer.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.h#trianglerendererh)]

7. <span data-ttu-id="b0704-146">코드 편집기에서 TriangleRenderer을 열고 자동으로 생성 된 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-146">Open TriangleRenderer.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.cpp#trianglerenderercpp)]

8. <span data-ttu-id="b0704-147">코드 편집기에서 stdafx.h를 열고 자동으로 생성 된 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-147">Open stdafx.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#StdafxH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/stdafx.h#stdafxh)]

9. <span data-ttu-id="b0704-148">코드 편집기에서 dllmain을 열고 자동으로 생성 된 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-148">Open dllmain.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#DllMain](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/dllmain.cpp#dllmain)]

10. <span data-ttu-id="b0704-149">코드 편집기에서 D3DContent를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-149">Open D3DContent.def in the code editor.</span></span>

11. <span data-ttu-id="b0704-150">자동으로 생성 된 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-150">Replace the automatically generated code with the following code.</span></span>

    ```cpp
    LIBRARY "D3DContent"

    EXPORTS

    SetSize
    SetAlpha
    SetNumDesiredSamples
    SetAdapter

    GetBackBufferNoRef
    Render
    Destroy
    ```

12. <span data-ttu-id="b0704-151">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-151">Build the project.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b0704-152">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b0704-152">Next Steps</span></span>

- <span data-ttu-id="b0704-153">WPF 응용 프로그램에서 Direct3D9 콘텐츠를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="b0704-153">Host the Direct3D9 content in a WPF application.</span></span> <span data-ttu-id="b0704-154">자세한 내용은 [연습: WPF](walkthrough-hosting-direct3d9-content-in-wpf.md)에서 Direct3D9 콘텐츠 호스팅</span><span class="sxs-lookup"><span data-stu-id="b0704-154">For more information, see [Walkthrough: Hosting Direct3D9 Content in WPF](walkthrough-hosting-direct3d9-content-in-wpf.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b0704-155">참고자료</span><span class="sxs-lookup"><span data-stu-id="b0704-155">See also</span></span>

- <xref:System.Windows.Interop.D3DImage>
- [<span data-ttu-id="b0704-156">Direct3D9 및 WPF 상호 운용성을 위한 성능 고려 사항</span><span class="sxs-lookup"><span data-stu-id="b0704-156">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
- [<span data-ttu-id="b0704-157">연습: WPF에서 Direct3D9 콘텐츠 호스팅</span><span class="sxs-lookup"><span data-stu-id="b0704-157">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>](walkthrough-hosting-direct3d9-content-in-wpf.md)
