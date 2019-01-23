---
title: '방법: SSL을 사용 하 여 IIS에서 호스팅되는 WCF 서비스를 구성 합니다.'
ms.date: 03/30/2017
ms.assetid: df2fe31f-a4bb-4024-92ca-b74ba055e038
ms.openlocfilehash: ca7343f14215d89b29636776437f5e4a6a8089a1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54639980"
---
# <a name="how-to-configure-an-iis-hosted-wcf-service-with-ssl"></a><span data-ttu-id="20c0e-102">방법: SSL을 사용 하 여 IIS에서 호스팅되는 WCF 서비스를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="20c0e-102">How to: Configure an IIS-hosted WCF service with SSL</span></span>
<span data-ttu-id="20c0e-103">이 항목에서는 HTTP 전송 보안을 사용하도록 IIS에서 호스트되는 WCF 서비스를 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="20c0e-103">This topic describes how to set up an IIS-hosted WCF service to use HTTP transport security.</span></span> <span data-ttu-id="20c0e-104">HTTP 전송 보안에는 IIS에 등록할 SSL 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="20c0e-104">HTTP transport security requires an SSL certificate to be registered with IIS.</span></span> <span data-ttu-id="20c0e-105">SSL 인증서가 없는 경우에는 IIS를 사용하여 테스트 인증서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20c0e-105">If you do not have an SSL certificate you can use IIS to generate a test certificate.</span></span> <span data-ttu-id="20c0e-106">그런 다음 SSL 바인딩을 웹 사이트에 추가하고 웹 사이트의 인증 속성을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20c0e-106">Next you must add an SSL binding to the web site and configure the web site’s authentication properties.</span></span> <span data-ttu-id="20c0e-107">마지막으로, HTTPS를 사용하도록 WCF 서비스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20c0e-107">Finally you need to configure the WCF service to use HTTPS.</span></span>  
  
### <a name="creating-a-self-signed-certificate"></a><span data-ttu-id="20c0e-108">자체 서명된 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="20c0e-108">Creating a Self-Signed Certificate</span></span>  
  
1.  <span data-ttu-id="20c0e-109">인터넷 정보 서비스 관리자(inetmgr.exe)를 열고 왼쪽 트리 뷰에서 컴퓨터 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20c0e-109">Open Internet Information Services Manager (inetmgr.exe), and select your computer name in the left-hand tree view.</span></span> <span data-ttu-id="20c0e-110">화면 오른쪽에서 서버 인증서를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20c0e-110">On the right-hand side of the screen select Server Certificates</span></span>  
  
     <span data-ttu-id="20c0e-111">![IIS Manager 홈 화면](../../../../docs/framework/wcf/feature-details/media/mg-inetmgrhome.jpg "mg_INetMgrHome")</span><span class="sxs-lookup"><span data-stu-id="20c0e-111">![IIS Manager Home Screen](../../../../docs/framework/wcf/feature-details/media/mg-inetmgrhome.jpg "mg_INetMgrHome")</span></span>  
  
2.  <span data-ttu-id="20c0e-112">서버 인증서 창에서 클릭 된 **자체 서명 된 인증서 만들기...**</span><span class="sxs-lookup"><span data-stu-id="20c0e-112">In the Server Certificates window click the **Create Self-Signed Certificate….**</span></span> <span data-ttu-id="20c0e-113">링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20c0e-113">Link.</span></span>  
  
     <span data-ttu-id="20c0e-114">![자체를 만드는&#45;IIS 사용 하 여 인증서 서명](../../../../docs/framework/wcf/feature-details/media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")</span><span class="sxs-lookup"><span data-stu-id="20c0e-114">![Creating a self&#45;signed certificate with IIS](../../../../docs/framework/wcf/feature-details/media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")</span></span>  
  
3.  <span data-ttu-id="20c0e-115">자체 서명 된 인증서에 대 한 친숙 한 이름을 입력 하 고 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="20c0e-115">Enter a friendly name for the self-signed certificate and click **OK**.</span></span>  
  
     <span data-ttu-id="20c0e-116">![자체를 만들려면&#45;서명 인증서 대화 상자](../../../../docs/framework/wcf/feature-details/media/mg-mycert.jpg "mg_MyCert")</span><span class="sxs-lookup"><span data-stu-id="20c0e-116">![Create Self&#45;Signed Certificate Dialog](../../../../docs/framework/wcf/feature-details/media/mg-mycert.jpg "mg_MyCert")</span></span>  
  
     <span data-ttu-id="20c0e-117">이제 새로 만든된 자체 서명 된 인증서 세부 정보에 표시 됩니다는 **서버 인증서** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="20c0e-117">The newly created self-signed certificate details are now shown in the **Server Certificates** window.</span></span>  
  
     <span data-ttu-id="20c0e-118">![서버 인증서 창](../../../../docs/framework/wcf/feature-details/media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")</span><span class="sxs-lookup"><span data-stu-id="20c0e-118">![Server Certificate Window](../../../../docs/framework/wcf/feature-details/media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")</span></span>  
  
     <span data-ttu-id="20c0e-119">생성된 인증서는 신뢰할 수 있는 루트 인증 기관 저장소에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="20c0e-119">The generated certificate is installed in the Trusted Root Certification Authorities store.</span></span>  
  
### <a name="add-ssl-binding"></a><span data-ttu-id="20c0e-120">SSL 바인딩 추가</span><span class="sxs-lookup"><span data-stu-id="20c0e-120">Add SSL Binding</span></span>  
  
1.  <span data-ttu-id="20c0e-121">인터넷 정보 서비스 관리자에서 확장 합니다 **사이트** 폴더 차례로 합니다 **기본 웹 사이트** 화면의 왼쪽의 트리 보기에서 폴더.</span><span class="sxs-lookup"><span data-stu-id="20c0e-121">Still in Internet Information Services Manager, expand the **Sites** folder and then the **Default Web Site** folder in the tree view on the left-hand side of the screen.</span></span>  
  
2.  <span data-ttu-id="20c0e-122">클릭 된 **바인딩...**</span><span class="sxs-lookup"><span data-stu-id="20c0e-122">Click the **Bindings….**</span></span> <span data-ttu-id="20c0e-123">링크는 **작업** 창의 오른쪽 위 부분에 대 한 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="20c0e-123">Link in the **Actions** section in the upper right hand portion of the window.</span></span>  
  
     <span data-ttu-id="20c0e-124">![SSL 바인딩 추가](../../../../docs/framework/wcf/feature-details/media/mg-addsslbinding.jpg "mg_AddSSLBinding")</span><span class="sxs-lookup"><span data-stu-id="20c0e-124">![Adding an SSL binding](../../../../docs/framework/wcf/feature-details/media/mg-addsslbinding.jpg "mg_AddSSLBinding")</span></span>  
  
3.  <span data-ttu-id="20c0e-125">사이트 바인딩 창에서 클릭 합니다 **추가** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="20c0e-125">In the Site Bindings window click the **Add** button.</span></span>  
  
     <span data-ttu-id="20c0e-126">![사이트 바인딩 대화 상자](../../../../docs/framework/wcf/feature-details/media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")</span><span class="sxs-lookup"><span data-stu-id="20c0e-126">![Site Bindings Dialog](../../../../docs/framework/wcf/feature-details/media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")</span></span>  
  
4.  <span data-ttu-id="20c0e-127">에 **사이트 바인딩 추가** 대화 상자에서 방금 자체 서명 된 인증서의 친숙 한 이름과 형식에 대 한 https를 선택 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="20c0e-127">In the **Add Site Binding** dialog, select https for the type and the friendly name of the self-signed certificate you just created.</span></span>  
  
     <span data-ttu-id="20c0e-128">![사이트 바인딩 예제](../../../../docs/framework/wcf/feature-details/media/mg-mycertbinding.jpg "mg_MyCertBinding")</span><span class="sxs-lookup"><span data-stu-id="20c0e-128">![Site binding example](../../../../docs/framework/wcf/feature-details/media/mg-mycertbinding.jpg "mg_MyCertBinding")</span></span>  
  
### <a name="configure-virtual-directory-for-ssl"></a><span data-ttu-id="20c0e-129">SSL용 가상 디렉터리 구성</span><span class="sxs-lookup"><span data-stu-id="20c0e-129">Configure Virtual Directory for SSL</span></span>  
  
1.  <span data-ttu-id="20c0e-130">인터넷 정보 서비스 관리자에서 WCF 보안 서비스를 포함하는 가상 디렉터리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20c0e-130">Still in Internet Information Services Manager, select the virtual directory that contains your WCF secure service.</span></span>  
  
2.  <span data-ttu-id="20c0e-131">창의 가운데 창에서 선택 **SSL 설정** IIS 섹션에서.</span><span class="sxs-lookup"><span data-stu-id="20c0e-131">In the center pane of the window, select **SSL Settings** in the IIS section.</span></span>  
  
     <span data-ttu-id="20c0e-132">![가상 디렉터리에 대 한 SSL 설정을](../../../../docs/framework/wcf/feature-details/media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")</span><span class="sxs-lookup"><span data-stu-id="20c0e-132">![SSL Settings for virtual directory](../../../../docs/framework/wcf/feature-details/media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")</span></span>  
  
3.  <span data-ttu-id="20c0e-133">SSL 설정 창에서 선택는 **SSL 필요** 확인란을 클릭 합니다 **적용** 링크를 **작업** 화면 오른쪽의 섹션.</span><span class="sxs-lookup"><span data-stu-id="20c0e-133">In the SSL Settings pane, select the **Require SSL** checkbox and click the **Apply** link in the **Actions** section on the right hand side of the screen.</span></span>  
  
     <span data-ttu-id="20c0e-134">![가상 디렉터리 SSL 설정](../../../../docs/framework/wcf/feature-details/media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")</span><span class="sxs-lookup"><span data-stu-id="20c0e-134">![Virtual directory SSL settings](../../../../docs/framework/wcf/feature-details/media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")</span></span>  
  
### <a name="configure-wcf-service-for-http-transport-security"></a><span data-ttu-id="20c0e-135">HTTP 전송 보안을 위한 WCF 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="20c0e-135">Configure WCF Service for HTTP Transport Security</span></span>  
  
1.  <span data-ttu-id="20c0e-136">WCF 서비스의 web.config에서 다음 XML에 표시된 것처럼 전송 보안을 사용하도록 HTTP 바인딩을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="20c0e-136">In the WCF service’s web.config configure the HTTP binding to use transport security as shown in the following XML.</span></span>  
  
    ```xml  
    <bindings>  
          <basicHttpBinding>  
            <binding name="secureHttpBinding">  
              <security mode="Transport">  
                <transport clientCredentialType="None"/>  
              </security>  
            </binding>  
          </basicHttpBinding>  
    </bindings>  
    ```  
  
2.  <span data-ttu-id="20c0e-137">다음 XML에 표시된 것처럼 서비스 및 서비스 엔드포인트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="20c0e-137">Specify your service and service endpoint as shown in the following XML.</span></span>  
  
    ```xml  
    <services>  
          <service name="MySecureWCFService.Service1">  
            <endpoint address=""  
                      binding="basicHttpBinding"  
                      bindingConfiguration="secureHttpBinding"  
                      contract="MySecureWCFService.IService1"/>  
  
            <endpoint address="mex"  
                      binding="mexHttpsBinding"  
                      contract="IMetadataExchange" />  
          </service>  
    </services>  
    ```  
  
## <a name="example"></a><span data-ttu-id="20c0e-138">예제</span><span class="sxs-lookup"><span data-stu-id="20c0e-138">Example</span></span>  
 <span data-ttu-id="20c0e-139">다음은 HTTP 전송 보안을 사용하는 WCF 서비스에 대한 web.config 파일의 전체 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="20c0e-139">The following is a complete example of a web.config file for a WCF service using HTTP transport security</span></span>  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
  
  <system.web>  
    <compilation debug="true" targetFramework="4.0" />  
  </system.web>  
  <system.serviceModel>  
    <services>  
      <service name="MySecureWCFService.Service1">  
        <endpoint address=""  
                  binding="basicHttpBinding"  
                  bindingConfiguration="secureHttpBinding"  
                  contract="MySecureWCFService.IService1"/>  
  
        <endpoint address="mex"  
                  binding="mexHttpsBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="secureHttpBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="None"/>  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <!-- To avoid disclosing metadata information, set the value below to false and remove the metadata endpoint above before deployment -->  
          <serviceMetadata httpsGetEnabled="true"/>  
          <!-- To receive exception details in faults for debugging purposes, set the value below to true.  Set to false before deployment to avoid disclosing exception information -->  
          <serviceDebug includeExceptionDetailInFaults="false"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <serviceHostingEnvironment multipleSiteBindingsEnabled="true" />  
  </system.serviceModel>  
  <system.webServer>  
    <modules runAllManagedModulesForAllRequests="true"/>  
  </system.webServer>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="20c0e-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="20c0e-140">See also</span></span>
- [<span data-ttu-id="20c0e-141">인터넷 정보 서비스에서 호스팅</span><span class="sxs-lookup"><span data-stu-id="20c0e-141">Hosting in Internet Information Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)
- [<span data-ttu-id="20c0e-142">인터넷 정보 서비스 호스팅 지침</span><span class="sxs-lookup"><span data-stu-id="20c0e-142">Internet Information Service Hosting Instructions</span></span>](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)
- [<span data-ttu-id="20c0e-143">인터넷 정보 서비스 호스팅을 위한 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="20c0e-143">Internet Information Services Hosting Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)
- [<span data-ttu-id="20c0e-144">인라인 코드를 사용한 IIS 호스팅</span><span class="sxs-lookup"><span data-stu-id="20c0e-144">IIS Hosting Using Inline Code</span></span>](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md)
