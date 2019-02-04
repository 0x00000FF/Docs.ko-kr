---
title: WCF 구성 스키마
ms.date: 03/30/2017
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
ms.openlocfilehash: ae9e660ee5c4163487e953077df8782955f90ef5
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675363"
---
# <a name="wcf-configuration-schema"></a><span data-ttu-id="e2798-102">WCF 구성 스키마</span><span class="sxs-lookup"><span data-stu-id="e2798-102">WCF Configuration Schema</span></span>
<span data-ttu-id="e2798-103">Windows Communication Foundation (WCF) 구성 요소를 사용 하 여 WCF 서비스 및 클라이언트 응용 프로그램을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2798-103">Windows Communication Foundation (WCF) configuration elements enable you to configure WCF service and client applications.</span></span> <span data-ttu-id="e2798-104">[구성 편집기 도구(SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)를 사용하여 클라이언트 및 서비스에 대한 구성 파일을 만들고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2798-104">You can use the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) to create and modify configuration files for clients and services.</span></span> <span data-ttu-id="e2798-105">구성 파일은 XML 형식이므로 텍스트 편집기를 사용하여 구성 파일을 수동으로 편집하려면 XML에 익숙해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2798-105">Since the configuration files are formatted as XML, you must be familiar with XML if you want to manually edit them using a text editor.</span></span> <span data-ttu-id="e2798-106">그렇지 않으면 찾을 수 없는 XML 요소 태그나 특성과 같은 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2798-106">Otherwise, you may run into issues such as an unfound XML element tag or attribute.</span></span> <span data-ttu-id="e2798-107">XML 요소 태그 및 속성이 대소문자를 구분하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e2798-107">This is because XML element tags and attributes are case-sensitive.</span></span>  
  
 <span data-ttu-id="e2798-108">WCF 구성 시스템은 기반으로 합니다 <xref:System.Configuration> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e2798-108">The WCF configuration system is based on the <xref:System.Configuration> namespace.</span></span> <span data-ttu-id="e2798-109">따라서 응용 프로그램 및 구성의 보안을 향상시키기 위해 구성 잠금, 암호화 및 병합과 같은 <xref:System.Configuration> 네임스페이스에서 제공하는 표준 기능을 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2798-109">Therefore, you can use all the standard features provided by the <xref:System.Configuration> namespace, such as configuration locking, encryption and merging to increase the security of your application and its configuration.</span></span> <span data-ttu-id="e2798-110">이러한 개념에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2798-110">For more information on these concepts, see the following topics.</span></span>  
  
 [<span data-ttu-id="e2798-111">구성 정보 암호화</span><span class="sxs-lookup"><span data-stu-id="e2798-111">Encrypting Configuration Information</span></span>](https://go.microsoft.com/fwlink/?LinkId=95337)  
  
 [<span data-ttu-id="e2798-112">구성 설정 잠금</span><span class="sxs-lookup"><span data-stu-id="e2798-112">Locking Configuration Settings</span></span>](https://go.microsoft.com/fwlink/?LinkId=95338)  
  
 <span data-ttu-id="e2798-113">이 섹션에서는 각 구성 항목의 가능한 모든 값 및 이 값이 다른 WCF 구성 요소와 상호 작용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e2798-113">This section describes all possible values of each configuration item, and how it interacts with other WCF configuration elements.</span></span> <span data-ttu-id="e2798-114">다음 맵에서는 WCF 구성 스키마를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e2798-114">The following map illustrates the WCF configuration schema.</span></span>  
  
 <span data-ttu-id="e2798-115">![WCF 구성 스키마](../../../../../docs/framework/configure-apps/file-schema/wcf/media/orcasconfigschema.gif "OrcasConfigSchema")</span><span class="sxs-lookup"><span data-stu-id="e2798-115">![WCF Configuration Schema](../../../../../docs/framework/configure-apps/file-schema/wcf/media/orcasconfigschema.gif "OrcasConfigSchema")</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="e2798-116">응용 프로그램 구성 파일 (app.config) 사용 하 여 적절 한 나열 ACL (Access Control) 잠재적 보안 위협을 방지 하기 위해에서 WCF 구성 섹션을 보호 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2798-116">You should protect WCF configuration sections in your application configuration files (app.config) with appropriate Access Control Lists (ACL) to prevent any potential security threats.</span></span>  <span data-ttu-id="e2798-117">예를 들어, 적절한 사용자만이 응용 프로그램 바인딩의 보안 설정 또는 서비스에 대한 구성 파일의 서비스 모델 섹션에 액세스하거나 이를 수정할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2798-117">For example, you should make sure that only the appropriate people can access or modify the security settings on application bindings, or the service model section of the configuration file for a service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e2798-118">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="e2798-118">In This Section</span></span>  
 [<span data-ttu-id="e2798-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e2798-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
 <span data-ttu-id="e2798-120">`ServiceModel` 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e2798-120">Describes the `ServiceModel` element.</span></span>  
  
 [<span data-ttu-id="e2798-121">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="e2798-121">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)  
 <span data-ttu-id="e2798-122">SMSvcHost.exe 도구를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e2798-122">Configures the SMSvcHost.exe tool.</span></span>  
  
 [<span data-ttu-id="e2798-123">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="e2798-123">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
 <span data-ttu-id="e2798-124"><xref:System.Runtime.Serialization.DataContractSerializer>와 같은 serializer를 사용하는 경우 옵션 설정의 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e2798-124">The top-level element for setting options when using serializers such as the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e2798-125">관련 단원</span><span class="sxs-lookup"><span data-stu-id="e2798-125">Related Sections</span></span>  
 [<span data-ttu-id="e2798-126">Windows Communication Foundation 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="e2798-126">Configuring Windows Communication Foundation Applications</span></span>](../../../wcf/configuring-services.md)  
 <span data-ttu-id="e2798-127">WCF 서비스 및 클라이언트를 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2798-127">Describes how to configure WCF services and clients.</span></span>
