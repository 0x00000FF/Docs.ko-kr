---
title: '방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 내용 정렬'
ms.date: 03/30/2017
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
ms.openlocfilehash: 8b8f9c7ad0ad7d3bbb7f3eeffd44e555207b82c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535648"
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="eba2d-102">방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 내용 정렬</span><span class="sxs-lookup"><span data-stu-id="eba2d-102">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="eba2d-103">Windows Forms 컨트롤은 데이터 바인딩 때 정렬 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eba2d-103">Windows Forms controls do not sort when they are data-bound.</span></span> <span data-ttu-id="eba2d-104">정렬 된 데이터를 표시 하려면 정렬을 지 원하는 데이터 원본을 사용 하 여 한 다음 결과 정렬할 데이터 원본.</span><span class="sxs-lookup"><span data-stu-id="eba2d-104">To display sorted data, use a data source that supports sorting and then have the data source sort it.</span></span> <span data-ttu-id="eba2d-105">정렬을 지 원하는 데이터 원본 데이터 뷰, 데이터 뷰, 관리자 및 정렬 된 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="eba2d-105">Data sources that support sorting are data views, data view managers, and sorted arrays.</span></span>  
  
 <span data-ttu-id="eba2d-106">컨트롤이 데이터 바인딩되지 않은 경우에이 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba2d-106">If the control is not data-bound, you can sort it.</span></span>  
  
### <a name="to-sort-the-list"></a><span data-ttu-id="eba2d-107">목록을 정렬 하려면</span><span class="sxs-lookup"><span data-stu-id="eba2d-107">To sort the list</span></span>  
  
1.  <span data-ttu-id="eba2d-108">`Sorted` 속성을 `true`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="eba2d-108">Set the `Sorted` property to `true`.</span></span>  
  
     <span data-ttu-id="eba2d-109">이 설정은 위치 정렬 된 순서 대로 모든 기존 목록 항목을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="eba2d-109">This setting repositions all existing list items in sorted order.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eba2d-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eba2d-110">See Also</span></span>  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 <xref:System.Windows.Forms.CheckedListBox>  
 [<span data-ttu-id="eba2d-111">Windows Forms 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="eba2d-111">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="eba2d-112">방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤에서 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="eba2d-112">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [<span data-ttu-id="eba2d-113">ListBox 대신 Windows Forms ComboBox를 사용해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="eba2d-113">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)  
 [<span data-ttu-id="eba2d-114">옵션 목록 표시에 사용된 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="eba2d-114">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
