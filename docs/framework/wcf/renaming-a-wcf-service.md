---
title: WCF 서비스 이름 바꾸기
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f2ab3d780f85131fc7adf24c5f420bd5fe643d9e
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2018
---
# <a name="renaming-a-wcf-service"></a><span data-ttu-id="2ffde-102">WCF 서비스 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="2ffde-102">Renaming a WCF Service</span></span>
<span data-ttu-id="2ffde-103">이 항목에서는 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 서비스 이름을 바꾸는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2ffde-103">This topic describes how you can rename a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service.</span></span>  
  
## <a name="renaming-a-wcf-service"></a><span data-ttu-id="2ffde-104">WCF 서비스 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="2ffde-104">Renaming a WCF Service</span></span>  
 <span data-ttu-id="2ffde-105">[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 템플릿에서 서비스 이름을 바꾸려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2ffde-105">Perform the following steps to rename a service in a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] template,</span></span>  
  
-   <span data-ttu-id="2ffde-106">서비스를 구현하는 클래스 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="2ffde-106">Change the name of the class that implements the service.</span></span>  
  
-   <span data-ttu-id="2ffde-107">다음 예제에 표시된 대로 서비스의 구성 파일에서 선택한 새 이름으로 서비스 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="2ffde-107">In the configuration file of the service, change the name of the service to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="2ffde-108">구성 파일은 호스팅 모델에 따라 app.config 또는 web.config 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="2ffde-108">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
-   <span data-ttu-id="2ffde-109">서비스가 WebHosted인 경우 \*.svc 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ffde-109">If your service is webhosted, it uses an \*.svc file.</span></span> <span data-ttu-id="2ffde-110">svc 파일을 열고 다음 예제에 표시된 대로 서비스 이름을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ffde-110">Open the svc file and modify the name of your service as indicated in the following example.</span></span> <span data-ttu-id="2ffde-111">svc 파일이 없는 경우 이 단계는 자체 호스팅 응용 프로그램에 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ffde-111">This step is not necessary for self-hosted applications, as there is no svc file.</span></span>  
  
```  
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a><span data-ttu-id="2ffde-112">WCF 서비스 계약 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="2ffde-112">Renaming a WCF Service Contract</span></span>  
  
-   <span data-ttu-id="2ffde-113">서비스 계약 이름을 바꾸려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2ffde-113">Perform the following steps to rename the service contract,</span></span>  
  
-   <span data-ttu-id="2ffde-114">서비스 계약 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="2ffde-114">Change the name of the service contract.</span></span>  
  
-   <span data-ttu-id="2ffde-115">다음 예제에 표시된 대로 서비스의 구성 파일에서 선택한 새 이름으로 서비스 계약 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="2ffde-115">In the configuration file of the service, change the name of the service contract to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="2ffde-116">구성 파일은 호스팅 모델에 따라 app.config 또는 web.config 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="2ffde-116">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
