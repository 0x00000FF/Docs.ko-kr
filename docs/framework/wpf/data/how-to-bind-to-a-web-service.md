---
title: '방법: 웹 서비스 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], Web service
- Web service binding [WPF]
- data binding [WPF], Web service
ms.assetid: 77e2d373-69ba-4cbd-b6f5-2c83c38fc98b
ms.openlocfilehash: 75d9d5b6981f868c7a172edd7f23cf923fedd525
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557292"
---
# <a name="how-to-bind-to-a-web-service"></a>방법: 웹 서비스 바인딩
이 예제에는 웹 서비스 메서드 호출에서 반환 된 개체에 바인딩하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 사용 하 여이 예제는 [MSDN/TechNet 게시 시스템 (MTPS) 콘텐츠 서비스](http://go.microsoft.com/fwlink/?LinkId=95677) 지정된 된 문서에서 지 원하는 언어의 목록을 검색할 수 있습니다.  
  
 웹 서비스를 호출 하기 전에 그에 대 한 참조 해야 합니다. 사용 하 여 MTPS 서비스에 대 한 웹 참조를 만들려면 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], 다음 단계를 수행 합니다.  
  
1.  프로젝트를 열고 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]합니다.  
  
2.  **프로젝트** 메뉴를 클릭 하 여 **웹 참조 추가**합니다.  
  
3.  대화 상자에서 설정 된 **URL** 를 [ http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl ](http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl)합니다.  
  
4.  키를 눌러 **이동** 차례로 **참조 추가**합니다.  
  
 웹 서비스 메서드를 호출 하는 다음으로 설정 하 고는 <xref:System.Windows.FrameworkElement.DataContext%2A> 적절 한 컨트롤 또는 반환된 된 개체에는 창입니다. **GetContent** MTPS 서비스의 메서드 사용에 대 한 참조는 **getContentRequest** 개체입니다. 따라서 다음 예제에서는 먼저 요청 개체를 설정합니다.  
  
 [!code-csharp[BindToWebService#Namespace](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 후의 <xref:System.Windows.FrameworkElement.DataContext%2A> 하는 개체의 속성에 대 한 바인딩을 만들 수 있습니다 설정 된는 <xref:System.Windows.FrameworkElement.DataContext%2A> 으로 설정 되었습니다. 이 예제에서는 <xref:System.Windows.FrameworkElement.DataContext%2A> 로 설정 되는 **getContentResponse** 에서 반환 된 개체는 **GetContent** 메서드. 다음 예제에서는 <xref:System.Windows.Controls.ItemsControl> 을 바인딩하고 표시는 **로캘** 값의 **availableVersionsAndLocales** 의 **getContentResponse**합니다.  
  
 [!code-xaml[BindToWebService#Binding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 구조에 대 한 내용은 **getContentResponse**, 참조 [콘텐츠 서비스 설명서](http://services.msdn.microsoft.com/ContentServices/ContentService.asmx)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [바인딩 소스 개요](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [XAML의 바인딩에 사용할 수 있는 데이터 만들기](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)
