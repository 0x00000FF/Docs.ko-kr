---
title: -codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: 8aee51df3ba9f92ca662fbbfbd73998e4a3b4538
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43532512"
---
# <a name="-codepage-visual-basic"></a>-codepage (Visual Basic)
컴파일할 때 모든 소스 코드 파일에 사용할 코드 페이지를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-codepage:id  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`id`|필수. 컴파일러에서 지정한 코드 페이지를 사용 하 여 `id` 원본 파일의 인코딩을 해석 합니다.|  
  
## <a name="remarks"></a>설명  
 특정 인코딩을 사용 하 여 저장 된 소스 코드를 컴파일하는 데 사용할 수 있습니다 `-codepage` 사용할 코드 페이지를 지정 합니다. `-codepage` 옵션 컴파일에서 모든 소스 코드 파일에 적용 됩니다. 자세한 내용은 [.NET Framework의 문자 인코딩](https://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9)합니다.  
  
 `-codepage` 옵션의 현재 ANSI 코드 페이지, Unicode 또는 u t F-8을 사용 하 여 서명을 사용 하 여 소스 코드 파일을 저장 한 경우에 필요 하지 않습니다. Visual Studio 저장 모든 소스 코드 파일의 현재 ANSI 코드 페이지를 사용 하 여 기본적으로 사용자에서 다른 인코딩을 지정 하지 않는 경우는 **Encoding** 대화 상자. Visual Studio에서 사용 하는 **Encoding** 대화 상자를 다른 코드 페이지를 사용 하 여 저장 하는 소스 코드 파일을 엽니다.  
  
> [!NOTE]
>  `-codepage` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 있는 명령줄에서 컴파일할 경우에 사용할 수 있는 것입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
