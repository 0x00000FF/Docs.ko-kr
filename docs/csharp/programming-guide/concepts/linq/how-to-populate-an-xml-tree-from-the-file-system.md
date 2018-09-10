---
title: '방법: 파일 시스템에서 XML 트리 채우기(C#)'
ms.date: 07/20/2015
ms.assetid: 2aa2ccac-4a22-47ae-9107-3bb8df232576
ms.openlocfilehash: 7bddab1942c5a673969e271338f17705914f81a4
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44204996"
---
# <a name="how-to-populate-an-xml-tree-from-the-file-system-c"></a><span data-ttu-id="350dc-102">방법: 파일 시스템에서 XML 트리 채우기(C#)</span><span class="sxs-lookup"><span data-stu-id="350dc-102">How to: Populate an XML Tree from the File System (C#)</span></span>
<span data-ttu-id="350dc-103">일반적으로 XML 트리는 계층적인 이름/값 데이터 저장소로 유용하게 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="350dc-103">A common and useful application of XML trees is as a hierarchical name/value data store.</span></span> <span data-ttu-id="350dc-104">계층적 데이터로 XML 트리를 채운 다음 쿼리 및 변환하고 필요한 경우 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="350dc-104">You can populate an XML tree with hierarchical data, and then query it, transform it, and if necessary, serialize it.</span></span> <span data-ttu-id="350dc-105">이 사용 시나리오에서 네임스페이스 및 공백 동작과 같은 많은 XML 관련 의미는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="350dc-105">In this usage scenario, many of the XML specific semantics, such as namespaces and white space behavior, are not important.</span></span> <span data-ttu-id="350dc-106">대신 XML 트리를 한 사용자가 사용하는 작고 계층적인 메모리 내 데이터베이스로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="350dc-106">Instead, you are using the XML tree as a small, in memory, single user hierarchical database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="350dc-107">예</span><span class="sxs-lookup"><span data-stu-id="350dc-107">Example</span></span>  
 <span data-ttu-id="350dc-108">다음 예제에서는 재귀를 사용하여 로컬 파일 시스템에서 XML 트리를 채운 다음</span><span class="sxs-lookup"><span data-stu-id="350dc-108">The following example populates an XML tree from the local file system using recursion.</span></span> <span data-ttu-id="350dc-109">트리를 쿼리하고 트리에 있는 모든 파일의 총 크기를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="350dc-109">It then queries the tree, calculating the total of the sizes of all files in the tree.</span></span>  
  
```csharp  
class Program  
{  
    static XElement CreateFileSystemXmlTree(string source)  
    {  
        DirectoryInfo di = new DirectoryInfo(source);  
        return new XElement("Dir",  
            new XAttribute("Name", di.Name),  
            from d in Directory.GetDirectories(source)  
            select CreateFileSystemXmlTree(d),  
            from fi in di.GetFiles()  
            select new XElement("File",  
                new XElement("Name", fi.Name),  
                new XElement("Length", fi.Length)  
            )  
        );  
    }  
  
    static void Main(string[] args)  
    {  
        XElement fileSystemTree = CreateFileSystemXmlTree("C:/Tmp");  
        Console.WriteLine(fileSystemTree);  
        Console.WriteLine("------");  
        long totalFileSize =  
            (from f in fileSystemTree.Descendants("File")  
             select (long)f.Element("Length")).Sum();  
        Console.WriteLine("Total File Size:{0}", totalFileSize);  
    }  
}  
```  
  
 <span data-ttu-id="350dc-110">이 예제의 결과는 다음과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="350dc-110">This example produces output similar to the following:</span></span>  
  
```xml  
<Dir Name="Tmp">  
  <Dir Name="ConsoleApplication1">  
    <Dir Name="bin">  
      <Dir Name="Debug">  
        <File>  
          <Name>ConsoleApplication1.exe</Name>  
          <Length>4608</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.pdb</Name>  
          <Length>11776</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.vshost.exe</Name>  
          <Length>9568</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.vshost.exe.manifest</Name>  
          <Length>473</Length>  
        </File>  
      </Dir>  
    </Dir>  
    <Dir Name="obj">  
      <Dir Name="Debug">  
        <Dir Name="TempPE" />  
        <File>  
          <Name>ConsoleApplication1.csproj.FileListAbsolute.txt</Name>  
          <Length>322</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.exe</Name>  
          <Length>4608</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.pdb</Name>  
          <Length>11776</Length>  
        </File>  
      </Dir>  
    </Dir>  
    <Dir Name="Properties">  
      <File>  
        <Name>AssemblyInfo.cs</Name>  
        <Length>1454</Length>  
      </File>  
    </Dir>  
    <File>  
      <Name>ConsoleApplication1.csproj</Name>  
      <Length>2546</Length>  
    </File>  
    <File>  
      <Name>ConsoleApplication1.sln</Name>  
      <Length>937</Length>  
    </File>  
    <File>  
      <Name>ConsoleApplication1.suo</Name>  
      <Length>10752</Length>  
    </File>  
    <File>  
      <Name>Program.cs</Name>  
      <Length>269</Length>  
    </File>  
  </Dir>  
</Dir>  
------  
Total File Size:59089  
```  
  
## <a name="see-also"></a><span data-ttu-id="350dc-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="350dc-111">See Also</span></span>

- [<span data-ttu-id="350dc-112">고급 쿼리 기술(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="350dc-112">Advanced Query Techniques (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
