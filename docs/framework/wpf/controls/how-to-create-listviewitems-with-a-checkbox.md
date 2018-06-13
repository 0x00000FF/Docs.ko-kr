---
title: '방법: CheckBox를 사용하여 ListViewItems 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ListView
- controls [WPF], CheckBox
- ListView controls [WPF], CheckBox controls
- CheckBox control [WPF], ListView control
ms.assetid: f6d66c7f-906c-4f65-a55a-0ede9d00e26a
ms.openlocfilehash: 424bc25f9c584017d80ba1c8f1517211595fd247
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552677"
---
# <a name="how-to-create-listviewitems-with-a-checkbox"></a><span data-ttu-id="509fb-102">방법: CheckBox를 사용하여 ListViewItems 만들기</span><span class="sxs-lookup"><span data-stu-id="509fb-102">How to: Create ListViewItems with a CheckBox</span></span>
<span data-ttu-id="509fb-103">열을 표시 하는 방법을 보여 주는이 예제 <xref:System.Windows.Controls.CheckBox> 컨트롤에 <xref:System.Windows.Controls.ListView> 컨트롤을 사용 하는 <xref:System.Windows.Controls.GridView>합니다.</span><span class="sxs-lookup"><span data-stu-id="509fb-103">This example shows how to display a column of <xref:System.Windows.Controls.CheckBox> controls in a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="509fb-104">예제</span><span class="sxs-lookup"><span data-stu-id="509fb-104">Example</span></span>  
 <span data-ttu-id="509fb-105">포함 된 열을 만들려면 <xref:System.Windows.Controls.CheckBox> 컨트롤에 <xref:System.Windows.Controls.ListView>, 만들는 <xref:System.Windows.DataTemplate> 를 포함 하는 <xref:System.Windows.Controls.CheckBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="509fb-105">To create a column that contains <xref:System.Windows.Controls.CheckBox> controls in a <xref:System.Windows.Controls.ListView>, create a <xref:System.Windows.DataTemplate> that contains a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="509fb-106">다음 설정의 <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> 의 <xref:System.Windows.Controls.GridViewColumn> 에 <xref:System.Windows.DataTemplate>합니다.</span><span class="sxs-lookup"><span data-stu-id="509fb-106">Then set the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> of a <xref:System.Windows.Controls.GridViewColumn> to the <xref:System.Windows.DataTemplate>.</span></span>  
  
 <span data-ttu-id="509fb-107">다음 예제에서는 한 <xref:System.Windows.DataTemplate> 를 포함 하는 <xref:System.Windows.Controls.CheckBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="509fb-107">The following example shows a <xref:System.Windows.DataTemplate> that contains a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="509fb-108">예제는 <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 속성의는 <xref:System.Windows.Controls.CheckBox> 에 <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> 속성 값이는 <xref:System.Windows.Controls.ListViewItem> 해당 항목을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="509fb-108">The example binds the <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> property of the <xref:System.Windows.Controls.CheckBox> to the <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> property value of the <xref:System.Windows.Controls.ListViewItem> that contains it.</span></span> <span data-ttu-id="509fb-109">따라서,는 <xref:System.Windows.Controls.ListViewItem> 를 포함 하는 <xref:System.Windows.Controls.CheckBox> 을 선택 하면는 <xref:System.Windows.Controls.CheckBox> 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="509fb-109">Therefore, when the <xref:System.Windows.Controls.ListViewItem> that contains the <xref:System.Windows.Controls.CheckBox> is selected, the <xref:System.Windows.Controls.CheckBox> is checked.</span></span>  
  
 [!code-xaml[ListViewChkBox#CheckBoxDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#checkboxdatatemplate)]  
  
 <span data-ttu-id="509fb-110">열을 만드는 방법을 보여 주는 다음 예제 <xref:System.Windows.Controls.CheckBox> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="509fb-110">The following example shows how to create a column of <xref:System.Windows.Controls.CheckBox> controls.</span></span> <span data-ttu-id="509fb-111">예제에서는 열으로 만들려면는 <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> 의 속성은 <xref:System.Windows.Controls.GridViewColumn> 에 <xref:System.Windows.DataTemplate>합니다.</span><span class="sxs-lookup"><span data-stu-id="509fb-111">To make the column, the example sets the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> property of the <xref:System.Windows.Controls.GridViewColumn> to the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewChkBox#GridViewColumnCheckBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#gridviewcolumncheckbox)]  
  
## <a name="see-also"></a><span data-ttu-id="509fb-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="509fb-112">See Also</span></span>  
 <xref:System.Windows.Controls.Control>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="509fb-113">ListView 개요</span><span class="sxs-lookup"><span data-stu-id="509fb-113">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="509fb-114">방법 항목</span><span class="sxs-lookup"><span data-stu-id="509fb-114">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="509fb-115">GridView 개요</span><span class="sxs-lookup"><span data-stu-id="509fb-115">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
