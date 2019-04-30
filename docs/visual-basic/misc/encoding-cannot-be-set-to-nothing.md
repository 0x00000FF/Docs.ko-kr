---
title: 인코딩은 Nothing으로 설정할 수 없음
ms.date: 07/20/2015
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
ms.openlocfilehash: 30b0b4a29fbdf931aa62263b75d1fa946e87b145
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970328"
---
# <a name="encoding-cannot-be-set-to-nothing"></a><span data-ttu-id="46fed-102">인코딩은 Nothing으로 설정할 수 없음</span><span class="sxs-lookup"><span data-stu-id="46fed-102">Encoding cannot be set to Nothing</span></span>
<span data-ttu-id="46fed-103">`encoding` 매개 변수가 `Nothing` 으로 설정되었지만 유효한 값이 필요하기 때문에 파일에서 읽거나 쓰려는 시도가 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="46fed-103">An attempt to read from or write to a file has failed because the parameter `encoding` has been set to `Nothing` but requires a valid value.</span></span>  
  
 <span data-ttu-id="46fed-104"><xref:System.Text.Encoding> 은 파일에 쓸 때 사용할 인코딩을 결정하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="46fed-104"><xref:System.Text.Encoding> is used to determine what encoding to use when writing to a file.</span></span> <span data-ttu-id="46fed-105">기본값은 UTF-8입니다.</span><span class="sxs-lookup"><span data-stu-id="46fed-105">The default is UTF-8.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="46fed-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="46fed-106">To correct this error</span></span>  
  
- <span data-ttu-id="46fed-107">`encoding` 매개 변수에 대한 유효한 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="46fed-107">Supply a valid value for the `encoding` parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46fed-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="46fed-108">See also</span></span>

- [<span data-ttu-id="46fed-109">파일 인코딩</span><span class="sxs-lookup"><span data-stu-id="46fed-109">File Encodings</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)
- [<span data-ttu-id="46fed-110">파일 읽기</span><span class="sxs-lookup"><span data-stu-id="46fed-110">Reading from Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [<span data-ttu-id="46fed-111">파일에 쓰기</span><span class="sxs-lookup"><span data-stu-id="46fed-111">Writing to Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
- [<span data-ttu-id="46fed-112">My.Computer.FileSystem.ReadAllText</span><span class="sxs-lookup"><span data-stu-id="46fed-112">My.Computer.FileSystem.ReadAllText</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A)
- [<span data-ttu-id="46fed-113">My.Computer.FileSystem.WriteAllText</span><span class="sxs-lookup"><span data-stu-id="46fed-113">My.Computer.FileSystem.WriteAllText</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A)
