---
title: "방법: 파일 대화 상자 자동 업그레이드 옵트아웃"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- OpenFileDialog [Windows Forms], opt out of automatic upgrade
- file dialog box [Windows Forms], opt out of automatic upgrade
- Windows Vista file dialog box [Windows Forms], opt out of automatic upgrade
- SaveFileDialog [Windows Forms], opt out of automatic upgrade
- AutoUpgradeEnabled property
ms.assetid: 522e482e-cc01-48b1-8d59-9617dc2c4ac1
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 01be9e29c00f39125c8ee645242e986fac178ba2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="a637e-102">방법: 파일 대화 상자 자동 업그레이드 옵트아웃</span><span class="sxs-lookup"><span data-stu-id="a637e-102">How To: Opt Out of File Dialog Box Automatic Upgrade</span></span>
<span data-ttu-id="a637e-103">경우는 <xref:System.Windows.Forms.OpenFileDialog> 및 <xref:System.Windows.Forms.SaveFileDialog> 클래스 응용 프로그램에서 사용 되 고, 해당 모양 및 동작의 응용 프로그램에서 실행 중인 Windows 버전에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a637e-103">When the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes are used in an application, their appearance and behavior depend on the version of Windows the application is running on.</span></span> <span data-ttu-id="a637e-104">때 작성 된 응용 프로그램의 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] 또는 이전에 표시 되는 [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> 및 <xref:System.Windows.Forms.SaveFileDialog> 와 자동으로 표시 되는 [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] 모양 및 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a637e-104">When an application that was created on the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] or earlier is displayed on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> are automatically displayed with the [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] appearance and behavior.</span></span> <span data-ttu-id="a637e-105">부터는 [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)]를 표시 하려면 자동 업그레이드를 취소 수 있습니다는 <xref:System.Windows.Forms.OpenFileDialog> 및 <xref:System.Windows.Forms.SaveFileDialog> 와 [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-모양 및 동작 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="a637e-105">Starting in the [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], you can opt out of the automatic upgrade to display the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> with a [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-style appearance and behavior.</span></span>  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="a637e-106">파일 대화 상자 자동 업그레이드를 옵트아웃하려면</span><span class="sxs-lookup"><span data-stu-id="a637e-106">To opt out of file dialog box automatic upgrade</span></span>  
  
1.  <span data-ttu-id="a637e-107">설정는 <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> 속성 <xref:System.Windows.Forms.OpenFileDialog> 또는 <xref:System.Windows.Forms.SaveFileDialog> 를 `false` 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a637e-107">Set the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property of <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> to `false` before you display the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a637e-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a637e-108">See Also</span></span>  
 <xref:System.Windows.Forms.FileDialog>
