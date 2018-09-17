---
title: '방법: 전역 프록시 선택 재정의'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 244315b5df4200524685bc5b9fb75a0d7fd9b39e
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45698356"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="1927d-102">방법: 전역 프록시 선택 재정의</span><span class="sxs-lookup"><span data-stu-id="1927d-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="1927d-103">이 예제에서는 글로벌 프록시 선택을 포트 80의 `alternateproxy`라는 프록시 서버로 재정의하는 **WebRequest**를 `www.contoso.com`에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="1927d-103">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1927d-104">예</span><span class="sxs-lookup"><span data-stu-id="1927d-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1927d-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="1927d-105">Compiling the Code</span></span>  
 <span data-ttu-id="1927d-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1927d-106">This example requires:</span></span>  
  
-   <span data-ttu-id="1927d-107">**System.Net** 네임스페이스에 대한 [`using` 지시문](~/docs/csharp/language-reference/keywords/using-directive.md)</span><span class="sxs-lookup"><span data-stu-id="1927d-107">A [`using` directive](~/docs/csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1927d-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1927d-108">See Also</span></span>  
 [<span data-ttu-id="1927d-109">응용 프로그램 프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="1927d-109">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 [<span data-ttu-id="1927d-110">프록시를 통해 인터넷 액세스</span><span class="sxs-lookup"><span data-stu-id="1927d-110">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
