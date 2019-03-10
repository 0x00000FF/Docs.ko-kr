---
title: '방법: 추가 및 제거할 항목을 Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- combo boxes [Windows Forms], adding items
- list boxes [Windows Forms], removing items
- ComboBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], adding and removing items
- list boxes [Windows Forms], adding items
- combo boxes [Windows Forms], removing items
- CheckedListBox control [Windows Forms], adding and removing items
ms.assetid: 7224c8d2-4118-443e-ae1e-d7c17d1e69ee
ms.openlocfilehash: 1430975a48fb0755c6b08d6d5c183d8f29434f55
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710448"
---
# <a name="how-to-add-and-remove-items-from-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="9b119-102">방법: 추가 및 제거할 항목을 Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9b119-102">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="9b119-103">항목을 Windows Forms 콤보 상자, 목록 상자에 추가할 수 있습니다 하거나 이러한 컨트롤을 다양 한 데이터 원본에 바인딩될 수 있으므로 다양 한 방법으로 목록 상자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b119-103">Items can be added to a Windows Forms combo box, list box, or checked list box in a variety of ways, because these controls can be bound to a variety of data sources.</span></span> <span data-ttu-id="9b119-104">그러나이 항목에서는 가장 간단한 방법을 설명 하며 데이터 바인딩이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b119-104">However, this topic demonstrates the simplest method and requires no data binding.</span></span> <span data-ttu-id="9b119-105">표시 된 항목은 일반적으로 문자열입니다. 그러나 모든 개체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b119-105">The items displayed are usually strings; however, any object can be used.</span></span> <span data-ttu-id="9b119-106">컨트롤에 표시 되는 텍스트를 반환 하는 값 개체의 `ToString` 메서드.</span><span class="sxs-lookup"><span data-stu-id="9b119-106">The text that is displayed in the control is the value returned by the object's `ToString` method.</span></span>  
  
### <a name="to-add-items"></a><span data-ttu-id="9b119-107">항목을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="9b119-107">To add items</span></span>  
  
1.  <span data-ttu-id="9b119-108">목록에 문자열 또는 개체를 사용 하 여 추가 합니다 `Add` 메서드는 `ObjectCollection` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9b119-108">Add the string or object to the list by using the `Add` method of the `ObjectCollection` class.</span></span> <span data-ttu-id="9b119-109">컬렉션은 사용 하 여 참조를 `Items` 속성:</span><span class="sxs-lookup"><span data-stu-id="9b119-109">The collection is referenced using the `Items` property:</span></span>  
  
    ```vb  
    ComboBox1.Items.Add("Tokyo")  
    ```  
  
    ```csharp  
    comboBox1.Items.Add("Tokyo");  
    ```  
  
    ```cpp  
    comboBox1->Items->Add("Tokyo");  
    ```  
  
     - <span data-ttu-id="9b119-110">또는</span><span class="sxs-lookup"><span data-stu-id="9b119-110">or -</span></span>  
  
2.  <span data-ttu-id="9b119-111">문자열 또는 개체를 사용 하 여 목록에서 원하는 지점에 삽입 된 `Insert` 메서드:</span><span class="sxs-lookup"><span data-stu-id="9b119-111">Insert the string or object at the desired point in the list with the `Insert` method:</span></span>  
  
    ```vb  
    CheckedListBox1.Items.Insert(0, "Copenhagen")  
    ```  
  
    ```csharp  
    checkedListBox1.Items.Insert(0, "Copenhagen");  
    ```  
  
    ```cpp  
    checkedListBox1->Items->Insert(0, "Copenhagen");  
    ```  
  
     - <span data-ttu-id="9b119-112">또는</span><span class="sxs-lookup"><span data-stu-id="9b119-112">or -</span></span>  
  
3.  <span data-ttu-id="9b119-113">전체 배열에 할당 된 `Items` 컬렉션:</span><span class="sxs-lookup"><span data-stu-id="9b119-113">Assign an entire array to the `Items` collection:</span></span>  
  
    ```vb  
    Dim ItemObject(9) As System.Object  
    Dim i As Integer  
       For i = 0 To 9  
       ItemObject(i) = "Item" & i  
    Next i  
    ListBox1.Items.AddRange(ItemObject)  
    ```  
  
    ```csharp  
    System.Object[] ItemObject = new System.Object[10];  
    for (int i = 0; i <= 9; i++)  
    {  
       ItemObject[i] = "Item" + i;  
    }  
    listBox1.Items.AddRange(ItemObject);  
    ```  
  
    ```cpp  
    Array<System::Object^>^ ItemObject = gcnew Array<System::Object^>(10);  
    for (int i = 0; i <= 9; i++)  
    {  
       ItemObject[i] = String::Concat("Item", i.ToString());  
    }  
    listBox1->Items->AddRange(ItemObject);  
    ```  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="9b119-114">항목을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="9b119-114">To remove an item</span></span>  
  
1.  <span data-ttu-id="9b119-115">호출 된 `Remove` 또는 `RemoveAt` 항목을 삭제 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="9b119-115">Call the `Remove` or `RemoveAt` method to delete items.</span></span>  
  
     <span data-ttu-id="9b119-116">`Remove` 제거할 항목을 지정 하는 하나의 인수가 있습니다.`RemoveAt`</span><span class="sxs-lookup"><span data-stu-id="9b119-116">`Remove` has one argument that specifies the item to remove.`RemoveAt`</span></span> <span data-ttu-id="9b119-117">지정된 된 인덱스 번호를 사용 하 여 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b119-117">removes the item with the specified index number.</span></span>  
  
    ```vb  
    ' To remove item with index 0:  
    ComboBox1.Items.RemoveAt(0)  
    ' To remove currently selected item:  
    ComboBox1.Items.Remove(ComboBox1.SelectedItem)  
    ' To remove "Tokyo" item:  
    ComboBox1.Items.Remove("Tokyo")  
    ```  
  
    ```csharp  
    // To remove item with index 0:  
    comboBox1.Items.RemoveAt(0);  
    // To remove currently selected item:  
    comboBox1.Items.Remove(comboBox1.SelectedItem);  
    // To remove "Tokyo" item:  
    comboBox1.Items.Remove("Tokyo");  
    ```  
  
    ```cpp  
    // To remove item with index 0:  
    comboBox1->Items->RemoveAt(0);  
    // To remove currently selected item:  
    comboBox1->Items->Remove(comboBox1->SelectedItem);  
    // To remove "Tokyo" item:  
    comboBox1->Items->Remove("Tokyo");  
    ```  
  
### <a name="to-remove-all-items"></a><span data-ttu-id="9b119-118">모든 항목을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="9b119-118">To remove all items</span></span>  
  
1.  <span data-ttu-id="9b119-119">호출 된 `Clear` 컬렉션에서 모든 항목을 제거 하는 방법.</span><span class="sxs-lookup"><span data-stu-id="9b119-119">Call the `Clear` method to remove all items from the collection:</span></span>  
  
    ```vb  
    ListBox1.Items.Clear()  
    ```  
  
    ```csharp  
    listBox1.Items.Clear();  
    ```  
  
    ```cpp  
    listBox1->Items->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9b119-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="9b119-120">See also</span></span>
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="9b119-121">방법: Windows의 내용을 정렬할 Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9b119-121">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="9b119-122">ListBox 대신 Windows Forms ComboBox를 사용해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="9b119-122">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [<span data-ttu-id="9b119-123">옵션 목록 표시에 사용된 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9b119-123">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
