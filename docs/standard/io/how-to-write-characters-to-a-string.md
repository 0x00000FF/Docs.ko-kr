---
title: '방법: 문자열에 문자 쓰기'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data streams, writing characters to string
- writing characters to strings
- streams, writing characters to strings
- I/O [.NET Framework], writing characters to strings
ms.assetid: 1222cbeb-0760-44bf-9888-914a2a37174b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 969a511f6b3d93450866d7a85cf2bcb198d2581e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-write-characters-to-a-string"></a><span data-ttu-id="7693a-102">방법: 문자열에 문자 쓰기</span><span class="sxs-lookup"><span data-stu-id="7693a-102">How to: Write Characters to a String</span></span>
<span data-ttu-id="7693a-103">다음 코드 예제는 문자 배열에서 문자열로 문자를 동기적 및 비동기적으로 씁니다.</span><span class="sxs-lookup"><span data-stu-id="7693a-103">The following code examples write characters synchronously and asynchronously from a character array into a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7693a-104">예</span><span class="sxs-lookup"><span data-stu-id="7693a-104">Example</span></span>  
 <span data-ttu-id="7693a-105">다음 예제는 배열에서 문자열로 5자를 동기적으로 씁니다.</span><span class="sxs-lookup"><span data-stu-id="7693a-105">The following example writes 5 characters synchronously from an array to a string.</span></span>  
  
 [!code-csharp[Conceptual.StringBuilder#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/example2.cs#9)]
 [!code-vb[Conceptual.StringBuilder#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/example2.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="7693a-106">예</span><span class="sxs-lookup"><span data-stu-id="7693a-106">Example</span></span>  
 <span data-ttu-id="7693a-107">다음 예제는 <xref:System.Windows.Controls.TextBox> 컨트롤에서 모든 문자를 비동기적으로 읽고 배열에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7693a-107">The next example reads all the characters asynchronously from a <xref:System.Windows.Controls.TextBox> control, and stores them in an array.</span></span> <span data-ttu-id="7693a-108">그런 다음 별도의 줄에 각 문자 또는 공백 문자를 비동기적으로 쓰고 이어서 <xref:System.Windows.Controls.TextBlock> 컨트롤에 대한 줄 바꿈이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7693a-108">It then asynchronously writes each letter or white space character on a separate line followed by a line break to a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="7693a-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7693a-109">See Also</span></span>  
 <xref:System.IO.StringWriter>  
 <xref:System.IO.StringWriter.Write%2A?displayProperty=nameWithType>  
 <xref:System.Text.StringBuilder>  
 [<span data-ttu-id="7693a-110">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="7693a-110">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)  
 [<span data-ttu-id="7693a-111">비동기 파일 I/O</span><span class="sxs-lookup"><span data-stu-id="7693a-111">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [<span data-ttu-id="7693a-112">방법: 디렉터리 및 파일 열거</span><span class="sxs-lookup"><span data-stu-id="7693a-112">How to: Enumerate Directories and Files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [<span data-ttu-id="7693a-113">방법: 새로 만든 데이터 파일 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="7693a-113">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [<span data-ttu-id="7693a-114">방법: 로그 파일 열기 및 추가</span><span class="sxs-lookup"><span data-stu-id="7693a-114">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [<span data-ttu-id="7693a-115">방법: 파일의 텍스트 읽기</span><span class="sxs-lookup"><span data-stu-id="7693a-115">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [<span data-ttu-id="7693a-116">방법: 파일에 텍스트 쓰기</span><span class="sxs-lookup"><span data-stu-id="7693a-116">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [<span data-ttu-id="7693a-117">방법: 문자열에서 문자 읽기</span><span class="sxs-lookup"><span data-stu-id="7693a-117">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)
