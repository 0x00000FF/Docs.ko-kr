---
title: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
api_name: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
api_location: Microsoft.VisualStudio.Activities.dll
api_type: Assembly
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e8d9e9bfb0967b6c41a3df0015bdd6b4101e0c06
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a><span data-ttu-id="820d5-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span><span class="sxs-lookup"><span data-stu-id="820d5-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span></span>
<span data-ttu-id="820d5-103">인스턴스를 만듭니다는 [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="820d5-103">Creates an instance of the [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="820d5-104">구문</span><span class="sxs-lookup"><span data-stu-id="820d5-104">Syntax</span></span>  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="820d5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="820d5-105">Parameters</span></span>  
  
## <a name="parameter-values"></a><span data-ttu-id="820d5-106">매개 변수 값</span><span class="sxs-lookup"><span data-stu-id="820d5-106">Parameter Values</span></span>  
 <span data-ttu-id="820d5-107">*operationDescription*</span><span class="sxs-lookup"><span data-stu-id="820d5-107">*operationDescription*</span></span>  
  
 <span data-ttu-id="820d5-108">: 작업 이름, 반환 형식 및 매개 변수 정보를 비롯하여 생성되는 워크플로 활동에서 수행될 작업에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="820d5-108">Describes the operation to be performed in the workflow activity that is to be generated, including the operation name, return type, and parameter information.</span></span> <span data-ttu-id="820d5-109">이 매개 변수 값이 아니어야 **null**합니다.</span><span class="sxs-lookup"><span data-stu-id="820d5-109">The value of this parameter must not be **null**.</span></span> <span data-ttu-id="820d5-110">메시지 계약을 사용하고 한 메시지에 인수를 사용하는 동기 작업을 설명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="820d5-110">It should describe a synchronous operation which uses a message contract and takes an argument with one message.</span></span> <span data-ttu-id="820d5-111">이러한 조건이 충족되지 않으면 생성자 및 이 클래스의 기타 메서드를 사용한 런타임 결과는 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="820d5-111">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="820d5-112">*configurationName*</span><span class="sxs-lookup"><span data-stu-id="820d5-112">*configurationName*</span></span>  
  
 <span data-ttu-id="820d5-113">: 끝점 구성 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="820d5-113">Specifies the endpoint configuration name.</span></span> <span data-ttu-id="820d5-114">이 매개 변수 값 중 하나 여야 하지 합니다 **null** 이거나 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="820d5-114">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="820d5-115">이러한 조건이 충족되지 않으면 생성자 및 이 클래스의 기타 메서드를 사용한 런타임 결과는 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="820d5-115">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="820d5-116">*proxyNamespace*</span><span class="sxs-lookup"><span data-stu-id="820d5-116">*proxyNamespace*</span></span>  
  
 <span data-ttu-id="820d5-117">: 작업의 서비스 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="820d5-117">Specifies the service namespace for the operation.</span></span> <span data-ttu-id="820d5-118">이 매개 변수 값 중 하나 여야 하지 합니다 **null** 이거나 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="820d5-118">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="820d5-119">이러한 조건이 충족되지 않으면 생성자 및 이 클래스의 기타 메서드를 사용한 런타임 결과는 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="820d5-119">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="820d5-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="820d5-120">See Also</span></span>  
 [<span data-ttu-id="820d5-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span><span class="sxs-lookup"><span data-stu-id="820d5-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
