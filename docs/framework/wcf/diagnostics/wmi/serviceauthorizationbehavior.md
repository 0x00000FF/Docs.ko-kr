---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: c916d0820a1eae333384deab7b0619abfbdc8167
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2018
ms.locfileid: "49415382"
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="02ab7-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="02ab7-102">ServiceAuthorizationBehavior</span></span>
<span data-ttu-id="02ab7-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="02ab7-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02ab7-104">구문</span><span class="sxs-lookup"><span data-stu-id="02ab7-104">Syntax</span></span>  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="02ab7-105">메서드</span><span class="sxs-lookup"><span data-stu-id="02ab7-105">Methods</span></span>  
 <span data-ttu-id="02ab7-106">ServiceAuthorizationBehavior 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02ab7-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="02ab7-107">속성</span><span class="sxs-lookup"><span data-stu-id="02ab7-107">Properties</span></span>  
 <span data-ttu-id="02ab7-108">ServiceAuthorizationBehavior 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02ab7-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="02ab7-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="02ab7-109">ImpersonateCallerForAllOperations</span></span>  
 <span data-ttu-id="02ab7-110">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="02ab7-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="02ab7-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="02ab7-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="02ab7-112">들어오는 메시지가 제공하는 자격 증명을 사용하여 서비스가 가장을 시도하는지 여부를 제어하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="02ab7-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="02ab7-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="02ab7-113">PrincipalPermissionMode</span></span>  
 <span data-ttu-id="02ab7-114">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="02ab7-114">Data type: string</span></span>  
  
 <span data-ttu-id="02ab7-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="02ab7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="02ab7-116">서버에서 작업을 수행할 때 사용되는 주체입니다.</span><span class="sxs-lookup"><span data-stu-id="02ab7-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="02ab7-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="02ab7-117">RoleProvider</span></span>  
 <span data-ttu-id="02ab7-118">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="02ab7-118">Data type: string</span></span>  
  
 <span data-ttu-id="02ab7-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="02ab7-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="02ab7-120">ASP.NET 역할 공급자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="02ab7-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="02ab7-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="02ab7-121">ServiceAuthorizationManager</span></span>  
 <span data-ttu-id="02ab7-122">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="02ab7-122">Data type: string</span></span>  
  
 <span data-ttu-id="02ab7-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="02ab7-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="02ab7-124">사용자 지정 인증에 사용되는 권한 부여 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="02ab7-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02ab7-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02ab7-125">Requirements</span></span>  
  
|<span data-ttu-id="02ab7-126">MOF</span><span class="sxs-lookup"><span data-stu-id="02ab7-126">MOF</span></span>|<span data-ttu-id="02ab7-127">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02ab7-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="02ab7-128">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="02ab7-128">Namespace</span></span>|<span data-ttu-id="02ab7-129">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02ab7-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="02ab7-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02ab7-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
