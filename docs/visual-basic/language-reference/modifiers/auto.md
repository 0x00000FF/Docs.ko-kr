---
title: Auto(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
ms.openlocfilehash: c128ab9982ae7ccd5fff34020f2750f703da16a1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664605"
---
# <a name="auto-visual-basic"></a><span data-ttu-id="99901-102">Auto(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99901-102">Auto (Visual Basic)</span></span>
<span data-ttu-id="99901-103">Visual Basic 선언 되는 외부 프로시저의 외부 이름을 기반으로 하는.NET Framework 규칙에 따라 문자열을 마샬링하고 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="99901-103">Specifies that Visual Basic should marshal strings according to .NET Framework rules based on the external name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="99901-104">프로젝트 외부에서 정의 된 프로시저를 호출할 때 Visual Basic 컴파일러는 프로시저를 올바르게 호출 하는 데 필요한 정보에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99901-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have to call the procedure correctly.</span></span> <span data-ttu-id="99901-105">문자열 문자 집합 사용 및 프로시저 위치한, 식별 하는 방법이, 호출 시퀀스가 및 반환 형식으로이 정보 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99901-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="99901-106">합니다 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) 외부 프로시저에 대 한 참조를 만들고이 필요한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="99901-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="99901-107">`charsetmodifier` 부분을 `Declare` 문은 외부 프로시저를 호출 하는 동안 문자열을 마샬링 한 문자 집합 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="99901-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="99901-108">또한 Visual Basic에서 외부 프로시저 이름에 대 한 외부 파일을 검색 하는 방식을 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="99901-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="99901-109">`Auto` Visual Basic.NET Framework 규칙에 따라 문자열을 마샬링 및 기본 문자 및 런타임 플랫폼의 집합을 결정 하는 초기 검색 하는 경우 외부 프로시저 이름을 수정 해야는 한정자 지정 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="99901-109">The `Auto` modifier specifies that Visual Basic should marshal strings according to .NET Framework rules, and that it should determine the base character set of the run-time platform and possibly modify the external procedure name if the initial search fails.</span></span> <span data-ttu-id="99901-110">자세한 내용은 "Character Sets"를 참조 하세요 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="99901-110">For more information, see "Character Sets" in [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md).</span></span>  
  
 <span data-ttu-id="99901-111">문자 집합 자가 지정 된 경우 `Ansi` 가 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="99901-111">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99901-112">설명</span><span class="sxs-lookup"><span data-stu-id="99901-112">Remarks</span></span>  
 <span data-ttu-id="99901-113">`Auto` 한정자는이 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99901-113">The `Auto` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="99901-114">Declare 문</span><span class="sxs-lookup"><span data-stu-id="99901-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="99901-115">스마트 디바이스 개발자 노트</span><span class="sxs-lookup"><span data-stu-id="99901-115">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="99901-116">이 키워드는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99901-116">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99901-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="99901-117">See also</span></span>
- [<span data-ttu-id="99901-118">ANSI</span><span class="sxs-lookup"><span data-stu-id="99901-118">Ansi</span></span>](../../../visual-basic/language-reference/modifiers/ansi.md)
- [<span data-ttu-id="99901-119">유니코드</span><span class="sxs-lookup"><span data-stu-id="99901-119">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)
- [<span data-ttu-id="99901-120">키워드</span><span class="sxs-lookup"><span data-stu-id="99901-120">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
