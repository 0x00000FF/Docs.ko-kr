---
title: "Windows Forms DataGridView 컨트롤의 데이터 형식 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in grids
- data grids [Windows Forms], formatting data
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e716dc74946ac6f18ab82c6834518f0bd6bbea76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="data-formatting-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="b04db-102">Windows Forms DataGridView 컨트롤의 데이터 형식 지정</span><span class="sxs-lookup"><span data-stu-id="b04db-102">Data Formatting in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="b04db-103"><xref:System.Windows.Forms.DataGridView> 컨트롤은 셀 값과 부모 열을 표시 하는 데이터 형식 사이의 자동 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04db-103">The <xref:System.Windows.Forms.DataGridView> control provides automatic conversion between cell values and the data types that the parent columns display.</span></span> <span data-ttu-id="b04db-104">예를 들어 텍스트 상자 열 날짜, 시간, 숫자 및 열거형 값의 문자열 표현을 표시 하 고 사용자가 입력 한 문자열 값을 데이터 저장소에 필요한 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04db-104">Text box columns, for example, display string representations of date, time, number, and enumeration values, and convert user-entered string values to the types required by the data store.</span></span>  
  
## <a name="formatting-with-the-datagridviewcellstyle-class"></a><span data-ttu-id="b04db-105">DataGridViewCellStyle 클래스와 형식 지정</span><span class="sxs-lookup"><span data-stu-id="b04db-105">Formatting with the DataGridViewCellStyle class</span></span>  
 <span data-ttu-id="b04db-106"><xref:System.Windows.Forms.DataGridView> 컨트롤의 셀 값을 통해 기본 데이터 형식을 제공는 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b04db-106">The <xref:System.Windows.Forms.DataGridView> control provides basic data formatting of cell values through the <xref:System.Windows.Forms.DataGridViewCellStyle> class.</span></span> <span data-ttu-id="b04db-107">사용할 수는 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> 속성에 설명 된 형식 지정자를 사용 하 여 현재 기본 문화권에 대 한 날짜, 시간, 숫자 및 열거형 값의 서식 지정을 [형식 지정](../../../../docs/standard/base-types/formatting-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b04db-107">You can use the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property to format date, time, number, and enumeration values for the current default culture using the format specifiers described in [Formatting Types](../../../../docs/standard/base-types/formatting-types.md).</span></span> <span data-ttu-id="b04db-108">사용 하 여 특정 문화권에 대 한 이러한 값의 형식을 지정할 수도 있습니다는 <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b04db-108">You can also format these values for specific cultures using the <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A> property.</span></span> <span data-ttu-id="b04db-109">지정된 된 형식의 데이터를 표시 하 고는 사용자가 지정된 된 형식으로 입력 데이터를 구문 분석에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b04db-109">The specified format is used both to display data and to parse data that the user enters in the specified format.</span></span>  
  
 <span data-ttu-id="b04db-110"><xref:System.Windows.Forms.DataGridViewCellStyle> 클래스 단어 잘림 방지, 텍스트 맞춤 및 null 데이터베이스 값의 사용자 지정 표시에 대 한 추가 서식 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04db-110">The <xref:System.Windows.Forms.DataGridViewCellStyle> class provides additional formatting properties for wordwrap, text alignment, and the custom display of null database values.</span></span> <span data-ttu-id="b04db-111">자세한 내용은 [방법: Windows Forms DataGridView 컨트롤의 데이터 형식 지정](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b04db-111">For more information, see [How to: Format Data in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="formatting-with-the-cellformatting-event"></a><span data-ttu-id="b04db-112">CellFormatting 이벤트와 서식 지정</span><span class="sxs-lookup"><span data-stu-id="b04db-112">Formatting with the CellFormatting Event</span></span>  
 <span data-ttu-id="b04db-113">기본 서식를 충족 하지 않으면 요구 사항에 대 한 처리기에서 서식 지정 하는 사용자 지정 데이터를 제공할 수 있습니다는 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="b04db-113">If the basic formatting does not meet your needs, you can provide custom data formatting in a handler for the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="b04db-114"><xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> 처리기에 전달에 <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> 처음에 셀 값을 포함 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b04db-114">The <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> passed to the handler has a <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> property that initially contains the cell value.</span></span> <span data-ttu-id="b04db-115">일반적으로이 값 표시 형식에 자동으로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b04db-115">Normally, this value is automatically converted to the display type.</span></span> <span data-ttu-id="b04db-116">값을 직접 변환 하려면 설정는 <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> 속성을 표시 하는 형식의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b04db-116">To convert the value yourself, set the <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> property to a value of the display type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b04db-117">사용자가 변경한 셀에 대 한 형식 문자열 적용 경우 재정의 <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> 속성 값을 설정 하지 않으면는 <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="b04db-117">If a format string is in effect for the cell, it overrides your change of the <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> property value unless you set the <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="b04db-118"><xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트는 설정 하려는 경우에 유용도 <xref:System.Windows.Forms.DataGridViewCellStyle> 개별 셀에 대 한 속성 값을 기반으로 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04db-118">The <xref:System.Windows.Forms.DataGridView.CellFormatting> event is also useful when you want to set <xref:System.Windows.Forms.DataGridViewCellStyle> properties for individual cells based on their values.</span></span> <span data-ttu-id="b04db-119">자세한 내용은 참조 [하는 방법: Windows Forms DataGridView 컨트롤에서 사용자 지정 데이터 형식](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b04db-119">For more information, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="b04db-120">기본 구문 분석 하는 사용자가 지정한 값에 맞지 않으면 요구에 맞게 처리할 수 있습니다는 <xref:System.Windows.Forms.DataGridView.CellParsing> 의 이벤트는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용자 지정을 구문 분석을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04db-120">If the default parsing of user-specified values does not meet your needs, you can handle the <xref:System.Windows.Forms.DataGridView.CellParsing> event of the <xref:System.Windows.Forms.DataGridView> control to provide custom parsing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b04db-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b04db-121">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 [<span data-ttu-id="b04db-122">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="b04db-122">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="b04db-123">Windows Forms DataGridView 컨트롤의 셀 스타일</span><span class="sxs-lookup"><span data-stu-id="b04db-123">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="b04db-124">방법: Windows Forms DataGridView 컨트롤의 데이터 형식 지정</span><span class="sxs-lookup"><span data-stu-id="b04db-124">How to: Format Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="b04db-125">방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b04db-125">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
