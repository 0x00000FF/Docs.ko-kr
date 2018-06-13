---
title: -nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 011c9499eaa728588e6181e33a96dd75b4a7b84b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648543"
---
# <a name="-nologo-visual-basic"></a>-nologo (Visual Basic)
컴파일 시 저작권 배너 및 정보 메시지를 표시를 하지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
-nologo  
```  
  
## <a name="remarks"></a>설명  
 지정 하는 경우 `-nologo`, 컴파일러 저작권 배너를 표시 하지 않습니다. 기본적으로 `-nologo`은 적용되지 않습니다.  
  
> [!NOTE]
>  `-nologo` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 경우에 사용할 수는 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `T2.vb` 를 저작권 배너를 표시 하지 않습니다.  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)  
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
