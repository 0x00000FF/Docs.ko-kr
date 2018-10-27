---
title: 문의 끝이 필요합니다.
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: 8df756009ebe3a0613ec47018d938151829214df
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50039025"
---
# <a name="end-of-statement-expected"></a><span data-ttu-id="8fe02-102">문의 끝이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8fe02-102">End of statement expected</span></span>
<span data-ttu-id="8fe02-103">문이 구문적으로 완료 되었지만 문을 완료 하는 요소 뒤에 추가 프로그래밍 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8fe02-103">The statement is syntactically complete, but an additional programming element follows the element that completes the statement.</span></span> <span data-ttu-id="8fe02-104">줄 종결자가 오는 모든 문의 끝에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fe02-104">A line terminator is required at the end of every statement.</span></span>
  
 <span data-ttu-id="8fe02-105">Visual Basic 소스 파일의 문자를 줄으로 분할 하는 줄 종결자입니다.</span><span class="sxs-lookup"><span data-stu-id="8fe02-105">A line terminator divides the characters of a Visual Basic source file into lines.</span></span> <span data-ttu-id="8fe02-106">줄 종결자의 예는 유니코드 캐리지 반환 문자 (HD)에 유니코드 줄 바꿈 문자 (& HA), 유니코드 캐리지 리턴 문자, 유니코드 줄 바꿈 문자 및 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fe02-106">Examples of line terminators are the Unicode carriage return character (&HD), the Unicode linefeed character (&HA), and the Unicode carriage return character followed by the Unicode linefeed character.</span></span> <span data-ttu-id="8fe02-107">줄 종결자에 대 한 자세한 내용은 참조는 [Visual Basic 언어 사양](~/_vblang/spec/lexical-grammar.md#line-terminators)합니다.</span><span class="sxs-lookup"><span data-stu-id="8fe02-107">For more information about line terminators, see the [Visual Basic Language Specification](~/_vblang/spec/lexical-grammar.md#line-terminators).</span></span>
  
 <span data-ttu-id="8fe02-108">**오류 ID:** BC30205</span><span class="sxs-lookup"><span data-stu-id="8fe02-108">**Error ID:** BC30205</span></span>
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8fe02-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="8fe02-109">To correct this error</span></span>
  
1.  <span data-ttu-id="8fe02-110">두 개의 다른 문으로 실수로 동일한 줄에 배치 된 경우를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fe02-110">Check to see if two different statements have inadvertently been put on the same line.</span></span>
  
2.  <span data-ttu-id="8fe02-111">문이 완료 되는 요소 뒤에 줄 종결자를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fe02-111">Insert a line terminator after the element that completes the statement.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8fe02-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8fe02-112">See Also</span></span>  
 [<span data-ttu-id="8fe02-113">방법: 코드에서 문 분리 및 결합</span><span class="sxs-lookup"><span data-stu-id="8fe02-113">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 [<span data-ttu-id="8fe02-114">문</span><span class="sxs-lookup"><span data-stu-id="8fe02-114">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
