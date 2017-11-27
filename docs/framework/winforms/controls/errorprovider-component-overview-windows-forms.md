---
title: "ErrorProvider 구성 요소 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8b47e55461610d2cc4bf85c839ddb1bef937d69e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="errorprovider-component-overview-windows-forms"></a>ErrorProvider 구성 요소 개요(Windows Forms)
Windows Forms [ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-windows-forms.md) 구성 요소는 폼 또는 컨트롤에서 사용자 입력의 유효성을 검사 하는 데 사용 됩니다. 일반적으로 폼에서 사용자 입력 유효성 검사 또는 데이터 집합의 오류 표시와 함께에서 사용 됩니다. 오류 공급자 방법이 더 나은 오류 메시지를 메시지 상자에 표시 이므로 메시지 상자가 해제 되 면 오류 메시지가 더 이상 표시 합니다. <xref:System.Windows.Forms.ErrorProvider> 오류 아이콘을 표시 하는 구성 요소 (![ErrorProvider 아이콘](../../../../docs/framework/winforms/controls/media/vberrorprovidericon.gif "vbErrorProviderIcon")) 텍스트 상자; 위에 마우스 포인터를 놓을 때와 같이 관련 컨트롤 옆에 도구 설명이 나타납니다 오류 아이콘, 오류 메시지 문자열을 표시 합니다.  
  
## <a name="key-properties"></a>키 속성  
 <xref:System.Windows.Forms.ErrorProvider> 구성 요소의 주요 속성은 <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>, 및 <xref:System.Windows.Forms.ErrorProvider.Icon%2A>합니다. 사용 하는 경우 <xref:System.Windows.Forms.ErrorProvider> 구성 요소 데이터 바인딩된 컨트롤에는 <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> 속성 폼에 오류 아이콘이 표시 하려면 구성 요소에서 적절 한 컨테이너 (일반적으로 Windows Form)으로 설정 되어 있어야 합니다. 구성 요소 디자이너에 추가 되는 <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> 포함 하는 폼 속성이; 코드에서 컨트롤을 추가 하면 직접 설정 해야 합니다.  
  
 <xref:System.Windows.Forms.ErrorProvider.Icon%2A> 기본값 대신 사용자 지정 오류 아이콘으로 속성을 설정할 수 있습니다. 경우는 <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> 속성이 설정 되어는 <xref:System.Windows.Forms.ErrorProvider> 구성 요소는 데이터 집합에 대 한 오류 메시지를 표시할 수 있습니다. 주요 메서드는 <xref:System.Windows.Forms.ErrorProvider> 구성 요소는는 <xref:System.Windows.Forms.ErrorProvider.SetError%2A> 메서드에서 오류 메시지 문자열을 지정 하는 오류 아이콘이 표시 됩니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ErrorProvider> 구성 요소 액세스 가능 클라이언트에 대 한 기본 제공 지원을 제공 하지 않습니다. 응용 프로그램에 액세스할 수 있도록이 구성 요소를 사용 하는 경우, 추가, 액세스할 수 있는 피드백 메커니즘을 제공 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ErrorProvider>  
 [방법: Windows Forms ErrorProvider 구성 요소를 사용하여 데이터 집합에 있는 오류 보기](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)  
 [방법: Windows Forms ErrorProvider 구성 요소를 사용하여 폼 유효성에 대한 오류 아이콘 표시](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)
