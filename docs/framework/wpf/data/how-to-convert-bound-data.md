---
title: '방법: 바인딩된 데이터 변환'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- converting [WPF], bound data
- data binding [WPF], converting bound data
- binding data [WPF], converting bound data
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
ms.openlocfilehash: f9ad390626092d481bf47f017f643a29302c1b29
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458863"
---
# <a name="how-to-convert-bound-data"></a>방법: 바인딩된 데이터 변환
이 예제에서는 바인딩에서 사용 되는 데이터로 변환을 적용 하는 방법을 보여 줍니다.  
  
 바인딩하는 동안 데이터를 변환 하려면 <xref:System.Windows.Data.IValueConverter.Convert%2A> 및 <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> 메서드를 포함 하는 <xref:System.Windows.Data.IValueConverter> 인터페이스를 구현 하는 클래스를 만들어야 합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 연도, 월, 일만 표시 되도록 전달 된 날짜 값을 변환 하는 날짜 변환기의 구현을 보여 줍니다. <xref:System.Windows.Data.IValueConverter> 인터페이스를 구현 하는 경우 다음 예제와 같이 변환에 관련 된 데이터 형식을 개발 도구에 나타내려면 <xref:System.Windows.Data.ValueConversionAttribute> 특성으로 구현을 데코 레이트 하는 것이 좋습니다.  
  
 [!code-csharp[DataBindingLab#18](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 변환기를 만든 후에는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일에 리소스로 추가할 수 있습니다. 다음 예제에서 *src* 는 *DateConverter* 가 정의 된 네임 스페이스에 매핑됩니다.  
  
 [!code-xaml[DataBindingLab#15](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 마지막으로 다음 구문을 사용 하 여 바인딩에서 변환기를 사용할 수 있습니다. 다음 예제에서 <xref:System.Windows.Controls.TextBlock>의 텍스트 콘텐츠는 외부 데이터 원본의 속성인 날짜/ *에 바인딩됩니다*.  
  
 [!code-xaml[DataBindingLab#17](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 위의 예제에서 참조 하는 스타일 리소스는이 항목에 표시 되지 않은 리소스 섹션에서 정의 됩니다.  
  
## <a name="see-also"></a>참조

- [바인딩 유효성 검사 구현](how-to-implement-binding-validation.md)
- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [방법 항목](data-binding-how-to-topics.md)
