---
title: "방법: 메타파일 로드 및 표시"
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
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 722b6d36801c69e500535a32e952ef8f45634d03
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-load-and-display-metafiles"></a>방법: 메타파일 로드 및 표시
<xref:System.Drawing.Imaging.Metafile> 클래스에서 상속 되는 <xref:System.Drawing.Image> 클래스, 기록, 표시 및 벡터 이미지를 검사 하기 위한 메서드를 제공 합니다.  
  
## <a name="example"></a>예제  
 화면에 벡터 이미지 (메타 파일)을 표시 하려면는 <xref:System.Drawing.Imaging.Metafile> 개체 및 <xref:System.Drawing.Graphics> 개체입니다. 파일 (또는 스트림)의 이름을 전달 하는 <xref:System.Drawing.Imaging.Metafile> 생성자입니다. 만든 후는 <xref:System.Drawing.Imaging.Metafile> 개체를 전달 하는 <xref:System.Drawing.Imaging.Metafile> 개체는 <xref:System.Drawing.Graphics.DrawImage%2A> 의 메서드는 <xref:System.Drawing.Graphics> 개체입니다.  
  
 이 예에서는 만듭니다는 <xref:System.Drawing.Imaging.Metafile> 개체 EMF (확장된 메타 파일) 파일에서 다음의 왼쪽 위 모퉁이에 있는 이미지를 그립니다 (60, 10).  
  
 다음 그림에서는 지정된 된 위치에 그려지는 메타 파일을 보여 줍니다.  
  
 ![이미지 위치](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.  
  
## <a name="see-also"></a>참고 항목  
 [이미지, 비트맵, 아이콘 및 메타파일 사용](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
