---
title: "WF의 오류 처리 활동"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24b68bd3-cef5-4413-ab82-2e2625f209aa
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bcb006f649fe0d2a92b4c789c435ba33916d140f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="error-handling-activities-in-wf"></a><span data-ttu-id="49cd2-102">WF의 오류 처리 활동</span><span class="sxs-lookup"><span data-stu-id="49cd2-102">Error Handling Activities in WF</span></span>
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]<span data-ttu-id="49cd2-103">에서는 오류 처리 및 복구를 구현하기 위해 여러 시스템 제공 활동을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="49cd2-103"> provides several system-provided activities for implementing error handling and recovery.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="49cd2-104">[예외](../../../docs/framework/windows-workflow-foundation/exceptions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="49cd2-104"> [Exceptions](../../../docs/framework/windows-workflow-foundation/exceptions.md).</span></span>  
  
## <a name="error-handling-activities"></a><span data-ttu-id="49cd2-105">오류 처리 작업</span><span class="sxs-lookup"><span data-stu-id="49cd2-105">Error handling activities</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.Rethrow>|<span data-ttu-id="49cd2-106">`TryCatch` 활동에서 throw된 마지막 예외를 다시 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="49cd2-106">Rethrows the last exception thrown from within a `TryCatch` activity.</span></span>|  
|<xref:System.Activities.Statements.Throw>|<span data-ttu-id="49cd2-107">예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="49cd2-107">Throws an exception.</span></span>|  
|<xref:System.Activities.Statements.TryCatch>|<span data-ttu-id="49cd2-108">예외 처리를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="49cd2-108">Implements exception handling.</span></span>|
