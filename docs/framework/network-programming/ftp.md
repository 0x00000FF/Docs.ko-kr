---
title: FTP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FTP
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 6c0e0172bc42b0b14eebdeaba85d454c5aec25c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ftp"></a>FTP
.NET Framework에서는 <xref:System.Net.FtpWebRequest> 및 <xref:System.Net.FtpWebResponse> 클래스를 사용한 FTP 프로토콜을 포괄적으로 지원합니다. 이러한 클래스는 <xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse>에서 파생됩니다. 대부분의 경우 <xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse> 클래스는 요청을 만드는 데 필요한 모든 것을 제공하지만, 속성으로 노출되는 FTP별 기능에 액세스해야 할 경우 이러한 클래스를 <xref:System.Net.FtpWebRequest> 또는 <xref:System.Net.FtpWebResponse>로 형식 캐스팅해야 합니다.  
  
## <a name="examples"></a>예제  
 자세한 내용은 [방법: FTP를 사용하여 파일 다운로드](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md), [방법: FTP를 사용하여 파일 업로드](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md) 및 [방법: FTP로 디렉터리 내용 나열](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md) 항목을 참조하세요.  
  
## <a name="ftp-and-proxies"></a>FTP 및 프록시  
 <xref:System.Net.FtpWebRequest.Proxy%2A> 속성으로 지정되는 프록시가 HTTP 프로시인 경우 <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory> 및 <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> 명령만 지원됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [프록시를 통해 인터넷 액세스](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [네트워크 프로그래밍 샘플](../../../docs/framework/network-programming/network-programming-samples.md)  
 [FTP 클라이언트 기술 샘플](http://go.microsoft.com/fwlink/?LinkID=179557)  
 [FTP 탐색기 기술 샘플](http://go.microsoft.com/fwlink/?LinkID=179569)  
 [응용 프로그램 프로토콜 사용](../../../docs/framework/network-programming/using-application-protocols.md)
