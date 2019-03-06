---
title: '방법: SelectedValue, SelectedValuePath 및 SelectedItem 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], SelectedValue properties
- Control class [WPF], SelectedItem properties
- Control class [WPF], TreeView properties
- Control class [WPF], SelectedValue properties
- TreeView control [WPF], SelectedItem properties
- SelectedValue [WPF], SelectedValuePath properties
- TreeView control [WPF], SelectedValuePath properties
- Control class [WPF], SelectedValuePath properties
- SelectedValue [WPF], SelectedItem properties
ms.assetid: 2fc92ad4-f02c-4f89-bbe9-d4978a7af0db
ms.openlocfilehash: e3f4e5e6a51426581082ab24a1c3a962e38846bd
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373831"
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a><span data-ttu-id="69476-102">방법: SelectedValue, SelectedValuePath 및 SelectedItem 사용</span><span class="sxs-lookup"><span data-stu-id="69476-102">How to: Use SelectedValue, SelectedValuePath, and SelectedItem</span></span>
<span data-ttu-id="69476-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> 및 <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 속성에 대 한 값을 지정 하는 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 의 <xref:System.Windows.Controls.TreeView>합니다.</span><span class="sxs-lookup"><span data-stu-id="69476-103">This example shows how to use the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> and <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> properties to specify a value for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> of a <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69476-104">예제</span><span class="sxs-lookup"><span data-stu-id="69476-104">Example</span></span>  
 <span data-ttu-id="69476-105"><xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 속성을 지정 하는 방법을 제공를 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> 에 대 한 합니다 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 에 <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="69476-105">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property provides a way to specify a <xref:System.Windows.Controls.TreeView.SelectedValue%2A> for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in a <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="69476-106">합니다 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 의 개체를 나타냅니다는 <xref:System.Windows.Controls.ItemsControl.Items%2A> 컬렉션 및 <xref:System.Windows.Controls.TreeView> 선택한 항목의 단일 속성의 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="69476-106">The <xref:System.Windows.Controls.TreeView.SelectedItem%2A> represents an object in the <xref:System.Windows.Controls.ItemsControl.Items%2A> collection and the <xref:System.Windows.Controls.TreeView> displays the value of a single property of the selected item.</span></span> <span data-ttu-id="69476-107">합니다 <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 속성의 값을 확인 하는 데 사용 되는 속성에 경로 지정 합니다 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="69476-107">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property specifies the path to the property that is used to determine the value of the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property.</span></span> <span data-ttu-id="69476-108">이 항목의 예제에서는이 개념을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="69476-108">The examples in this topic illustrate this concept.</span></span>  
  
 <span data-ttu-id="69476-109">다음 예제는 <xref:System.Windows.Data.XmlDataProvider> 직원 정보를 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="69476-109">The following example shows an <xref:System.Windows.Data.XmlDataProvider> that contains employee information.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 <span data-ttu-id="69476-110">다음 예제에서는 정의 <xref:System.Windows.HierarchicalDataTemplate> 표시 하는 `EmployeeName` 및 `EmployeeWorkDay` 의 `Employee`.</span><span class="sxs-lookup"><span data-stu-id="69476-110">The following example defines a <xref:System.Windows.HierarchicalDataTemplate> that displays the `EmployeeName` and `EmployeeWorkDay` of the `Employee`.</span></span> <span data-ttu-id="69476-111">유의 합니다 <xref:System.Windows.HierarchicalDataTemplate> 지정 하지 않습니다는 `EmployeeNumber` 템플릿의 일부로.</span><span class="sxs-lookup"><span data-stu-id="69476-111">Note that the <xref:System.Windows.HierarchicalDataTemplate> does not specify the `EmployeeNumber` as part of the template.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 <span data-ttu-id="69476-112">다음 예제와 <xref:System.Windows.Controls.TreeView> 를 사용 하는 이전에 정의 된 <xref:System.Windows.HierarchicalDataTemplate> 로 설정 하 고는 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> 속성을는 `EmployeeNumber`합니다.</span><span class="sxs-lookup"><span data-stu-id="69476-112">The following example shows a <xref:System.Windows.Controls.TreeView> that uses the previously defined <xref:System.Windows.HierarchicalDataTemplate> and that sets the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property to the `EmployeeNumber`.</span></span> <span data-ttu-id="69476-113">선택 하는 경우는 `EmployeeName` 에 <xref:System.Windows.Controls.TreeView>, <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 속성에서 반환 합니다 `EmployeeInfo` 선택한에 해당 하는 데이터 항목 `EmployeeName`.</span><span class="sxs-lookup"><span data-stu-id="69476-113">When you select an `EmployeeName` in the <xref:System.Windows.Controls.TreeView>, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property returns the `EmployeeInfo` data item that corresponds to the selected `EmployeeName`.</span></span> <span data-ttu-id="69476-114">그러나 때문에 <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 이 <xref:System.Windows.Controls.TreeView> 로 설정 되어 `EmployeeNumber`의 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> 로 설정 됩니다는 `EmployeeNumber`합니다.</span><span class="sxs-lookup"><span data-stu-id="69476-114">However, because the <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> of this <xref:System.Windows.Controls.TreeView> is set to `EmployeeNumber`, the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> is set to the `EmployeeNumber`.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a><span data-ttu-id="69476-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="69476-115">See also</span></span>
- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [<span data-ttu-id="69476-116">TreeView 개요</span><span class="sxs-lookup"><span data-stu-id="69476-116">TreeView Overview</span></span>](treeview-overview.md)
- [<span data-ttu-id="69476-117">방법 항목</span><span class="sxs-lookup"><span data-stu-id="69476-117">How-to Topics</span></span>](treeview-how-to-topics.md)
