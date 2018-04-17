---
title: '방법: Visual Basic에서 StringBuilder를 사용하여 문자열 만들기'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c0e15c7df07822ee104a88525c209768c05470e3
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="d8175-102">방법: Visual Basic에서 StringBuilder를 사용하여 문자열 만들기</span><span class="sxs-lookup"><span data-stu-id="d8175-102">How to: Create Strings Using a StringBuilder in Visual Basic</span></span>
<span data-ttu-id="d8175-103">사용 하 여 여러 개의 짧은 문자열에서 긴 문자열을 구성 하는이 예제는 <xref:System.Text.StringBuilder> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d8175-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="d8175-104"><xref:System.Text.StringBuilder> 클래스 보다 더 효율적입니다.는 `&=` 많은 문자열을 연결 하기 위한 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="d8175-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8175-105">예제</span><span class="sxs-lookup"><span data-stu-id="d8175-105">Example</span></span>  
 <span data-ttu-id="d8175-106">다음 예제에서는의 인스턴스는 <xref:System.Text.StringBuilder> 클래스, 1, 000 문자열 해당 인스턴스에 추가 하 고 다음 문자열 표현을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8175-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation.</span></span>  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d8175-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8175-107">See Also</span></span>  
 [<span data-ttu-id="d8175-108">StringBuilder 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="d8175-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)  
 [<span data-ttu-id="d8175-109">&= 연산자</span><span class="sxs-lookup"><span data-stu-id="d8175-109">&= Operator</span></span>](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [<span data-ttu-id="d8175-110">문자열</span><span class="sxs-lookup"><span data-stu-id="d8175-110">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [<span data-ttu-id="d8175-111">새 문자열 만들기</span><span class="sxs-lookup"><span data-stu-id="d8175-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)  
 [<span data-ttu-id="d8175-112">문자열 조작</span><span class="sxs-lookup"><span data-stu-id="d8175-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)  
 <span data-ttu-id="d8175-113">[문자열 샘플](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d8175-113">[Strings Sample](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))</span></span>
