---
title: SendMail 사용자 지정 활동
ms.date: 03/30/2017
ms.assetid: 947a9ae6-379c-43a3-9cd5-87f573a5739f
ms.openlocfilehash: 3bbb16fd99d5d7de4183b26030c0afe65ebc90cd
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617309"
---
# <a name="sendmail-custom-activity"></a>SendMail 사용자 지정 활동
이 샘플에서는 워크플로 응용 프로그램 내에서 사용하기 위해 <xref:System.Activities.AsyncCodeActivity>로부터 파생되는 사용자 지정 활동을 만들어 SMTP를 사용하여 메일을 보내는 방법을 보여 줍니다. 기능을 사용 하는 사용자 지정 활동 <xref:System.Net.Mail.SmtpClient> 비동기적으로 전자 메일을 보내려면 및 인증 된 메일을 보냅니다. 또한 테스트 모드, 토큰 바꾸기, 파일 템플릿 및 테스트 드롭 경로와 같은 몇 가지 최종 사용자 기능도 제공합니다.  
  
 다음 표에서는 `SendMail` 활동의 인수에 대해 자세히 설명합니다.  
  
|이름|형식|설명|  
|-|-|-|  
|호스트|문자열|SMTP 서버 호스트의 주소입니다.|  
|포트|문자열|호스트에 있는 SMTP 서비스의 포트입니다.|  
|EnableSsl|bool|<xref:System.Net.Mail.SmtpClient>에서 SSL(Secure Sockets Layer)을 사용하여 연결을 암호화할지 여부를 지정합니다.|  
|UserName|문자열|보낸 사람의 <xref:System.Net.Mail.SmtpClient.Credentials%2A> 속성을 인증하는 자격 증명을 설정할 사용자 이름입니다.|  
|암호|문자열|보낸 사람의 <xref:System.Net.Mail.SmtpClient.Credentials%2A> 속성을 인증하는 자격 증명을 설정할 암호입니다.|  
|제목|<xref:System.Activities.InArgument%601>\<string>|메시지 제목입니다.|  
|본문|<xref:System.Activities.InArgument%601>\<string>|메시지 본문입니다.|  
|첨부 파일|<xref:System.Activities.InArgument%601>\<string>|이 전자 메일 메시지에 첨부 된 데이터를 저장 하는 데 사용 되는 첨부 파일 컬렉션입니다.|  
|시작|<xref:System.Net.Mail.MailAddress>|이 이메일 메시지의 주소입니다.|  
|대상|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|이 전자 메일 메시지의 받는 사람이 들어 있는 주소 컬렉션입니다.|  
|CC|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|이 이메일 메시지의 cc () 받는 사람이 들어 있는 컬렉션을 해결 합니다.|  
|BCC|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|이 이메일 메시지의 bcc (숨은 참조) 받는 사람이 들어 있는 주소 컬렉션입니다.|  
|토큰|<xref:System.Activities.InArgument%601><IDictionary\<string, string>>|본문에서 바꿀 토큰입니다. 사용자는 이 기능을 통해 나중에 이 속성을 사용하여 제공된 토큰으로 바꿀 수 있는 일부 값을 본문에 지정할 수 있습니다.|  
|BodyTemplateFilePath|문자열|본문에 대한 템플릿의 경로입니다. `SendMail` 활동은 이 파일의 내용을 본문 속성에 복사합니다.<br /><br /> 템플릿에는 토큰 속성의 내용으로 바뀌는 토큰이 포함될 수 있습니다.|  
|TestMailTo|<xref:System.Net.Mail.MailAddress>|이 속성을 설정 하는 경우 모든 전자 메일에 지정 된 주소로 전송 됩니다.<br /><br /> 이 속성은 워크플로를 테스트할 때 사용할 수 있습니다. 예를 들어 있는지 확인 하려는 경우 실제 받는 사람에 게 보내지는 않고 모든 전자 메일 전송 됩니다.|  
|TestDropPath|문자열|이 속성을 설정 하는 경우 모든 전자 메일은 지정된 된 파일에도 저장 됩니다.<br /><br /> 이 속성을 테스트 하거나 형식과 보내는 전자 메일의 내용은 적합 한지 확인 하려면 워크플로 디버깅 하는 경우 사용할 수 있습니다.|  
  
## <a name="solution-contents"></a>솔루션 개념  
 솔루션에는 두 개의 프로젝트가 포함되어 있습니다.  
  
|프로젝트|설명|중요한 파일|  
|-------------|-----------------|---------------------|  
|SendMail|SendMail 활동|1.  SendMail.cs: 기본 활동에 대한 구현<br />2.  SendMailDesigner.xaml 및 SendMailDesigner.xaml.cs: SendMail 활동에 대한 디자이너<br />3.  MailTemplateBody.htm: 보낼 전자 메일에 대한 템플릿|  
|SendMailTestClient|SendMail 활동을 테스트할 클라이언트입니다.  이 프로젝트에서는 SendMail 활동을 호출하는 두 가지 방식, 즉 선언 방식과 프로그래밍 방식을 보여 줍니다.|1.  Sequence1.xaml: SendMail 활동을 호출하는 워크플로입니다.<br />2.  Program.cs: Sequence1을 호출하고 SendMail을 사용하는 워크플로를 프로그래밍 방식으로 만듭니다.|  
  
## <a name="further-configuration-of-the-sendmail-activity"></a>SendMail 활동의 추가 구성  
 샘플에는 표시되지 않지만 사용자는 SendMail 활동의 구성을 추가할 수 있습니다. 다음 세 개의 섹션에서는 이를 수행하는 방법을 보여 줍니다.  
  
### <a name="sending-an-email-using-tokens-specified-in-the-body"></a>본문에 지정된 토큰을 사용하여 전자 메일 보내기  
 이 코드 조각에서는 본문에 토큰이 포함된 전자 메일을 보낼 수 있는 방법을 보여 줍니다. 토큰이 본문 속성에 어떻게 제공되는지 확인합니다. 해당 토큰 값은 토큰 속성에 제공됩니다.  
  
```html  
IDictionary<string, string> tokens = new Dictionary<string, string>();  
tokens.Add("@name", "John Doe");  
tokens.Add("@date", DateTime.Now.ToString());  
tokens.Add("@server", "localhost");  
  
new SendMail  
{  
    From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
    To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
    Subject = "Test email",  
    Body = "Hello @name. This is a test email sent from @server. Current date is @date",  
    Host = "localhost",  
    Port = 25,  
    Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens)  
};  
```  
  
### <a name="sending-an-email-using-a-template"></a>템플릿을 사용하여 전자 메일 보내기  
 이 조각에서는 본문의 템플릿 토큰을 사용하여 전자 메일을 보내는 방법을 보여 줍니다. `BodyTemplateFilePath` 속성을 설정할 때 Body 속성 값을 제공할 필요가 없습니다. 템플릿 파일의 내용이 본문에 복사되기 때문입니다.  
  
```  
new SendMail  
{    
    From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
    To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
    Subject = "Test email",  
    Host = "localhost",  
    Port = 25,  
    Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens),  
    BodyTemplateFilePath = @"..\..\..\SendMail\Templates\MailTemplateBody.htm",   
};  
```  
  
### <a name="sending-mails-in-testing-mode"></a>테스트 모드에서 메일 보내기  
 이 코드 조각은 두 개의 테스트 속성을 설정 하는 방법을 보여 줍니다: 설정 하 여 `TestMailTo` 모든 메시지를 보낼 `john.doe@contoso.con` (To, Cc, Bcc 값의 관계) 없이 합니다. TestDropPath를 설정하면 나가는 모든 전자 메일이 제공된 경로에도 기록됩니다. 이러한 속성은 서로 관련되어 있지 않으므로 독립적으로 설정할 수 있습니다.  
  
```  
new SendMail  
{    
   From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
   To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
   Subject = "Test email",  
   Host = "localhost",  
   Port = 25,  
   Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens),  
   BodyTemplateFilePath = @"..\..\..\SendMail\Templates\MailTemplateBody.htm",  
   TestMailTo= new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
   TestDropPath = @"c:\Samples\SendMail\TestDropPath\",  
};  
```  
  
## <a name="set-up-instructions"></a>설치 지침  
 이 샘플을 실행하려면 SMTP 서버에 액세스해야 합니다.  
  
 SMTP 서버 설정에 대 한 자세한 내용은 다음 링크를 참조 하세요.  
  
- [Microsoft Technet](https://go.microsoft.com/fwlink/?LinkId=166060)  
  
- [SMTP 서비스 (IIS 6.0) 구성](https://go.microsoft.com/fwlink/?LinkId=150456)  
  
- [IIS 7.0: SMTP 전자 메일 구성](https://go.microsoft.com/fwlink/?LinkId=150457)  
  
- [SMTP 서비스를 설치 하는 방법](https://go.microsoft.com/fwlink/?LinkId=150458)  
  
 타사에서 제공하는 SMTP 에뮬레이터를 다운로드할 수 있습니다.  
  
##### <a name="to-run-this-sample"></a>이 샘플을 실행하려면  
  
1. SendMail.sln 솔루션 파일을 열고 Visual Studio 2010을 사용 합니다.  
  
2. 올바른 SMTP 서버에 액세스할 수 있는 권한이 있는지 확인합니다. 설치 지침을 참조하세요.  
  
3. 서버 주소를 사용 하 여 및 전자 메일 주소로 프로그램을 구성 합니다.  
  
     이 샘플을 올바르게 실행 하려면 Program.cs 및 Sequence.xaml에서 전자 메일 주소와 SMTP 서버 주소를의 값을 구성 해야 합니다. 프로그램은 메일을 두 가지 다른 방식으로 보내므로 두 위치에서 모두 주소를 변경해야 합니다.  
  
4. Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
5. Ctrl+F5를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`