---
title: '방법: 웹 페이지 요청 및 결과를 스트림으로 검색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: 5ef1867d84b619c58a7b3e29ed0f81f9db0c07a5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54578587"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="ef120-102">방법: 웹 페이지 요청 및 결과를 스트림으로 검색</span><span class="sxs-lookup"><span data-stu-id="ef120-102">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>
<span data-ttu-id="ef120-103">이 예제에서는 웹 페이지를 요청하고 스트림에서 결과를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ef120-103">This example shows how to request a Web page and retrieve the results in a stream.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef120-104">예제</span><span class="sxs-lookup"><span data-stu-id="ef120-104">Example</span></span>  
  
```csharp  
WebClient myClient = new WebClient();  
Stream response = myClient.OpenRead("http://www.contoso.com/index.htm");  
// The stream data is used here.  
response.Close();  
```  
  
```vb  
Dim myClient As WebClient = New WebClient()  
Dim response As Stream = myClient.OpenRead("http://www.contoso.com/index.htm")  
' The stream data is used here.  
response.Close()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ef120-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="ef120-105">Compiling the Code</span></span>  
 <span data-ttu-id="ef120-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ef120-106">This example requires:</span></span>  
  
-   <span data-ttu-id="ef120-107"><xref:System.IO> 및 <xref:System.Net> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="ef120-107">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef120-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef120-108">See also</span></span>
- [<span data-ttu-id="ef120-109">데이터 요청</span><span class="sxs-lookup"><span data-stu-id="ef120-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
