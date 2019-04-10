---
title: '방법: IListSource 인터페이스 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], implementing
- IListSource interface
ms.assetid: 63ce27aa-2e23-4fbd-8228-0c1726f6c421
ms.openlocfilehash: bd4e554b7e4be51847496307b50be3084d0115d5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159785"
---
# <a name="how-to-implement-the-ilistsource-interface"></a><span data-ttu-id="6e96c-102">방법: IListSource 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="6e96c-102">How to: Implement the IListSource Interface</span></span>
<span data-ttu-id="6e96c-103">구현 된 <xref:System.ComponentModel.IListSource> 인터페이스를 구현 하지 않는 바인딩 가능한 클래스를 만들려면 <xref:System.Collections.IList> 않지만 다른 위치에서 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e96c-103">Implement the <xref:System.ComponentModel.IListSource> interface to create a bindable class that does not implement <xref:System.Collections.IList> but instead provides a list from another location.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e96c-104">예제</span><span class="sxs-lookup"><span data-stu-id="6e96c-104">Example</span></span>  
 <span data-ttu-id="6e96c-105">다음 코드 예제를 구현 하는 방법에 설명 합니다 <xref:System.ComponentModel.IListSource> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="6e96c-105">The following code example demonstrates how to implement the <xref:System.ComponentModel.IListSource> interface.</span></span> <span data-ttu-id="6e96c-106">이라는 구성 요소 `EmployeeListSource` 노출를 <xref:System.Collections.IList> 구현 하 여 데이터 바인딩에 <xref:System.ComponentModel.IListSource.GetList%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="6e96c-106">A component named `EmployeeListSource` exposes an <xref:System.Collections.IList> for data binding by implementing the <xref:System.ComponentModel.IListSource.GetList%2A> method.</span></span>  
  
 [!code-csharp[System.ComponentModel.IListSource#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IListSource/CS/EmployeeListSource.cs#1)]
 [!code-vb[System.ComponentModel.IListSource#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IListSource/VB/EmployeeListSource.vb#1)]  
  
 [!code-csharp[System.ComponentModel.IListSource#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IListSource/CS/Employee.cs#10)]
 [!code-vb[System.ComponentModel.IListSource#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IListSource/VB/Employee.vb#10)]  
  
 [!code-csharp[System.ComponentModel.IListSource#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IListSource/CS/BusinessObjectBase.cs#100)]
 [!code-vb[System.ComponentModel.IListSource#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IListSource/VB/BusinessObjectBase.vb#100)]  
  
 [!code-csharp[System.ComponentModel.IListSource#1000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IListSource/CS/Form1.cs#1000)]
 [!code-vb[System.ComponentModel.IListSource#1000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IListSource/VB/Form1.vb#1000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6e96c-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="6e96c-107">Compiling the Code</span></span>  
 <span data-ttu-id="6e96c-108">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6e96c-108">This example requires:</span></span>  
  
-   <span data-ttu-id="6e96c-109">System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="6e96c-109">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e96c-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="6e96c-110">See also</span></span>

- <xref:System.ComponentModel.IListSource>
- <xref:System.ComponentModel.ITypedList>
- <xref:System.ComponentModel.BindingList%601>
- <xref:System.ComponentModel.IBindingList>
- [<span data-ttu-id="6e96c-111">데이터 바인딩 및 Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6e96c-111">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
