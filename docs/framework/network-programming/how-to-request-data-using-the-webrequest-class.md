---
title: '방법: WebRequest 클래스를 사용하여 데이터 요청'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- downloading Internet resources, steps
- requesting data from Internet, steps
- WebRequest class, receiving data
- receiving data, using WebRequest class
- Internet, requesting data
ms.assetid: 368b8d0f-dc5e-4469-a8b8-b2adbf5dd800
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 8928ce8790f58b6920c16cbfd9fc8d9aa6644a44
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2018
ms.locfileid: "47197827"
---
# <a name="how-to-request-data-using-the-webrequest-class"></a><span data-ttu-id="da3d6-102">방법: WebRequest 클래스를 사용하여 데이터 요청</span><span class="sxs-lookup"><span data-stu-id="da3d6-102">How to: Request Data Using the WebRequest Class</span></span>
<span data-ttu-id="da3d6-103">다음 프로시저에서는 서버의 웹 페이지 또는 파일과 같은 리소스를 요청하는 데 사용되는 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="da3d6-103">The following procedure describes the steps used to request a resource from a server, for example, a Web page or file.</span></span> <span data-ttu-id="da3d6-104">리소스는 URI로 식별되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da3d6-104">The resource must be identified by a URI.</span></span>  
  
### <a name="to-request-data-from-a-host-server"></a><span data-ttu-id="da3d6-105">호스트 서버의 데이터를 요청하려면</span><span class="sxs-lookup"><span data-stu-id="da3d6-105">To request data from a host server</span></span>  
  
1.  <span data-ttu-id="da3d6-106">리소스 URI를 통해 <xref:System.Net.WebRequest.Create%2A>를 호출하여 <xref:System.Net.WebRequest> 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="da3d6-106">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A> with the URI of the resource.</span></span>  
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/")  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="da3d6-107">.NET Framework에서는 “http:”, “https:”, “ftp:” 및 “file:”으로 시작하는 URI에 대해 **WebRequest** 및 **WebResponse**에서 파생된 프로토콜별 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="da3d6-107">The .NET Framework provides protocol-specific classes derived from **WebRequest** and **WebResponse** for URIs that begin with "http:", "https:'', "ftp:", and "file:".</span></span> <span data-ttu-id="da3d6-108">다른 프로토콜을 사용하는 리소스에 액세스하려면 **WebRequest** 및 **WebResponse**에서 파생되는 프로토콜별 클래스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da3d6-108">To access resources using other protocols, you must implement protocol-specific classes that derive from **WebRequest** and **WebResponse**.</span></span> <span data-ttu-id="da3d6-109">자세한 내용은 [플러그형 프로토콜 프로그래밍](../../../docs/framework/network-programming/programming-pluggable-protocols.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da3d6-109">For more information, see [Programming Pluggable Protocols](../../../docs/framework/network-programming/programming-pluggable-protocols.md) .</span></span>  
  
2.  <span data-ttu-id="da3d6-110">**WebRequest**에서 필요한 속성 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="da3d6-110">Set any property values that you need in the **WebRequest**.</span></span> <span data-ttu-id="da3d6-111">예를 들어 인증을 사용하도록 설정하려면 **Credentials** 속성을 <xref:System.Net.NetworkCredential> 클래스의 인스턴스로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="da3d6-111">For example, to enable authentication, set the **Credentials** property to an instance of the <xref:System.Net.NetworkCredential> class.</span></span>  
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
    ```  
  
     <span data-ttu-id="da3d6-112">대부분의 경우 데이터를 수신하는 데는 **WebRequest**로 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="da3d6-112">In most cases, the **WebRequest** class is sufficient to receive data.</span></span> <span data-ttu-id="da3d6-113">그러나 프로토콜별 속성을 설정해야 할 경우 **WebRequest**를 프로토콜별 형식으로 캐스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da3d6-113">However, if you need to set protocol-specific properties, you must cast the **WebRequest** to the protocol-specific type.</span></span> <span data-ttu-id="da3d6-114">예를 들어 <xref:System.Net.HttpWebRequest>의 HTTP 관련 속성에 액세스하려면 **WebRequest**를 **HttpWebRequest** 참조로 캐스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da3d6-114">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebRequest>, cast the **WebRequest** to an **HttpWebRequest** reference.</span></span> <span data-ttu-id="da3d6-115">다음 코드 예제에서는 HTTP 관련 <xref:System.Net.HttpWebRequest.UserAgent%2A> 속성을 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da3d6-115">The following code example shows how to set the HTTP-specific <xref:System.Net.HttpWebRequest.UserAgent%2A> property.</span></span>  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  <span data-ttu-id="da3d6-116">요청을 서버에 보내려면 <xref:System.Net.HttpWebRequest.GetResponse%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="da3d6-116">To send the request to the server, call <xref:System.Net.HttpWebRequest.GetResponse%2A>.</span></span> <span data-ttu-id="da3d6-117">반환된 **WebResponse** 개체의 실제 형식은 요청된 URI 구성표에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="da3d6-117">The actual type of the returned **WebResponse** object is determined by the scheme of the requested URI.</span></span>  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="da3d6-118"><xref:System.Net.WebResponse> 개체가 필요 없게 되면 <xref:System.Net.WebResponse.Close%2A> 메서드를 호출하여 개체를 닫아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da3d6-118">After you are finished with a <xref:System.Net.WebResponse> object, you must close it by calling the <xref:System.Net.WebResponse.Close%2A> method.</span></span> <span data-ttu-id="da3d6-119">또는 응답 개체에서 응답 스트림을 이미 가져온 경우 <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> 메서드를 호출하여 스트림을 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da3d6-119">Alternatively, if you have gotten the response stream from the response object, you can close the stream by calling the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="da3d6-120">응답이나 스트림을 닫지 않으면 응용 프로그램이 서버에 대한 연결을 모두 사용하여 추가 요청을 처리하지 못하게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da3d6-120">If you do not close either the response or the stream, your application can run out of connections to the server and become unable to process additional requests.</span></span>  
  
4.  <span data-ttu-id="da3d6-121">**WebResponse**의 속성에 액세스하거나 **WebResponse**를 프로토콜별 인스턴스로 캐스팅하여 프로토콜별 속성을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da3d6-121">You can access the properties of the **WebResponse** or cast the **WebResponse** to a protocol-specific instance to read protocol-specific properties.</span></span> <span data-ttu-id="da3d6-122">예를 들어 <xref:System.Net.HttpWebResponse>의 HTTP 관련 속성에 액세스하려면 **WebResponse**를 **HttpWebResponse** 참조로 캐스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da3d6-122">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast the **WebResponse** to a **HttpWebResponse** reference.</span></span> <span data-ttu-id="da3d6-123">다음 코드 예제에서는 응답과 함께 전송된 상태 정보를 표시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da3d6-123">The following code example shows how to display the status information sent with a response.</span></span>  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)  
    ```  
  
5.  <span data-ttu-id="da3d6-124">서버에서 전송된 응답 데이터를 포함하는 스트림을 가져오려면 **WebResponse**의 <xref:System.Net.HttpWebResponse.GetResponseStream%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="da3d6-124">To get the stream containing response data sent by the server, use the <xref:System.Net.HttpWebResponse.GetResponseStream%2A> method of the **WebResponse**.</span></span>  
  
    ```csharp  
    Stream dataStream = response.GetResponseStream();  
    ```  
  
    ```vb  
    Dim dataStream As Stream = response.GetResponseStream()  
    ```  
  
6.  <span data-ttu-id="da3d6-125">응답에서 데이터를 읽은 후 **Stream.Close** 메서드를 사용하여 응답 스트림을 닫거나 **WebResponse.Close** 메서드를 사용하여 응답을 닫아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da3d6-125">After reading the data from the response, you must either close the response stream using the **Stream.Close** method or close the response using the **WebResponse.Close** method.</span></span> <span data-ttu-id="da3d6-126">응답 스트림 및 **WebResponse**에서 둘 다 **Close** 메서드를 호출할 필요가 없지만 호출해도 문제가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da3d6-126">It is not necessary to call the **Close** method on both the response stream and the **WebResponse**, but doing so is not harmful.</span></span> <span data-ttu-id="da3d6-127">**WebResponse.Close**는 응답을 닫을 때 **Stream.Close**를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="da3d6-127">**WebResponse.Close** calls **Stream.Close** when closing the response.</span></span>  
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
    ```  
  
## <a name="example"></a><span data-ttu-id="da3d6-128">예</span><span class="sxs-lookup"><span data-stu-id="da3d6-128">Example</span></span>  
  
```csharp  
using System;  
using System.IO;  
using System.Net;  
using System.Text;  
  
namespace Examples.System.Net  
{  
    public class WebRequestGetExample  
    {  
        public static void Main()  
        {  
            // Create a request for the URL.   
            WebRequest request = WebRequest.Create(  
              "http://www.contoso.com/default.html");  
            // If required by the server, set the credentials.  
            request.Credentials = CredentialCache.DefaultCredentials;  
            // Get the response.  
            WebResponse response = request.GetResponse();  
            // Display the status.  
            Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
            // Get the stream containing content returned by the server.  
            Stream dataStream = response.GetResponseStream();  
            // Open the stream using a StreamReader for easy access.  
            StreamReader reader = new StreamReader(dataStream);  
            // Read the content.  
            string responseFromServer = reader.ReadToEnd();  
            // Display the content.  
            Console.WriteLine(responseFromServer);  
            // Clean up the streams and the response.  
            reader.Close();  
            response.Close();  
        }  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Net  
Imports System.Text  
Namespace Examples.System.Net  
    Public Class WebRequestGetExample  
  
        Public Shared Sub Main()  
            ' Create a request for the URL.   
            Dim request As WebRequest = _  
              WebRequest.Create("http://www.contoso.com/default.html")  
            ' If required by the server, set the credentials.  
            request.Credentials = CredentialCache.DefaultCredentials  
            ' Get the response.  
            Dim response As WebResponse = request.GetResponse()  
            ' Display the status.  
            Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)  
            ' Get the stream containing content returned by the server.  
            Dim dataStream As Stream = response.GetResponseStream()  
            ' Open the stream using a StreamReader for easy access.  
            Dim reader As New StreamReader(dataStream)  
            ' Read the content.  
            Dim responseFromServer As String = reader.ReadToEnd()  
            ' Display the content.  
            Console.WriteLine(responseFromServer)  
            ' Clean up the streams and the response.  
            reader.Close()  
            response.Close()  
        End Sub   
    End Class   
End Namespace  
```  
  
## <a name="see-also"></a><span data-ttu-id="da3d6-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da3d6-129">See Also</span></span>  
 [<span data-ttu-id="da3d6-130">인터넷 요청 만들기</span><span class="sxs-lookup"><span data-stu-id="da3d6-130">Creating Internet Requests</span></span>](../../../docs/framework/network-programming/creating-internet-requests.md)  
 [<span data-ttu-id="da3d6-131">네트워크에서 스트림 사용</span><span class="sxs-lookup"><span data-stu-id="da3d6-131">Using Streams on the Network</span></span>](../../../docs/framework/network-programming/using-streams-on-the-network.md)  
 [<span data-ttu-id="da3d6-132">프록시를 통해 인터넷 액세스</span><span class="sxs-lookup"><span data-stu-id="da3d6-132">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [<span data-ttu-id="da3d6-133">데이터 요청</span><span class="sxs-lookup"><span data-stu-id="da3d6-133">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)  
 [<span data-ttu-id="da3d6-134">방법: WebRequest 클래스를 사용하여 데이터 보내기</span><span class="sxs-lookup"><span data-stu-id="da3d6-134">How to: Send Data Using the WebRequest Class</span></span>](../../../docs/framework/network-programming/how-to-send-data-using-the-webrequest-class.md)
