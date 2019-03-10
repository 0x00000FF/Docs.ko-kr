---
title: '방법: ShowDialog 메서드로 Windows Form을 표시 하 여 COM Interop 지원'
ms.date: 03/30/2017
helpviewer_keywords:
- COM [Windows Forms]
- Windows Forms, unmanaged
- COM interop [Windows Forms], calling methods
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: 87aac8ad-3c04-43b3-9b0c-d0b00df9ee74
ms.openlocfilehash: 56ded3118d0961f38c77d3db4fc879eb241a7520
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715440"
---
# <a name="how-to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a>방법: ShowDialog 메서드로 Windows Form을 표시 하 여 COM Interop 지원
<xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> 메서드를 사용하여 만드는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 메시지 루프에 Windows Form에 표시하여 COM(구성 요소 개체 모델) 상호 운용성 문제를 해결할 수 있습니다.  
  
 폼이 COM 클라이언트 애플리케이션에서 제대로 작동하게 하려면 Windows Forms 메시지 루프에서 실행해야 합니다. 이렇게 하려면 다음 접근 방식 중 하나를 사용합니다.  
  
-   <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 메서드를 사용하여 Windows Form을 표시합니다.  
  
-   각 Windows Form을 별도 스레드에 표시합니다. 자세한 내용은 [방법: 각 Windows Form을 별개의 스레드에서 표시 하 여 COM Interop 지원](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)합니다.  
  
## <a name="procedure"></a>프로시저  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 메서드를 사용하는 것이 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 메시지 루프에 폼을 표시하는 가장 쉬운 방법일 수 있습니다. 모든 방법 중에서 이 방법이 코드 구현을 가장 적게 요구하기 때문입니다.  
  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 메서드는 관리되지 않는 응용 프로그램의 메시지 루프를 일시 중단하고 폼을 대화 상자로 표시합니다. 호스트 애플리케이션의 메시지 루프가 일시 중단되었기 때문에 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 메서드는 새 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 메시지 루프를 만들어 폼의 메시지를 처리합니다.  
  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 메서드 사용의 단점은 폼이 모달 대화 상자로 열린다는 것입니다. 즉, Windows Form이 열려 있는 동안에는 호출하는 애플리케이션에서 UI(사용자 인터페이스)가 차단됩니다. 사용자가 폼을 종료하면 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 메시지 루프가 닫히고 이전 애플리케이션의 메시지 루프가 다시 실행되기 시작합니다.  
  
 폼을 표시할 메서드를 가지고 있는 클래스 라이브러리를 Windows Forms에서 만든 다음 COM interop에 대한 클래스 라이브러리를 빌드할 수 있습니다. Visual Basic 6.0 또는 MFC(Microsoft Foundation Classes)에서 이 DLL 파일을 사용할 수 있으며, 이러한 환경 중 하나에서 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 메서드를 호출하여 폼을 표시할 수 있습니다.  
  
#### <a name="to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a>ShowDialog 메서드로 Windows Form을 표시하여 COM Interop를 지원하려면  
  
-   <xref:System.Windows.Forms.Form.Show%2A?displayProperty=nameWithType> 메서드에 대한 모든 호출을 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 구성 요소의 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 메서드에 대한 호출로 바꿉니다.  
  
## <a name="see-also"></a>참고자료
- [.NET Framework 구성 요소를 COM에 노출](../../interop/exposing-dotnet-components-to-com.md)
- [방법: 각 Windows Form을 별개의 스레드에서 표시 하 여 COM Interop 지원](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)
- [Windows Forms 및 관리되지 않는 응용 프로그램](windows-forms-and-unmanaged-applications.md)
