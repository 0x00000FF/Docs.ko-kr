---
title: "방법: Windows Forms LinkLabel 컨트롤에서 웹 페이지 표시(Visual Basic)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- vb
f1_keywords:
- LinkLabel1_LinkClicked
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Web pages [Windows Forms], displaying
- linking [Windows Forms], to Web pages from forms
- Windows Forms, linking to Web pages
- LinkLabel control [Windows Forms], examples
ms.assetid: 477a7398-5971-4de3-b24c-f49f32bdb28a
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ba5ba3b29bab148087e0f8b80b3f1c43aa74e761
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a><span data-ttu-id="da196-102">방법: Windows Forms LinkLabel 컨트롤에서 웹 페이지 표시(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da196-102">How to: Display a Web Page from a Windows Forms LinkLabel Control (Visual Basic)</span></span>
<span data-ttu-id="da196-103">이 예제에서는 Windows Forms를 클릭할 때 기본 브라우저에서 웹 페이지 표시 <xref:System.Windows.Forms.LinkLabel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="da196-103">This example displays a Web page in the default browser when a user clicks a Windows Forms <xref:System.Windows.Forms.LinkLabel> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da196-104">예</span><span class="sxs-lookup"><span data-stu-id="da196-104">Example</span></span>  
  
```vb  
Private Sub Form1_Load(ByVal sender As System.Object, ByVal e _  
As System.EventArgs) Handles MyBase.Load  
    LinkLabel1.Text = "Click here to get more info."  
    LinkLabel1.Links.Add(6, 4, "www.microsoft.com")  
End Sub  
Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, ByVal _  
e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) Handles _  
LinkLabel1.LinkClicked  
    System.Diagnostics.Process.Start(e.Link.LinkData.ToString())  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="da196-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="da196-105">Compiling the Code</span></span>  
 <span data-ttu-id="da196-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="da196-106">This example requires:</span></span>  
  
-   <span data-ttu-id="da196-107">이라는 Windows Form `Form1`합니다.</span><span class="sxs-lookup"><span data-stu-id="da196-107">A Windows Form named `Form1`.</span></span>  
  
-   <span data-ttu-id="da196-108">`LinkLabel1`이라는 <xref:System.Windows.Forms.LinkLabel> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="da196-108">A <xref:System.Windows.Forms.LinkLabel> control named `LinkLabel1`.</span></span>  
  
-   <span data-ttu-id="da196-109">현재 인터넷에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="da196-109">An active Internet connection.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="da196-110">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="da196-110">.NET Framework Security</span></span>  
 <span data-ttu-id="da196-111">에 대 한 호출에서 <xref:System.Diagnostics.Process.Start%2A> 메서드는 완전 신뢰가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="da196-111">The call to the <xref:System.Diagnostics.Process.Start%2A> method requires full trust.</span></span> <span data-ttu-id="da196-112">자세한 내용은 <xref:System.Security.SecurityException>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da196-112">For more information, see <xref:System.Security.SecurityException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da196-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da196-113">See Also</span></span>  
 <xref:System.Windows.Forms.LinkLabel>  
 [<span data-ttu-id="da196-114">LinkLabel 컨트롤</span><span class="sxs-lookup"><span data-stu-id="da196-114">LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)
