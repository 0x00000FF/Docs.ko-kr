---
title: <proceduresignature1>은(는) 배열 매개 변수 형식의 배열만 다르거나 배열 매개 변수 형식의 차수만 다른 <proceduresignature2>을(를) 오버로드하므로 CLS 규격이 아닙니다.
ms.date: 07/20/2015
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
ms.openlocfilehash: 0bda4ad6a4d5368d93e2ca603b78bf9db6aca858
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269564"
---
# <a name="proceduresignature1-is-not-cls-compliant-because-it-overloads-proceduresignature2-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a>\<proceduresignature1 > 오버 로드 하므로 CLS 규격이 아닙니다 \<proceduresignature2 > 배열 매개 변수 형식의 배열 또는 배열 매개 변수 형식의 차수만에서 달리
프로시저 또는 속성으로 표시 되어 `<CLSCompliant(True)>` 때 다른 프로시저 또는 속성을 재정의 하 고 해당 매개 변수 목록 간의 유일한 차이점은 가변 배열의 중첩 수준 또는 배열 차수입니다.  
  
 두 번째 및 세 번째 선언 다음 선언에서이 오류를 생성합니다.  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 두 번째 선언에는 1 차원 원래 매개 변수 변경 `arrayParam` 하는 배열로 이루어진 배열입니다. 세 번째 선언 변경 `arrayParam` 를 2 차원 배열 (순위 2). Visual Basic에 이러한 변경 사항 중 하나에 의해서만 달라 지는 오버 로드를 허용 하는 동안 이러한 오버 로드와 호환 되지 않는 합니다 [Language Independence and Language-independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).  
  
 <xref:System.CLSCompliantAttribute>를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False`로 설정하여 준수 여부를 나타냅니다. 이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.  
  
 요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC40035  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   CLS 규격이 필요 하면,이 도움말 페이지에 언급 된 변경 내용만 보다 많은 방법으로 서로 다를 오버 로드를 정의 합니다.  
  
-   오버 로드 다는 필요한 경우이 도움말에 언급 된 변경에 의해서만 페이지에서 제거 합니다 <xref:System.CLSCompliantAttribute> 해당 정의에서 그대로 표시 또는 `<CLSCompliant(False)>`합니다.  
  
## <a name="see-also"></a>참고자료

- [프로시저 오버로딩](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [오버로드](../../../visual-basic/language-reference/modifiers/overloads.md)
