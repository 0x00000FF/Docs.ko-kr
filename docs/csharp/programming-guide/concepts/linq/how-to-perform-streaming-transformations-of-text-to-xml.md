---
title: "방법: 텍스트를 XML로 변환 스트리밍 수행(C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 9b3bd941-d0ff-4f2d-ae41-7c3b81d8fae6
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3351f88bb27807714b3566992242e72a5d03ac14
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-perform-streaming-transformations-of-text-to-xml-c"></a><span data-ttu-id="fa68c-102">방법: 텍스트를 XML로 변환 스트리밍 수행(C#)</span><span class="sxs-lookup"><span data-stu-id="fa68c-102">How to: Perform Streaming Transformations of Text to XML (C#)</span></span>
<span data-ttu-id="fa68c-103">텍스트 파일을 처리하는 한 가지 방법은 `yield return` 구문을 사용하여 한 번에 한 줄씩 텍스트 파일을 스트리밍하는 확장 메서드를 작성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fa68c-103">One approach to processing a text file is to write an extension method that streams the text file a line at a time using the `yield return` construct.</span></span> <span data-ttu-id="fa68c-104">그런 다음 지연된 방식으로 텍스트 파일을 처리하는 LINQ 쿼리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa68c-104">You then can write a LINQ query that processes the text file in a lazy deferred fashion.</span></span> <span data-ttu-id="fa68c-105"><xref:System.Xml.Linq.XStreamingElement>를 사용하여 출력을 스트림하면 소스 텍스트 파일의 크기에 관계없이 최소 메모리 크기를 사용하는 XML로 텍스트 파일을 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa68c-105">If you then use <xref:System.Xml.Linq.XStreamingElement> to stream output, you then can create a transformation from the text file to XML that uses a minimal amount of memory, regardless of the size of the source text file.</span></span>  
  
 <span data-ttu-id="fa68c-106">스트리밍 변환과 관련된 몇 가지 주의 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa68c-106">There are some caveats regarding streaming transformations.</span></span> <span data-ttu-id="fa68c-107">스트리밍 변환은 전체 파일을 한 번만 처리할 수 있는 경우와 소스 문서에서 발생하는 순서대로 줄을 처리할 수 있는 경우에 가장 효과적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa68c-107">A streaming transformation is best applied in situations where you can process the entire file once, and if you can process the lines in the order that they occur in the source document.</span></span> <span data-ttu-id="fa68c-108">파일을 두 번 이상 처리해야 하거나 줄을 처리하기 전에 정렬해야 하는 경우에는 스트리밍 기법 사용의 많은 이점을 얻을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa68c-108">If you have to process the file more than once, or if you have to sort the lines before you can process them, you will lose many of the benefits of using a streaming technique.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa68c-109">예제</span><span class="sxs-lookup"><span data-stu-id="fa68c-109">Example</span></span>  
 <span data-ttu-id="fa68c-110">아래에 있는 People.txt 텍스트 파일은 이 예제의 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="fa68c-110">The following text file, People.txt, is the source for this example.</span></span>  
  
```  
#This is a comment  
1,Tai,Yee,Writer  
2,Nikolay,Grachev,Programmer  
3,David,Wright,Inventor  
```  
  
 <span data-ttu-id="fa68c-111">다음 코드에는 지연된 방식으로 텍스트 파일의 줄을 스트림하는 확장 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa68c-111">The following code contains an extension method that streams the lines of the text file in a deferred fashion.</span></span>  
  
```csharp  
public static class StreamReaderSequence  
{  
    public static IEnumerable<string> Lines(this StreamReader source)  
    {  
        String line;  
  
        if (source == null)  
            throw new ArgumentNullException("source");  
        while ((line = source.ReadLine()) != null)  
        {  
            yield return line;  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        StreamReader sr = new StreamReader("People.txt");  
        XStreamingElement xmlTree = new XStreamingElement("Root",  
            from line in sr.Lines()  
            let items = line.Split(',')  
            where !line.StartsWith("#")  
            select new XElement("Person",  
                       new XAttribute("ID", items[0]),  
                       new XElement("First", items[1]),  
                       new XElement("Last", items[2]),  
                       new XElement("Occupation", items[3])  
                   )  
        );  
        Console.WriteLine(xmlTree);  
        sr.Close();  
    }  
}  
```  
  
 <span data-ttu-id="fa68c-112">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fa68c-112">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Person ID="1">  
    <First>Tai</First>  
    <Last>Yee</Last>  
    <Occupation>Writer</Occupation>  
  </Person>  
  <Person ID="2">  
    <First>Nikolay</First>  
    <Last>Grachev</Last>  
    <Occupation>Programmer</Occupation>  
  </Person>  
  <Person ID="3">  
    <First>David</First>  
    <Last>Wright</Last>  
    <Occupation>Inventor</Occupation>  
  </Person>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa68c-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa68c-113">See Also</span></span>  
 <span data-ttu-id="fa68c-114"><xref:System.Xml.Linq.XStreamingElement></span><span class="sxs-lookup"><span data-stu-id="fa68c-114"><xref:System.Xml.Linq.XStreamingElement></span></span>   
 [<span data-ttu-id="fa68c-115">고급 쿼리 기술(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="fa68c-115">Advanced Query Techniques (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)

