---
title: '방법: 선택키가 있고 텍스트 줄 바꿈을 사용하는 컨트롤 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- access keys [WPF], control for
- controls [WPF], text wrapping
- wrapping text [WPF]
- keys [WPF], control for
- controls [WPF], access keys
- text wrapping [WPF]
ms.assetid: 205099d9-2551-4302-a25e-a15af9f67e04
ms.openlocfilehash: 8343c660ddeb5487f46e87534e555936d1b86371
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553790"
---
# <a name="how-to-create-a-control-that-has-an-access-key-and-text-wrapping"></a><span data-ttu-id="7a4c2-102">방법: 선택키가 있고 텍스트 줄 바꿈을 사용하는 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="7a4c2-102">How to: Create a Control That Has an Access Key and Text Wrapping</span></span>
<span data-ttu-id="7a4c2-103">이 예제에서는 선택키가 있고 텍스트 배치를 지원하는 컨트롤을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-103">This example shows how to create a control that has an access key and supports text wrapping.</span></span> <span data-ttu-id="7a4c2-104">이 예제에서는 사용는 <xref:System.Windows.Controls.Label> 컨트롤을 이러한 개념을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-104">The example uses a <xref:System.Windows.Controls.Label> control to illustrate these concepts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a4c2-105">예제</span><span class="sxs-lookup"><span data-stu-id="7a4c2-105">Example</span></span>  
 <span data-ttu-id="7a4c2-106">**레이블에 텍스트 배치 추가**</span><span class="sxs-lookup"><span data-stu-id="7a4c2-106">**Add Text Wrapping to Your Label**</span></span>  
  
 <span data-ttu-id="7a4c2-107"><xref:System.Windows.Controls.Label> 컨트롤에 텍스트 줄 바꿈을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-107">The <xref:System.Windows.Controls.Label> control does not support text wrapping.</span></span> <span data-ttu-id="7a4c2-108">여러 줄로 줄 바꿈되는 레이블이 필요한 경우 텍스트 배치를 지원하는 다른 요소를 중첩시키고 해당 요소를 레이블 내부에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-108">If you need a label that wraps across multiple lines, you can nest another element that does support text wrapping and put the element inside the label.</span></span> <span data-ttu-id="7a4c2-109">사용 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.TextBlock> 여러 줄의 텍스트를 래핑하는 레이블 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-109">The following example shows how to use a <xref:System.Windows.Controls.TextBlock> to make a label that wraps several lines of text.</span></span>  
  
 [!code-xaml[LabelSnippet#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#5)]  
  
 <span data-ttu-id="7a4c2-110">**레이블에 선택키 및 텍스트 배치 추가**</span><span class="sxs-lookup"><span data-stu-id="7a4c2-110">**Add an Access Key and Text Wrapping to Your Label**</span></span>  
  
 <span data-ttu-id="7a4c2-111">필요한 경우 한 <xref:System.Windows.Controls.Label> 키 (니모닉)을 사용 하 여는 <xref:System.Windows.Controls.AccessText> 내에 있는 요소는 <xref:System.Windows.Controls.Label>합니다.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-111">If you need a <xref:System.Windows.Controls.Label> that has an access key (mnemonic), use the <xref:System.Windows.Controls.AccessText> element that is inside the <xref:System.Windows.Controls.Label>.</span></span>  
  
 <span data-ttu-id="7a4c2-112">와 같은 컨트롤 <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, 및 <xref:System.Windows.Controls.GroupBox> 기본 컨트롤 템플릿이 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-112">Controls such as <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, and <xref:System.Windows.Controls.GroupBox> have default control templates.</span></span> <span data-ttu-id="7a4c2-113">이러한 템플릿에 포함 되어는 <xref:System.Windows.Controls.ContentPresenter>합니다.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-113">These templates contain a <xref:System.Windows.Controls.ContentPresenter>.</span></span> <span data-ttu-id="7a4c2-114">에 설정할 수 있는 속성 중 하나는 <xref:System.Windows.Controls.ContentPresenter> 은 <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>= "true", 컨트롤에 대 한 액세스 키를 지정 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-114">One of the properties that you can set on the <xref:System.Windows.Controls.ContentPresenter> is <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>="true", which you can use to specify an access key for the control.</span></span>  
  
 <span data-ttu-id="7a4c2-115">만드는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.Label> 선택 키가 있는 및 텍스트 줄 바꿈을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-115">The following example shows how to create a <xref:System.Windows.Controls.Label> that has an access key and supports text wrapping.</span></span> <span data-ttu-id="7a4c2-116">예제에서는 텍스트 줄 바꿈을 사용 하도록 설정 하려면는 <xref:System.Windows.Controls.AccessText.TextWrapping%2A> 밑줄 문자 선택 키를 지정 하는를 사용 하 여 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-116">To enable text wrapping, the example sets the <xref:System.Windows.Controls.AccessText.TextWrapping%2A> property and uses an underline character to specify the access key.</span></span> <span data-ttu-id="7a4c2-117">이 경우 밑줄 문자 바로 다음에 오는 문자가 선택키가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-117">(The character that immediately follows the underline character is the access key.)</span></span>  
  
 [!code-xaml[LabelSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="7a4c2-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a4c2-118">See Also</span></span>  
 [<span data-ttu-id="7a4c2-119">방법: 레이블의 대상 속성 설정</span><span class="sxs-lookup"><span data-stu-id="7a4c2-119">How to: Set the Target Property of a Label</span></span>](http://msdn.microsoft.com/library/b24c6977-ebcb-4855-a9bb-3fd4435af8f8)
