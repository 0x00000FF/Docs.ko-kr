---
title: My.Resources 개체
ms.date: 07/20/2015
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
ms.openlocfilehash: 9fd23cb119ff9148a45d32ec70ccc4dad08ab876
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604707"
---
# <a name="myresources-object"></a><span data-ttu-id="9e97e-102">My.Resources 개체</span><span class="sxs-lookup"><span data-stu-id="9e97e-102">My.Resources Object</span></span>
<span data-ttu-id="9e97e-103">응용 프로그램의 리소스에 액세스 하기 위한 속성 및 클래스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-103">Provides properties and classes for accessing the application's resources.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e97e-104">설명</span><span class="sxs-lookup"><span data-stu-id="9e97e-104">Remarks</span></span>  
 <span data-ttu-id="9e97e-105">`My.Resources` 개체 응용 프로그램의 리소스에 대 한 액세스를 제공 하며, 사용 하면 동적으로 응용 프로그램에 대 한 리소스를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-105">The `My.Resources` object provides access to the application's resources and lets you dynamically retrieve resources for your application.</span></span> <span data-ttu-id="9e97e-106">자세한 내용은 참조 [응용 프로그램 리소스 관리 (.NET)](/visualstudio/ide/managing-application-resources-dotnet)합니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-106">For more information, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
 <span data-ttu-id="9e97e-107">`My.Resources` 만 전역 리소스를 노출 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-107">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="9e97e-108">폼과 연관 된 리소스 파일에 대 한 액세스를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-108">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="9e97e-109">폼에서 폼 리소스에 액세스 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-109">You must access the form resources from the form.</span></span>  
  
 <span data-ttu-id="9e97e-110">응용 프로그램의 문화권 관련 리소스 파일에 액세스할 수 있습니다는 `My.Resources` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-110">You can access the application's culture-specific resource files from the `My.Resources` object.</span></span> <span data-ttu-id="9e97e-111">기본적으로는 `My.Resources` culture에 일치 하는 리소스 파일에서 리소스를 조회 하는 개체는 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-111">By default, the `My.Resources` object looks up resources from the resource file that matches the culture in the <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> property.</span></span> <span data-ttu-id="9e97e-112">그러나이 동작을 재정의할 수 있으며 특정 리소스에 사용할 culture를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-112">However, you can override this behavior and specify a particular culture to use for the resources.</span></span> <span data-ttu-id="9e97e-113">자세한 내용은 [데스크톱 앱의 리소스](../../../framework/resources/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e97e-113">For more information, see [Resources in Desktop Apps](../../../framework/resources/index.md).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9e97e-114">속성</span><span class="sxs-lookup"><span data-stu-id="9e97e-114">Properties</span></span>  
 <span data-ttu-id="9e97e-115">속성은 `My.Resources` 개체 응용 프로그램의 리소스에 대 한 읽기 전용 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-115">The properties of the `My.Resources` object provide read-only access to your application's resources.</span></span> <span data-ttu-id="9e97e-116">를 추가 하거나 리소스를 제거 하려면 사용 하 여는 **프로젝트 디자이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-116">To add or remove resources, use the **Project Designer**.</span></span> <span data-ttu-id="9e97e-117">통해 추가 된 리소스에 액세스할 수 있습니다는 **프로젝트 디자이너** 를 사용 하 여 `My.Resources.``resourceName`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-117">You can access resources added through the **Project Designer** by using `My.Resources.``resourceName`.</span></span>  
  
 <span data-ttu-id="9e97e-118">추가 하거나에서 프로젝트를 선택 하 여 리소스 파일을 제거할 수도 **솔루션 탐색기** 클릭 하 고 **새 항목 추가** 또는 **기존 항목 추가** 에서  **프로젝트** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="9e97e-118">You can also add or remove resource files by selecting your project in **Solution Explorer** and clicking **Add New Item** or **Add Existing Item** from the **Project** menu.</span></span> <span data-ttu-id="9e97e-119">이런이 방식으로 사용 하 여 추가 리소스에 액세스할 수 있습니다 `My.Resources.``resourceFileName`.`resourceName`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-119">You can access resources added in this manner by using `My.Resources.``resourceFileName`.`resourceName`.</span></span>  
  
 <span data-ttu-id="9e97e-120">이러한 리소스 설정에 따라 리소스를 액세스 하는 속성에 표시 되는 방식을 결정 하 고 이름, 범주 및 값을 각 리소스에는 `My.Resources` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-120">Each resource has a name, category, and value, and these resource settings determine how the property to access the resource appears in the `My.Resources` object.</span></span> <span data-ttu-id="9e97e-121">추가 된 리소스에 대 한는 **프로젝트 디자이너**:</span><span class="sxs-lookup"><span data-stu-id="9e97e-121">For resources added in the **Project Designer**:</span></span>  
  
-   <span data-ttu-id="9e97e-122">이름에는 속성의 이름이 결정</span><span class="sxs-lookup"><span data-stu-id="9e97e-122">The name determines the name of the property,</span></span>  
  
-   <span data-ttu-id="9e97e-123">리소스 데이터는 속성의 값</span><span class="sxs-lookup"><span data-stu-id="9e97e-123">The resource data is the value of the property,</span></span>  
  
-   <span data-ttu-id="9e97e-124">범주에는 속성의 유형을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-124">The category determines the type of the property:</span></span>  
  
|<span data-ttu-id="9e97e-125">범주</span><span class="sxs-lookup"><span data-stu-id="9e97e-125">Category</span></span>|<span data-ttu-id="9e97e-126">속성 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9e97e-126">Property data type</span></span>|  
|---|---|  
|<span data-ttu-id="9e97e-127">**문자열**</span><span class="sxs-lookup"><span data-stu-id="9e97e-127">**Strings**</span></span>|[<span data-ttu-id="9e97e-128">String</span><span class="sxs-lookup"><span data-stu-id="9e97e-128">String</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|<span data-ttu-id="9e97e-129">**이미지**</span><span class="sxs-lookup"><span data-stu-id="9e97e-129">**Images**</span></span>|<xref:System.Drawing.Bitmap>|  
|<span data-ttu-id="9e97e-130">**아이콘**</span><span class="sxs-lookup"><span data-stu-id="9e97e-130">**Icons**</span></span>|<xref:System.Drawing.Icon>|  
|<span data-ttu-id="9e97e-131">**오디오**</span><span class="sxs-lookup"><span data-stu-id="9e97e-131">**Audio**</span></span>|<xref:System.IO.UnmanagedMemoryStream><br /><br /> <span data-ttu-id="9e97e-132"><xref:System.IO.UnmanagedMemoryStream> 클래스에서 파생 되는 <xref:System.IO.Stream> 클래스와 같은 스트림를 사용 하는 메서드와 함께 사용할 수 있도록는 <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="9e97e-132">The <xref:System.IO.UnmanagedMemoryStream> class derives from the <xref:System.IO.Stream> class, so it can be used with methods that take streams, such as the <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> method.</span></span>|  
|<span data-ttu-id="9e97e-133">**파일**</span><span class="sxs-lookup"><span data-stu-id="9e97e-133">**Files**</span></span>|<span data-ttu-id="9e97e-134">-   [문자열](../../../visual-basic/language-reference/data-types/string-data-type.md) 텍스트 파일에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-134">-   [String](../../../visual-basic/language-reference/data-types/string-data-type.md) for text files.</span></span><br /><span data-ttu-id="9e97e-135">-   <xref:System.Drawing.Bitmap> 이미지 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-135">-   <xref:System.Drawing.Bitmap> for image files.</span></span><br /><span data-ttu-id="9e97e-136">-   <xref:System.Drawing.Icon> 아이콘 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-136">-   <xref:System.Drawing.Icon> for icon files.</span></span><br /><span data-ttu-id="9e97e-137">-   <xref:System.IO.UnmanagedMemoryStream> 사운드 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-137">-   <xref:System.IO.UnmanagedMemoryStream> for sound files.</span></span>|  
|<span data-ttu-id="9e97e-138">**기타**</span><span class="sxs-lookup"><span data-stu-id="9e97e-138">**Other**</span></span>|<span data-ttu-id="9e97e-139">디자이너에 있는 정보에 의해 결정 **형식** 열입니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-139">Determined by the information in the designer's **Type** column.</span></span>|  
  
## <a name="classes"></a><span data-ttu-id="9e97e-140">클래스</span><span class="sxs-lookup"><span data-stu-id="9e97e-140">Classes</span></span>  
 <span data-ttu-id="9e97e-141">`My.Resources` 개체 공유 속성을 사용 하 여 클래스와 각 리소스 파일을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-141">The `My.Resources` object exposes each resource file as a class with shared properties.</span></span> <span data-ttu-id="9e97e-142">클래스 이름은 리소스 파일의 이름과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-142">The class name is the same as the name of the resource file.</span></span> <span data-ttu-id="9e97e-143">이전 섹션에서 설명한 리소스 파일의 리소스 클래스에 속성으로 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-143">As described in the previous section, the resources in a resource file are exposed as properties in the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e97e-144">예제</span><span class="sxs-lookup"><span data-stu-id="9e97e-144">Example</span></span>  
 <span data-ttu-id="9e97e-145">이 예에서는 라는 문자열 리소스에는 폼의 제목을 설정 `Form1Title` 응용 프로그램 리소스 파일에서입니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-145">This example sets the title of a form to the string resource named `Form1Title` in the application resource file.</span></span> <span data-ttu-id="9e97e-146">이 예제에서 응용 프로그램 이라는 문자열 있어야 `Form1Title` 의 리소스 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-146">For the example to work, the application must have a string named `Form1Title` in its resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#1](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="9e97e-147">예제</span><span class="sxs-lookup"><span data-stu-id="9e97e-147">Example</span></span>  
 <span data-ttu-id="9e97e-148">이 예에서는 이라는 아이콘을 폼의 아이콘 설정 `Form1Icon` 응용 프로그램의 리소스 파일에 저장 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-148">This example sets the icon of the form to the icon named `Form1Icon` that is stored in the application's resource file.</span></span> <span data-ttu-id="9e97e-149">이 예제에서 응용 프로그램 이라는 아이콘이 있어야 `Form1Icon` 의 리소스 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-149">For the example to work, the application must have an icon named `Form1Icon` in its resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#2](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="9e97e-150">예제</span><span class="sxs-lookup"><span data-stu-id="9e97e-150">Example</span></span>  
 <span data-ttu-id="9e97e-151">명명 된 이미지 리소스를 폼의 배경 이미지를 설정 하는이 예제 `Form1Background`, 응용 프로그램 리소스 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-151">This example sets the background image of a form to the image resource named `Form1Background`, which is in the application resource file.</span></span> <span data-ttu-id="9e97e-152">이 예제가 작동 하려면 응용 프로그램에 있어야 명명 된 이미지 리소스 `Form1Background` 의 리소스 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-152">For this example to work, the application must have an image resource named `Form1Background` in its resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#3](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="9e97e-153">예제</span><span class="sxs-lookup"><span data-stu-id="9e97e-153">Example</span></span>  
 <span data-ttu-id="9e97e-154">이 예제에서는 명명 된 오디오 리소스로 저장 된 소리를 재생 `Form1Greeting` 응용 프로그램의 리소스 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-154">This example plays the sound that is stored as an audio resource named `Form1Greeting` in the application's resource file.</span></span> <span data-ttu-id="9e97e-155">이 예제에서 응용 프로그램 이라는 오디오 리소스가 있어야 `Form1Greeting` 의 리소스 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-155">For the example to work, the application must have an audio resource named `Form1Greeting` in its resource file.</span></span> <span data-ttu-id="9e97e-156">`My.Computer.Audio.Play` 메서드는 Windows Forms 응용 프로그램에 대해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-156">The `My.Computer.Audio.Play` method is available only for Windows Forms applications.</span></span>  
  
 [!code-vb[VbVbalrMyResources#4](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_4.vb)]  
  
## <a name="example"></a><span data-ttu-id="9e97e-157">예제</span><span class="sxs-lookup"><span data-stu-id="9e97e-157">Example</span></span>  
 <span data-ttu-id="9e97e-158">이 예제에서는 응용 프로그램의 문자열 리소스의 프랑스어 culture 버전을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-158">This example retrieves the French-culture version of a  string resource of the application.</span></span> <span data-ttu-id="9e97e-159">리소스의 이름은 지정 `Message`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-159">The resource is named `Message`.</span></span> <span data-ttu-id="9e97e-160">Culture를 변경 하는 `My.Resources` 개체가 사용, 사용 하 여 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-160">To change the culture that the `My.Resources` object uses, the example uses <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.</span></span>  
  
 <span data-ttu-id="9e97e-161">이 예제가 작동 하려면 응용 프로그램 이라는 문자열 있어야 `Message` 상대방이 리소스 파일과 응용 프로그램 없어야 Resources.fr-r e s x 해당 리소스 파일의 문화권 프랑스어 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-161">For this example to work, the application must have a string named `Message` in its resource file, and the application should have the French-culture version of that resource file, Resources.fr-FR.resx.</span></span> <span data-ttu-id="9e97e-162">응용 프로그램에 리소스 파일의 문화권 프랑스어 버전이 없는 경우는 `My.Resource` 개체는 기본 문화권 리소스 파일에서 리소스를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e97e-162">If the application does not have the French-culture version of the resource file, the `My.Resource` object retrieves the resource from the default-culture resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#10](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_5.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="9e97e-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e97e-163">See Also</span></span>  
 [<span data-ttu-id="9e97e-164">응용 프로그램 리소스 관리(.NET)</span><span class="sxs-lookup"><span data-stu-id="9e97e-164">Managing Application Resources (.NET)</span></span>](/visualstudio/ide/managing-application-resources-dotnet)  
 [<span data-ttu-id="9e97e-165">데스크톱 앱의 리소스</span><span class="sxs-lookup"><span data-stu-id="9e97e-165">Resources in Desktop Apps</span></span>](../../../framework/resources/index.md)  

