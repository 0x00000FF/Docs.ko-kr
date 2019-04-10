---
title: '방법: MMC 스냅인을 사용 하 여 인증서 보기'
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 69f79b64250ff46524e7b4720d13351774875a3f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59167507"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="dd934-102">방법: MMC 스냅인을 사용 하 여 인증서 보기</span><span class="sxs-lookup"><span data-stu-id="dd934-102">How to: View certificates with the MMC snap-in</span></span>
<span data-ttu-id="dd934-103">보안 클라이언트 또는 서비스를 만들 때 사용할 수 있습니다는 [인증서](working-with-certificates.md) 자격 증명으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd934-103">When you create a secure client or service, you can use a [certificate](working-with-certificates.md) as the credential.</span></span> <span data-ttu-id="dd934-104">예를 들어, 일반적인 자격 증명 형식은 X.509 인증서를 사용 하 여 만든는 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="dd934-104">For example, a common type of credential is the X.509 certificate, which you create with the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> method.</span></span> 

<span data-ttu-id="dd934-105">세 가지 유형의 Windows 시스템에서 Microsoft Management Console (MMC) 사용 하 여 검사할 수 있는 인증서 저장소에는</span><span class="sxs-lookup"><span data-stu-id="dd934-105">There are three different types of certificate stores that you can examine with the Microsoft Management Console (MMC) on Windows systems:</span></span>

- <span data-ttu-id="dd934-106">로컬 컴퓨터: 로컬 장치 및 장치의 모든 사용자에 게 전역 인지 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd934-106">Local computer: The store is local to the device and global to all users on the device.</span></span>

- <span data-ttu-id="dd934-107">현재 사용자: 저장소 장치에서 현재 사용자 계정에 로컬입니다.</span><span class="sxs-lookup"><span data-stu-id="dd934-107">Current user: The store is local to the current user account on the device.</span></span>

- <span data-ttu-id="dd934-108">서비스 계정: 저장소 장치에서 특정 서비스에 로컬입니다.</span><span class="sxs-lookup"><span data-stu-id="dd934-108">Service account: The store is local to a particular service on the device.</span></span>

## <a name="view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="dd934-109">MMC 스냅인에서 인증서 보기</span><span class="sxs-lookup"><span data-stu-id="dd934-109">View certificates in the MMC snap-in</span></span> 

<span data-ttu-id="dd934-110">다음 절차에는 적절 한 인증서를 찾으려면 장치의 로컬 저장소를 검사 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dd934-110">The following procedure demonstrates how to examine the stores on your local device to find an appropriate certificate:</span></span> 
  
1. <span data-ttu-id="dd934-111">선택 **실행** 에서 합니다 **시작** 메뉴에서 누릅니다 *mmc*.</span><span class="sxs-lookup"><span data-stu-id="dd934-111">Select **Run** from the **Start** menu, and then enter *mmc*.</span></span> 

    <span data-ttu-id="dd934-112">MMC에는 다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd934-112">The MMC appears.</span></span> 
  
2. <span data-ttu-id="dd934-113">**파일** 메뉴에서 **스냅인 추가/제거**합니다.</span><span class="sxs-lookup"><span data-stu-id="dd934-113">From the **File** menu, select **Add/Remove Snap In**.</span></span> 
    
    <span data-ttu-id="dd934-114">합니다 **추가 / 스냅인 제거** 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="dd934-114">The **Add or Remove Snap-ins** window appears.</span></span>
  
3. <span data-ttu-id="dd934-115">**사용 가능한 스냅인** 목록에서 선택 **인증서**을 선택한 후 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="dd934-115">From the **Available snap-ins** list, choose **Certificates**, then select **Add**.</span></span>  

    ![인증서 스냅인 추가](./media/mmc-add-certificate-snap-in.png)
  
4. <span data-ttu-id="dd934-117">에 **인증서 스냅인** 창에서 **컴퓨터 계정**를 선택한 후 **다음**합니다.</span><span class="sxs-lookup"><span data-stu-id="dd934-117">In the **Certificates snap-in** window, select **Computer account**, and then select **Next**.</span></span> 
  
    <span data-ttu-id="dd934-118">필요에 따라 선택할 수 있습니다 **내 사용자 계정** 현재 사용자 또는 **서비스 계정** 특정 서비스에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd934-118">Optionally, you can select **My user account** for the current user or **Service account** for a particular service.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="dd934-119">모르는 경우 관리자가 장치에 대 한, 사용자 계정에 대해서만 인증서를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd934-119">If you're not an administrator for your device, you can manage certificates only for your user account.</span></span>
  
5. <span data-ttu-id="dd934-120">에 **컴퓨터 선택** 두십시오 창 **로컬 컴퓨터** 을 선택한 다음 선택 **마침**합니다.</span><span class="sxs-lookup"><span data-stu-id="dd934-120">In the **Select Computer** window, leave **Local computer** selected, and then select **Finish**.</span></span>  
  
6. <span data-ttu-id="dd934-121">에 **추가 또는 제거 스냅인** 창에서 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="dd934-121">In the **Add or Remove Snap-in** window, select **OK**.</span></span>  
  
    ![인증서 스냅인 추가](./media/mmc-certificate-snap-in-selected.png)

7. <span data-ttu-id="dd934-123">선택 사항: **파일** 메뉴에서 **저장** 또는 **이름으로 저장** 나중에 사용할 MMC 콘솔 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd934-123">Optional: From the **File** menu, select **Save** or **Save As** to save the MMC console file for later use.</span></span>  

8. <span data-ttu-id="dd934-124">MMC 스냅인에서 인증서를 보려면 선택 **콘솔 루트** 왼쪽된 창에서 확장 **인증서 (로컬 컴퓨터)** 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd934-124">To view your certificates in the MMC snap-in, select **Console Root** in the left pane, then expand **Certificates (Local Computer)**.</span></span>

    <span data-ttu-id="dd934-125">각 유형의 인증서에 대 한 디렉터리 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd934-125">A list of directories for each type of certificate appears.</span></span> <span data-ttu-id="dd934-126">각 인증서 디렉터리에서 보기, 내보내기,를 가져오고 해당 인증서를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd934-126">From each certificate directory, you can view, export, import, and delete its certificates.</span></span>

## <a name="view-certificates-with-the-certificate-manager-tool"></a><span data-ttu-id="dd934-127">인증서 관리자 도구를 사용 하 여 인증서 보기</span><span class="sxs-lookup"><span data-stu-id="dd934-127">View certificates with the Certificate Manager tool</span></span>

<span data-ttu-id="dd934-128">있습니다 수도 보기, 내보내기, 가져오기 및 인증서 관리자 도구를 사용 하 여 인증서를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd934-128">You can also view, export, import, and delete certificates by using the Certificate Manager tool.</span></span>

### <a name="to-view-certificates-for-the-local-device"></a><span data-ttu-id="dd934-129">로컬 장치에 대 한 인증서를 보려면</span><span class="sxs-lookup"><span data-stu-id="dd934-129">To view certificates for the local device</span></span>

1. <span data-ttu-id="dd934-130">선택 **실행** 에서 **시작** 메뉴에서 누릅니다 *certlm.msc*합니다.</span><span class="sxs-lookup"><span data-stu-id="dd934-130">Select **Run** from the **Start** menu, and then enter *certlm.msc*.</span></span> 

    <span data-ttu-id="dd934-131">로컬 장치에 대 한 인증서 관리자 도구에는 다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd934-131">The Certificate Manager tool for the local device appears.</span></span> 
  
2. <span data-ttu-id="dd934-132">아래에서 인증서를 보려면 **인증서-로컬 컴퓨터** 왼쪽된 창에서 보려는 인증서 종류에 대 한 디렉터리를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd934-132">To view your certificates, under **Certificates - Local Computer** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

### <a name="to-view-certificates-for-the-current-user"></a><span data-ttu-id="dd934-133">현재 사용자에 대 한 인증서를 보려면</span><span class="sxs-lookup"><span data-stu-id="dd934-133">To view certificates for the current user</span></span>

1. <span data-ttu-id="dd934-134">선택 **실행** 에서 합니다 **시작** 메뉴에서 누릅니다 *certmgr.msc*.</span><span class="sxs-lookup"><span data-stu-id="dd934-134">Select **Run** from the **Start** menu, and then enter *certmgr.msc*.</span></span> 

    <span data-ttu-id="dd934-135">현재 사용자에 대 한 인증서 관리자 도구에는 다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd934-135">The Certificate Manager tool for the current user appears.</span></span> 
  
2. <span data-ttu-id="dd934-136">아래에서 인증서를 보려면 **인증서-현재 사용자** 왼쪽된 창에서 보려는 인증서 종류에 대 한 디렉터리를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd934-136">To view your certificates, under **Certificates - Current User** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd934-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="dd934-137">See also</span></span>

- [<span data-ttu-id="dd934-138">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="dd934-138">Working with certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="dd934-139">방법: 개발 중 사용할 임시 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="dd934-139">How to: Create temporary certificates for use during development</span></span>](how-to-create-temporary-certificates-for-use-during-development.md)
- [<span data-ttu-id="dd934-140">방법: 인증서의 지문 검색</span><span class="sxs-lookup"><span data-stu-id="dd934-140">How to: Retrieve the thumbprint of a certificate</span></span>](how-to-retrieve-the-thumbprint-of-a-certificate.md)
