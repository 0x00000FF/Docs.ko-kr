---
title: Erase 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 317e2a7dc5facb08388f3a3e635734e4daed5eac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33601795"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="35a44-102">Erase 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="35a44-102">Erase Statement (Visual Basic)</span></span>
<span data-ttu-id="35a44-103">배열 변수를 해제 하 고 해당 요소에 사용 되는 메모리 할당을 취소 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a44-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35a44-104">구문</span><span class="sxs-lookup"><span data-stu-id="35a44-104">Syntax</span></span>  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="35a44-105">요소</span><span class="sxs-lookup"><span data-stu-id="35a44-105">Parts</span></span>  
 `arraylist`  
 <span data-ttu-id="35a44-106">필수.</span><span class="sxs-lookup"><span data-stu-id="35a44-106">Required.</span></span> <span data-ttu-id="35a44-107">지울 배열 변수 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="35a44-107">List of array variables to be erased.</span></span> <span data-ttu-id="35a44-108">여러 변수는 쉼표로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="35a44-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35a44-109">설명</span><span class="sxs-lookup"><span data-stu-id="35a44-109">Remarks</span></span>  
 <span data-ttu-id="35a44-110">`Erase` 문을 프로시저 수준 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a44-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="35a44-111">즉, 배열을 프로시저 내의 하지만 클래스 또는 모듈 수준에 없는 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a44-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="35a44-112">`Erase` 문을 할당 같습니다 `Nothing` 각 배열 변수에 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a44-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35a44-113">예제</span><span class="sxs-lookup"><span data-stu-id="35a44-113">Example</span></span>  
 <span data-ttu-id="35a44-114">다음 예제에서는 `Erase` 두 배열을 지우고 되 고 해당 메모리를 확보 문을 (1000 개 및 100 저장소 요소 각각).</span><span class="sxs-lookup"><span data-stu-id="35a44-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="35a44-115">`ReDim` 그런 다음 문은 3 차원 배열에는 새 배열 인스턴스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a44-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/erase-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="35a44-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35a44-116">See Also</span></span>  
 [<span data-ttu-id="35a44-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="35a44-117">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)  
 [<span data-ttu-id="35a44-118">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="35a44-118">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
