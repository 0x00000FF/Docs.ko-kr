---
title: F#을 사용 하 여 Azure Queue storage 시작
description: Azure 큐는 응용 프로그램 구성 요소 간에 안정적이 고 비동기 메시징을 제공 합니다. 클라우드 메시징을 사용 하면 독립적으로 확장할 응용 프로그램 구성 요소입니다.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 14bbc657f965fc262d2a83b1fdf982fe5e75d55e
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2018
ms.locfileid: "33569420"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a><span data-ttu-id="0383e-104">F#을 사용 하 여 Azure Queue storage 시작</span><span class="sxs-lookup"><span data-stu-id="0383e-104">Get started with Azure Queue storage using F#</span></span> #

<span data-ttu-id="0383e-105">Azure Queue storage는 응용 프로그램 구성 요소 간에 클라우드 메시징을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-105">Azure Queue storage provides cloud messaging between application components.</span></span> <span data-ttu-id="0383e-106">눈금에 대 한 응용 프로그램을 디자인, 응용 프로그램 구성 요소는 종종 분리 독립적으로 확장할 수 있도록.</span><span class="sxs-lookup"><span data-stu-id="0383e-106">In designing applications for scale, application components are often decoupled, so that they can scale independently.</span></span> <span data-ttu-id="0383e-107">Queue storage는 클라우드, 데스크톱, 온-프레미스 서버를 또는 모바일 장치에서에서 실행 중인지 여부를 응용 프로그램 구성 요소 간의 통신을 위한 비동기 메시징을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-107">Queue storage delivers asynchronous messaging for communication between application components, whether they are running in the cloud, on the desktop, on an on-premises server, or on a mobile device.</span></span> <span data-ttu-id="0383e-108">큐 저장소는 비동기 작업 관리와 프로세스 워크플로 작성도 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-108">Queue storage also supports managing asynchronous tasks and building process work flows.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="0383e-109">이 자습서 정보</span><span class="sxs-lookup"><span data-stu-id="0383e-109">About this tutorial</span></span>

<span data-ttu-id="0383e-110">이 자습서에서는 작성 하는 방법을 보여 줍니다. F# Azure Queue storage를 사용 하 여 몇 가지 일반적인 작업에 대 한 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-110">This tutorial shows how to write F# code for some common tasks using Azure Queue storage.</span></span> <span data-ttu-id="0383e-111">다루는 작업 만들기 및 큐를 삭제 하 고 추가, 읽기 및 큐 메시지를 삭제를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-111">Tasks covered include creating and deleting queues and adding, reading, and deleting queue messages.</span></span>

<span data-ttu-id="0383e-112">큐 저장소의 개념적인 개요를 참조 하세요 [큐 저장소에 대 한.NET 가이드](/azure/storage/storage-dotnet-how-to-use-queues)합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-112">For a conceptual overview of queue storage, please see [the .NET guide for queue storage](/azure/storage/storage-dotnet-how-to-use-queues).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0383e-113">전제 조건</span><span class="sxs-lookup"><span data-stu-id="0383e-113">Prerequisites</span></span>

<span data-ttu-id="0383e-114">이 가이드를 사용 하려면 먼저 [Azure storage 계정 만들기](/azure/storage/storage-create-storage-account)합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-114">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="0383e-115">또한이 계정에 대 한 저장소 액세스 키를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-115">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="0383e-116">만들기는 F# 스크립트와 시작 F# 대화형</span><span class="sxs-lookup"><span data-stu-id="0383e-116">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="0383e-117">이 문서의 샘플에에서는 F# 응용 프로그램 또는 F# 스크립트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-117">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="0383e-118">F# 스크립트를 만들려면 사용 하 여 파일을 만듭니다는 `.fsx` 확장명을 예를 들어 `queues.fsx`, F# 개발 환경에서.</span><span class="sxs-lookup"><span data-stu-id="0383e-118">To create an F# script, create a file with the `.fsx` extension, for example `queues.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="0383e-119">다음을 사용 하 여는 [패키지 관리자](package-management.md) 와 같은 [Paket](https://fsprojects.github.io/Paket/) 또는 [NuGet](https://www.nuget.org/) 설치 하는 `WindowsAzure.Storage` 패키지 및 참조 `WindowsAzure.Storage.dll` 를사용하여스크립트에서`#r`지시문입니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-119">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="0383e-120">네임 스페이스 선언을 추가합니다</span><span class="sxs-lookup"><span data-stu-id="0383e-120">Add namespace declarations</span></span>

<span data-ttu-id="0383e-121">다음을 추가 합니다 `open` 의 맨 위에 문을 `queues.fsx` 파일:</span><span class="sxs-lookup"><span data-stu-id="0383e-121">Add the following `open` statements to the top of the `queues.fsx` file:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a><span data-ttu-id="0383e-122">연결 문자열 가져오기</span><span class="sxs-lookup"><span data-stu-id="0383e-122">Get your connection string</span></span>

<span data-ttu-id="0383e-123">이 자습서에 대 한 Azure Storage 연결 문자열을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-123">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="0383e-124">연결 문자열에 대 한 자세한 내용은 참조 하세요. [저장소 연결 문자열 구성](/azure/storage/storage-configure-connection-string)합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-124">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="0383e-125">자습서의 경우 다음과 같은 스크립트에서 연결 문자열을 입력 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-125">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

<span data-ttu-id="0383e-126">그러나 이것이 **좋지** 실제 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-126">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="0383e-127">저장소 계정 키는 저장소 계정의 루트 암호와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-127">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="0383e-128">항상 저장소 계정 키를 보호 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-128">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="0383e-129">다른 사용자에 하드 코딩 하거나 다른 사용자에 게 액세스할 수 있는 일반 텍스트 파일을 저장 하 게 배포 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="0383e-129">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="0383e-130">손상 되었다고 생각 하는 경우 Azure Portal을 사용 하 여 키를 다시 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-130">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="0383e-131">실제 응용 프로그램 저장소 연결 문자열을 유지 하는 가장 좋은 방법은 구성 파일에서 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-131">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="0383e-132">구성 파일에서 연결 문자열을 가져올,이 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-132">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

<span data-ttu-id="0383e-133">Azure 구성 관리자를 사용 하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-133">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="0383e-134">.NET Framework의 등의 API를 사용할 수도 있습니다 `ConfigurationManager` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-134">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="0383e-135">연결 문자열을 구문 분석</span><span class="sxs-lookup"><span data-stu-id="0383e-135">Parse the connection string</span></span>

<span data-ttu-id="0383e-136">연결 문자열을 구문 분석 하려면 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-136">To parse the connection string, use:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

<span data-ttu-id="0383e-137">이 반환 된 `CloudStorageAccount`합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-137">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-queue-service-client"></a><span data-ttu-id="0383e-138">큐 서비스 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="0383e-138">Create the Queue service client</span></span>

<span data-ttu-id="0383e-139">`CloudQueueClient` 클래스를 사용 하면 큐 저장소에 저장 된 큐를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-139">The `CloudQueueClient` class enables you to retrieve queues stored in Queue storage.</span></span> <span data-ttu-id="0383e-140">서비스 클라이언트를 만드는 한 가지 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-140">Here's one way to create the service client:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

<span data-ttu-id="0383e-141">이제 데이터를 읽어 오고 큐 저장소로 데이터를 기록 하는 코드를 작성할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-141">Now you are ready to write code that reads data from and writes data to Queue storage.</span></span>

## <a name="create-a-queue"></a><span data-ttu-id="0383e-142">큐 만들기</span><span class="sxs-lookup"><span data-stu-id="0383e-142">Create a queue</span></span>

<span data-ttu-id="0383e-143">이 예제에는 이미 존재 하지 않는 경우 큐를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-143">This example shows how to create a queue if it doesn't already exist:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a><span data-ttu-id="0383e-144">큐에 메시지를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-144">Insert a message into a queue</span></span>

<span data-ttu-id="0383e-145">기존 큐에 메시지를 삽입, 먼저 만들려면 새 `CloudQueueMessage`합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-145">To insert a message into an existing queue, first create a new `CloudQueueMessage`.</span></span> <span data-ttu-id="0383e-146">그런 다음 호출 하 여 `AddMessage` 메서드.</span><span class="sxs-lookup"><span data-stu-id="0383e-146">Next, call the `AddMessage` method.</span></span> <span data-ttu-id="0383e-147">A `CloudQueueMessage` 문자열 (utf-8 형식)에서 만들 수 있습니다 또는 `byte` 같이 배열:</span><span class="sxs-lookup"><span data-stu-id="0383e-147">A `CloudQueueMessage` can be created from either a string (in UTF-8 format) or a `byte` array, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a><span data-ttu-id="0383e-148">다음 메시지를 피킹하십시오</span><span class="sxs-lookup"><span data-stu-id="0383e-148">Peek at the next message</span></span>

<span data-ttu-id="0383e-149">호출 하 여 큐에서 제거 하지 않고 큐 앞의 메시지를 피킹할 수 있습니다는 `PeekMessage` 메서드.</span><span class="sxs-lookup"><span data-stu-id="0383e-149">You can peek at the message in the front of a queue, without removing it from the queue, by calling the `PeekMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a><span data-ttu-id="0383e-150">처리를 위해 다음 메시지를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-150">Get the next message for processing</span></span>

<span data-ttu-id="0383e-151">호출 하 여 처리를 위해 큐의 앞에서 메시지를 검색할 수 있습니다는 `GetMessage` 메서드.</span><span class="sxs-lookup"><span data-stu-id="0383e-151">You can retrieve the message at the front of a queue for processing by calling the `GetMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

<span data-ttu-id="0383e-152">나중에 사용 하 여 메시지를 성공적으로 처리를 나타낼 `DeleteMessage`합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-152">You later indicate successful processing of the message by using `DeleteMessage`.</span></span>

## <a name="change-the-contents-of-a-queued-message"></a><span data-ttu-id="0383e-153">대기 중인된 메시지의 내용을 변경합니다</span><span class="sxs-lookup"><span data-stu-id="0383e-153">Change the contents of a queued message</span></span>

<span data-ttu-id="0383e-154">검색된 메시지에에서 있는 큐의 내용을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-154">You can change the contents of a retrieved message in-place in the queue.</span></span> <span data-ttu-id="0383e-155">메시지 작업을 나타내는 경우에 작업의 상태를 업데이트 하려면이 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-155">If the message represents a work task, you could use this feature to update the status of the work task.</span></span> <span data-ttu-id="0383e-156">다음 코드는 큐 메시지를 새로운 콘텐츠로 업데이트 하 고 표시 제한 시간이 60 초 더 늘어나도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-156">The following code updates the queue message with new contents, and sets the visibility timeout to extend another 60 seconds.</span></span> <span data-ttu-id="0383e-157">이 메시지와 연결 된 작업의 상태를 저장 하 고 클라이언트 메시지에 작업을 계속 하려면 다른 분을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-157">This saves the state of work associated with the message, and gives the client another minute to continue working on the message.</span></span> <span data-ttu-id="0383e-158">처리 단계가 하드웨어 또는 소프트웨어 오류로 인해 실패 하면 처음부터 다시 시작 하지 않고도 큐 메시지에서 다단계 워크플로 추적 하려면이 기법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-158">You could use this technique to track multi-step workflows on queue messages, without having to start over from the beginning if a processing step fails due to hardware or software failure.</span></span> <span data-ttu-id="0383e-159">일반적으로 재시도 횟수를 유지 하 고 메시지를 몇 번 이상 다시 시도 하는 경우 파일을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-159">Typically, you would keep a retry count as well, and if the message is retried more than some number of times, you would delete it.</span></span> <span data-ttu-id="0383e-160">이 처리 될 때마다 응용 프로그램 오류를 트리거하는 메시지를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-160">This protects against a message that triggers an application error each time it is processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a><span data-ttu-id="0383e-161">큐에서 다음 메시지 제거</span><span class="sxs-lookup"><span data-stu-id="0383e-161">De-queue the next message</span></span>

<span data-ttu-id="0383e-162">코드는 두 단계를 거쳐 큐에서 메시지를 큐에서 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-162">Your code de-queues a message from a queue in two steps.</span></span> <span data-ttu-id="0383e-163">호출 하는 경우 `GetMessage`, 큐에서 다음 메시지를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-163">When you call `GetMessage`, you get the next message in a queue.</span></span> <span data-ttu-id="0383e-164">반환 된 메시지 `GetMessage` 이 큐에서 메시지를 읽는 다른 코드에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-164">A message returned from `GetMessage` becomes invisible to any other code reading messages from this queue.</span></span> <span data-ttu-id="0383e-165">이 메시지 기본적으로 30 초 동안 보이지 않는 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-165">By default, this message stays invisible for 30 seconds.</span></span> <span data-ttu-id="0383e-166">큐에서 메시지 제거를 완료 하려면 호출도 해야 `DeleteMessage`합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-166">To finish removing the message from the queue, you must also call `DeleteMessage`.</span></span> <span data-ttu-id="0383e-167">메시지를 제거 하는이 2 단계 프로세스는 코드가 하드웨어 또는 소프트웨어 오류로 인해 메시지를 처리 하는 데 실패 하는 경우 코드의 다른 인스턴스가 수 동일한 메시지가 다시 시도 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-167">This two-step process of removing a message assures that if your code fails to process a message due to hardware or software failure, another instance of your code can get the same message and try again.</span></span> <span data-ttu-id="0383e-168">코드 호출 `DeleteMessage` 직후 메시지가 처리 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-168">Your code calls `DeleteMessage` right after the message has been processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a><span data-ttu-id="0383e-169">일반적인 큐 저장소 Api와 함께 사용 하 여 비동기 워크플로</span><span class="sxs-lookup"><span data-stu-id="0383e-169">Use Async workflows with common Queue storage APIs</span></span>

<span data-ttu-id="0383e-170">이 예제에서는 일반적인 큐 저장소 Api 사용 하 여 비동기 워크플로 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-170">This example shows how to use an async workflow with common Queue storage APIs.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a><span data-ttu-id="0383e-171">취소 큐 메시지에 대 한 추가 옵션</span><span class="sxs-lookup"><span data-stu-id="0383e-171">Additional options for de-queuing messages</span></span>

<span data-ttu-id="0383e-172">두 가지 방법으로 큐에서 메시지 검색을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-172">There are two ways you can customize message retrieval from a queue.</span></span>
<span data-ttu-id="0383e-173">먼저 배치 (최대 32 개) 메시지를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-173">First, you can get a batch of messages (up to 32).</span></span> <span data-ttu-id="0383e-174">둘째, 각 메시지를 완전히 처리 하는 데 시간이 덜 자세한 또는 코드를 허용 더 길거나 더 짧은 표시 안 함 시간 제한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-174">Second, you can set a longer or shorter invisibility timeout, allowing your code more or less time to fully process each message.</span></span> <span data-ttu-id="0383e-175">다음 코드 예제에서는 `GetMessages` 얻으려면 20 메시지 하나를 호출 하 고 다음 각 메시지를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-175">The following code example uses `GetMessages` to get 20 messages in one call and then processes each message.</span></span> <span data-ttu-id="0383e-176">또한 각 메시지에 대해 5 분 내에 표시 하지 않는 제한 시간을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-176">It also sets the invisibility timeout to five minutes for each message.</span></span> <span data-ttu-id="0383e-177">5 분부터 모든 메시지에 대해 동시에는 호출 후 5 분 경과 `GetMessages`, 삭제 되지 않은 모든 메시지가 다시 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-177">Note that the 5 minutes starts for all messages at the same time, so after 5 minutes have passed since the call to `GetMessages`, any messages which have not been deleted will become visible again.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a><span data-ttu-id="0383e-178">큐 길이 가져오기</span><span class="sxs-lookup"><span data-stu-id="0383e-178">Get the queue length</span></span>

<span data-ttu-id="0383e-179">큐의 메시지 수의 추정치를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-179">You can get an estimate of the number of messages in a queue.</span></span> <span data-ttu-id="0383e-180">`FetchAttributes` 메서드는 메시지 수를 포함 하 여 큐 특성을 검색 하도록 큐 서비스에 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="0383e-180">The `FetchAttributes` method asks the Queue service to retrieve the queue attributes, including the message count.</span></span> <span data-ttu-id="0383e-181">합니다 `ApproximateMessageCount` 속성에서 검색 된 마지막 값을 반환 합니다 `FetchAttributes` , 큐 서비스를 호출 하지 않고 메서드.</span><span class="sxs-lookup"><span data-stu-id="0383e-181">The `ApproximateMessageCount` property returns the last value retrieved by the `FetchAttributes` method, without calling the Queue service.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a><span data-ttu-id="0383e-182">큐 삭제</span><span class="sxs-lookup"><span data-stu-id="0383e-182">Delete a queue</span></span>

<span data-ttu-id="0383e-183">큐 및 그 안에 포함 된 모든 메시지를 삭제 하려면 호출을 `Delete` 큐 개체의 메서드.</span><span class="sxs-lookup"><span data-stu-id="0383e-183">To delete a queue and all the messages contained in it, call the `Delete` method on the queue object.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a><span data-ttu-id="0383e-184">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0383e-184">Next steps</span></span>

<span data-ttu-id="0383e-185">이제 큐 저장소의 기본 사항을 배웠으므로 다음 링크를 더 복잡 한 저장소 작업에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="0383e-185">Now that you've learned the basics of Queue storage, follow these links to learn about more complex storage tasks.</span></span>

- [<span data-ttu-id="0383e-186">.NET 용 azure Storage Api</span><span class="sxs-lookup"><span data-stu-id="0383e-186">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="0383e-187">Azure Storage 형식 공급자</span><span class="sxs-lookup"><span data-stu-id="0383e-187">Azure Storage Type Provider</span></span>](https://github.com/fsprojects/AzureStorageTypeProvider)
- [<span data-ttu-id="0383e-188">Azure Storage 팀 블로그</span><span class="sxs-lookup"><span data-stu-id="0383e-188">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="0383e-189">Azure Storage 연결 문자열 구성</span><span class="sxs-lookup"><span data-stu-id="0383e-189">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="0383e-190">Azure Storage 서비스 REST API 참조</span><span class="sxs-lookup"><span data-stu-id="0383e-190">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
