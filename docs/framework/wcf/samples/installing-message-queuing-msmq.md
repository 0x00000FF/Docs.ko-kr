---
title: 메시지 큐(MSMQ) 설치
ms.date: 03/30/2017
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
ms.openlocfilehash: 64736f8f0a34a53658dd2838738a3d36b3891d2d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59305093"
---
# <a name="installing-message-queuing-msmq"></a><span data-ttu-id="0e53c-102">메시지 큐(MSMQ) 설치</span><span class="sxs-lookup"><span data-stu-id="0e53c-102">Installing Message Queuing (MSMQ)</span></span>
<span data-ttu-id="0e53c-103">다음 절차에서는 메시지 큐 4.0 및 메시지 큐 3.0을 설치하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0e53c-103">The following procedures show how to install Message Queuing 4.0 and Message Queuing 3.0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e53c-104">[!INCLUDE[wxp](../../../../includes/wxp-md.md)] 및 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]에서는 메시지 큐 4.0을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0e53c-104">Message Queuing 4.0 is not available in [!INCLUDE[wxp](../../../../includes/wxp-md.md)] and [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a><span data-ttu-id="0e53c-105">Windows Server 2008 또는 Windows Server 2008 R2에 메시지 큐 4.0을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="0e53c-105">To install Message Queuing 4.0 on Windows Server 2008 or Windows Server 2008 R2</span></span>  
  
1. <span data-ttu-id="0e53c-106">서버 관리자에서 클릭 **기능**합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53c-106">In Server Manager, click **Features**.</span></span>  
  
2. <span data-ttu-id="0e53c-107">오른쪽 창의 **기능 요약**, 클릭 **추가 기능**합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53c-107">In the right-hand pane under **Features Summary**, click **Add Features**.</span></span>  
  
3. <span data-ttu-id="0e53c-108">결과 창에서 확장 **메시지 큐**합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53c-108">In the resulting window, expand **Message Queuing**.</span></span>  
  
4. <span data-ttu-id="0e53c-109">확장 **큐 서비스 메시지**합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53c-109">Expand **Message Queuing Services**.</span></span>  
  
5. <span data-ttu-id="0e53c-110">클릭 **디렉터리 서비스 통합** (컴퓨터에 대 한 도메인에 가입)를 클릭 **HTTP 지원을**합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53c-110">Click **Directory Services Integration** (for computers joined to a Domain), then click **HTTP Support**.</span></span>  
  
6. <span data-ttu-id="0e53c-111">클릭 **다음**, 클릭 **설치**합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53c-111">Click **Next**,then click **Install**.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a><span data-ttu-id="0e53c-112">Windows 7 또는 Windows Vista에 메시지 큐 4.0을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="0e53c-112">To install Message Queuing 4.0 on Windows 7 or Windows Vista</span></span>  
  
1. <span data-ttu-id="0e53c-113">**제어판**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0e53c-113">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="0e53c-114">클릭 **프로그램** 차례로 **프로그램 및 기능**, 클릭 **Windows 기능 사용 안 함 설정 및 해제**합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53c-114">Click **Programs** and then, under **Programs and Features**, click **Turn Windows Features on and off**.</span></span>  
  
3. <span data-ttu-id="0e53c-115">MSMQ(Microsoft Message Queue) Server, MSMQ(Microsoft Message Queue) Server Core를 차례로 확장한 후 설치할 다음과 같은 메시지 큐 기능 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53c-115">Expand Microsoft Message Queue (MSMQ) Server, expand Microsoft Message Queue (MSMQ) Server Core, and then select the check boxes for the following Message Queuing features to install:</span></span>  
  
    -   <span data-ttu-id="0e53c-116">MSMQ Active Directory 도메인 서비스 통합(도메인에 연결된 컴퓨터의 경우)</span><span class="sxs-lookup"><span data-stu-id="0e53c-116">MSMQ Active Directory Domain Services Integration (for computers joined to a Domain).</span></span>  
  
    -   <span data-ttu-id="0e53c-117">MSMQ HTTP 지원</span><span class="sxs-lookup"><span data-stu-id="0e53c-117">MSMQ HTTP Support.</span></span>  
  
4. <span data-ttu-id="0e53c-118">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53c-118">Click **OK**.</span></span>  
  
5. <span data-ttu-id="0e53c-119">컴퓨터 다시 시작 하 라는 메시지가 나타나면 클릭 **확인** 설치를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53c-119">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a><span data-ttu-id="0e53c-120">Windows XP 및 Windows Server 2003에 메시지 큐 3.0을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="0e53c-120">To install Message Queuing 3.0 on Windows XP and Windows Server 2003</span></span>  
  
1. <span data-ttu-id="0e53c-121">**제어판**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0e53c-121">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="0e53c-122">클릭 **프로그램 추가 / 제거** 을 클릭 한 다음 **Windows 구성 요소 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53c-122">Click **Add Remove Programs** and then click **Add Windows Components**.</span></span>  
  
3. <span data-ttu-id="0e53c-123">메시지 큐를 선택 하 고 클릭 **세부 정보**합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53c-123">Select Message Queuing and click **Details**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0e53c-124">[!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]을 실행 중인 경우 메시지 큐에 액세스하기 위해 응용 프로그램 서버를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53c-124">If you are running [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], select Application Server to access Message Queuing.</span></span>  
  
4. <span data-ttu-id="0e53c-125">MSMQ HTTP 지원 옵션이 자세히 페이지에 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53c-125">Ensure that the option MSMQ HTTP Support is selected on the details page.</span></span>  
  
5. <span data-ttu-id="0e53c-126">클릭 **확인** 세부 정보 페이지를 종료 한 다음 클릭 **다음**합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53c-126">Click **OK** to exit the details page, and then click **Next**.</span></span> <span data-ttu-id="0e53c-127">설치를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53c-127">Complete the installation.</span></span>  
  
6. <span data-ttu-id="0e53c-128">컴퓨터 다시 시작 하 라는 메시지가 나타나면 클릭 **확인** 설치를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53c-128">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e53c-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="0e53c-129">See also</span></span>

- [<span data-ttu-id="0e53c-130">설치 지침</span><span class="sxs-lookup"><span data-stu-id="0e53c-130">Set-Up Instructions</span></span>](../../../../docs/framework/wcf/samples/set-up-instructions.md)
