---
title: '#error(C# 참조)'
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: ed43c1f85142ec6c54e44db5e3b0b7de3ef36bb8
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259888"
---
# <a name="error-c-reference"></a><span data-ttu-id="79811-102">#error(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="79811-102">#error (C# Reference)</span></span>
<span data-ttu-id="79811-103">`#error`를 사용하면 코드의 특정 위치에서 [CS1029](../compiler-messages/cs1029.md) 사용자 정의 오류를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79811-103">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="79811-104">예:</span><span class="sxs-lookup"><span data-stu-id="79811-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="79811-105">설명</span><span class="sxs-lookup"><span data-stu-id="79811-105">Remarks</span></span>  
 <span data-ttu-id="79811-106">`#error`은 일반적으로 조건부 지시문에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="79811-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="79811-107">[#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md)을 사용하여 사용자 정의 경고를 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79811-107">It is also possible to generate a user-defined warning with [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="79811-108">예</span><span class="sxs-lookup"><span data-stu-id="79811-108">Example</span></span>  
  
```csharp
// preprocessor_error.cs  
// CS1029 expected  
#define DEBUG  
class MainClass   
{  
    static void Main()   
    {  
#if DEBUG  
#error DEBUG is defined  
#endif  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="79811-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="79811-109">See Also</span></span>

- [<span data-ttu-id="79811-110">C# 참조</span><span class="sxs-lookup"><span data-stu-id="79811-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="79811-111">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="79811-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="79811-112">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="79811-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
