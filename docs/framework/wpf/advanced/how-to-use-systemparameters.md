---
title: '방법: SystemParameters 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], SystemParameters
ms.assetid: 02e7a5de-94eb-4953-b91c-52e6c872ad5b
ms.openlocfilehash: 344fb54b48bcbf188b36a29d8205c21deff713c4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199858"
---
# <a name="how-to-use-systemparameters"></a><span data-ttu-id="67922-102">방법: SystemParameters 사용</span><span class="sxs-lookup"><span data-stu-id="67922-102">How to: Use SystemParameters</span></span>
<span data-ttu-id="67922-103">액세스 속성을 사용 하는 방법을 보여주는이 예제 <xref:System.Windows.SystemParameters> 스타일을 지정 하거나 단추를 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="67922-103">This example shows how to access and use the properties of <xref:System.Windows.SystemParameters> in order to style or customize a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67922-104">예제</span><span class="sxs-lookup"><span data-stu-id="67922-104">Example</span></span>  
 <span data-ttu-id="67922-105">시스템 리소스는 시스템 설정과 일관된 시각적 효과를 만들 수 있도록 몇 가지 시스템 기반 설정을 리소스로 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="67922-105">System resources expose several system based settings as resources in order to help you create visuals that are consistent with system settings.</span></span> <span data-ttu-id="67922-106"><xref:System.Windows.SystemParameters> 시스템 매개 변수 값 속성 및 값에 바인딩되는 리소스 키를 모두 포함 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="67922-106"><xref:System.Windows.SystemParameters> is a class that contains both system parameter value properties, and resource keys that bind to the values.</span></span> <span data-ttu-id="67922-107">예를 들어 <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> 되는 <xref:System.Windows.SystemParameters> 속성 값 및 <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> 해당 리소스 키입니다.</span><span class="sxs-lookup"><span data-stu-id="67922-107">For example, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> is a <xref:System.Windows.SystemParameters> property value and <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> is the corresponding resource key.</span></span>  
  
 <span data-ttu-id="67922-108">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서의 멤버를 사용할 수 있습니다 <xref:System.Windows.SystemParameters> 는 정적 속성 사용 또는 동적 리소스 참조 (정적 속성 값을 키로).</span><span class="sxs-lookup"><span data-stu-id="67922-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can use the members of <xref:System.Windows.SystemParameters> as either a static property usage, or a dynamic resource references (with the static property value as the key).</span></span> <span data-ttu-id="67922-109">애플리케이션이 실행되는 동안 시스템 기반 값을 자동으로 업데이트하려면 동적 리소스 참조를 사용하고 자동으로 업데이트하지 않으려면 정적 참조를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="67922-109">Use a dynamic resource reference if you want the system based value to update automatically while the application runs; otherwise, use a static reference.</span></span> <span data-ttu-id="67922-110">리소스 키 접미사가 `Key` 속성 이름에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="67922-110">Resource keys have the suffix `Key` appended to the property name.</span></span>  
  
 <span data-ttu-id="67922-111">다음 예제에서는 액세스 하 고 정적 값을 사용 하는 방법을 보여 줍니다 <xref:System.Windows.SystemParameters> 스타일을 지정 하거나 단추를 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="67922-111">The following example shows how to access and use the static values of <xref:System.Windows.SystemParameters> to style or customize a button.</span></span> <span data-ttu-id="67922-112">이 태그 예제에서는 단추의 크기를 조정 적용 하 여 <xref:System.Windows.SystemParameters> 단추에는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="67922-112">This markup example sizes a button by applying <xref:System.Windows.SystemParameters> values to a button.</span></span>  
  
 [!code-xaml[SystemRes_snip#ParameterStaticResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#parameterstaticresources)]  
  
 <span data-ttu-id="67922-113">값을 사용 하도록 <xref:System.Windows.SystemParameters> 코드에서 필요가 없습니다 정적 참조 또는 동적 리소스 참조를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="67922-113">To use the values of <xref:System.Windows.SystemParameters> in code, you do not have to use either static references or dynamic resource references.</span></span> <span data-ttu-id="67922-114">대신 값을 사용 합니다 <xref:System.Windows.SystemParameters> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="67922-114">Instead, use the values of the <xref:System.Windows.SystemParameters> class.</span></span> <span data-ttu-id="67922-115">키가 아닌 속성이 정적 속성의 런타임 동작으로 정의 된 것 이지만 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시스템에서 호스트 속성에서 실시간으로 다시 계산 하 고 적절 하 게 시스템 값을 사용자가 수행한 변경 작업에 대 한 고려 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67922-115">Although the non-key properties are apparently defined as static properties, the runtime behavior of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] as hosted by the system will reevaluate the properties in realtime, and will properly account for user-driven changes to system values.</span></span> <span data-ttu-id="67922-116">다음 예제를 사용 하 여 단추의 높이 너비를 설정 하는 방법을 보여 줍니다 <xref:System.Windows.SystemParameters> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="67922-116">The following example shows how to set the width and height of a button by using <xref:System.Windows.SystemParameters> values.</span></span>  
  
 [!code-csharp[SystemRes_snip#ParameterResourcesCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#parameterresourcescode)]
 [!code-vb[SystemRes_snip#ParameterResourcesCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#parameterresourcescode)]  
  
## <a name="see-also"></a><span data-ttu-id="67922-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="67922-117">See also</span></span>

- <xref:System.Windows.SystemParameters>
- [<span data-ttu-id="67922-118">시스템 브러시로 영역 그리기</span><span class="sxs-lookup"><span data-stu-id="67922-118">Paint an Area with a System Brush</span></span>](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="67922-119">SystemFonts 사용</span><span class="sxs-lookup"><span data-stu-id="67922-119">Use SystemFonts</span></span>](how-to-use-systemfonts.md)
- [<span data-ttu-id="67922-120">시스템 매개 변수 키 사용</span><span class="sxs-lookup"><span data-stu-id="67922-120">Use System Parameters Keys</span></span>](how-to-use-system-parameters-keys.md)
- [<span data-ttu-id="67922-121">방법 항목</span><span class="sxs-lookup"><span data-stu-id="67922-121">How-to Topics</span></span>](resources-how-to-topics.md)
