---
title: DatePicker
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], DatePicker
- DatePicker control [WPF]
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
ms.openlocfilehash: 34df32ceecf66061b74834dcecdef8a080b7af34
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565602"
---
# <a name="datepicker"></a>DatePicker
합니다 <xref:System.Windows.Controls.DatePicker> 컨트롤을 사용 하면 사용자가 입력 하 여 두 텍스트 필드에 또는 드롭 다운을 사용 하 여 날짜를 선택할 <xref:System.Windows.Controls.Calendar> 제어 합니다.  
  
 다음 그림에 표시 된 <xref:System.Windows.Controls.DatePicker>합니다.  
  
 ![DatePicker 컨트롤](../../../../docs/framework/wpf/controls/media/ndp-datepicker.png "NDP_DatePicker")  
DatePicker 컨트롤  
  
 많은 <xref:System.Windows.Controls.DatePicker> 컨트롤의 속성은 해당 기본 제공을 관리 하기 위한 <xref:System.Windows.Controls.Calendar>, 및 함수에 해당 하는 속성에 동일 하 게 <xref:System.Windows.Controls.Calendar>합니다. 특히 합니다 <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>, 및 <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> 속성을 동일 하 게 작동 해당 <xref:System.Windows.Controls.Calendar> 대응 합니다. 자세한 내용은 <xref:System.Windows.Controls.Calendar>을 참조하세요.  
  
 사용자가 날짜를 설정 하는 텍스트 필드에 직접 입력할 수는 <xref:System.Windows.Controls.DatePicker.Text%2A> 속성입니다. 경우는 <xref:System.Windows.Controls.DatePicker> 는 유효한 날짜 입력된 된 문자열을 변환할 수 없습니다는 <xref:System.Windows.Controls.DatePicker.DateValidationError> 이벤트가 발생 합니다. 기본적으로이 인해는 예외에 대 한 이벤트 처리기 <xref:System.Windows.Controls.DatePicker.DateValidationError> 설정할 수는 <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> 속성을 `false` 및 예외가 발생 하지 않게 합니다.  
  
## <a name="see-also"></a>참고자료
- [컨트롤](../../../../docs/framework/wpf/controls/index.md)
- [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)
