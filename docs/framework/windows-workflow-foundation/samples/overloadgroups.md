---
title: OverloadGroups
ms.date: 03/30/2017
ms.assetid: d1d547d2-f5fb-4de3-a959-ee6139a4f1ad
ms.openlocfilehash: 489d27e05c96d3b3893052254a879d1c9d75788c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515625"
---
# <a name="overloadgroups"></a><span data-ttu-id="58cd6-102">OverloadGroups</span><span class="sxs-lookup"><span data-stu-id="58cd6-102">OverloadGroups</span></span>
<span data-ttu-id="58cd6-103">이 샘플은 눈여겨 봐야 할 두 가지 특징을 지닌 활동(`CreateLocation`)으로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58cd6-103">This sample consists of an activity (`CreateLocation`), which has two interesting characteristics:</span></span>  
  
1.  <span data-ttu-id="58cd6-104">이 활동에는 몇 가지 필수 인수와 몇 가지 선택적 인수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58cd6-104">It has some required arguments and some optional ones.</span></span>  
  
2.  <span data-ttu-id="58cd6-105">이 활동에서 서로 다른 두 가지 인수 집합 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58cd6-105">It allows the user to choose to provide one of two different sets of arguments.</span></span>  
  
 <span data-ttu-id="58cd6-106">이러한 동작을 수행하는 데는 다음과 같은 두 가지 기능이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="58cd6-106">These behaviors are accomplished by using these two features:</span></span>  
  
-   <span data-ttu-id="58cd6-107">`[isRequired]`는 특정 활동의 속성이 할당되었는지 여부를 검사하고, 속성이 할당되지 않았으면 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="58cd6-107">`[isRequired]` validates that a property of a specific activity is assign, and if not, it throws an exception.</span></span>  
  
-   <span data-ttu-id="58cd6-108">`[OverloadGroup]`은 인수 집합을 함께 묶어 활동 사용자가 특정 집합을 선택하여 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="58cd6-108">`[OverloadGroup]` puts together a set of arguments, so that the user of the activity can choose between using one set or another.</span></span> <span data-ttu-id="58cd6-109">동일한 인스턴스 내에서 다른 오버로드 그룹의 인수를 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58cd6-109">The user cannot use arguments from different Overload Groups in the same instance.</span></span>  
  
 <span data-ttu-id="58cd6-110">다른 워크플로를 설정하고 나면 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>의 <xref:System.Activities.Validation.ValidationResults> 컬렉션을 반환하는 <xref:System.Activities.Validation.Constraint>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="58cd6-110">After setting up different workflows, call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.Constraint>.</span></span> <span data-ttu-id="58cd6-111"><xref:System.Activities.Validation.Constraint> 개체를 콘솔에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="58cd6-111">Print the <xref:System.Activities.Validation.Constraint> objects to the console.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="58cd6-112">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="58cd6-112">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="58cd6-113">열기는 **OverloadGroups.sln** 샘플 솔루션을 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="58cd6-113">Open the **OverloadGroups.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="58cd6-114">솔루션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="58cd6-114">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="58cd6-115">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58cd6-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="58cd6-116">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="58cd6-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="58cd6-117">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="58cd6-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="58cd6-118">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58cd6-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\OverloadGroups`
