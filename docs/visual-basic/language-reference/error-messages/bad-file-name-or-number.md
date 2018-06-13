---
title: 파일 이름 또는 번호가 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: 903be68e71ad590b4b669545afd077175534ef4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585569"
---
# <a name="bad-file-name-or-number"></a><span data-ttu-id="708a6-102">파일 이름 또는 번호가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="708a6-102">Bad file name or number</span></span>
<span data-ttu-id="708a6-103">지정한 파일에 액세스 하는 동안 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="708a6-103">An error occurred while trying to access the specified file.</span></span> <span data-ttu-id="708a6-104">이 오류의 가능한 원인:</span><span class="sxs-lookup"><span data-stu-id="708a6-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="708a6-105">문에서 참조에 지정 되지 않은 파일 이름 또는 숫자로 파일에는 `FileOpen` 문 또는 하에 지정 된는 `FileOpen` 하지만 된 문이 이후에 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="708a6-105">A statement refers to a file with a file name or number that was not specified in the `FileOpen` statement or that was specified in a `FileOpen` statement but was subsequently closed.</span></span>  
  
-   <span data-ttu-id="708a6-106">문에서 숫자 파일 번호의 범위를 벗어난를 사용 하 여 파일 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="708a6-106">A statement refers to a file with a number that is out of the range of file numbers.</span></span>  
  
-   <span data-ttu-id="708a6-107">문에서 파일 이름 또는 유효 하지 않은 숫자를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="708a6-107">A statement refers to a file name or number that is not valid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="708a6-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="708a6-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="708a6-109">파일 이름 지정은 확인 된 `FileOpen` 문.</span><span class="sxs-lookup"><span data-stu-id="708a6-109">Make sure the file name is specified in a `FileOpen` statement.</span></span> <span data-ttu-id="708a6-110">호출 된 경우에 `FileClose` 문 인수 없이 있습니다 닫힐 수 열려 있는 모든 파일.</span><span class="sxs-lookup"><span data-stu-id="708a6-110">Note that if you invoked the `FileClose` statement without arguments, you may have inadvertently closed all open files.</span></span>  
  
2.  <span data-ttu-id="708a6-111">코드 생성 하는 경우 파일 번호 알고리즘 방식으로,은 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="708a6-111">If your code is generating file numbers algorithmically, make sure the numbers are valid.</span></span>  
  
3.  <span data-ttu-id="708a6-112">운영 체제 규칙을 준수 하는지 확인 하려면 파일 이름을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="708a6-112">Check the file names to make sure they conform to operating system conventions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="708a6-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="708a6-113">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>  
 [<span data-ttu-id="708a6-114">Visual Basic 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="708a6-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
