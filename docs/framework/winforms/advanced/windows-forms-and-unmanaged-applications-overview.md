---
title: "Windows Forms 및 관리되지 않는 응용 프로그램 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "COM[Windows Forms]"
  - "Windows Forms, 관리되지 않음"
  - "COM interop"
  - "ActiveX 컨트롤[Windows Forms], ActiveX 컨트롤 정보"
  - "Windows Forms, interop"
ms.assetid: 0a26d99d-8135-4895-8760-c9a2b5f67f14
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Windows Forms 및 관리되지 않는 응용 프로그램 개요
Windows Forms 응용 프로그램과 컨트롤은 관리되지 않는 응용 프로그램과 상호 운용될 수 있지만 몇 가지 주의할 사항이 있습니다. 다음 섹션에서는 Windows Forms 응용 프로그램과 컨트롤이 지원하는 시나리오 및 구성과 지원하지 않는 시나리오 및 구성을 설명합니다.  
  
## Windows Forms 컨트롤 및 ActiveX 응용 프로그램  
 Microsoft Internet Explorer 및 MFC\(Microsoft Foundation Classes\)를 제외하고 Windows Forms 컨트롤은 ActiveX 컨트롤을 호스트하도록 설계된 응용 프로그램에서 지원되지 않습니다. Visual Studio .NET 2003 이전 Visual Studio 버전의 ActiveX 테스트 컨테이너를 포함하여 ActiveX 컨트롤을 호스트할 수 있는 다른 응용 프로그램과 개발 도구는 Windows Forms 컨트롤에 대해 지원되는 호스트가 아닙니다.  
  
 이러한 제약 조건은 COM\(구성 요소 개체 모델\) interop를 통한 Windows Forms 컨트롤 사용에도 적용됩니다. CCW\(COM 호출 가능 래퍼\)를 통한 Windows Forms 컨트롤 사용은 Internet Explorer에서만 지원됩니다. COM interop에 대한 자세한 내용은  
  
 [COM Interop](../Topic/COM%20Interop%20\(Visual%20Basic\).md).  
  
 다음 표에서는 Windows Forms 컨트롤에 사용할 수 있는 ActiveX 호스팅 지원을 보여 줍니다.  
  
|Windows Forms 버전|지원|  
|----------------------|--------|  
|.NET Framework 버전 1.0|Internet Explorer 5.01 이상 버전|  
|.NET Framework 버전 1.1 이상|Internet Explorer 5.01 이상 버전<br /><br /> MFC\(Microsoft Foundation Classes\) 7.0 이상|  
  
## ActiveX 컨트롤로 Windows Forms 구성 요소 호스트  
 .NET Framework 1.1에서는 MFC 7.0 이상 버전을 포함하도록 지원이 확장되었습니다. 이 지원에는 MFC 7.0 이상 ActiveX 컨트롤 컨테이너와 완전히 호환되는 모든 컨테이너가 포함됩니다.  
  
 그러나 Windows Forms 컨트롤을 ActiveX 컨트롤로 등록하는 기능은 지원되지 않습니다. 또한 Windows Forms 컨트롤에 대한 `com.ms.win32.Ole32.CoCreateInstance` 메서도 호출도 지원되지 않습니다. Windows Forms 컨트롤의 관리되는 활성화만 지원됩니다. Windows Forms 컨트롤을 만든 후에 ActiveX 컨트롤과 마찬가지로 MFC 응용 프로그램에서 호스트할 수 있습니다.  
  
 관리되지 않는 응용 프로그램에서 Windows Forms 컨트롤을 사용하려면 관리되지 않는 CLR 호스팅 API로 CLR을 호스트하거나 C\+\+ interop 기능을 사용해야 합니다. C\+\+ interop 기능 사용이 권장 솔루션입니다.  
  
## COM 클라이언트 응용 프로그램의 Windows Forms  
 Visual Basic 6.0 응용 프로그램이나 MFC 응용 프로그램과 같은 COM 클라이언트 응용 프로그램에서 Windows Form을 여는 경우 폼이 예기치 않게 동작할 수 있습니다. 예를 들어 Tab 키를 누를 때 포커스가 한 컨트롤에서 다른 컨트롤로 변경되지 않습니다. 명령 단추에 포커스가 있는 동안 Enter 키를 누를 때 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트가 발생하지 않습니다. 키 입력이나 마우스 활동에 대한 예기치 않은 동작이 발생할 수도 있습니다.  
  
 이 동작은 관리되지 않는 응용 프로그램에서 Windows Forms이 제대로 작동하는 데 필요한 메시지 루프 지원을 구현하지 않기 때문에 발생합니다. COM 클라이언트 응용 프로그램에서 제공하는 메시지 루프는 기본적으로 Windows Forms 메시지 루프와 다릅니다.  
  
 응용 프로그램의 메시지 루프는 스레드의 메시지 큐에서 메시지를 검색하고 변환한 다음 처리되도록 응용 프로그램에 보내는 내부 프로그램 루프입니다. Windows Form의 메시지 루프에는 Visual Basic 6.0 응용 프로그램 및 MFC 응용 프로그램과 같은 이전 응용 프로그램이 제공하는 메시지 루프와 동일한 아키텍처가 없습니다. 메시지 루프에 게시된 창 메시지가 Windows Form의 예상과 다르게 처리될 수 있습니다. 따라서 예기치 않은 동작이 발생할 수 있습니다. 일부 키 입력 조합이 작동하지 않거나, 일부 마우스 활동이 작동하지 않거나, 일부 이벤트가 예상대로 발생하지 않을 수 있습니다.  
  
## 상호 운용성 문제 해결  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=fullName> 메서드를 사용하여 만든 폼을 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 메시지 루프에 표시하여 이러한 문제를 해결할 수 있습니다.  
  
 Windows Form이 COM 클라이언트 응용 프로그램에서 제대로 작동하게 하려면 Windows Forms 메시지 루프에서 실행해야 합니다. 이렇게 하려면 다음 접근 방식 중 하나를 사용합니다.  
  
-   <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=fullName> 메서드를 사용하여 Windows Form을 표시합니다. 자세한 내용은 [방법: ShowDialog 메서드로 Windows Form을 표시하여 COM Interop 지원](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md)을 참조하세요.  
  
-   각 Windows Form을 새 스레드에 표시합니다. 자세한 내용은 [방법: 각 Windows Form을 별개의 스레드에서 표시하여 COM Interop 지원](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)을 참조하세요.  
  
## 참고 항목  
 [Windows Forms 및 관리되지 않는 응용 프로그램](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md)   
 [COM Interop](../Topic/COM%20Interop%20\(Visual%20Basic\).md)   
 [COM Interoperability in .NET Framework Applications](../Topic/COM%20Interoperability%20in%20.NET%20Framework%20Applications%20\(Visual%20Basic\).md)   
 [COM Interoperability Samples](http://msdn.microsoft.com/ko-kr/09c38567-6380-4d70-848a-e896a4ca05f4)   
 [Aximp.exe \(Windows Forms ActiveX 컨트롤 가져오기\)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md)   
 [.NET Framework 구성 요소를 COM에 노출](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [COM에서 사용할 어셈블리의 패키징](../../../../docs/framework/interop/packaging-an-assembly-for-com.md)   
 [COM에 어셈블리 등록](../../../../docs/framework/interop/registering-assemblies-with-com.md)   
 [방법: ShowDialog 메서드로 Windows Form을 표시하여 COM Interop 지원](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md)   
 [방법: 각 Windows Form을 별개의 스레드에서 표시하여 COM Interop 지원](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)