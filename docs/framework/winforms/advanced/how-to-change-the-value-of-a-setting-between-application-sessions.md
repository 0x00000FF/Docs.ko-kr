---
title: "방법: 응용 프로그램 세션 간 설정 값 변경"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c00e61001d9c8877b1fcaa0e938c92249c7915e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="0abe2-102">방법: 응용 프로그램 세션 간 설정 값 변경</span><span class="sxs-lookup"><span data-stu-id="0abe2-102">How To: Change the Value of a Setting Between Application Sessions</span></span>
<span data-ttu-id="0abe2-103">때때로 다음 응용 프로그램을 컴파일 및 배포 후 응용 프로그램 세션 간 설정 값을 변경 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0abe2-103">At times, you might want to change the value of a setting between application sessions after the application has been compiled and deployed.</span></span> <span data-ttu-id="0abe2-104">예를 들어 다음 올바른 데이터베이스 위치를 가리키도록 연결 문자열을 변경 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0abe2-104">For example, you might want to change a connection string to point to the correct database location.</span></span> <span data-ttu-id="0abe2-105">이후 응용 프로그램을 컴파일 및 배포 후 디자인 타임 도구를 사용할 수 없는 경우 파일에서 수동으로 설정 값을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0abe2-105">Since design-time tools are not available after the application has been compiled and deployed, you must change the setting value manually in the file.</span></span>  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="0abe2-106">응용 프로그램 세션 간 설정 값을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="0abe2-106">To Change the Value of a Setting Between Application Sessions</span></span>  
  
1.  <span data-ttu-id="0abe2-107">Microsoft 메모장 또는 다른 텍스트 또는 XML 편집기를 사용 하 여, 응용 프로그램과 연결 된.config 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0abe2-107">Using Microsoft Notepad or some other text or XML editor, open the .config file associated with your application.</span></span>  
  
2.  <span data-ttu-id="0abe2-108">변경할 설정에 대 한 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0abe2-108">Locate the entry for the setting you want to change.</span></span> <span data-ttu-id="0abe2-109">아래 제시 된 예와 비슷해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0abe2-109">It should look similar to the example presented below.</span></span>  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  <span data-ttu-id="0abe2-110">설정에 대 한 새 값을 입력 하 고 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0abe2-110">Type a new value for your setting and save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0abe2-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0abe2-111">See Also</span></span>  
 [<span data-ttu-id="0abe2-112">응용 프로그램 설정 및 사용자 설정 사용</span><span class="sxs-lookup"><span data-stu-id="0abe2-112">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="0abe2-113">응용 프로그램 설정 개요</span><span class="sxs-lookup"><span data-stu-id="0abe2-113">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
