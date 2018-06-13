---
title: '방법: Windows Form에서 리소스에 포함된 소리 재생'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], playing from resources
- resources [Windows Forms], playing sounds
- playing sounds [Windows Forms], from resources
- SoundPlayer class [Windows Forms], playing sounds from resources
ms.assetid: 7d148bb6-8a1e-47d7-a08d-35828d2e688f
ms.openlocfilehash: c9dc8499e2d12ed17f9b409a805148d08da894fc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532137"
---
# <a name="how-to-play-a-sound-embedded-in-a-resource-from-a-windows-form"></a>방법: Windows Form에서 리소스에 포함된 소리 재생
사용할 수는 <xref:System.Media.SoundPlayer> 포함된 리소스에서 소리를 재생 하는 클래스입니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[System.Windows.Forms.Sound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Sound/CS/soundtestform.cs#10)]
 [!code-vb[System.Windows.Forms.Sound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Sound/VB/soundtestform.vb#10)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
 가져오기는 <xref:System.Media?displayProperty=nameWithType> 네임 스페이스입니다.  
  
 프로젝트에 사운드 파일을 포함된 리소스로 포함합니다.  
  
 "\<AssemblyName>"을 사운드 파일이 포함된 어셈블리의 이름으로 바꿉니다. ".dll" 접미사는 포함하지 마세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Media.SoundPlayer>  
 [방법: Windows Form에서 소리 재생](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)  
 [방법: Windows Form에서 소리 재생 반복](../../../../docs/framework/winforms/controls/how-to-loop-a-sound-playing-on-a-windows-form.md)
