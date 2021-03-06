---
title: -nostdlib
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: db6b047f521d8ef44d2bd1b70b654a4233ebb1a7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347908"
---
# <a name="-nostdlib-visual-basic"></a>-nostdlib(Visual Basic)
컴파일러가 표준 라이브러리를 자동으로 참조하지 않도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-nostdlib  
```  
  
## <a name="remarks"></a>설명  
 `-nostdlib` 옵션은 System.dll 어셈블리에 대한 자동 참조를 제거하고 컴파일러에서 Vbc.rsp 파일을 읽을 수 없도록 합니다. Vbc.exe 파일과 동일한 디렉터리에 있는 Vbc.rsp 파일은 일반적으로 사용되는 .NET Framework 어셈블리를 참조하고 `System` 및 `Microsoft.VisualBasic` 네임스페이스를 가져옵니다.  
  
> [!NOTE]
> Mscorlib.dll 및 Microsoft.VisualBasic.dll 어셈블리는 항상 참조됩니다.  
  
> [!NOTE]
> Visual Studio 개발 환경 내에서는 `-nostdlib` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드는 표준 라이브러리를 참조하지 않고 `T2.vb`를 컴파일합니다. `My` 개체를 제거하려면 `_MYTYPE` 조건부 컴파일 상수를 문자열 "Empty"로 설정해야 합니다.  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>참조

- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [My에 사용할 수 있는 개체 사용자 지정](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
