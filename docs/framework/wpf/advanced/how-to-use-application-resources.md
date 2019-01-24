---
title: '방법: 응용 프로그램 리소스 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF]
- resources [WPF], application resources
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
ms.openlocfilehash: acd172448ebdefd6395feec6ad50e1c9491d9e27
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733599"
---
# <a name="how-to-use-application-resources"></a><span data-ttu-id="b3396-102">방법: 응용 프로그램 리소스 사용</span><span class="sxs-lookup"><span data-stu-id="b3396-102">How to: Use Application Resources</span></span>
<span data-ttu-id="b3396-103">이 예제에서는 애플리케이션 리소스를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b3396-103">This example shows how to use application resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3396-104">예제</span><span class="sxs-lookup"><span data-stu-id="b3396-104">Example</span></span>  
 <span data-ttu-id="b3396-105">다음 예제에서는 애플리케이션 정의 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b3396-105">The following example shows an application definition file.</span></span> <span data-ttu-id="b3396-106">리소스 섹션을 정의 하는 응용 프로그램 정의 파일 (에 대 한 값을 <xref:System.Windows.Application.Resources%2A> 속성).</span><span class="sxs-lookup"><span data-stu-id="b3396-106">The application definition file defines a resource section (a value for the <xref:System.Windows.Application.Resources%2A> property).</span></span> <span data-ttu-id="b3396-107">애플리케이션 수준에 정의된 리소스는 애플리케이션의 일부인 다른 모든 페이지에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3396-107">Resources defined at the application level can be accessed by all other pages that are part of the application.</span></span> <span data-ttu-id="b3396-108">이 경우 리소스는 선언된 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="b3396-108">In this case, the resource is a declared style.</span></span> <span data-ttu-id="b3396-109">이 예제에서는 내에 정의 된 컨트롤 템플릿을 생략 컨트롤 템플릿을 포함 하는 전체 스타일 일 수 있으므로 시간이 오래 걸리는 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 스타일의 속성 setter.</span><span class="sxs-lookup"><span data-stu-id="b3396-109">Because a complete style that includes a control template can be lengthy, this example omits the control template that is defined within the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> property setter of the style.</span></span>  
  
 [!code-xaml[ResourcesApplication#PreTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xaml[ResourcesApplication#PostTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 <span data-ttu-id="b3396-110">다음 예제와 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 앞의 예제에서 정의한 응용 프로그램 수준 리소스를 참조 하는 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="b3396-110">The following example shows a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page that references the application-level resource that the previous example defined.</span></span> <span data-ttu-id="b3396-111">리소스를 사용 하 여 참조 되는 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) 요청된 된 리소스에 대 한 고유한 리소스 키를 지정 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3396-111">The resource is referenced by using a     [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) that specifies the unique resource key for the requested resource.</span></span> <span data-ttu-id="b3396-112">현재 페이지에서 키가 “GelButton”인 리소스를 찾지 못했으므로 요청한 리소스에 대한 리소스 조회 범위가 현재 페이지 범위를 벗어나서 정의된 애플리케이션 수준 리소스로 이어집니다.</span><span class="sxs-lookup"><span data-stu-id="b3396-112">No resource with key of "GelButton" is found in the current page, so the resource lookup scope for the requested resource continues beyond the current page and into the defined application-level resources.</span></span>  
  
 [!code-xaml[ResourcesApplication#ConsumingPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## <a name="see-also"></a><span data-ttu-id="b3396-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="b3396-113">See also</span></span>
- [<span data-ttu-id="b3396-114">XAML 리소스</span><span class="sxs-lookup"><span data-stu-id="b3396-114">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)
- [<span data-ttu-id="b3396-115">응용 프로그램 관리 개요</span><span class="sxs-lookup"><span data-stu-id="b3396-115">Application Management Overview</span></span>](../../../../docs/framework/wpf/app-development/application-management-overview.md)
- [<span data-ttu-id="b3396-116">방법 항목</span><span class="sxs-lookup"><span data-stu-id="b3396-116">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)
