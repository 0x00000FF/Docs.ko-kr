---
title: "방법: 전역 어셈블리 캐시의 내용 보기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, viewing contents
- viewing assemblies in global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- GAC (global assembly cache), viewing contents
- list of assemblies in global assembly cache
- Global Assembly Cache tool
ms.assetid: c5f786a0-969b-4f14-9f02-e77c3384d9af
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e50292d1cbb5f2906f053ffd6e21ca21174e2914
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a><span data-ttu-id="b80ea-102">방법: 전역 어셈블리 캐시의 내용 보기</span><span class="sxs-lookup"><span data-stu-id="b80ea-102">How to: View the Contents of the Global Assembly Cache</span></span>
<span data-ttu-id="b80ea-103">[전역 어셈블리 캐시 도구(Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)를 사용하면 전역 어셈블리캐시의 콘텐츠를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b80ea-103">Use the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache.</span></span>  
  
### <a name="to-view-a-list-of-the-assemblies-in-the-global-assembly-cache"></a><span data-ttu-id="b80ea-104">전역 어셈블리 캐시에서 어셈블리 목록을 보려면</span><span class="sxs-lookup"><span data-stu-id="b80ea-104">To view a list of the assemblies in the global assembly cache</span></span>  
  
1.  <span data-ttu-id="b80ea-105">[Visual Studio 명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)에서 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b80ea-105">At the [Visual Studio command prompt](../../../docs/framework/tools/developer-command-prompt-for-vs.md), type the following command:</span></span>  
  
     <span data-ttu-id="b80ea-106">**gacutil -l** </span><span class="sxs-lookup"><span data-stu-id="b80ea-106">**gacutil -l** </span></span>  
     <span data-ttu-id="b80ea-107">또는</span><span class="sxs-lookup"><span data-stu-id="b80ea-107">-or-</span></span>  
    <span data-ttu-id="b80ea-108">**gacutil /l**</span><span class="sxs-lookup"><span data-stu-id="b80ea-108">**gacutil /l**</span></span>  
  
 <span data-ttu-id="b80ea-109">이전 버전의 .NET Framework에서는 [Shfusion.dll](http://msdn.microsoft.com/library/0d9464cf-ddba-4ca9-bbec-f678fb58f380) Windows 셸 확장을 통해 파일 탐색기에서 전역 어셈블리 캐시를 볼 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="b80ea-109">In earlier versions of the .NET Framework, the [Shfusion.dll](http://msdn.microsoft.com/library/0d9464cf-ddba-4ca9-bbec-f678fb58f380) Windows shell extension enabled you to view the global assembly cache in File Explorer.</span></span> <span data-ttu-id="b80ea-110">[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]부터는 Shfusion.dll이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b80ea-110">Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll is obsolete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b80ea-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b80ea-111">See Also</span></span>  
 [<span data-ttu-id="b80ea-112">어셈블리 및 전역 어셈블리 캐시 사용</span><span class="sxs-lookup"><span data-stu-id="b80ea-112">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="b80ea-113">Gacutil.exe(전역 어셈블리 캐시 도구)</span><span class="sxs-lookup"><span data-stu-id="b80ea-113">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
