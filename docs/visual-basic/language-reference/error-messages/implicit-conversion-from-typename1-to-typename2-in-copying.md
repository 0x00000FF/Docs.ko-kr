---
title: 암시적으로 변환 &#39; &lt;typename1&gt; &#39; 를 &#39; &lt;typename2&gt; &#39; 의 값을 복사 &#39;ByRef&#39; 매개 변수 &#39; &lt; parametername&gt; &#39; 일치 하는 인수에 다시 합니다.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 86a618206bcfd932e41410e80c12bc166a3f67f3
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="implicit-conversion-from-39lttypename1gt39-to-39lttypename2gt39-in-copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument"></a>암시적으로 변환 &#39; &lt;typename1&gt; &#39; 를 &#39; &lt;typename2&gt; &#39; 의 값을 복사 &#39;ByRef&#39; 매개 변수 &#39; &lt; parametername&gt; &#39; 일치 하는 인수에 다시 합니다.
프로시저를 호출는 [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) 해당 매개 변수의 형식과 다른 형식의 인수입니다.  
  
 인수를 전달 하는 경우 `ByRef`, Visual Basic에서 참조를 전달 하는 대신 프로시저의 지역 변수에 인수 값을 복사 합니다. 이 경우 프로시저가 반환 되 면 Visual Basic에서 지역 변수 값을 호출 코드의 인수에 다시 복사 해야 합니다.  
  
 `ByRef` 인수 값이 프로시저에 복사되고 인수 및 매개 변수가 동일한 형식인 경우에는 변환이 필요하지 않습니다. 그러나 형식이 서로 다르면, Visual Basic 양방향으로 변환 해야 합니다. 사용할 수 없으므로 `CType` 암시적 프로시저 인수 또는 매개 변수, 이러한 변환에서 다른 변환 키워드 중 하나는 항상 또는 합니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC41999  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   가능 하면 Visual Basic 모든 변환을 수행 하지 않아도 되므로 프로시저 매개 변수와 동일한 형식의 호출 인수를 사용 합니다.  
  
-   인수로 사용 하 여 프로시저를 호출 하는 경우 입력 매개 변수 형식과 다른 하지만 호출 인수에 값을 반환 하려면 매개 변수를 정의 합니다. 필요 하지 않은 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) 대신 `ByRef`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [절차](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [프로시저 매개 변수 및 인수](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [값 또는 참조로 인수 전달](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [암시적 변환과 명시적 변환](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
