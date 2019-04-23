---
title: '방법: 파일이 어셈블리인지 확인(C#)'
ms.date: 07/20/2015
ms.assetid: ea5186bb-5bff-4dcb-bde9-d6ba4e2edd00
ms.openlocfilehash: e8026ab5fa44b7601e54b5e76ebf9eb434596a07
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59340141"
---
# <a name="how-to-determine-if-a-file-is-an-assembly-c"></a><span data-ttu-id="8e4c4-102">방법: 파일이 어셈블리인지 확인(C#)</span><span class="sxs-lookup"><span data-stu-id="8e4c4-102">How to: Determine If a File Is an Assembly (C#)</span></span>
<span data-ttu-id="8e4c4-103">파일은 관리되고 해당 메타데이터에 어셈블리 항목을 포함하는 경우에만 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="8e4c4-103">A file is an assembly if and only if it is managed, and contains an assembly entry in its metadata.</span></span> <span data-ttu-id="8e4c4-104">어셈블리 및 메타데이터에 대한 자세한 내용은 [어셈블리 매니페스트](../../../../../docs/framework/app-domains/assembly-manifest.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e4c4-104">For more information on assemblies and metadata, see the topic [Assembly Manifest](../../../../../docs/framework/app-domains/assembly-manifest.md).</span></span>  
  
### <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="8e4c4-105">파일이 어셈블리인지 수동으로 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="8e4c4-105">How to manually determine if a file is an assembly</span></span>  
  
1. <span data-ttu-id="8e4c4-106">[Ildasm.exe(IL 디스어셈블러)](../../../../framework/tools/ildasm-exe-il-disassembler.md)를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8e4c4-106">Start the [Ildasm.exe (IL Disassembler)](../../../../framework/tools/ildasm-exe-il-disassembler.md).</span></span>  
  
2. <span data-ttu-id="8e4c4-107">테스트하려는 파일을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="8e4c4-107">Load the file you wish to test.</span></span>  
  
3. <span data-ttu-id="8e4c4-108">**ILDASM**에서 파일이 PE(이식 가능) 파일이 아니라고 보고하는 경우에는 어셈블리가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8e4c4-108">If **ILDASM** reports that the file is not a portable executable (PE) file, then it is not an assembly.</span></span> <span data-ttu-id="8e4c4-109">자세한 내용은 항목 [방법: 어셈블리 콘텐츠 보기](../../../../framework/app-domains/how-to-view-assembly-contents.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e4c4-109">For more information, see the topic [How to: View Assembly Contents](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span></span>  
  
### <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="8e4c4-110">파일이 어셈블리인지 프로그래밍 방식으로 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="8e4c4-110">How to programmatically determine if a file is an assembly</span></span>  
  
1. <span data-ttu-id="8e4c4-111">테스트하는 파일의 전체 파일 경로와 이름을 전달하여 <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8e4c4-111">Call the <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method, passing the full file path and name of the file you are testing.</span></span>  
  
2. <span data-ttu-id="8e4c4-112"><xref:System.BadImageFormatException> 예외가 throw되는 경우 파일이 어셈블리가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8e4c4-112">If a <xref:System.BadImageFormatException> exception is thrown, the file is not an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e4c4-113">예</span><span class="sxs-lookup"><span data-stu-id="8e4c4-113">Example</span></span>  
 <span data-ttu-id="8e4c4-114">이 예제에서는 DLL을 테스트하여 어셈블리인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8e4c4-114">This example tests a DLL to see if it is an assembly.</span></span>  
  
```csharp
class TestAssembly  
{  
    static void Main()  
    {  
  
        try  
        {  
            System.Reflection.AssemblyName testAssembly =  
                System.Reflection.AssemblyName.GetAssemblyName(@"C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll");  
  
            System.Console.WriteLine("Yes, the file is an assembly.");  
        }  
  
        catch (System.IO.FileNotFoundException)  
        {  
            System.Console.WriteLine("The file cannot be found.");  
        }  
  
        catch (System.BadImageFormatException)  
        {  
            System.Console.WriteLine("The file is not an assembly.");  
        }  
  
        catch (System.IO.FileLoadException)  
        {  
            System.Console.WriteLine("The assembly has already been loaded.");  
        }  
    }  
}  
/* Output (with .NET Framework 3.5 installed):  
    Yes, the file is an assembly.  
*/  
```  
  
 <span data-ttu-id="8e4c4-115"><xref:System.Reflection.AssemblyName.GetAssemblyName%2A> 메서드는 테스트 파일을 로드한 다음 정보를 읽고 나면 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="8e4c4-115">The <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method loads the test file, and then releases it once the information is read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e4c4-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e4c4-116">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="8e4c4-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="8e4c4-117">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="8e4c4-118">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="8e4c4-118">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
