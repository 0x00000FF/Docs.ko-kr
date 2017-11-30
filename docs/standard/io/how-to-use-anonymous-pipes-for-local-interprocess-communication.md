---
title: "방법: 로컬 프로세스 간 통신에 익명 파이프 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- anonymous pipes [.NET Framework]
- parent-child communication [.NET Framework]
- pipes [.NET Framework]
- one-way communication [.NET Framework]
- local computer communication [.NET Framework], pipes
ms.assetid: e7773c77-c646-4a01-8a96-a003d59fc4c9
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f457cc91e6fbfc118e5363d1b0a8e8c2ad800748
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-anonymous-pipes-for-local-interprocess-communication"></a><span data-ttu-id="4dae1-102">방법: 로컬 프로세스 간 통신에 익명 파이프 사용</span><span class="sxs-lookup"><span data-stu-id="4dae1-102">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>
<span data-ttu-id="4dae1-103">익명 파이프는 로컬 컴퓨터에서 프로세스 간 통신을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4dae1-103">Anonymous pipes provide interprocess communication on a local computer.</span></span> <span data-ttu-id="4dae1-104">명명된 파이프보다 적은 기능을 제공하지만 오버로드를 더 적게 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dae1-104">They offer less functionality than named pipes, but also require less overhead.</span></span> <span data-ttu-id="4dae1-105">프로세스 간 통신 로컬 컴퓨터에 쉽게 수행할 수 있도록 익명 파이프를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dae1-105">You can use anonymous pipes to make interprocess communication on a local computer easier.</span></span> <span data-ttu-id="4dae1-106">네트워크를 통한 통신에 대 한 익명 파이프를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4dae1-106">You cannot use anonymous pipes for communication over a network.</span></span>  
  
 <span data-ttu-id="4dae1-107">익명 파이프를 구현하려면, <xref:System.IO.Pipes.AnonymousPipeServerStream> 및 <xref:System.IO.Pipes.AnonymousPipeClientStream> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4dae1-107">To implement anonymous pipes, use the <xref:System.IO.Pipes.AnonymousPipeServerStream> and <xref:System.IO.Pipes.AnonymousPipeClientStream> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4dae1-108">예제</span><span class="sxs-lookup"><span data-stu-id="4dae1-108">Example</span></span>  
 <span data-ttu-id="4dae1-109">다음 예제에서는 익명 파이프를 사용 하는 자식 프로세스에는 부모 프로세스에서 문자열을 보내는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4dae1-109">The following example demonstrates a way to send a string from a parent process to a child process using anonymous pipes.</span></span> <span data-ttu-id="4dae1-110">이 예제에서는 만듭니다는 <xref:System.IO.Pipes.AnonymousPipeServerStream> 인 부모 프로세스의 개체는 <xref:System.IO.Pipes.PipeDirection> 값 <xref:System.IO.Pipes.PipeDirection.Out>합니다.</span><span class="sxs-lookup"><span data-stu-id="4dae1-110">This example creates an <xref:System.IO.Pipes.AnonymousPipeServerStream> object in a parent process with a <xref:System.IO.Pipes.PipeDirection> value of <xref:System.IO.Pipes.PipeDirection.Out>.</span></span> <span data-ttu-id="4dae1-111">부모 프로세스를 만들려면 클라이언트 핸들을 사용 하 여 다음는 자식 프로세스를 생성 한 <xref:System.IO.Pipes.AnonymousPipeClientStream> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4dae1-111">The parent process then creates a child process by using a client handle to create an <xref:System.IO.Pipes.AnonymousPipeClientStream> object.</span></span> <span data-ttu-id="4dae1-112">자식 프로세스에는 <xref:System.IO.Pipes.PipeDirection> 값 <xref:System.IO.Pipes.PipeDirection.In>합니다.</span><span class="sxs-lookup"><span data-stu-id="4dae1-112">The child process has a <xref:System.IO.Pipes.PipeDirection> value of <xref:System.IO.Pipes.PipeDirection.In>.</span></span>  
  
 <span data-ttu-id="4dae1-113">그런 다음 부모 프로세스는 자식 프로세스에는 사용자가 제공한 문자열을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="4dae1-113">The parent process then sends a user-supplied string to the child process.</span></span> <span data-ttu-id="4dae1-114">문자열은 자식 프로세스에서 콘솔에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4dae1-114">The string is displayed to the console in the child process.</span></span>  
  
 <span data-ttu-id="4dae1-115">다음 예제에서는 서버 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4dae1-115">The following example shows the server process.</span></span>  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/vb/program.vb#01)]  
  
## <a name="example"></a><span data-ttu-id="4dae1-116">예제</span><span class="sxs-lookup"><span data-stu-id="4dae1-116">Example</span></span>  
 <span data-ttu-id="4dae1-117">다음 예제에서는 클라이언트 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4dae1-117">The following example shows the client process.</span></span> <span data-ttu-id="4dae1-118">서버 프로세스가 클라이언트 프로세스를 시작 하 고 클라이언트 핸들이 프로세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dae1-118">The server process starts the client process and gives that process a client handle.</span></span> <span data-ttu-id="4dae1-119">클라이언트 코드에서 결과 실행 파일 이름을 지정 해야 `pipeClient.exe` 서버 프로세스를 실행 하기 전에 실행 되는 서버와 동일한 디렉터리에 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4dae1-119">The resulting executable from the client code should be named `pipeClient.exe` and be copied to the same directory as the server executable before running the server process.</span></span>  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/vb/program.vb#01)]  
  
## <a name="see-also"></a><span data-ttu-id="4dae1-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4dae1-120">See Also</span></span>  
 [<span data-ttu-id="4dae1-121">파이프</span><span class="sxs-lookup"><span data-stu-id="4dae1-121">Pipes</span></span>](../../../docs/standard/io/pipe-operations.md)  
 [<span data-ttu-id="4dae1-122">방법: 네트워크 프로세스 간 통신에 명명된 파이프 사용</span><span class="sxs-lookup"><span data-stu-id="4dae1-122">How to: Use Named Pipes for Network Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
