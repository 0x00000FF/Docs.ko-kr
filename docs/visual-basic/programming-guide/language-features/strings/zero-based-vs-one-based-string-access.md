---
title: "Vs&0;부터 시작 합니다. Visual Basic에서&1;부터 시작 하는 문자열 액세스 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d8d1000f134fa8f99509d12727b9fbd84cb0e831
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="10e57-102">Vs&0;부터 시작 합니다. Visual Basic에서&1;부터 시작 하는 문자열 액세스</span><span class="sxs-lookup"><span data-stu-id="10e57-102">Zero-based vs. One-based String Access in Visual Basic</span></span>
<span data-ttu-id="10e57-103">이 항목에서는 비교 방법을 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 및 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 문자열의 문자에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="10e57-103">This topic compares how [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] and the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] provide access to the characters in a string.</span></span> <span data-ttu-id="10e57-104">[!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 항상는 문자열의에서 문자에 대 한&0;부터 시작 액세스를 제공 하지만 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 함수에 따라&0;부터 시작 하 고&1;부터 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="10e57-104">The [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] always provides zero-based access to the characters in a string, whereas [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="10e57-105">1부터 시작</span><span class="sxs-lookup"><span data-stu-id="10e57-105">One-Based</span></span>  
 <span data-ttu-id="10e57-106">1부터 시작 하는 예로 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 함수를 고려해 야는 `Mid` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="10e57-106">For an example of a one-based [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] function, consider the `Mid` function.</span></span> <span data-ttu-id="10e57-107">부분 문자열이 시작 위치 1부터 시작 하는 문자 위치를 지정 하는 인수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="10e57-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="10e57-108">[!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Substring%2A?displayProperty=fullName>메서드는 문자의 인덱스 부분 문자열을 시작 하려면 문자열 위치 0부터 시작 합니다.</xref:System.String.Substring%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="10e57-108">The [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Substring%2A?displayProperty=fullName> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="10e57-109">따라서 "ABCDE" 문자열이 있는 경우 개별 문자 매겨집니다와 함께 사용할 1,2,3,4,5는 `Mid` 함수가 있지만 함께 사용할 0,1,2,3,4는 <xref:System.String.Substring%2A?displayProperty=fullName>메서드.</xref:System.String.Substring%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="10e57-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=fullName> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="10e57-110">0부터 시작</span><span class="sxs-lookup"><span data-stu-id="10e57-110">Zero-Based</span></span>  
 <span data-ttu-id="10e57-111">0부터 시작에 대 한 예제 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 함수를 고려해 야는 `Split` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="10e57-111">For an example of a zero-based [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] function, consider the `Split` function.</span></span> <span data-ttu-id="10e57-112">문자열을 분할 하 고 부분 문자열이 포함 된 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="10e57-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="10e57-113">[!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Split%2A?displayProperty=fullName>메서드는 문자열을 분할 및 부분 문자열이 포함 된 배열을 반환 합니다.</xref:System.String.Split%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="10e57-113">The [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Split%2A?displayProperty=fullName> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="10e57-114">때문에 `Split` 함수 및 <xref:System.String.Split%2A>메서드가 반환 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 배열은&0;부터 시작 해야 합니다.</xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="10e57-114">Because the `Split` function and <xref:System.String.Split%2A> method return [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10e57-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="10e57-115">See Also</span></span>  
 <span data-ttu-id="10e57-116"><xref:Microsoft.VisualBasic.Strings.Mid%2A></xref:Microsoft.VisualBasic.Strings.Mid%2A></span><span class="sxs-lookup"><span data-stu-id="10e57-116"><xref:Microsoft.VisualBasic.Strings.Mid%2A></span></span>   
 <span data-ttu-id="10e57-117"><xref:Microsoft.VisualBasic.Strings.Split%2A></xref:Microsoft.VisualBasic.Strings.Split%2A></span><span class="sxs-lookup"><span data-stu-id="10e57-117"><xref:Microsoft.VisualBasic.Strings.Split%2A></span></span>   
 <span data-ttu-id="10e57-118"><xref:System.String.Substring%2A></xref:System.String.Substring%2A></span><span class="sxs-lookup"><span data-stu-id="10e57-118"><xref:System.String.Substring%2A></span></span>   
 <span data-ttu-id="10e57-119"><xref:System.String.Split%2A></xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="10e57-119"><xref:System.String.Split%2A></span></span>   
<span data-ttu-id="10e57-120"> [Visual Basic의 문자열 소개](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)</span><span class="sxs-lookup"><span data-stu-id="10e57-120"> [Introduction to Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)</span></span>
