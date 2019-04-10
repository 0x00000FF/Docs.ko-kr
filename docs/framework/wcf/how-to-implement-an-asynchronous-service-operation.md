---
title: '방법: 비동기 서비스 작업 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e5d2ea5-d8f8-4712-bd18-ea3c5461702c
ms.openlocfilehash: ec1c6549c4a386f529ca2191e1876975b2bf5dcd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186851"
---
# <a name="how-to-implement-an-asynchronous-service-operation"></a><span data-ttu-id="4b57d-102">방법: 비동기 서비스 작업 구현</span><span class="sxs-lookup"><span data-stu-id="4b57d-102">How to: Implement an Asynchronous Service Operation</span></span>
<span data-ttu-id="4b57d-103">Windows Communication Foundation (WCF) 응용 프로그램에서 서비스 작업이 호출 하는 방법을 클라이언트에 지시 하지 않고 동기적으로 열렸는지 또는 비동기적을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b57d-103">In Windows Communication Foundation (WCF) applications, a service operation can be implemented asynchronously or synchronously without dictating to the client how to call it.</span></span> <span data-ttu-id="4b57d-104">예를 들어 비동기 서비스 작업을 동기적으로 호출할 수 있습니다 및 동기 서비스 작업을 비동기적으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b57d-104">For example, asynchronous service operations can be called synchronously, and synchronous service operations can be called asynchronously.</span></span> <span data-ttu-id="4b57d-105">클라이언트 응용 프로그램에서 작업을 비동기적으로 호출 하는 방법을 보여 주는 예제를 참조 하세요. [방법: 서비스 작업을 비동기적으로 호출](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4b57d-105">For an example that shows how to call an operation asynchronously in a client application, see [How to: Call Service Operations Asynchronously](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span></span> <span data-ttu-id="4b57d-106">동기 및 비동기 작업에 대 한 자세한 내용은 참조 하세요. [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md) 하 고 [동기 및 비동기 작업](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4b57d-106">For more information about synchronous and asynchronous operations, see [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md) and [Synchronous and Asynchronous Operations](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span></span> <span data-ttu-id="4b57d-107">이 항목에서는 비동기 서비스 작업의 기본 구조에 대해 설명하지만 코드가 완성되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="4b57d-107">This topic describes the basic structure of an asynchronous service operation, the code is not complete.</span></span> <span data-ttu-id="4b57d-108">서비스 및 클라이언트 측의 전체 예제를 참조 하세요 [비동기](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms751505(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="4b57d-108">For a complete example of both the service and client sides, see [Asynchronous](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms751505(v=vs.100)).</span></span>  
  
### <a name="implement-a-service-operation-asynchronously"></a><span data-ttu-id="4b57d-109">비동기 서비스 작업 구현</span><span class="sxs-lookup"><span data-stu-id="4b57d-109">Implement a service operation asynchronously</span></span>  
  
1.  <span data-ttu-id="4b57d-110">서비스 계약에서 .NET 비동기 디자인 지침에 따라 비동기 메서드 쌍을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="4b57d-110">In your service contract, declare an asynchronous method pair according to the .NET asynchronous design guidelines.</span></span> <span data-ttu-id="4b57d-111">`Begin` 메서드는 매개 변수, 콜백 개체 및 상태 개체를 가져와서 <xref:System.IAsyncResult?displayProperty=nameWithType> 및 `End`를 가져오는 일치하는 <xref:System.IAsyncResult?displayProperty=nameWithType> 메서드를 반환한 다음 반환 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4b57d-111">The `Begin` method takes a parameter, a callback object, and a state object, and returns a <xref:System.IAsyncResult?displayProperty=nameWithType> and a matching `End` method that takes a <xref:System.IAsyncResult?displayProperty=nameWithType> and returns the return value.</span></span> <span data-ttu-id="4b57d-112">비동기 호출에 대 한 자세한 내용은 참조 하세요. [비동기 프로그래밍 디자인 패턴](https://go.microsoft.com/fwlink/?LinkId=248221)합니다.</span><span class="sxs-lookup"><span data-stu-id="4b57d-112">For more information about asynchronous calls, see [Asynchronous Programming Design Patterns](https://go.microsoft.com/fwlink/?LinkId=248221).</span></span>  
  
2.  <span data-ttu-id="4b57d-113">`Begin` 특성을 가진 비동기 메서드 쌍의 <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType> 메서드를 표시하고 <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=nameWithType> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4b57d-113">Mark the `Begin` method of the asynchronous method pair with the <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType> attribute and set the <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="4b57d-114">예를 들어 다음 코드에서는 단계 1 및 2를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4b57d-114">For example, the following code performs steps 1 and 2.</span></span>  
  
     [!code-csharp[C_SyncAsyncClient#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#6)]
     [!code-vb[C_SyncAsyncClient#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#6)]  
  
3.  <span data-ttu-id="4b57d-115">비동기 디자인 지침에 따라 서비스 클래스에서 `Begin/End` 메서드 쌍을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="4b57d-115">Implement the `Begin/End` method pair in your service class according to the asynchronous design guidelines.</span></span> <span data-ttu-id="4b57d-116">예를 들어 다음 코드 예제에서는 비동기 서비스 작업의 `Begin` 및 `End` 부분 모두의 콘솔에 기록된 문자열의 구현 및 `End` 작업의 반환 값이 클라이언트에 반환되는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b57d-116">For example, the following code example shows an implementation in which a string is written to the console in both the `Begin` and `End` portions of the asynchronous service operation, and the return value of the `End` operation is returned to the client.</span></span> <span data-ttu-id="4b57d-117">전체 코드 예제를 보려면 예제 단원을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4b57d-117">For the complete code example, see the Example section.</span></span>  
  
     [!code-csharp[C_SyncAsyncClient#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#3)]
     [!code-vb[C_SyncAsyncClient#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="4b57d-118">예제</span><span class="sxs-lookup"><span data-stu-id="4b57d-118">Example</span></span>  
 <span data-ttu-id="4b57d-119">다음 코드 예제에서는 다음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b57d-119">The following code examples show:</span></span>  
  
1.  <span data-ttu-id="4b57d-120">다음을 포함한 서비스 계약 인터페이스:</span><span class="sxs-lookup"><span data-stu-id="4b57d-120">A service contract interface with:</span></span>  
  
    1.  <span data-ttu-id="4b57d-121">동기 `SampleMethod` 작업.</span><span class="sxs-lookup"><span data-stu-id="4b57d-121">A synchronous `SampleMethod` operation.</span></span>  
  
    2.  <span data-ttu-id="4b57d-122">비동기 `BeginSampleMethod` 작업.</span><span class="sxs-lookup"><span data-stu-id="4b57d-122">An asynchronous `BeginSampleMethod` operation.</span></span>  
  
    3.  <span data-ttu-id="4b57d-123">비동기 `BeginServiceAsyncMethod` / `EndServiceAsyncMethod` 작업 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="4b57d-123">An asynchronous `BeginServiceAsyncMethod`/`EndServiceAsyncMethod` operation pair.</span></span>  
  
2.  <span data-ttu-id="4b57d-124"><xref:System.IAsyncResult?displayProperty=nameWithType> 개체를 사용하여 서비스 구현.</span><span class="sxs-lookup"><span data-stu-id="4b57d-124">A service implementation using a <xref:System.IAsyncResult?displayProperty=nameWithType> object.</span></span>  
  
 [!code-csharp[C_SyncAsyncClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#1)]
 [!code-vb[C_SyncAsyncClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4b57d-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="4b57d-125">See also</span></span>

- [<span data-ttu-id="4b57d-126">서비스 계약 디자인</span><span class="sxs-lookup"><span data-stu-id="4b57d-126">Designing Service Contracts</span></span>](../../../docs/framework/wcf/designing-service-contracts.md)
- [<span data-ttu-id="4b57d-127">동기 및 비동기 작업</span><span class="sxs-lookup"><span data-stu-id="4b57d-127">Synchronous and Asynchronous Operations</span></span>](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)
