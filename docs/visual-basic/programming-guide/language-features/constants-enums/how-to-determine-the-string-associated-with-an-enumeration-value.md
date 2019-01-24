---
title: '방법: 열거형 값 (Visual Basic)를 사용 하 여 연결 문자열 확인'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: 92d2e9918429c9cf408f288f832e4615b95ad423
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690191"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a><span data-ttu-id="ebf37-102">방법: 열거형 값 (Visual Basic)를 사용 하 여 연결 문자열 확인</span><span class="sxs-lookup"><span data-stu-id="ebf37-102">How to: Determine the String Associated with an Enumeration Value (Visual Basic)</span></span>
<span data-ttu-id="ebf37-103">합니다 <xref:System.Enum.GetValues%2A> 고 <xref:System.Enum.GetNames%2A> 메서드를 사용 하는 문자열과 열거형 멤버와 연결 된 값을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebf37-103">The <xref:System.Enum.GetValues%2A> and <xref:System.Enum.GetNames%2A> methods allow you to determine the strings and values associated with enumeration members.</span></span>  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a><span data-ttu-id="ebf37-104">열거형을 사용 하 여 연결 된 문자열을 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="ebf37-104">To determine the string associated with an enumeration</span></span>  
  
-   <span data-ttu-id="ebf37-105">사용 된 <xref:System.Enum.GetNames%2A> 열거형 멤버와 연결 된 문자열을 검색 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="ebf37-105">Use the <xref:System.Enum.GetNames%2A> method to retrieve the strings associated with the enumeration members.</span></span> <span data-ttu-id="ebf37-106">이 예제에서는 열거형 선언 `flavorEnum`를 사용 하 여는 <xref:System.Enum.GetNames%2A> 각 멤버와 연결 된 문자열을 표시 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="ebf37-106">This example declares an enumeration, `flavorEnum`, then uses the <xref:System.Enum.GetNames%2A> method to display the strings associated with each member.</span></span>  
  
     [!code-vb[VbEnumsTask#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-determine-the-string-associated-with-an-enumeration-value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ebf37-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="ebf37-107">See also</span></span>
- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [<span data-ttu-id="ebf37-108">방법: 열거형 선언</span><span class="sxs-lookup"><span data-stu-id="ebf37-108">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="ebf37-109">방법: 열거형 멤버 참조</span><span class="sxs-lookup"><span data-stu-id="ebf37-109">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="ebf37-110">열거형 및 이름 한정</span><span class="sxs-lookup"><span data-stu-id="ebf37-110">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="ebf37-111">방법: Visual Basic에서 열거형 반복</span><span class="sxs-lookup"><span data-stu-id="ebf37-111">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="ebf37-112">열거형을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="ebf37-112">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="ebf37-113">Enum 문</span><span class="sxs-lookup"><span data-stu-id="ebf37-113">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
