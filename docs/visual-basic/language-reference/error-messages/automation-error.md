---
title: 자동화 오류
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: 8370f744b916ce4a797c808ed58c5fc9580e6278
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304314"
---
# <a name="automation-error"></a><span data-ttu-id="738ef-102">자동화 오류</span><span class="sxs-lookup"><span data-stu-id="738ef-102">Automation error</span></span>
<span data-ttu-id="738ef-103">메서드를 실행하는 동안 또는 개체 변수의 속성을 가져오거나 설정하는 동안 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="738ef-103">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="738ef-104">이 오류는 개체를 만든 응용 프로그램에서 보고했습니다.</span><span class="sxs-lookup"><span data-stu-id="738ef-104">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="738ef-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="738ef-105">To correct this error</span></span>  
  
1. <span data-ttu-id="738ef-106">`Err` 개체의 속성을 점검해 오류의 원인과 특성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="738ef-106">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2. <span data-ttu-id="738ef-107">액세스하는 문 바로 전에 `On Error Resume Next` 문을 사용하고, 액세스하는 문 바로 후에 오류가 발생하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="738ef-107">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="738ef-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="738ef-108">See also</span></span>

- [<span data-ttu-id="738ef-109">오류 형식</span><span class="sxs-lookup"><span data-stu-id="738ef-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="738ef-110">의견 보내기</span><span class="sxs-lookup"><span data-stu-id="738ef-110">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
