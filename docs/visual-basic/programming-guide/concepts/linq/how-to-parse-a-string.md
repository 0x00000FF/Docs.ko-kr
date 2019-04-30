---
title: '방법: (Visual Basic) 문자열을 구문 분석'
ms.date: 07/20/2015
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
ms.openlocfilehash: 815e94b3b41c2c0cc1d18d598307ab292919bea4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942599"
---
# <a name="how-to-parse-a-string-visual-basic"></a><span data-ttu-id="19ef3-102">방법: (Visual Basic) 문자열을 구문 분석</span><span class="sxs-lookup"><span data-stu-id="19ef3-102">How to: Parse a String (Visual Basic)</span></span>
<span data-ttu-id="19ef3-103">이 항목에서는 XML 트리를 만드는 방법 C#입니다.</span><span class="sxs-lookup"><span data-stu-id="19ef3-103">This topic shows how to create an XML tree in C#.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19ef3-104">예제</span><span class="sxs-lookup"><span data-stu-id="19ef3-104">Example</span></span>  
 <span data-ttu-id="19ef3-105">사용 하 여 Visual Basic의 문자열을 구문 분석할 수 있습니다는 `XElement.Parse` 메서드.</span><span class="sxs-lookup"><span data-stu-id="19ef3-105">You can parse a string in Visual Basic by using the `XElement.Parse` method.</span></span> <span data-ttu-id="19ef3-106">그러나 XML 리터럴 문자열에서 XML을 구문 분석으로 동일한 성능 저하의 저하가 발생 하지 않기 때문에 다음 코드에 표시 된 대로 XML 리터럴을 사용 하 여를 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="19ef3-106">However, it is more efficient to use XML literals, as shown in following code, because XML literals do not suffer from the same performance penalties as parsing XML from a string.</span></span>  
  
 <span data-ttu-id="19ef3-107">XML 리터럴을 사용 하 여 복사 하 고 Visual Basic 프로그램에 XML을 붙여 넣습니다. 방금 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19ef3-107">By using XML literals, you can just copy and paste your XML into your Visual Basic program.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19ef3-108">텍스트의 구문을 분석하거나 텍스트 파일에서 XML 문서를 로드하는 방법은 함수 생성보다 효율적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19ef3-108">Parsing text or loading an XML document from a text file is less efficient than functional construction.</span></span> <span data-ttu-id="19ef3-109">코드에서 XML 트리를 초기화하는 경우 텍스트의 구문을 분석하는 경우보다 함수 생성을 사용하는 경우에 프로세서 시간을 적게 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="19ef3-109">If you are initializing an XML tree from code, it takes less processor time to use functional construction than to parse text.</span></span>  
  
```vb  
Dim contacts as XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type="home">206-555-0144</Phone>  
            <Phone Type="work">425-555-0145</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>10</NetWorth>  
        </Contact>  
        <Contact>  
            <Name>Gretchen Rivas</Name>  
            <Phone Type="mobile">206-555-0163</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>11</NetWorth>  
        </Contact>  
    </Contacts>  
```  
  
## <a name="see-also"></a><span data-ttu-id="19ef3-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="19ef3-110">See also</span></span>

- [<span data-ttu-id="19ef3-111">(Visual Basic) XML 구문 분석</span><span class="sxs-lookup"><span data-stu-id="19ef3-111">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
