---
title: Vs 0부터 시작 합니다. Visual Basic에서 하나 기반 문자열 액세스
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: a0a42f72d94adf1c10865374017fa61e833df40f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a>Vs 0부터 시작 합니다. Visual Basic에서 하나 기반 문자열 액세스
이 항목에서는 Visual Basic 비교 및 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 문자열의 문자에 대 한 액세스를 제공 합니다. [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 항상 함수에 따라 0부터 시작 하 고 1부터 액세스를 제공 하는 Visual Basic는 문자열의 문자에 대 한 0부터 시작 액세스를 제공 합니다.  
  
## <a name="one-based"></a>1부터 시작  
 1부터 Visual Basic 함수 예를 들어 고려는 `Mid` 함수입니다. 부분 문자열은 시작할 위치 1부터 시작 문자 위치를 나타내는 인수를 사용 합니다. [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType> 메서드는 문자의 인덱스 부분 문자열을 시작 하려면 문자열이 위치 0부터 시작 합니다. 따라서 "ABCDE" 문자열이 있는 경우 개별 문자 번호는 함께 사용할 1,2,3,4,5는 `Mid` 함수가 있지만 함께 사용할 0,1,2,3,4는 <xref:System.String.Substring%2A?displayProperty=nameWithType> 메서드.  
  
## <a name="zero-based"></a>0부터 시작  
 0부터 시작 하는 Visual Basic 함수 예를 들어 고려는 `Split` 함수입니다. 문자열을 분할 하 고 부분 문자열이 포함 된 배열을 반환 합니다. [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType> 메서드는 문자열을 분할 및 부분 문자열이 포함 된 배열을 반환 합니다. 때문에 `Split` 함수 및 <xref:System.String.Split%2A> 메서드 반환 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 배열은 0부터 시작 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 <xref:Microsoft.VisualBasic.Strings.Split%2A>  
 <xref:System.String.Substring%2A>  
 <xref:System.String.Split%2A>  
 [Visual Basic의 문자열 소개](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
