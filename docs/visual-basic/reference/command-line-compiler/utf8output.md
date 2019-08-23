---
title: -utf8output (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 789df84bb4011d1ad128c50a9c689d1217be6694
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937273"
---
# <a name="-utf8output-visual-basic"></a>-utf8output (Visual Basic)
UTF-8 인코딩을 사용하여 컴파일러 출력을 표시합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a>인수  
 `+` &#124; `-`  
 선택 사항입니다. 이 옵션의 기본값은입니다 `-utf8output-`. 즉, 컴파일러 출력에서 utf-8 인코딩을 사용 하지 않습니다. `-utf8output`를 지정하는 것은 `-utf8output+`를 지정하는 것과 같습니다.  
  
## <a name="remarks"></a>설명  
 일부 국가별 구성에서는 컴파일러 출력이 콘솔에 올바르게 표시 되지 않습니다. 이러한 경우를 사용 `-utf8output` 하 고 컴파일러 출력을 파일로 리디렉션합니다.  
  
> [!NOTE]
> 이 `-utf8output` 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드 `In.vb` 는 utf-8 인코딩을 사용 하 여 출력을 표시 하도록 컴파일러에 지시 합니다.  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
