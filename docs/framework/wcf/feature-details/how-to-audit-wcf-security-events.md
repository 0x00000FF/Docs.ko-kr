---
title: '방법: Windows Communication Foundation 보안 이벤트 감사'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], auditing events
ms.assetid: e71e9587-3336-46a2-9a9e-d72a1743ecec
author: BrucePerlerMS
ms.openlocfilehash: 1efd651751e0f81b5125b64f81f7d2087d002d8d
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170628"
---
# <a name="how-to-audit-windows-communication-foundation-security-events"></a><span data-ttu-id="bf63a-102">방법: Windows Communication Foundation 보안 이벤트 감사</span><span class="sxs-lookup"><span data-stu-id="bf63a-102">How to: Audit Windows Communication Foundation Security Events</span></span>
<span data-ttu-id="bf63a-103">Windows Communication Foundation (WCF)를 사용 하면 Windows 이벤트 뷰어를 사용 하 여 볼 수 있는 Windows 이벤트 로그에 보안 이벤트를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-103">Windows Communication Foundation (WCF) allows you to log security events to the Windows event log, which can be viewed using the Windows Event Viewer.</span></span> <span data-ttu-id="bf63a-104">이 항목에서는 보안 이벤트를 기록하도록 응용 프로그램을 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-104">This topic explains how to set up an application so that it logs security events.</span></span> <span data-ttu-id="bf63a-105">WCF 감사 하는 방법에 대 한 자세한 내용은 참조 하세요. [감사](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-105">For more information about WCF auditing, see [Auditing](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).</span></span>  
  
### <a name="to-audit-security-events-in-code"></a><span data-ttu-id="bf63a-106">코드에서 보안 이벤트를 감사하려면</span><span class="sxs-lookup"><span data-stu-id="bf63a-106">To audit security events in code</span></span>  
  
1.  <span data-ttu-id="bf63a-107">감사 로그 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-107">Specify the audit log location.</span></span> <span data-ttu-id="bf63a-108">이렇게 하려면 다음 코드와 같이 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A> 클래스의 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> 속성을 <xref:System.ServiceModel.AuditLogLocation> 열거형 값 중 하나로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-108">To do this, set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A> property of the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> class to one of the <xref:System.ServiceModel.AuditLogLocation> enumeration values, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#2)]
     [!code-vb[AuditingSecurityEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#2)]  
  
     <span data-ttu-id="bf63a-109">합니다 <xref:System.ServiceModel.AuditLogLocation> 열거의 세 가지 값: `Application`를 `Security`, 또는 `Default`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-109">The <xref:System.ServiceModel.AuditLogLocation> enumeration has three values: `Application`, `Security`, or `Default`.</span></span> <span data-ttu-id="bf63a-110">이 값은 이벤트 뷰어에서 볼 수 있는 로그(보안 로그 또는 응용 프로그램 로그) 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-110">The value specifies one of the logs visible in the Event Viewer, either the Security log or the Application log.</span></span> <span data-ttu-id="bf63a-111">`Default` 값을 사용하는 경우 실제 로그는 응용 프로그램을 실행하는 운영 체제에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-111">If you use the `Default` value, the actual log will depend on the operating system the application is running on.</span></span> <span data-ttu-id="bf63a-112">감사를 사용하지만 로그 위치가 지정되지 않은 경우 기본값은 보안 로그에 쓰기를 지원하는 플랫폼의 `Security` 로그입니다. 그렇지 않으면 `Application` 로그에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-112">If auditing is enabled and the log location is not specified, the default is the `Security` log for platforms that support writing to the Security log; otherwise, it will write to the `Application` log.</span></span> <span data-ttu-id="bf63a-113">기본적으로 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 및 [!INCLUDE[wv](../../../../includes/wv-md.md)]만 보안 로그에 쓰기를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-113">Only [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] and [!INCLUDE[wv](../../../../includes/wv-md.md)] support writing to the Security log by default.</span></span>  
  
2.  <span data-ttu-id="bf63a-114">감사할 이벤트 형식을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-114">Set up the types of events to audit.</span></span> <span data-ttu-id="bf63a-115">서비스 수준 이벤트나 메시지 수준 권한 부여 이벤트를 동시에 감사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-115">You can simultaneously audit service-level events or message-level authorization events.</span></span> <span data-ttu-id="bf63a-116">이렇게 하려면 다음 코드와 같이 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A> 속성이나 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A> 속성을 <xref:System.ServiceModel.AuditLevel> 열거형 값 중 하나로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-116">To do this, set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A> property or the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A> property to one of the <xref:System.ServiceModel.AuditLevel> enumeration values, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#3)]
     [!code-vb[AuditingSecurityEvents#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#3)]  
  
3.  <span data-ttu-id="bf63a-117">로그 감사 이벤트에 대해 오류를 응용 프로그램에 노출할지 또는 표시하지 않을지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-117">Specify whether to suppress or expose failures to the application regarding log audit events.</span></span> <span data-ttu-id="bf63a-118">다음 코드와 같이 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> 속성을 `true` 또는 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-118">Set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> property to either `true` or `false`, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#4)]
     [!code-vb[AuditingSecurityEvents#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#4)]  
  
     <span data-ttu-id="bf63a-119">기본 `SuppressAuditFailure` 속성이 `true`이므로 감사하지 못해도 응용 프로그램에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-119">The default `SuppressAuditFailure` property is `true`, so that the failure to audit does not affect the application.</span></span> <span data-ttu-id="bf63a-120">그렇지 않으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-120">Otherwise, an exception is thrown.</span></span> <span data-ttu-id="bf63a-121">성공한 모든 감사에 대해 자세한 추적이 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-121">For any successful audit, a verbose trace is written.</span></span> <span data-ttu-id="bf63a-122">감사하지 못하면 오류 수준에서 추적이 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-122">For any failure to audit, the trace is written at the Error level.</span></span>  
  
4.  <span data-ttu-id="bf63a-123"><xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>의 설명에 있는 동작 컬렉션에서 기존 <xref:System.ServiceModel.ServiceHost>를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-123">Delete the existing <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> from the collection of behaviors found in the description of a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="bf63a-124">동작 컬렉션은 <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> 컬렉션에서 액세스되는 <xref:System.ServiceModel.ServiceHostBase.Description%2A> 속성으로 액세스됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-124">The behavior collection is accessed by the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> property, which in turn is accessed from the <xref:System.ServiceModel.ServiceHostBase.Description%2A> property.</span></span> <span data-ttu-id="bf63a-125">다음 코드와 같이 동일한 컬렉션에 새 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-125">Then add the new <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to the same collection, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#5)]
     [!code-vb[AuditingSecurityEvents#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#5)]  
  
### <a name="to-set-up-auditing-in-configuration"></a><span data-ttu-id="bf63a-126">구성에서 감사를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="bf63a-126">To set up auditing in configuration</span></span>  
  
1.  <span data-ttu-id="bf63a-127">구성에서 감사를 설정 하려면 추가 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 요소를 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) web.config 파일의 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-127">To set up auditing in configuration, add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) section of the web.config file.</span></span> <span data-ttu-id="bf63a-128">다음 추가 [ \<serviceSecurityAudit >](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) 요소 및 다양 한 특성을 다음 예제에서와 같이 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-128">Then add a [\<serviceSecurityAudit>](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) element and set the various attributes, as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
       <behavior name="myAuditBehavior">  
          <serviceSecurityAudit auditLogLocation="Application"  
                suppressAuditFailure="false"   
                serviceAuthorizationAuditLevel="None"   
                messageAuthenticationAuditLevel="SuccessOrFailure" />  
          </behavior>  
    </behaviors>  
    ```  
  
2.  <span data-ttu-id="bf63a-129">다음 예제와 같이 서비스의 동작을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-129">You must specify the behavior for the service, as shown in the following example.</span></span>  
  
    ```xml  
    <services>  
        <service type="WCS.Samples.Service.Echo"   
        behaviorConfiguration=" myAuditBehavior">  
           <endpoint address=""  
                    binding="wsHttpBinding"  
                    bindingConfiguration="CertificateDefault"   
                    contract="WCS.Samples.Service.IEcho" />  
        </service>  
    </services>  
    ```  
  
## <a name="example"></a><span data-ttu-id="bf63a-130">예제</span><span class="sxs-lookup"><span data-stu-id="bf63a-130">Example</span></span>  
 <span data-ttu-id="bf63a-131">다음 코드에서는 <xref:System.ServiceModel.ServiceHost> 클래스의 인스턴스를 만들고 동작 컬렉션에 새 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-131">The following code creates an instance of the <xref:System.ServiceModel.ServiceHost> class and adds a new <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to its collection of behaviors.</span></span>  
  
 [!code-csharp[AuditingSecurityEvents#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#1)]
 [!code-vb[AuditingSecurityEvents#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#1)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="bf63a-132">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="bf63a-132">.NET Framework Security</span></span>  
 <span data-ttu-id="bf63a-133"><xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> 속성을 `true`로 설정하면 보안 감사 생성 오류가 표시되지 않습니다. `false`로 설정하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-133">Setting the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> property to `true`, suppresses any failure to generate security audits (if set to `false`, an exception is thrown).</span></span> <span data-ttu-id="bf63a-134">그러나 다음 Windows를 사용 하도록 설정 하면 **로컬 보안 설정** 속성 감사 이벤트를 생성 하지 못함 즉시 종료 하려면 Windows 하면:</span><span class="sxs-lookup"><span data-stu-id="bf63a-134">However, if you enable the following Windows **Local Security Setting** property, a failure to generate audit events will cause Windows to shut down immediately:</span></span>  
  
 <span data-ttu-id="bf63a-135">**감사: 보안 감사를 로그할 수 없는 경우 즉시 시스템 종료**</span><span class="sxs-lookup"><span data-stu-id="bf63a-135">**Audit: Shut down system immediately if unable to log security audits**</span></span>  
  
 <span data-ttu-id="bf63a-136">속성을 설정 하려면 엽니다는 **로컬 보안 설정** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="bf63a-136">To set the property, open the **Local Security Settings** dialog box.</span></span> <span data-ttu-id="bf63a-137">아래 **보안 설정**, 클릭 **로컬 정책**합니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-137">Under **Security Settings**, click **Local Policies**.</span></span> <span data-ttu-id="bf63a-138">누른 **보안 옵션**합니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-138">Then click **Security Options**.</span></span>  
  
 <span data-ttu-id="bf63a-139">경우는 <xref:System.ServiceModel.AuditLogLocation> 속성이 <xref:System.ServiceModel.AuditLogLocation.Security> 및 **개체 액세스 감사** 설정 하지 않으면 합니다 **로컬 보안 정책**, 감사 이벤트가 보안 로그에 기록 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-139">If the <xref:System.ServiceModel.AuditLogLocation> property is set to <xref:System.ServiceModel.AuditLogLocation.Security> and **Audit Object Access** is not set in the **Local Security Policy**, audit events will not be written to the Security log.</span></span> <span data-ttu-id="bf63a-140">오류가 반환되지는 않지만 감사 항목이 보안 로그에 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf63a-140">Note that no failure is returned, but audit entries are not written to the Security log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf63a-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bf63a-141">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A>  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>  
 <xref:System.ServiceModel.AuditLogLocation>  
 [<span data-ttu-id="bf63a-142">감사</span><span class="sxs-lookup"><span data-stu-id="bf63a-142">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)
