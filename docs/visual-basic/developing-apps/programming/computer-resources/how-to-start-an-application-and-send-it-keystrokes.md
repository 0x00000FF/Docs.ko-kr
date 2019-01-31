---
title: '방법: 애플리케이션 시작 및 키 입력 보내기(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- keystrokes, sending
- Shell command example [Visual Basic]
- processes, starting and sending keystrokes
- SendKeys.SendWait examples
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
ms.openlocfilehash: 36d6110a9e0ccf20718e95e6d7601e21e8d8f22c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688391"
---
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a><span data-ttu-id="1983a-102">방법: 애플리케이션 시작 및 키 입력 보내기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1983a-102">How to: Start an Application and Send it Keystrokes (Visual Basic)</span></span>
<span data-ttu-id="1983a-103">이 예제에서는 `Shell` 함수를 사용하여 계산기 애플리케이션을 시작한 다음 `My.Computer.Keyboard.SendKeys` 메서드를 통해 키 입력을 전송하여 두 숫자를 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="1983a-103">This example uses the `Shell` function to start the calculator application and then multiplies two numbers by sending keystrokes using the `My.Computer.Keyboard.SendKeys` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1983a-104">예제</span><span class="sxs-lookup"><span data-stu-id="1983a-104">Example</span></span>  
 [!code-vb[VbVbalrMyComputer#25](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-start-an-application-and-send-it-keystrokes_1.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="1983a-105">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="1983a-105">Robust Programming</span></span>  
 <span data-ttu-id="1983a-106">요청된 프로세스 식별자를 가진 애플리케이션을 찾을 수 없는 경우 <xref:System.ArgumentException> 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="1983a-106">A <xref:System.ArgumentException> exception is raised if an application with the requested process identifier cannot be found.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="1983a-107">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="1983a-107">.NET Framework Security</span></span>  
 <span data-ttu-id="1983a-108">`Shell` 함수에 대한 호출은 완전 신뢰가 필요합니다(<xref:System.Security.SecurityException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="1983a-108">The call to the `Shell` function requires full trust (<xref:System.Security.SecurityException> class).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1983a-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1983a-109">See also</span></span>
- <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>
- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>
