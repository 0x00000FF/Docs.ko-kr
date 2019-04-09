---
title: 기존 .NET 앱을 Azure IaaS(클라우드 인프라 지원)로 리프트 앤 시프트하기
description: Azure 클라우드와 Windows 컨테이너를 사용하여 기존.NET 응용 프로그램을 최신으로 변경합니다.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 2b987d43f476f261bfdbd1b2af6ca7f792178cf8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266626"
---
# <a name="lift-and-shift-existing-net-apps-to-azure-iaas-cloud-infrastructure-ready"></a><span data-ttu-id="1b208-103">기존 .NET 앱을 Azure IaaS(클라우드 인프라 지원)로 리프트 앤 시프트하기</span><span class="sxs-lookup"><span data-stu-id="1b208-103">Lift and shift existing .NET apps to Azure IaaS (Cloud Infrastructure-Ready)</span></span>

> <span data-ttu-id="1b208-104">Vision: 첫 번째 단계를 통해 온-프레미스 투자와 하드웨어 및 네트워킹 유지 관리의 총 비용을 줄이기 위해 단순히 rehost 클라우드에서 기존 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-104">Vision: As a first step, to reduce your on-premises investment and total cost of hardware and networking maintenance, simply rehost your existing applications in the cloud.</span></span>

<span data-ttu-id="1b208-105">기존 응용 프로그램을 Azure 서비스 형태의 인프라(IaaS) 플랫폼으로 마이그레이션하는 *방법*을 살펴보기 전에, Azure의 IaaS로 직접 마이그레이션하려는 *이유*를 분석하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-105">Before getting into *how* to migrate your existing applications to the Azure infrastructure as a service (IaaS) platform, it's important to analyze the reasons *why* you'd want to migrate directly to IaaS in Azure.</span></span> <span data-ttu-id="1b208-106">이 최신화 성숙도 시나리오에서는 기본적으로 기존 온-프레미스 인프라를 사용하지 않고 클라우드의 VM을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-106">The scenario at this modernization maturity level essentially is to start using VMs in the cloud, instead of continuing to use your current, on-premises infrastructure.</span></span>

<span data-ttu-id="1b208-107">그 밖에 분석할 점은 Azure의 고급 관리 서비스를 추가하지 않고 순수 IaaS 클라우드로 마이그레이션하려는 *이유*입니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-107">Another point to analyze is *why* you might want to migrate to pure IaaS cloud instead of just adding more advanced managed services in Azure.</span></span> <span data-ttu-id="1b208-108">처음부터 IaaS가 필요한 사례를 결정하십시오.</span><span class="sxs-lookup"><span data-stu-id="1b208-108">Determine what cases might require IaaS in the first place.</span></span>

<span data-ttu-id="1b208-109">다음 그림 2-1에서는 최신화 성숙도에서 클라우드 인프라 지원 응용 프로그램의 위치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-109">Figure 2-1 positions Cloud Infrastructure-Ready applications in the modernization maturity levels:</span></span>

![클라우드 인프라 지원 응용 프로그램 위치](./media/image2-1.png)

> <span data-ttu-id="1b208-111">**그림 2-1.**</span><span class="sxs-lookup"><span data-stu-id="1b208-111">**Figure 2-1.**</span></span> <span data-ttu-id="1b208-112">클라우드 인프라 지원 응용 프로그램 위치</span><span class="sxs-lookup"><span data-stu-id="1b208-112">Positioning Cloud Infrastructure-Ready applications</span></span>

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a><span data-ttu-id="1b208-113">기존.NET 웹 응용 프로그램을 Azure IaaS로 마이그레이션하는 이유</span><span class="sxs-lookup"><span data-stu-id="1b208-113">Why migrate existing .NET web applications to Azure IaaS</span></span>

<span data-ttu-id="1b208-114">이유는 초기 IaaS 수준에도 클라우드로 마이그레이션할 비용 절감 달성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-114">The main reason to migrate to the cloud, even at an initial IaaS level, is to achieve cost reductions.</span></span> <span data-ttu-id="1b208-115">더 많은 관리 되는 인프라 서비스를 사용 하 여 조직의 하드웨어 유지 관리, 서버 또는 VM 프로 비전 및 배포 및 인프라 관리에 소요 된 투자를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-115">By using more managed infrastructure services, your organization can lower its investment in hardware maintenance, server or VM provisioning and deployment, and infrastructure management.</span></span>

<span data-ttu-id="1b208-116">앱을 클라우드로 이동 하도록 결정을 내리면 이유와 IaaS 처럼 PaaS는 단순히 더 많은 고급 옵션 대신 IaaS 환경 주된 이유는 더 익숙할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-116">After you make the decision to move your apps to the cloud, the main reason why you might choose IaaS instead of more advanced options like PaaS is simply that the IaaS environment will be more familiar.</span></span> <span data-ttu-id="1b208-117">현재 유사한 환경으로 이동 하는, 온-프레미스 환경에서는 클라우드에서 가장 빠른 경로 사용 하면 낮은 학습 곡선을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-117">Moving to an environment that's similar to your current, on-premises environment offers a lower learning curve, which makes it the quickest path to the cloud.</span></span>

<span data-ttu-id="1b208-118">그러나 클라우드에서 가장 빠른 경로로 이동 한다고 클라우드에서 실행 중인 응용 프로그램에서 대부분의 이점을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-118">However, taking the quickest path to the cloud doesn't mean that you will gain the most benefit from having your applications running in the cloud.</span></span> <span data-ttu-id="1b208-119">조직의는 클라우드 마이그레이션 도입 되었습니다. 이미 클라우드 최적화 및 클라우드-네이티브 완성도 수준에서 가장 중요 한 이점을 얻을 수 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-119">Any organization will gain the most significant benefits from a cloud migration at the already introduced Cloud-Optimized and Cloud-Native maturity levels.</span></span>

<span data-ttu-id="1b208-120">또한 되었기 때문에 응용 프로그램을 현대화 하 고 IaaS의 경우에 클라우드에 이미 실행 중인 경우 앞으로 아키텍처 변경 하기가 분명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-120">It also has become evident that applications are easier to modernize and rearchitect in the future when they are already running in the cloud, even on IaaS.</span></span> <span data-ttu-id="1b208-121">응용 프로그램 데이터 마이그레이션 이미 목표를 달성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-121">Application data migration has already been achieved.</span></span> <span data-ttu-id="1b208-122">또한 조직은 클라우드에서 작업 하는 데 필요한 기술을 얻을 있고 "클라우드 문화권입니다."에서 작동 하는 전환 수</span><span class="sxs-lookup"><span data-stu-id="1b208-122">Also, your organization will have gained skills required for working in the cloud and made the shift to operating in a "cloud culture."</span></span>

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a><span data-ttu-id="1b208-123">PaaS로 대신 IaaS로 마이그레이션할 시기</span><span class="sxs-lookup"><span data-stu-id="1b208-123">When to migrate to IaaS instead of to PaaS</span></span>

<span data-ttu-id="1b208-124">다음 섹션에서는 대부분 PaaS 플랫폼 및 서비스에 기반 하는 클라우드에 최적화 된 응용 프로그램을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-124">The next sections discuss Cloud-Optimized applications that are mostly based on PaaS platforms and services.</span></span> <span data-ttu-id="1b208-125">이러한 앱을 클라우드로 마이그레이션하면 대부분의 혜택을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-125">These apps give you the most benefits from migrating to the cloud.</span></span> 

<span data-ttu-id="1b208-126">목표는 단순히 클라우드로 기존 응용 프로그램을 이동 하는, 하는 경우 먼저 Azure App Service에서 실행 하려면 상당한 수정이 필요 하지 않습니다는 기존 응용 프로그램을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-126">If your goal is simply to move existing applications to the cloud, first, identify existing applications that would not require substantial modification to run in Azure App Service.</span></span> <span data-ttu-id="1b208-127">이러한 앱에 대 한 첫 번째 후보 있어야 클라우드 최적화 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-127">These apps should be the first candidates for Cloud-Optimized.</span></span> 

<span data-ttu-id="1b208-128">그런 다음 앱에 대 한는 계속 이동할 수 없습니다 Windows 컨테이너 및 PaaS App Service 또는 Azure Service Fabric과 같은 오 케 스트레이 터는 간단한 일반 Vm (IaaS)에 마이그레이션 등.</span><span class="sxs-lookup"><span data-stu-id="1b208-128">Then, for the apps that still cannot move to Windows Containers and PaaS such as App Service or orchestrators like Azure Service Fabric, migrate those to simple plain VMs (IaaS).</span></span> 

<span data-ttu-id="1b208-129">그러나 제대로 구성, 보호 및 Vm을 유지 관리 해야 한다는 훨씬 더 많은 시간과 IT 전문 지식을 Azure에서 PaaS 서비스를 사용 하 여 비교할 염두에서에 둡니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-129">But, keep in mind that correctly configuring, securing, and maintaining VMs requires much more time and IT expertise compared to using PaaS services in Azure.</span></span> <span data-ttu-id="1b208-130">Azure Virtual Machines를 고려 하는 경우를 고려해 야 패치, 업데이트 및 VM 환경을 관리 하는 데 필요한 지속적인 유지 관리 노력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-130">If you are considering Azure Virtual Machines, make sure that you take into account the ongoing maintenance effort required to patch, update, and manage your VM environment.</span></span> <span data-ttu-id="1b208-131">Azure Virtual Machines는 IaaS.</span><span class="sxs-lookup"><span data-stu-id="1b208-131">Azure Virtual Machines is IaaS.</span></span>

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a><span data-ttu-id="1b208-132">Azure Migrate을 사용 하 여 분석 하 고 Azure로 기존 응용 프로그램 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="1b208-132">Use Azure Migrate to analyze and migrate your existing applications to Azure</span></span>

<span data-ttu-id="1b208-133">클라우드로의 마이그레이션은 어렵지 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-133">Migrating to the cloud doesn't have to be difficult.</span></span> <span data-ttu-id="1b208-134">하지만 대부분의 조직에서는 환경 및 응용 프로그램, 작업 및 데이터 간의 긴밀 하 게 상호 종속성에 대 한 심층 파악을 시작 하는 데 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-134">But many organizations struggle to get started - to get deep visibility into the environment and the tight interdependencies between applications, workloads, and data.</span></span> <span data-ttu-id="1b208-135">해당 표시 하지 않고 앞으로 경로 계획 하는 것이 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-135">Without that visibility, it can be difficult to plan the path forward.</span></span> <span data-ttu-id="1b208-136">성공적인 마이그레이션에 필요한 항목에 대 한 자세한 내용은 없이 조직 내에서 올바른 대화를 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-136">Without detailed information on what's required for a successful migration, you can't have the right conversations within your organization.</span></span> <span data-ttu-id="1b208-137">잠재적 비용 이점에 대해 알 수 없는 워크 로드만 리프트 앤 시프트 수 또는 성공적으로 마이그레이션하려면 상당한 재작업 해야 하는지 여부 또는 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-137">You don't know enough about the potential cost benefits, or whether workloads could just lift-and-shift or would require significant rework to migrate successfully.</span></span> <span data-ttu-id="1b208-138">대부분의 조직에서는 언제 든 지 당연 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-138">No wonder many organizations hesitate.</span></span>

<span data-ttu-id="1b208-139">[Azure Migrate](https://aka.ms/azuremigrate) 는 지침, insights 및 Azure로 마이그레이션하는 데 도움이 하는 데 필요한 메커니즘을 제공 하는 새로운 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-139">[Azure Migrate](https://aka.ms/azuremigrate) is a new service that provides the guidance, insights, and mechanisms needed to assist you in migrating to Azure.</span></span> <span data-ttu-id="1b208-140">Azure Migrate는 다음을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-140">Azure Migrate provides:</span></span>

- <span data-ttu-id="1b208-141">검색 및 온-프레미스 가상 컴퓨터에 대 한 평가</span><span class="sxs-lookup"><span data-stu-id="1b208-141">Discovery and assessment for on-premises virtual machines</span></span>

- <span data-ttu-id="1b208-142">다중 계층 응용 프로그램의 높은 정확도 검색에 대 한 기본 제공된 종속성 매핑</span><span class="sxs-lookup"><span data-stu-id="1b208-142">Inbuilt dependency mapping for high-confidence discovery of multi-tier applications</span></span>

- <span data-ttu-id="1b208-143">Azure virtual machines에 지능형 오른쪽 크기 조정</span><span class="sxs-lookup"><span data-stu-id="1b208-143">Intelligent right sizing to Azure virtual machines</span></span>

- <span data-ttu-id="1b208-144">호환성 수정 잠재적인 문제에 대 한 지침을 사용 하 여 보고</span><span class="sxs-lookup"><span data-stu-id="1b208-144">Compatibility reporting with guidelines for remediating potential issues</span></span>

- <span data-ttu-id="1b208-145">데이터베이스 검색 및 마이그레이션에 대 한 Azure 데이터베이스 관리 서비스와의 통합</span><span class="sxs-lookup"><span data-stu-id="1b208-145">Integration with Azure Database Management Service for database discovery and migration</span></span>

<span data-ttu-id="1b208-146">Azure Migrate는 비즈니스에 영향을 최소화 하면서 워크 로드 수 마이그레이션하고 Azure에서 예상 대로 실행 하는 확신을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-146">Azure Migrate gives you confidence that your workloads can migrate with minimal impact to the business and run as expected in Azure.</span></span> <span data-ttu-id="1b208-147">적절 한 도구 및 지침을 사용 하 여 최대는 중요 한 성능 보장 하는 동안 투자 수익률을 얻을 수 있습니다 및 안정성 요구 사항이 충족 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-147">With the right tools and guidance, you can achieve maximum return on investment while assuring that critical performance and reliability needs are met.</span></span>

<span data-ttu-id="1b208-148">그림 2-2 Azure Migrate에서 수행 하는 모든 서버 및 응용 프로그램 연결에 대 한 기본 제공 종속성 매핑을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-148">Figure 2-2 shows you the built-in dependency mapping for all server and application connections performed by Azure Migrate.</span></span>

![클라우드 인프라 지원 응용 프로그램 위치](./media/image2-2.png)

> <span data-ttu-id="1b208-150">**그림 2-2입니다.**</span><span class="sxs-lookup"><span data-stu-id="1b208-150">**Figure 2-2.**</span></span> <span data-ttu-id="1b208-151">클라우드 인프라 지원 응용 프로그램 위치</span><span class="sxs-lookup"><span data-stu-id="1b208-151">Positioning Cloud Infrastructure-Ready applications</span></span>

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a><span data-ttu-id="1b208-152">Azure Site Recovery를 사용 하 여 Azure Vm에 기존 Vm을 마이그레이션하려면</span><span class="sxs-lookup"><span data-stu-id="1b208-152">Use Azure Site Recovery to migrate your existing VMs to Azure VMs</span></span>

<span data-ttu-id="1b208-153">엔드-투-엔드의 일부로 [Azure Migrate](https://aka.ms/azuremigrate)하십시오 [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) 쉽게 Azure에서 Vm에 웹 앱을 마이그레이션 하는 데 사용할 수 있는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-153">As part of the end-to-end [Azure Migrate](https://aka.ms/azuremigrate), [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) is a tool that you can use to easily migrate your web apps to VMs in Azure.</span></span> <span data-ttu-id="1b208-154">보조 온-프레미스 위치에 복제 또는 온-프레미스 Vm 및 물리적 서버를 Azure로 복제에 Site Recovery를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-154">You can use Site Recovery to replicate on-premises VMs and physical servers to Azure, or to replicate them to a secondary on-premises location.</span></span> <span data-ttu-id="1b208-155">온-프레미스는 지원 되는 Azure VM에서 실행 되는 워크 로드도 복제할 수 있습니다 *Hyper-v* VM의는 *VMware* VM 또는 Windows 나 Linux 물리적 서버.</span><span class="sxs-lookup"><span data-stu-id="1b208-155">You can even replicate a workload that's running on a supported Azure VM, on an on-premises *Hyper-V* VM, on a *VMware* VM, or on a Windows or Linux physical server.</span></span> <span data-ttu-id="1b208-156">Azure로 복제를 보조 데이터 센터를 유지 관리 하 고 비용을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-156">Replication to Azure eliminates the cost and complexity of maintaining a secondary datacenter.</span></span>

<span data-ttu-id="1b208-157">Site Recovery에도 부분적으로 하이브리드 환경에 맞게 이루어집니다 온-프레미스 및 Azure에서 부분적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-157">Site Recovery is also made specifically for hybrid environments that are partly on-premises and partly on Azure.</span></span> <span data-ttu-id="1b208-158">Site Recovery Vm에서 실행 되는 앱을 유지 하 여 비즈니스 연속성을 보장 하는 데 도움이 됩니다 및 온-프레미스 물리적 서버를 사용할 수 있는 사이트 다운 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-158">Site Recovery helps ensure business continuity by keeping your apps that are running on VMs and on-premises physical servers available if a site goes down.</span></span> <span data-ttu-id="1b208-159">되도록 사용할 수 있는 보조 위치에서 기본 사이트를 사용할 수 없는 경우 Vm 및 물리적 서버에서 실행 되는 워크 로드를 복제 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-159">It replicates workloads that are running on VMs and physical servers so that they remain available in a secondary location if the primary site isn't available.</span></span> <span data-ttu-id="1b208-160">워크 로드 되 면 기본 사이트를 다시 실행 복구 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-160">It recovers workloads to the primary site when it's up and running again.</span></span>

<span data-ttu-id="1b208-161">그림 2-3 Azure Site Recovery를 사용 하 여 여러 VM 마이그레이션 실행을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1b208-161">Figure 2-3 shows the execution of multiple VM migrations by using Azure Site Recovery.</span></span>

![클라우드 인프라 지원 응용 프로그램 위치](./media/image2-3.png)

> <span data-ttu-id="1b208-163">**그림 2-3입니다.**</span><span class="sxs-lookup"><span data-stu-id="1b208-163">**Figure 2-3.**</span></span> <span data-ttu-id="1b208-164">클라우드 인프라 지원 응용 프로그램 위치</span><span class="sxs-lookup"><span data-stu-id="1b208-164">Positioning Cloud Infrastructure-Ready applications</span></span>

### <a name="additional-resources"></a><span data-ttu-id="1b208-165">추가 자료</span><span class="sxs-lookup"><span data-stu-id="1b208-165">Additional resources</span></span>

- <span data-ttu-id="1b208-166">**Azure Migrate 데이터 시트**</span><span class="sxs-lookup"><span data-stu-id="1b208-166">**Azure Migrate Datasheet**</span></span>

    [https://aka.ms/azuremigration\_datasheet](https://aka.ms/azuremigration\_datasheet)

- <span data-ttu-id="1b208-167">**Azure Migrate**</span><span class="sxs-lookup"><span data-stu-id="1b208-167">**Azure Migrate**</span></span>

    [https://aka.ms/azuremigrate](https://aka.ms/azuremigrate)

- <span data-ttu-id="1b208-168">**Azure 마이그레이션 센터**</span><span class="sxs-lookup"><span data-stu-id="1b208-168">**Azure migration center**</span></span>

    [https://azure.microsoft.com/migration/](https://azure.microsoft.com/migration/)

- <span data-ttu-id="1b208-169">**Site Recovery 사용 하 여 Azure로 마이그레이션**</span><span class="sxs-lookup"><span data-stu-id="1b208-169">**Migrate to Azure with Site Recovery**</span></span>

    [https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure](https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure)

- <span data-ttu-id="1b208-170">**Azure Site Recovery 서비스 개요**</span><span class="sxs-lookup"><span data-stu-id="1b208-170">**Azure Site Recovery service overview**</span></span>

    [https://docs.microsoft.com/azure/site-recovery/site-recovery-overview](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview)

- <span data-ttu-id="1b208-171">**Azure Vm에 AWS에서 Vm 마이그레이션**</span><span class="sxs-lookup"><span data-stu-id="1b208-171">**Migrating VMs in AWS to Azure VMs**</span></span>

    [https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure](https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure)

>[!div class="step-by-step"]
><span data-ttu-id="1b208-172">[이전](index.md)
>[다음](migrate-your-relational-databases-to-azure.md)</span><span class="sxs-lookup"><span data-stu-id="1b208-172">[Previous](index.md)
[Next](migrate-your-relational-databases-to-azure.md)</span></span>
