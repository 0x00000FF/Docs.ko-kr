---
title: 피어 투 피어 네트워킹
ms.date: 03/30/2017
ms.assetid: ad6cb67b-fd1c-4ca1-a767-b410da2e16ca
ms.openlocfilehash: fe3fe122e758d8460d98793cb8028ad696cb5302
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491870"
---
# <a name="peer-to-peer-networking"></a><span data-ttu-id="79cb3-102">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="79cb3-102">Peer-to-Peer Networking</span></span>
<span data-ttu-id="79cb3-103">피어 채널은 단체, 피어-투-피어 (P2P) 통신 기술로 Windows Communication Foundation (WCF)입니다.</span><span class="sxs-lookup"><span data-stu-id="79cb3-103">Peer Channel is a multiparty, peer-to-peer (P2P) communication technology in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="79cb3-104">피어 채널은 응용 프로그램 개발자에게 안전하고 확장 가능한 메시지 기반 P2P 통신 채널을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="79cb3-104">It provides a secure and scalable message-based P2P communication channel for application developers.</span></span> <span data-ttu-id="79cb3-105">피어 채널을 활용할 수 있는 다자간 응용 프로그램의 대표적인 예로 여러 사용자가 서버 없이 피어 투 피어 방식으로 서로 채트하는 대화방 같은 공동 작업 응용 프로그램을 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79cb3-105">One common example of a multiparty application that can benefit from Peer Channel is a collaborative application, such as chat, where a group of people chat with one another in a peer-to-peer manner without servers.</span></span> <span data-ttu-id="79cb3-106">피어 채널은 소비자 및 기업 시나리오 모두에서 P2P 공동 작업, 콘텐츠 배포, 부하 분산 및 분산 처리를 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="79cb3-106">Peer Channel enables P2P collaboration, content distribution, load balancing, and distributed processing for both consumer and enterprise scenarios.</span></span>  
  
 <span data-ttu-id="79cb3-107">피어 채널에서 기본적으로 활성화 되어 [!INCLUDE[wv](../../../../includes/wv-md.md)]와 마찬가지로 모든 WCF 합니다.</span><span class="sxs-lookup"><span data-stu-id="79cb3-107">Peer Channel is enabled by default on [!INCLUDE[wv](../../../../includes/wv-md.md)], as is all of WCF.</span></span> <span data-ttu-id="79cb3-108">피어 채널 클래스에 액세스하려면 프로젝트에 System.ServiceModel.dll에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="79cb3-108">To access Peer Channel classes, add references to System.ServiceModel.dll to your project.</span></span>  
  
 <span data-ttu-id="79cb3-109">다음 단원에는 피어 투 피어 네트워킹에 대한 정보와 피어 채널 클래스를 사용하여 피어가 활성화된 네트워크 응용 프로그램을 만드는 데 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79cb3-109">The following sections contain information about peer-to-peer networking and the use of Peer Channel classes to create peer-enabled network applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="79cb3-110">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="79cb3-110">In This Section</span></span>  
 <span data-ttu-id="79cb3-111">[피어 채널 시나리오](../../../../docs/framework/wcf/feature-details/peer-channel-scenarios.md): 게시/구독 메시징, 공동 작업, 분산 처리 및 게임과 같은 피어 채널 Api에서 지 원하는 개발 시나리오에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="79cb3-111">[Peer Channel Scenarios](../../../../docs/framework/wcf/feature-details/peer-channel-scenarios.md):  Describes development scenarios supported by the Peer Channel APIs, such as publication/subscription messaging, collaboration, distributed processing, and gaming.</span></span>  
  
 <span data-ttu-id="79cb3-112">[피어 채널 개념](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md): 설명 피어 메시, 피어 노드, 피어 채널 보안 및 피어 확인자입니다.</span><span class="sxs-lookup"><span data-stu-id="79cb3-112">[Peer Channel Concepts](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md):  Describes Peer Meshes, Peer Nodes, Peer Channel security, and Peer Resolvers.</span></span>  
  
 <span data-ttu-id="79cb3-113">[피어 채널 응용 프로그램 빌드](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md): 피어 채널 응용 프로그램 개발 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="79cb3-113">[Building a Peer Channel Application](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md):  Provides guidance on developing Peer Channel applications.</span></span>  
  
## <a name="peer-channel-code-examples"></a><span data-ttu-id="79cb3-114">피어 채널 코드 예제</span><span class="sxs-lookup"><span data-stu-id="79cb3-114">Peer Channel Code Examples</span></span>  
 [<span data-ttu-id="79cb3-115">피어 채널 사용자 지정 피어 확인자</span><span class="sxs-lookup"><span data-stu-id="79cb3-115">Peer Channel Custom Peer Resolver</span></span>](http://msdn.microsoft.com/library/5b75a2bb-7ff1-4a14-abe7-3debf0537d23)  
  
## <a name="peer-channel-team-blog"></a><span data-ttu-id="79cb3-116">피어 채널 팀 블로그</span><span class="sxs-lookup"><span data-stu-id="79cb3-116">Peer Channel Team blog</span></span>  
 <span data-ttu-id="79cb3-117">[피어 채널 팀 블로그](http://go.microsoft.com/fwlink/?LinkID=114530) 드 (http://go.microsoft.com/fwlink/?LinkID=114530)</span><span class="sxs-lookup"><span data-stu-id="79cb3-117">[Peer Channel Team Blog](http://go.microsoft.com/fwlink/?LinkID=114530) (http://go.microsoft.com/fwlink/?LinkID=114530)</span></span>
