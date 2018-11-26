---
title: -nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 21c708ef632cc0ed923713cd49e22d44848b4db3
ms.sourcegitcommit: 35316b768394e56087483cde93f854ba607b63bc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2018
ms.locfileid: "52297233"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="1b2e2-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b2e2-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="1b2e2-103">컴파일하는 동안 저작권 배너 및 정보 메시지를 표시를 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b2e2-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b2e2-104">구문</span><span class="sxs-lookup"><span data-stu-id="1b2e2-104">Syntax</span></span>  
  
```  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="1b2e2-105">설명</span><span class="sxs-lookup"><span data-stu-id="1b2e2-105">Remarks</span></span>  
 <span data-ttu-id="1b2e2-106">지정 하는 경우 `-nologo`, 컴파일러를 저작권 배너를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b2e2-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="1b2e2-107">기본적으로 `-nologo`은 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b2e2-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b2e2-108">`-nologo` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 있는 명령줄에서 컴파일할 경우에 사용할 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1b2e2-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b2e2-109">예제</span><span class="sxs-lookup"><span data-stu-id="1b2e2-109">Example</span></span>  
 <span data-ttu-id="1b2e2-110">다음 코드에서는 `T2.vb` 를 저작권 배너를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b2e2-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="1b2e2-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1b2e2-111">See Also</span></span>  
 [<span data-ttu-id="1b2e2-112">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="1b2e2-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="1b2e2-113">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="1b2e2-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
