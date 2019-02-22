---
title: Windows Forms 컨트롤의 여백 및 안쪽 여백
ms.date: 03/30/2017
helpviewer_keywords:
- Padding property [Windows Forms]
- layout [Windows Forms], margins and padding
- Windows Forms, layout
- Margin property [Windows Forms]
ms.assetid: 3781b5a1-3085-4072-bed0-44670c23ffdc
ms.openlocfilehash: a3218ad029735f4a5d70b3166951dcd93e061c26
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56665227"
---
# <a name="margin-and-padding-in-windows-forms-controls"></a>Windows Forms 컨트롤의 여백 및 안쪽 여백
폼의 정확한 컨트롤 배치는 많은 응용 프로그램에서 우선 순위가 높습니다. <xref:System.Windows.Forms?displayProperty=nameWithType> 네임스페이스는 이 목적을 위한 다양한 레이아웃 기능을 제공합니다. 가장 중요한 두 가지 기능은 <xref:System.Windows.Forms.Control.Margin%2A> 및 <xref:System.Windows.Forms.Control.Padding%2A> 속성입니다.  
  
 <xref:System.Windows.Forms.Control.Margin%2A> 속성은 다른 컨트롤을 컨트롤의 테두리에서 지정된 거리에 유지하는 컨트롤 주위의 공간을 정의합니다.  
  
 <xref:System.Windows.Forms.Control.Padding%2A> 속성은 컨트롤의 내용(예: <xref:System.Windows.Forms.Control.Text%2A> 속성의 값)을 컨트롤의 테두리에서 지정된 거리에 유지하는 컨트롤 내부의 공간을 정의합니다.  
  
 다음 그림에서는 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 및 <xref:System.Windows.Forms.Control.Margin%2A> 속성을 보여 줍니다.  
  
 ![안쪽 여백 및 여백을 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")  
  
 Visual Studio에서는 디자인 타임에 이 기능을 지원합니다. 또한 참조 [연습: 레이아웃 Windows Forms 컨트롤 Padding, Margins 및 AutoSize 속성을 사용 하 여](windows-forms-controls-padding-autosize.md)입니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- <xref:System.Windows.Forms.Control.LayoutEngine%2A>
- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
