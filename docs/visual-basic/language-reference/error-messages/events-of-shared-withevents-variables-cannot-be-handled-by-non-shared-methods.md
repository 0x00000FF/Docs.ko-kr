---
title: 비공유 메서드에서는 공유 WithEvents 변수의 이벤트를 처리할 수 없습니다.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 53372927b88df3946583564492df42170f302739
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a><span data-ttu-id="c6964-102">비공유 메서드에서는 공유 WithEvents 변수의 이벤트를 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c6964-102">Events of shared WithEvents variables cannot be handled by non-shared methods</span></span>
<span data-ttu-id="c6964-103">선언 된 변수는 `Shared` 한정자는 공유 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="c6964-103">A variable declared with the `Shared` modifier is a shared variable.</span></span> <span data-ttu-id="c6964-104">공유 변수는 정확히 하나의 저장 위치를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="c6964-104">A shared variable identifies exactly one storage location.</span></span> <span data-ttu-id="c6964-105">선언 된 변수는 `WithEvents` 변수 속해 있는 형식 변수 발생 하는 이벤트 집합을 처리 하는 한정자 어설션 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6964-105">A variable declared with the `WithEvents` modifier asserts that the type to which the variable belongs handles the set of events the variable raises.</span></span> <span data-ttu-id="c6964-106">속성에서 만든 값이 변수에 할당 되는 경우는 `WithEvents` 기존 이벤트 처리기를 언 후크합니다 선언과 연결 하는 통해 새 이벤트 처리기는 `Add` 메서드.</span><span class="sxs-lookup"><span data-stu-id="c6964-106">When a value is assigned to the variable, the property created by the `WithEvents` declaration unhooks any existing event handler and hooks up the new event handler via the `Add` method.</span></span>  
  
 <span data-ttu-id="c6964-107">**오류 ID:** BC30594</span><span class="sxs-lookup"><span data-stu-id="c6964-107">**Error ID:** BC30594</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c6964-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="c6964-108">To correct this error</span></span>  
  
-   <span data-ttu-id="c6964-109">이벤트 처리기 선언 `Shared`합니다.</span><span class="sxs-lookup"><span data-stu-id="c6964-109">Declare your event handler `Shared`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6964-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6964-110">See Also</span></span>  
 [<span data-ttu-id="c6964-111">공유</span><span class="sxs-lookup"><span data-stu-id="c6964-111">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)  
 [<span data-ttu-id="c6964-112">WithEvents</span><span class="sxs-lookup"><span data-stu-id="c6964-112">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
