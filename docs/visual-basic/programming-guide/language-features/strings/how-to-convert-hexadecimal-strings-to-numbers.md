---
title: "방법: 16진수 문자열을 숫자로 변환(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e6b1beae273fa737ca7c95a253d95c947e760f9c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a><span data-ttu-id="191c2-102">방법: 16진수 문자열을 숫자로 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="191c2-102">How to: Convert Hexadecimal Strings to Numbers (Visual Basic)</span></span>
<span data-ttu-id="191c2-103">사용 하 여 정수를 16 진수 문자열로 변환 하는이 예제는 <xref:System.Convert.ToInt32%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="191c2-103">This example converts a hexadecimal string to an integer using the <xref:System.Convert.ToInt32%2A> method.</span></span>  
  
### <a name="to-convert-a-hexadecimal-string-to-a-number"></a><span data-ttu-id="191c2-104">16 진수 문자열을 숫자로 변환 하려면</span><span class="sxs-lookup"><span data-stu-id="191c2-104">To convert a hexadecimal string to a number</span></span>  
  
-   <span data-ttu-id="191c2-105">사용 하 여는 <xref:System.Convert.ToInt32%2A> 정수로 16 진수로 표시 된 숫자를 변환 하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="191c2-105">Use the <xref:System.Convert.ToInt32%2A> method to convert the number expressed in base-16 to an integer.</span></span>  
  
     <span data-ttu-id="191c2-106">첫 번째 인수는 <xref:System.Convert.ToInt32%2A> 메서드는 변환할 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="191c2-106">The first argument of the <xref:System.Convert.ToInt32%2A> method is the string to convert.</span></span> <span data-ttu-id="191c2-107">두 번째 인수는 숫자; 기 수를 나타냅니다. 16 진수는 기본 16 개입니다.</span><span class="sxs-lookup"><span data-stu-id="191c2-107">The second argument describes what base the number is expressed in; hexadecimal is base 16.</span></span>  
  
     [!code-vb[VbVbalrStrings#62](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-hexadecimal-strings-to-numbers_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="191c2-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="191c2-108">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:System.Convert.ToInt32%2A>
