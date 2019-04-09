---
title: '방법: 사용자 지정 개체에 대한 유효성 검사 논리 구현'
ms.date: 08/02/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- checking for validation errors [WPF]
- validation errors [WPF], checking for
- implementing validation logic on custom objects [WPF]
- custom objects [WPF], implementing validation logic on
ms.assetid: 751fda9b-44f9-4d63-b4f2-1df07ac41e0f
ms.openlocfilehash: 8520504757e9e9ec9557b84ca2608b4cb99daf62
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085924"
---
# <a name="how-to-implement-validation-logic-on-custom-objects"></a><span data-ttu-id="afc47-102">방법: 사용자 지정 개체에 대한 유효성 검사 논리 구현</span><span class="sxs-lookup"><span data-stu-id="afc47-102">How to: Implement Validation Logic on Custom Objects</span></span>
<span data-ttu-id="afc47-103">이 예제에서는 사용자 지정 개체에서 유효성 검사 논리를 구현 하 고 다음에 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="afc47-103">This example shows how to implement validation logic on a custom object and then bind to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afc47-104">예제</span><span class="sxs-lookup"><span data-stu-id="afc47-104">Example</span></span>  
 <span data-ttu-id="afc47-105">소스 개체가 구현 하는 경우 비즈니스 계층에 유효성 검사 논리를 제공할 수 있습니다 <xref:System.ComponentModel.IDataErrorInfo>정의 하는 다음 예제 에서처럼를 `Person` 구현 하는 개체 <xref:System.ComponentModel.IDataErrorInfo>:</span><span class="sxs-lookup"><span data-stu-id="afc47-105">You can provide validation logic on the business layer if your source object implements <xref:System.ComponentModel.IDataErrorInfo>, as in the following example, which defines a `Person` object that implements <xref:System.ComponentModel.IDataErrorInfo>:</span></span>  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](~/samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 <span data-ttu-id="afc47-106">다음 예제에서는 텍스트 상자의 text 속성에 바인딩합니다 합니다 `Person.Age` 바인딩에 지정 된 리소스 선언을 통해 사용할 수 있는 속성을 `x:Key` `data`.</span><span class="sxs-lookup"><span data-stu-id="afc47-106">In the following example, the text property of the text box binds to the `Person.Age` property, which has been made available for binding through a resource declaration that is given the `x:Key` `data`.</span></span> <span data-ttu-id="afc47-107">합니다 <xref:System.Windows.Controls.DataErrorValidationRule> 에서 발생 한 유효성 검사 오류에 대 한 검사를 <xref:System.ComponentModel.IDataErrorInfo> 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="afc47-107">The <xref:System.Windows.Controls.DataErrorValidationRule> checks for the validation errors raised by the <xref:System.ComponentModel.IDataErrorInfo> implementation.</span></span>  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml?highlight=8,11-19,25-42)]  
  
 <span data-ttu-id="afc47-108">사용 하는 대신 또는 합니다 <xref:System.Windows.Controls.DataErrorValidationRule>를 설정할 수 있습니다 합니다 <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> 속성을 `true`.</span><span class="sxs-lookup"><span data-stu-id="afc47-108">Alternatively, instead of using the <xref:System.Windows.Controls.DataErrorValidationRule>, you can set the <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afc47-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="afc47-109">See also</span></span>

- <xref:System.Windows.Controls.ExceptionValidationRule>
- [<span data-ttu-id="afc47-110">바인딩 유효성 검사 구현</span><span class="sxs-lookup"><span data-stu-id="afc47-110">Implement Binding Validation</span></span>](how-to-implement-binding-validation.md)
- [<span data-ttu-id="afc47-111">방법 항목</span><span class="sxs-lookup"><span data-stu-id="afc47-111">How-to Topics</span></span>](data-binding-how-to-topics.md)
