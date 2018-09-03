---
title: 문자 데이터 형식(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
ms.openlocfilehash: 3b031c6e3dc04637128f95ca8e922d3298981287
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2018
ms.locfileid: "43462425"
---
# <a name="character-data-types-visual-basic"></a><span data-ttu-id="93e4a-102">문자 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93e4a-102">Character Data Types (Visual Basic)</span></span>
<span data-ttu-id="93e4a-103">Visual Basic에서는 *문자 데이터 형식* 인쇄 하거나 표시할 수 있는 문자를 사용 하 여 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="93e4a-103">Visual Basic provides *character data types* to deal with printable and displayable characters.</span></span> <span data-ttu-id="93e4a-104">유니코드 문자를 모두 처리 하는 동안 `Char` 반면 단일 문자를 포함 `String` 불특정 개수의 문자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="93e4a-104">While they both deal with Unicode characters, `Char` holds a single character whereas `String` contains an indefinite number of characters.</span></span>  
  
 <span data-ttu-id="93e4a-105">Side-by-side-Visual Basic 데이터 형식 비교를 표시 하는 테이블을 참조 하세요 [데이터 형식](../../../../visual-basic/language-reference/data-types/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="93e4a-105">For a table that displays a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/index.md).</span></span>  
  
## <a name="char-type"></a><span data-ttu-id="93e4a-106">Char 형식</span><span class="sxs-lookup"><span data-stu-id="93e4a-106">Char Type</span></span>  
 <span data-ttu-id="93e4a-107">`Char` 데이터 형식은 2 바이트 (16 비트) 단일 유니코드 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="93e4a-107">The `Char` data type is a single two-byte (16-bit) Unicode character.</span></span> <span data-ttu-id="93e4a-108">변수는 항상 정확 하 게 하나의 문자에 저장 된 경우 선언으로 `Char`입니다.</span><span class="sxs-lookup"><span data-stu-id="93e4a-108">If a variable always stores exactly one character, declare it as `Char`.</span></span> <span data-ttu-id="93e4a-109">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="93e4a-109">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 <span data-ttu-id="93e4a-110">가능한 각 값을 `Char` 또는 `String` 변수가 *코드 포인트*, 또는 유니코드 문자 집합의 문자 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="93e4a-110">Each possible value in a `Char` or `String` variable is a *code point*, or character code, in the Unicode character set.</span></span> <span data-ttu-id="93e4a-111">유니코드 문자에는 기본 ASCII 문자 집합, 다양 한 다른 알파벳 문자, 악센트, 통화 기호, 분수, 분음 부호, 및 수학 및 공학 기호 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93e4a-111">Unicode characters include the basic ASCII character set, various other alphabet letters, accents, currency symbols, fractions, diacritics, and mathematical and technical symbols.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93e4a-112">유니코드 문자 집합 코드 포인트에 대 한 55296 55551 10 진수 DFFF 까지의 D800 *서로게이트 쌍*, 단일 코드 포인트를 나타내는 두 개의 16 비트 값 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="93e4a-112">The Unicode character set reserves the code points D800 through DFFF (55296 through 55551 decimal) for *surrogate pairs*, which require two 16-bit values to represent a single code point.</span></span> <span data-ttu-id="93e4a-113">A `Char` 변수는 서로게이트 쌍을 포함할 수 없습니다 및 `String` 쌍을 유지 하기 위해 두 위치를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="93e4a-113">A `Char` variable cannot hold a surrogate pair, and a `String` uses two positions to hold such a pair.</span></span>  
  
 <span data-ttu-id="93e4a-114">자세한 내용은 [데이터 형식 Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="93e4a-114">For more information, see [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span></span>  
  
## <a name="string-type"></a><span data-ttu-id="93e4a-115">문자열 형식</span><span class="sxs-lookup"><span data-stu-id="93e4a-115">String Type</span></span>  
 <span data-ttu-id="93e4a-116">`String` 데이터 형식은 0 개 이상의 2 바이트 (16 비트) 유니코드 문자 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="93e4a-116">The `String` data type is a sequence of zero or more two-byte (16-bit) Unicode characters.</span></span> <span data-ttu-id="93e4a-117">변수에서 불특정 개수의 문자를 포함할 수 있으면로 선언 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="93e4a-117">If a variable can contain an indefinite number of characters, declare it as `String`.</span></span> <span data-ttu-id="93e4a-118">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="93e4a-118">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 <span data-ttu-id="93e4a-119">자세한 내용은 [문자열 데이터 형식](../../../../visual-basic/language-reference/data-types/string-data-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="93e4a-119">For more information, see [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93e4a-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93e4a-120">See Also</span></span>  
 [<span data-ttu-id="93e4a-121">기본 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="93e4a-121">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="93e4a-122">복합 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="93e4a-122">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [<span data-ttu-id="93e4a-123">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="93e4a-123">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="93e4a-124">값 형식과 참조 형식</span><span class="sxs-lookup"><span data-stu-id="93e4a-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="93e4a-125">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="93e4a-125">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="93e4a-126">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="93e4a-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="93e4a-127">형식 문자</span><span class="sxs-lookup"><span data-stu-id="93e4a-127">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
