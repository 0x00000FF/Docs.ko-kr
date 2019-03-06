---
title: 애플리케이션과 함께 글꼴 패키징
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], packaging fonts with
- fonts [WPF], packaging with applications
- typography [WPF], packaging fonts with applications
- packaging fonts with applications [WPF]
ms.assetid: db15ee48-4d24-49f5-8b9d-a64460865286
ms.openlocfilehash: e66841fe72281bf0562b2ce50925a5c3a6bb9b54
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378875"
---
# <a name="packaging-fonts-with-applications"></a><span data-ttu-id="5eef4-102">애플리케이션과 함께 글꼴 패키징</span><span class="sxs-lookup"><span data-stu-id="5eef4-102">Packaging Fonts with Applications</span></span>
<span data-ttu-id="5eef4-103">이 항목에서는 글꼴을 패키지 하는 방법에 대 한 개요를 제공 하면 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-103">This topic provides an overview of how to package fonts with your [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5eef4-104">대부분의 소프트웨어와 마찬가지로 글꼴 파일도 판매되는 것이 아니라 사용이 허가됩니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-104">As with most types of software, font files are licensed, rather than sold.</span></span> <span data-ttu-id="5eef4-105">글꼴 사용을 관리 하는 라이선스 다 공급 업체 하지만 일반적 글꼴 포함 하 여 대부분의 라이선스 [!INCLUDE[TLA#tla_ms#initcap](../../../../includes/tlasharptla-mssharpinitcap-md.md)] 응용 프로그램 제공 및 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], 글꼴 또는 응용 프로그램 내에 포함 되도록 허용 하지 않습니다 재배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-105">Licenses that govern the use of fonts vary from vendor to vendor but in general most licenses, including those covering the fonts [!INCLUDE[TLA#tla_ms#initcap](../../../../includes/tlasharptla-mssharpinitcap-md.md)] supplies with applications and [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], do not allow the fonts to be embedded within applications or otherwise redistributed.</span></span> <span data-ttu-id="5eef4-106">따라서 개발자는 애플리케이션 내에 포함하거나 기타 다른 방법으로 재배포하려는 글꼴에 대해 필요한 라이선스 권한이 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-106">Therefore, as a developer it is your responsibility to ensure that you have the required license rights for any font you embed within an application or otherwise redistribute.</span></span>  
  

  
<a name="introduction_to_packaging_fonts"></a>   
## <a name="introduction-to-packaging-fonts"></a><span data-ttu-id="5eef4-107">글꼴 패키징 소개</span><span class="sxs-lookup"><span data-stu-id="5eef4-107">Introduction to Packaging Fonts</span></span>  
 <span data-ttu-id="5eef4-108">내에 리소스로 글꼴을 쉽게 패키징할 수 있습니다 프로그램 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 사용자 인터페이스 텍스트 및 다른 형식의 텍스트를 표시 하는 응용 프로그램 콘텐츠를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-108">You can easily package fonts as resources within your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications to display user interface text and other types of text based content.</span></span> <span data-ttu-id="5eef4-109">글꼴은 애플리케이션의 어셈블리 파일 내에 포함하거나 별도로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-109">The fonts can be separate from or embedded within the application's assembly files.</span></span> <span data-ttu-id="5eef4-110">리소스 전용 글꼴 라이브러리를 만들어 애플리케이션에서 이를 참조하도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-110">You can also create a resource-only font library, which your application can reference.</span></span>  
  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] <span data-ttu-id="5eef4-111">및 [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)] 글꼴에는 글꼴에 대 한 글꼴 포함 라이선스 권한을 나타내는 fstype 이라는 형식 플래그가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-111">and [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)] fonts contain a type flag, fsType, that indicates font embedding licensing rights for the font.</span></span> <span data-ttu-id="5eef4-112">그러나 이 형식 플래그는 문서에 저장된 포함된 글꼴만 참조하고 애플리케이션에 포함된 글꼴은 참조하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-112">However, this type flag only refers to embedded fonts stored in a document–it does not refer to fonts embedded in an application.</span></span> <span data-ttu-id="5eef4-113">글꼴 만들어 포함 되는 글꼴에 대 한 권한을 검색할 수 있습니다는 <xref:System.Windows.Media.GlyphTypeface> 개체 및 참조 해당 <xref:System.Windows.Media.GlyphTypeface.EmbeddingRights%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-113">You can retrieve the font embedding rights for a font by creating a <xref:System.Windows.Media.GlyphTypeface> object and referencing its <xref:System.Windows.Media.GlyphTypeface.EmbeddingRights%2A> property.</span></span> <span data-ttu-id="5eef4-114">"os/2 및 Windows 메트릭" 섹션을 참조 합니다 [OpenType 사양](https://www.microsoft.com/typography/otspec/os2.htm) fsType 플래그에 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-114">Refer to the "OS/2 and Windows Metrics" section of the [OpenType Specification](https://www.microsoft.com/typography/otspec/os2.htm) for more information on the fsType flag.</span></span>  
  
 <span data-ttu-id="5eef4-115">합니다 [Microsoft 입력 체계](https://docs.microsoft.com/typography/) 웹 사이트에 도움이 될 수 있는 사용자 지정 작업에 대 한 글꼴 공급 업체를 찾거나 특정 글꼴 공급 업체를 찾을 연락처 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-115">The [Microsoft Typography](https://docs.microsoft.com/typography/) Web site includes contact information that can help you locate a particular font vendor or find a font vendor for custom work.</span></span>  
  
<a name="adding_fonts_as_content_items"></a>   
## <a name="adding-fonts-as-content-items"></a><span data-ttu-id="5eef4-116">콘텐츠 항목으로 글꼴 추가</span><span class="sxs-lookup"><span data-stu-id="5eef4-116">Adding Fonts as Content Items</span></span>  
 <span data-ttu-id="5eef4-117">애플리케이션의 어셈블리 파일과는 별도의 프로젝트 콘텐츠 항목으로 애플리케이션에 글꼴을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-117">You can add fonts to your application as project content items that are separate from the application's assembly files.</span></span> <span data-ttu-id="5eef4-118">이 경우 콘텐츠 항목이 어셈블리에 리소스로 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-118">This means that content items are not embedded as resources within an assembly.</span></span> <span data-ttu-id="5eef4-119">다음 프로젝트 파일 예제에서는 콘텐츠 항목을 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-119">The following project file example shows how to define content items.</span></span>  
  
```xml  
<Project DefaultTargets="Build"  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- Other project build settings ... -->  
  
  <ItemGroup>  
    <Content Include="Peric.ttf" />  
    <Content Include="Pericl.ttf" />  
  </ItemGroup>  
</Project>  
```  
  
 <span data-ttu-id="5eef4-120">애플리케이션에서 런타임에 글꼴을 사용할 수 있도록 하려면 애플리케이션의 배포 디렉터리에서 해당 글꼴에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-120">In order to ensure that the application can use the fonts at run time, the fonts must be accessible in the application's deployment directory.</span></span> <span data-ttu-id="5eef4-121">`<CopyToOutputDirectory>` 응용 프로그램의 프로젝트 파일에서는 요소를 사용 하면 자동으로 빌드 프로세스 중에 글꼴 응용 프로그램 배포 디렉터리에 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-121">The `<CopyToOutputDirectory>` element in the application's project file allows you to automatically copy the fonts to the application deployment directory during the build process.</span></span> <span data-ttu-id="5eef4-122">다음 프로젝트 파일 예제에서는 글꼴을 배포 디렉터리에 복사하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-122">The following project file example shows how to copy fonts to the deployment directory.</span></span>  
  
```xml  
<ItemGroup>  
  <Content Include="Peric.ttf">  
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
  </Content>  
  <Content Include="Pericl.ttf">  
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
  </Content>  
</ItemGroup>  
```  
  
 <span data-ttu-id="5eef4-123">다음 코드 예제에서는 애플리케이션의 글꼴을 콘텐츠 항목으로 참조하는 방법을 보여 줍니다. 참조되는 콘텐츠 항목은 애플리케이션의 어셈블리 파일과 동일한 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-123">The following code example shows how to reference the application's font as a content item—the referenced content item must be in the same directory as the application's assembly files.</span></span>  
  
 [!code-xaml[FontSnippets#FontPackageSnippet8](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet8)]  
  
<a name="adding_fonts_as_resource_items"></a>   
## <a name="adding-fonts-as-resource-items"></a><span data-ttu-id="5eef4-124">리소스 항목으로 글꼴 추가</span><span class="sxs-lookup"><span data-stu-id="5eef4-124">Adding Fonts as Resource Items</span></span>  
 <span data-ttu-id="5eef4-125">애플리케이션의 어셈블리 파일에 포함된 프로젝트 리소스 항목으로 애플리케이션에 글꼴을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-125">You can add fonts to your application as project resource items that are embedded within the application's assembly files.</span></span> <span data-ttu-id="5eef4-126">리소스에 별도의 하위 디렉터리를 사용하면 애플리케이션의 프로젝트 파일을 보다 간편하게 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-126">Using a separate subdirectory for resources helps to organize the application's project files.</span></span> <span data-ttu-id="5eef4-127">다음 프로젝트 파일 예제에서는 별도의 하위 디렉터리에 리소스 항목으로 글꼴을 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-127">The following project file example shows how to define fonts as resource items in a separate subdirectory.</span></span>  
  
```xml  
<Project DefaultTargets="Build"  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- Other project build settings ... -->  
  
  <ItemGroup>  
    <Resource Include="resources\Peric.ttf" />  
    <Resource Include="resources\Pericl.ttf" />  
  </ItemGroup>  
</Project>  
```  
  
> [!NOTE]
>  <span data-ttu-id="5eef4-128">글꼴 리소스와 응용 프로그램에 추가할 때 설정 하는 있는지 확인 합니다 `<Resource>` 요소를 아니라는 `<EmbeddedResource>` 응용 프로그램의 프로젝트 파일의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-128">When you add fonts as resources to your application, make sure you are setting the `<Resource>` element, and not the `<EmbeddedResource>` element in your application's project file.</span></span> <span data-ttu-id="5eef4-129">`<EmbeddedResource>` 빌드 작업에 대 한 요소가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-129">The `<EmbeddedResource>` element for the build action is not supported.</span></span>  
  
 <span data-ttu-id="5eef4-130">다음 태그 예제에서는 애플리케이션의 글꼴 리소스를 참조하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-130">The following markup example shows how to reference the application's font resources.</span></span>  
  
 [!code-xaml[FontSnippets#FontPackageSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet1)]  
  
### <a name="referencing-font-resource-items-from-code"></a><span data-ttu-id="5eef4-131">코드에서 글꼴 리소스 항목 참조</span><span class="sxs-lookup"><span data-stu-id="5eef4-131">Referencing Font Resource Items from Code</span></span>  
 <span data-ttu-id="5eef4-132">을 코드에서 글꼴 리소스 항목을 참조 하기 위해 두 부분으로 구성 글꼴 리소스 참조를 제공 해야 합니다: 기본 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]; 및 글꼴 위치 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-132">In order to reference font resource items from code, you must supply a two-part font resource reference: the base [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]; and the font location reference.</span></span> <span data-ttu-id="5eef4-133">이러한 값에 대 한 매개 변수로 사용 되는 <xref:System.Windows.Media.FontFamily.%23ctor%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="5eef4-133">These values are used as the parameters for the <xref:System.Windows.Media.FontFamily.%23ctor%2A> method.</span></span> <span data-ttu-id="5eef4-134">다음 코드 예제에서는 라는 프로젝트 하위 디렉터리에 응용 프로그램의 글꼴 리소스를 참조 하는 방법을 보여 줍니다. `resources`합니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-134">The following code example shows how to reference the application's font resources in the project subdirectory called `resources`.</span></span>  
  
 [!code-csharp[FontSnippets#FontPackageSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet2)]
 [!code-vb[FontSnippets#FontPackageSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet2)]  
  
 <span data-ttu-id="5eef4-135">기본 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] 글꼴 리소스가 있는 응용 프로그램 하위 디렉터리가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-135">The base [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] can include the application subdirectory where the font resource resides.</span></span> <span data-ttu-id="5eef4-136">이 경우 글꼴 위치 참조에서 디렉터리를 지정할 필요가 없습니다만 앞에 포함 "`./`"를 기본으로 지정 된 동일한 디렉터리에는 글꼴 리소스를 나타내는 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-136">In this case, the font location reference would not need to specify a directory, but would have to include a leading "`./`", which indicates the font resource is in the same directory specified by the base [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)].</span></span> <span data-ttu-id="5eef4-137">다음 코드 예제에서는 위의 코드 예제에 나오는 것과 동일한 글꼴 리소스 항목을 참조하는 다른 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-137">The following code example shows an alternate way of referencing the font resource item—it is equivalent to the previous code example.</span></span>  
  
 [!code-csharp[FontSnippets#FontPackageSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet5)]
 [!code-vb[FontSnippets#FontPackageSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet5)]  
  
### <a name="referencing-fonts-from-the-same-application-subdirectory"></a><span data-ttu-id="5eef4-138">동일한 애플리케이션 하위 디렉터리에서 글꼴 참조</span><span class="sxs-lookup"><span data-stu-id="5eef4-138">Referencing Fonts from the Same Application Subdirectory</span></span>  
 <span data-ttu-id="5eef4-139">애플리케이션 콘텐츠와 리소스 파일을 모두 애플리케이션 프로젝트의 동일한 사용자 정의 하위 디렉터리에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-139">You can place both application content and resource files within the same user-defined subdirectory of your application project.</span></span> <span data-ttu-id="5eef4-140">다음 프로젝트 파일 예제에서는 동일한 하위 디렉터리에 정의된 콘텐츠 페이지와 글꼴 리소스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-140">The following project file example shows a content page and font resources defined in the same subdirectory.</span></span>  
  
```xml  
<ItemGroup>  
  <Page Include="pages\HomePage.xaml" />  
</ItemGroup>  
<ItemGroup>  
  <Resource Include="pages\Peric.ttf" />  
  <Resource Include="pages\Pericl.ttf" />  
</ItemGroup>  
```  
  
 <span data-ttu-id="5eef4-141">애플리케이션 콘텐츠와 글꼴이 동일한 하위 디렉터리에 있으므로 글꼴 참조가 애플리케이션 콘텐츠를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-141">Since the application content and font are in the same subdirectory, the font reference is relative to the application content.</span></span> <span data-ttu-id="5eef4-142">다음 예제에서는 글꼴이 애플리케이션과 동일한 디렉터리에 있는 경우 애플리케이션의 글꼴 리소스를 참조하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-142">The following examples show how to reference the application's font resource when the font is in the same directory as the application.</span></span>  
  
 [!code-xaml[FontSnippets#FontPackageSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml#fontpackagesnippet3)]  
  
 [!code-csharp[FontSnippets#FontPackageSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml.cs#fontpackagesnippet4)]
 [!code-vb[FontSnippets#FontPackageSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/pages/homepage.xaml.vb#fontpackagesnippet4)]  
  
### <a name="enumerating-fonts-in-an-application"></a><span data-ttu-id="5eef4-143">애플리케이션의 글꼴 열거</span><span class="sxs-lookup"><span data-stu-id="5eef4-143">Enumerating Fonts in an Application</span></span>  
 <span data-ttu-id="5eef4-144">응용 프로그램에서 리소스 항목으로 글꼴을 열거할 하나를 사용 합니다 <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> 또는 <xref:System.Windows.Media.Fonts.GetTypefaces%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="5eef4-144">To enumerate fonts as resource items in your application, use either the <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> or <xref:System.Windows.Media.Fonts.GetTypefaces%2A> method.</span></span> <span data-ttu-id="5eef4-145">다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다 <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> 의 컬렉션을 반환 하는 방법 <xref:System.Windows.Media.FontFamily> 응용 프로그램 글꼴 위치에서 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-145">The following example shows how to use the <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> method to return the collection of <xref:System.Windows.Media.FontFamily> objects from the application font location.</span></span> <span data-ttu-id="5eef4-146">이 경우에는 애플리케이션에 “resources”라는 하위 디렉터리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-146">In this case, the application contains a subdirectory named "resources".</span></span>  
  
 [!code-csharp[FontSnippets#FontsSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet3)]
 [!code-vb[FontSnippets#FontsSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet3)]  
  
 <span data-ttu-id="5eef4-147">다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다 <xref:System.Windows.Media.Fonts.GetTypefaces%2A> 의 컬렉션을 반환 하는 방법 <xref:System.Windows.Media.Typeface> 응용 프로그램 글꼴 위치에서 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-147">The following example shows how to use the <xref:System.Windows.Media.Fonts.GetTypefaces%2A> method to return the collection of <xref:System.Windows.Media.Typeface> objects from the application font location.</span></span> <span data-ttu-id="5eef4-148">이 경우에는 애플리케이션에 “resources”라는 하위 디렉터리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-148">In this case, the application contains a subdirectory named "resources".</span></span>  
  
 [!code-csharp[FontSnippets#FontsSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet7)]
 [!code-vb[FontSnippets#FontsSnippet7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet7)]  
  
<a name="creating_a_font_resource_library"></a>   
## <a name="creating-a-font-resource-library"></a><span data-ttu-id="5eef4-149">글꼴 리소스 라이브러리 만들기</span><span class="sxs-lookup"><span data-stu-id="5eef4-149">Creating a Font Resource Library</span></span>  
 <span data-ttu-id="5eef4-150">글꼴만 포함된 리소스 전용 라이브러리를 만들 수 있습니다. 이러한 유형의 라이브러리 프로젝트에는 코드가 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-150">You can create a resource-only library that contains only fonts—no code is part of this type of library project.</span></span> <span data-ttu-id="5eef4-151">리소스 전용 라이브러리는 일반적으로 리소스와 리소스를 사용하는 애플리케이션 코드를 분리하려는 경우에 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-151">Creating a resource-only library is a common technique for decoupling resources from the application code that uses them.</span></span> <span data-ttu-id="5eef4-152">리소스 전용 라이브러리를 만들면 라이브러리 어셈블리를 여러 애플리케이션 프로젝트에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-152">This also allows the library assembly to be included with multiple application projects.</span></span> <span data-ttu-id="5eef4-153">다음 프로젝트 파일 예제에서는 리소스 전용 라이브러리 프로젝트의 주요 부분을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-153">The following project file example shows the key portions of a resource-only library project.</span></span>  
  
```xml  
<PropertyGroup>  
  <AssemblyName>FontLibrary</AssemblyName>  
  <OutputType>library</OutputType>  
  ...  
</PropertyGroup>  
...  
<ItemGroup>  
  <Resource Include="Kooten.ttf" />  
  <Resource Include="Pesca.ttf" />  
</ItemGroup  
```  
  
### <a name="referencing-a-font-in-a-resource-library"></a><span data-ttu-id="5eef4-154">리소스 라이브러리의 글꼴 참조</span><span class="sxs-lookup"><span data-stu-id="5eef4-154">Referencing a Font in a Resource Library</span></span>  
 <span data-ttu-id="5eef4-155">애플리케이션에서 리소스 라이브러리의 글꼴을 참조하려면 라이브러리 어셈블리의 이름을 글꼴 참조의 접두사로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-155">To reference a font in a resource library from your application, you must prefix the font reference with the name of the library assembly.</span></span> <span data-ttu-id="5eef4-156">이 경우 글꼴 리소스 어셈블리는 “FontLibrary”입니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-156">In this case, the font resource assembly is "FontLibrary".</span></span> <span data-ttu-id="5eef4-157">어셈블리 이름을 어셈블리 내의 참조와 구분하려면 ‘;’ 문자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-157">To separate the assembly name from the reference within the assembly, use a ';' character.</span></span> <span data-ttu-id="5eef4-158">글꼴 이름에 “Component” 키워드와 참조를 차례로 추가하면 글꼴 라이브러리의 리소스에 대한 전체 참조가 완성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-158">Adding the "Component" keyword followed by the reference to the font name completes the full reference to the font library's resource.</span></span> <span data-ttu-id="5eef4-159">다음 코드 예제에서는 리소스 라이브러리 어셈블리의 글꼴을 참조하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-159">The following code example shows how to reference a font in a resource library assembly.</span></span>  
  
 [!code-xaml[OpenTypeFontsSample#OpenTypeFontsSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontsSample/CS/Kootenay.xaml#opentypefontssample1)]  
  
> [!NOTE]
>  <span data-ttu-id="5eef4-160">이 SDK 샘플의 집합을 포함 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 사용 하 여 사용할 수 있는 글꼴 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-160">This SDK contains a set of sample [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fonts that you can use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span> <span data-ttu-id="5eef4-161">글꼴은 리소스 전용 라이브러리에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-161">The fonts are defined in a resource-only library.</span></span> <span data-ttu-id="5eef4-162">자세한 내용은 [샘플 OpenType 글꼴 팩](sample-opentype-font-pack.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5eef4-162">For more information, see [Sample OpenType Font Pack](sample-opentype-font-pack.md).</span></span>  
  
<a name="limitations_on_font_usage"></a>   
## <a name="limitations-on-font-usage"></a><span data-ttu-id="5eef4-163">글꼴 사용의 제한 사항</span><span class="sxs-lookup"><span data-stu-id="5eef4-163">Limitations on Font Usage</span></span>  
 <span data-ttu-id="5eef4-164">다음 목록에는 패키징 및 글꼴을 사용 하 여 몇 가지 제한 사항이 설명 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램:</span><span class="sxs-lookup"><span data-stu-id="5eef4-164">The following list describes several limitations on the packaging and use of fonts in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications:</span></span>  
  
-   <span data-ttu-id="5eef4-165">**글꼴 포함 권한 비트:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램은 글꼴 포함 권한 비트를 확인하거나 적용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-165">**Font embedding permission bits:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not check or enforce any font embedding permission bits.</span></span> <span data-ttu-id="5eef4-166">참조 된 [글꼴 패키징 소개](#introduction_to_packaging_fonts) 자세한 내용은 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-166">See the [Introduction_to_Packing Fonts](#introduction_to_packaging_fonts) section for more information.</span></span>  
  
-   <span data-ttu-id="5eef4-167">**원래 사이트 글꼴:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램은 http 또는 ftp에 대 한 글꼴 참조를 허용 하지 않습니다 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-167">**Site of origin fonts:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not allow a font reference to an http or ftp [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)].</span></span>  
  
-   <span data-ttu-id="5eef4-168">**팩을 사용 하는 절대 URI: 표기법:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 만들 수 없습니다는 <xref:System.Windows.Media.FontFamily> 사용 하 여 프로그래밍 방식으로 "팩:" 절대의 일부로 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] 글꼴에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-168">**Absolute URI using the pack: notation:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not allow you to create a <xref:System.Windows.Media.FontFamily> object programmatically using "pack:" as part of the absolute [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] reference to a font.</span></span> <span data-ttu-id="5eef4-169">예를 들어 `"pack://application:,,,/resources/#Pericles Light"` 잘못 된 글꼴 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-169">For example, `"pack://application:,,,/resources/#Pericles Light"` is an invalid font reference.</span></span>  
  
-   <span data-ttu-id="5eef4-170">**자동 글꼴 포함:** 디자인 타임에 응용 프로그램의 글꼴 사용을 검색 하 고 자동으로 응용 프로그램의 리소스에 글꼴을 포함 하는 것에 대 한 지원은 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-170">**Automatic font embedding:** During design time, there is no support for searching an application's use of fonts and automatically embedding the fonts in the application's resources.</span></span>  
  
-   <span data-ttu-id="5eef4-171">**글꼴 하위 집합:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램은 고정되지 않은 문서에 대해서는 글꼴 하위 집합을 만드는 것을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-171">**Font subsets:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not support the creation of font subsets for non-fixed documents.</span></span>  
  
-   <span data-ttu-id="5eef4-172">올바르지 않은 참조가 있는 경우 애플리케이션에서는 사용 가능한 글꼴로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="5eef4-172">In cases where there is an incorrect reference, the application falls back to using an available font.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eef4-173">참고자료</span><span class="sxs-lookup"><span data-stu-id="5eef4-173">See also</span></span>
- <xref:System.Windows.Documents.Typography>
- <xref:System.Windows.Media.FontFamily>
- [<span data-ttu-id="5eef4-174">Microsoft 입력 체계: 링크, 뉴스 및 연락처</span><span class="sxs-lookup"><span data-stu-id="5eef4-174">Microsoft Typography: Links, News, and Contacts</span></span>](https://docs.microsoft.com/typography/)
- [<span data-ttu-id="5eef4-175">OpenType 사양</span><span class="sxs-lookup"><span data-stu-id="5eef4-175">OpenType Specification</span></span>](https://www.microsoft.com/typography/otspec/)
- [<span data-ttu-id="5eef4-176">OpenType 글꼴 기능</span><span class="sxs-lookup"><span data-stu-id="5eef4-176">OpenType Font Features</span></span>](opentype-font-features.md)
- [<span data-ttu-id="5eef4-177">샘플 OpenType 글꼴 팩</span><span class="sxs-lookup"><span data-stu-id="5eef4-177">Sample OpenType Font Pack</span></span>](sample-opentype-font-pack.md)
