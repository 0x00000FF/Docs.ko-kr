---
title: 원본 Office Open XML 문서 (Visual Basic) 만들기
ms.date: 07/20/2015
ms.assetid: 61ccd6fb-0c47-4075-afdf-5b5021330f21
ms.openlocfilehash: 83cb7d0a325e11c9669f1331e57bed7bf09f27c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59333693"
---
# <a name="creating-the-source-office-open-xml-document-visual-basic"></a><span data-ttu-id="5c1e5-102">원본 Office Open XML 문서 (Visual Basic) 만들기</span><span class="sxs-lookup"><span data-stu-id="5c1e5-102">Creating the Source Office Open XML Document (Visual Basic)</span></span>
<span data-ttu-id="5c1e5-103">이 항목에서는 이 자습서의 다른 예제에서 사용하는 Office Open XML WordprocessingML 문서를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c1e5-103">This topic shows how to create the Office Open XML WordprocessingML document that the other examples in this tutorial use.</span></span> <span data-ttu-id="5c1e5-104">이러한 지침을 따르는 경우 출력은 각 예제에서 제공되는 출력과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="5c1e5-104">If you follow these instructions, your output will match the output provided in each example.</span></span>  
  
 <span data-ttu-id="5c1e5-105">그러나 이 자습서의 예제는 모든 유효한 WordprocessingML 문서와 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="5c1e5-105">However, the examples in this tutorial will work with any valid WordprocessingML document.</span></span>  
  
 <span data-ttu-id="5c1e5-106">이 자습서에서 사용하는 문서를 만들려면 Microsoft Office 2007 이상이 설치되어 있거나 Word, Excel 및 PowerPoint 2007 파일 형식용 Microsoft Office 호환 기능 팩이 포함된 Microsoft Office 2003이 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c1e5-106">To create the document that this tutorial uses, you must either have Microsoft Office 2007 or later installed, or you must have Microsoft Office 2003 with the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>  
  
## <a name="creating-the-wordprocessingml-document"></a><span data-ttu-id="5c1e5-107">WordprocessingML 문서 만들기</span><span class="sxs-lookup"><span data-stu-id="5c1e5-107">Creating the WordprocessingML Document</span></span>  
  
#### <a name="to-create-the-wordprocessingml-document"></a><span data-ttu-id="5c1e5-108">WordprocessingML 문서를 만들려면</span><span class="sxs-lookup"><span data-stu-id="5c1e5-108">To create the WordprocessingML document</span></span>  
  
1. <span data-ttu-id="5c1e5-109">Microsoft Word 문서를 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5c1e5-109">Create a new Microsoft Word document.</span></span>  
  
2. <span data-ttu-id="5c1e5-110">다음 텍스트를 새 문서에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="5c1e5-110">Paste the following text into the new document:</span></span>  
  
    ```  
    Parsing WordprocessingML with LINQ to XML  
  
    The following example prints to the console.  
  
    Imports System  
  
    Class Program  
        Public Shared  Sub Main(ByVal args() As String)  
            Console.WriteLine("Hello World")  
        End Sub  
    End Class  
  
    This example produces the following output:  
  
    Hello World  
    ```  
  
3. <span data-ttu-id="5c1e5-111">"제목 1" 스타일로 첫 번째 줄의 서식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c1e5-111">Format the first line with the style "Heading 1".</span></span>  
  
4. <span data-ttu-id="5c1e5-112">Visual Basic 코드를 포함 하는 줄을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c1e5-112">Select the lines that contain the Visual Basic code.</span></span> <span data-ttu-id="5c1e5-113">첫 번째 줄은 `Imports` 키워드로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5c1e5-113">The first line starts with the `Imports` keyword.</span></span> <span data-ttu-id="5c1e5-114">마지막 줄은 "End Class"입니다.</span><span class="sxs-lookup"><span data-stu-id="5c1e5-114">The last line is "End Class".</span></span> <span data-ttu-id="5c1e5-115">courier 글꼴로 줄의 서식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c1e5-115">Format the lines with the courier font.</span></span> <span data-ttu-id="5c1e5-116">새 스타일로 줄의 서식을 지정한 다음 새 스타일의 이름을 "Code"로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c1e5-116">Format them with a new style, and name the new style "Code".</span></span>  
  
5. <span data-ttu-id="5c1e5-117">마지막으로 출력이 포함된 전체 줄을 선택하고 `Code` 스타일로 서식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c1e5-117">Finally, select the entire line that contains the output, and format it with the `Code` style.</span></span>  
  
6. <span data-ttu-id="5c1e5-118">문서를 저장하고 SampleDoc.docx로 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c1e5-118">Save the document, and name it SampleDoc.docx.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5c1e5-119">Microsoft Word 2003을 사용하는 경우 **파일 형식** 드롭다운 목록에서 **Word 2007 문서**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c1e5-119">If you are using Microsoft Word 2003, select **Word 2007 Document** in the **Save as Type** drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c1e5-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="5c1e5-120">See also</span></span>

- [<span data-ttu-id="5c1e5-121">자습서: (Visual Basic) WordprocessingML 문서에서 내용 조작</span><span class="sxs-lookup"><span data-stu-id="5c1e5-121">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
