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
ms.openlocfilehash: bd26d396c238bfc53858320b8f4487df84b3436a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59312581"
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="047a1-102">방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 내용 정렬</span><span class="sxs-lookup"><span data-stu-id="047a1-102">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="047a1-103">데이터 바인딩된 경우에 Windows Forms 컨트롤 정렬 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="047a1-103">Windows Forms controls do not sort when they are data-bound.</span></span> <span data-ttu-id="047a1-104">정렬 된 데이터를 표시 하려면 정렬을 지 원하는 데이터 원본을 사용 하 여 한 후 결과 정렬할 데이터 원본입니다.</span><span class="sxs-lookup"><span data-stu-id="047a1-104">To display sorted data, use a data source that supports sorting and then have the data source sort it.</span></span> <span data-ttu-id="047a1-105">정렬을 지 원하는 데이터 원본의 데이터 뷰, 데이터 관리자, 보기 및 정렬 된 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="047a1-105">Data sources that support sorting are data views, data view managers, and sorted arrays.</span></span>  
  
 <span data-ttu-id="047a1-106">컨트롤이 데이터 바인딩되지 않은 경우에이 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="047a1-106">If the control is not data-bound, you can sort it.</span></span>  
  
### <a name="to-sort-the-list"></a><span data-ttu-id="047a1-107">목록을 정렬 하려면</span><span class="sxs-lookup"><span data-stu-id="047a1-107">To sort the list</span></span>  
  
1. <span data-ttu-id="047a1-108">`Sorted` 속성을 `true`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="047a1-108">Set the `Sorted` property to `true`.</span></span>  
  
     <span data-ttu-id="047a1-109">이 설정은 위치 정렬 된 순서 대로 모든 기존 목록 항목을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="047a1-109">This setting repositions all existing list items in sorted order.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="047a1-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="047a1-110">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="047a1-111">Windows Forms 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="047a1-111">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="047a1-112">방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤에서 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="047a1-112">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="047a1-113">ListBox 대신 Windows Forms ComboBox를 사용해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="047a1-113">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [<span data-ttu-id="047a1-114">옵션 목록 표시에 사용하는 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="047a1-114">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
