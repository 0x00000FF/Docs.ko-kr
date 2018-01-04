---
title: "방법: 설치된 디코더 나열"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image decoders [Windows Forms], listing
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7993345a39a24c770fdd717580d428968dae836
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-list-installed-decoders"></a><span data-ttu-id="21581-102">방법: 설치된 디코더 나열</span><span class="sxs-lookup"><span data-stu-id="21581-102">How to: List Installed Decoders</span></span>
<span data-ttu-id="21581-103">응용 프로그램에서 특정 이미지 파일 형식을 읽을 수 있는지 확인 하는 컴퓨터에서 사용할 수 있는 이미지 디코더를 나열할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21581-103">You may want to list the image decoders available on a computer, to determine whether your application can read a particular image file format.</span></span> <span data-ttu-id="21581-104"><xref:System.Drawing.Imaging.ImageCodecInfo> 클래스를 제공 된 <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> 정적 메서드를 이미지 디코더를 사용할 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21581-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> static methods so that you can determine which image decoders are available.</span></span> <span data-ttu-id="21581-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A>배열을 반환 <xref:System.Drawing.Imaging.ImageCodecInfo> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="21581-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21581-106">예</span><span class="sxs-lookup"><span data-stu-id="21581-106">Example</span></span>  
 <span data-ttu-id="21581-107">다음 코드 예제에서는 설치 된 디코더 목록 및 해당 속성 값을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="21581-107">The following code example outputs the list of installed decoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="21581-108">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="21581-108">Compiling the Code</span></span>  
 <span data-ttu-id="21581-109">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="21581-109">This example requires:</span></span>  
  
-   <span data-ttu-id="21581-110">Windows Forms 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="21581-110">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="21581-111">A <xref:System.Windows.Forms.PaintEventArgs>의 매개 변수인 <xref:System.Windows.Forms.PaintEventHandler>합니다.</span><span class="sxs-lookup"><span data-stu-id="21581-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21581-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21581-112">See Also</span></span>  
 [<span data-ttu-id="21581-113">방법: 설치된 인코더 나열</span><span class="sxs-lookup"><span data-stu-id="21581-113">How to: List Installed Encoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [<span data-ttu-id="21581-114">관리되는 GDI+에서 이미지 인코더 및 디코더 사용</span><span class="sxs-lookup"><span data-stu-id="21581-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
