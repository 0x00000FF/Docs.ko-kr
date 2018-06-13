---
title: '방법: 바인딩 유효성 검사 구현'
ms.date: 03/30/2017
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
ms.openlocfilehash: 347e38ba036e5c1a716a9edb75572c1a49f99631
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556967"
---
# <a name="how-to-implement-binding-validation"></a>방법: 바인딩 유효성 검사 구현
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 및 잘못 된 값을 입력 한 경우 사용자에 게 시각적 피드백을 제공 하는 스타일 트리거는 사용자 지정 유효성 검사 규칙에 기반 합니다.  
  
## <a name="example"></a>예제  
 텍스트의 콘텐츠는 <xref:System.Windows.Controls.TextBox> 에 바인딩된 다음 예제에서는 `Age` 속성 (int) 형식의 명명 된 바인딩 소스 개체의 `ods`합니다. 바인딩이 `AgeRangeRule`이라는 유효성 검사 규칙을 사용하도록 설정되어 있으므로 숫자가 아닌 문자 또는 21보다 작거나 130보다 큰 값을 입력하면 빨간색 느낌표가 텍스트 상자 옆에 나타나고 텍스트 상자 위로 마우스를 이동하면 오류 메시지가 포함된 도구 설명이 나타납니다.  
  
 [!code-xaml[BindValidation#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]  
  
 다음 예제에서는 구현의 `AgeRangeRule`에서 상속 되 <xref:System.Windows.Controls.ValidationRule> 재정의 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드. Int32.parse() 메서드가 값에 호출되어 값에 잘못된 문자가 포함되어 있지 않은지 확인합니다. <xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드가 반환 되는 <xref:System.Windows.Controls.ValidationResult> 인지 여부를 나타내는 값 유효한 분석 하는 동안 예외가 포착 되는 여부 및 기간 값이 하 한과 상한을 외 여부에 따라 합니다.  
  
 [!code-csharp[BindValidation#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]  
  
 다음 예제에서는 사용자 지정 <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` 만들어지는 유효성 검사 오류가 사용자에 게 알리도록 빨간색 느낌표가 표시 합니다. 컨트롤 템플릿을 사용하여 컨트롤의 모양을 다시 정의합니다.  
  
 [!code-xaml[BindValidation#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]  
  
 다음 예에서 같이 <xref:System.Windows.Controls.ToolTip> 라는 스타일을 사용 하 여 오류 메시지를 작성을 보여 주는 `textBoxInError`합니다. 하는 경우의 값 <xref:System.Windows.Controls.Validation.HasError%2A> 은 `true`, 현재의 도구 설명을 설정 하는 트리거 <xref:System.Windows.Controls.TextBox> 의 첫 번째 유효성 검사 오류를 합니다. <xref:System.Windows.Data.Binding.RelativeSource%2A> 로 설정 된 <xref:System.Windows.Data.RelativeSourceMode.Self>현재 요소에 참조 합니다.  
  
 [!code-xaml[BindValidation#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]  
  
 전체 예제는 [Binding Validation Sample](http://go.microsoft.com/fwlink/?LinkID=159972)(바인딩 유효성 검사 샘플)을 참조하세요.  
  
 경우에 사용자 지정을 제공 하지 않으면 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 유효성 검사 오류가 있을 때 사용자에 게 시각적 피드백을 제공 하는 기본 오류 템플릿이 나타납니다. 자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)의 “데이터 유효성 검사”를 참조하세요. 또한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]은 바인딩 소스 속성을 업데이트하는 동안 throw된 예외를 catch하는 기본 제공 유효성 검사 규칙을 제공합니다. 자세한 내용은 <xref:System.Windows.Controls.ExceptionValidationRule>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
