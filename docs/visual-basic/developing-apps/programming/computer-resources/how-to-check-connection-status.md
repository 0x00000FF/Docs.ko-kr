---
title: "방법: Visual Basic에서 연결 상태 확인"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Web connections
- IsAvailable property, about IsAvailable
- connections, checking status
- connection status
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a3654eb51bb47317c2dc7bf74979a847438b0ae8
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-check-connection-status-in-visual-basic"></a><span data-ttu-id="1c9bd-102">방법: Visual Basic에서 연결 상태 확인</span><span class="sxs-lookup"><span data-stu-id="1c9bd-102">How to: Check Connection Status in Visual Basic</span></span>
<span data-ttu-id="1c9bd-103"><xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A> 속성은 컴퓨터에 작동하는 네트워크 또는 인터넷 연결이 있는지 확인하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9bd-103">The <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A> property can be used to determine whether the computer has a working network or Internet connection.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-check-whether-a-computer-has-a-working-connection"></a><span data-ttu-id="1c9bd-104">컴퓨터에 작동하는 연결이 있는지 확인하려면</span><span class="sxs-lookup"><span data-stu-id="1c9bd-104">To check whether a computer has a working connection</span></span>  
  
-   <span data-ttu-id="1c9bd-105">`IsAvailable` 속성이 `True` 또는 `False`인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9bd-105">Determine whether the `IsAvailable` property is `True` or `False`.</span></span> <span data-ttu-id="1c9bd-106">다음 코드에서는 속성의 상태를 확인하고 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9bd-106">The following code checks the property's status and reports it:</span></span>  
  
     <span data-ttu-id="1c9bd-107">[!code-vb[VbResourceTasks#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-check-connection-status_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="1c9bd-107">[!code-vb[VbResourceTasks#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-check-connection-status_1.vb)]</span></span>  
  
     <span data-ttu-id="1c9bd-108">이 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9bd-108">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="1c9bd-109">코드 조각 선택에서는 **연결 및 네트워킹**에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9bd-109">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="1c9bd-110">자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c9bd-110">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c9bd-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c9bd-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A>

