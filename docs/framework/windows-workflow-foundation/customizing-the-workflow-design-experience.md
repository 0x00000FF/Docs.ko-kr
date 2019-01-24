---
title: 워크플로 디자인 환경 사용자 지정
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 87b49b025cfb27812933511b76c5a024cde4995a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680307"
---
# <a name="customizing-the-workflow-design-experience"></a><span data-ttu-id="81f69-102">워크플로 디자인 환경 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="81f69-102">Customizing the Workflow Design Experience</span></span>

<span data-ttu-id="81f69-103">[!INCLUDE[wfd1](../../../includes/wfd1-md.md)]에서는 사용자 지정 활동을 디자인하고 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]를 다시 호스트하기 위한 시나리오가 크게 단순화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="81f69-103">The scenarios for designing custom activities and for rehosting the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] have been greatly simplified in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span></span> <span data-ttu-id="81f69-104">따라서 개발과 배포를 더 쉽고 유연하게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f69-104">Development and deployment are now both easier and more flexible.</span></span> <span data-ttu-id="81f69-105">핵심 인프라 변경 내용을 새로운 활동 디자이너 프로그래밍 모델이 Windows Presentation Foundation (WPF)으로 빌드되는 경우</span><span class="sxs-lookup"><span data-stu-id="81f69-105">The key infrastructural change is that the new activity designer programming model is built upon Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="81f69-106">따라서 다른 응용 프로그램에서 비교적 쉽게 활동 디자이너를 선언적으로 정의하고 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]를 다시 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f69-106">This gives you the ability to define activity designers declaratively and to rehost the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in other applications with comparative easy.</span></span> <span data-ttu-id="81f69-107">Workflow Designer를 다시 호스트하면 IntelliSense 또는 간소화된 식 도메인을 지원하는 사용자 지정 식 편집기를 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f69-107">When rehosting, a custom expression editor can be developed to support IntelliSense or a simplified expression domain.</span></span> <span data-ttu-id="81f69-108">통합 Windows Communication Foundation (WCF)를 사용 하 여 워크플로 서비스를 사용 하 여 더욱 원활 하 게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="81f69-108">The integration with Windows Communication Foundation (WCF) has become more seamless with use of workflow services.</span></span> <span data-ttu-id="81f69-109">사용자 지정 활동 디자이너와 모델 항목 트리를 사용하여 다시 호스트된 워크플로 디자이너의 디자인 타임 환경을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f69-109">Custom activity designers and the Model Item Tree can be used to enhance design time experiences in rehosted workflow designers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="81f69-110">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="81f69-110">In This Section</span></span>

 [<span data-ttu-id="81f69-111">사용자 지정 활동 디자이너 및 템플릿 사용</span><span class="sxs-lookup"><span data-stu-id="81f69-111">Using Custom Activity Designers and Templates</span></span>](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md)

 <span data-ttu-id="81f69-112">새로운 사용자 지정 활동 디자이너와 템플릿을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="81f69-112">Describes how to create new custom activity designers and templates.</span></span>

 [<span data-ttu-id="81f69-113">워크플로 디자이너 재호스트</span><span class="sxs-lookup"><span data-stu-id="81f69-113">Rehosting the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)

 <span data-ttu-id="81f69-114">다시 호스트 하는 방법에 설명 합니다 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] Visual Studio 업데이트 및 유효성 검사 오류를 표시 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="81f69-114">Describes how to re-host the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] outside of Visual Studio and how to display validation errors.</span></span>

 [<span data-ttu-id="81f69-115">사용자 지정 식 편집기 사용</span><span class="sxs-lookup"><span data-stu-id="81f69-115">Using a Custom Expression Editor</span></span>](../../../docs/framework/windows-workflow-foundation/using-a-custom-expression-editor.md)

 <span data-ttu-id="81f69-116">Visual Studio 2010 외부에서 다시 호스트 된 워크플로 디자이너를 사용 하려면 사용자 지정 식 편집기를 구현 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f69-116">Describes how to implement a custom expression editor to use with workflow designers rehosted outside of Visual Studio 2010.</span></span>

## <a name="reference"></a><span data-ttu-id="81f69-117">참조</span><span class="sxs-lookup"><span data-stu-id="81f69-117">Reference</span></span>

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a><span data-ttu-id="81f69-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="81f69-118">See also</span></span>

- [<span data-ttu-id="81f69-119">Windows Workflow Foundation 확장</span><span class="sxs-lookup"><span data-stu-id="81f69-119">Extending Windows Workflow Foundation</span></span>](../../../docs/framework/windows-workflow-foundation/extend.md)
- [<span data-ttu-id="81f69-120">디자이너</span><span class="sxs-lookup"><span data-stu-id="81f69-120">Designer</span></span>](../../../docs/framework/windows-workflow-foundation/samples/designer.md)
- [<span data-ttu-id="81f69-121">사용자 지정 작업 디자이너</span><span class="sxs-lookup"><span data-stu-id="81f69-121">Custom Activity Designers</span></span>](../../../docs/framework/windows-workflow-foundation/samples/custom-activity-designers.md)
- [<span data-ttu-id="81f69-122">디자이너 재호스팅</span><span class="sxs-lookup"><span data-stu-id="81f69-122">Designer ReHosting</span></span>](../../../docs/framework/windows-workflow-foundation/samples/designer-rehosting.md)