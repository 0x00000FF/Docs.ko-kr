---
title: 레코드 길이가 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
ms.openlocfilehash: b4b311e2eb504c485772091ed126b3beb71729cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="bad-record-length"></a>레코드 길이가 잘못되었습니다.
이 오류의 가능한 원인:  
  
-   에 지정 된 레코드 변수의 길이 `FileGet`, `FileGetObject`, `FilePut` 또는 `FilePutObject` 해당에 지정 된 길이에서 다른 문을 `FileOpen` 문.  
  
-   변수는 `FilePut` 또는 `FilePutObject` 문이 하거나 다양 한 길이의 문자열을 포함 합니다.  
  
-   변수는 `FilePut` 또는 `FilePutObject` 되거나 포함 하는 `Variant` 유형입니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  인지 확인 레코드 변수의 형식을 정의 하는 사용자 정의 형식에서 고정 길이 변수의 크기의 합계와 동일한 값에 명시 된 대로 `FileOpen` 문의 `Len` 절.  
  
2.  경우에 변수가 `FilePut` 또는 `FilePutObject` , 다양 한 길이의 문자열 길이 최소 2 자 레코드에 지정 된 길이 보다 짧은 반드시 문이 하거나 다양 한 길이의 문자열을 포함는 `Len` 절은 `FileOpen` 문입니다.  
  
3.  하는 경우의 변수는 `FilePut` 또는 `FilePutObject` 되거나 포함 하는 `Variant` 가변 길이 문자열에 지정 된 레코드 길이 보다 짧은 4 바이트 이상 인지 확인는 `Len` 절은 `FileOpen` 문.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
