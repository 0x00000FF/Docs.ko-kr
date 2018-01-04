---
title: "방법: 데이터 개체 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataObject class [WPF], creating
- data objects [WPF], creating
- drag-and-drop [WPF], creating data objects
ms.assetid: 022fa142-717d-4fea-a53c-3b52e9d91aff
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 014d5229026a6fdaab203c82932742c7b2c7639e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-data-object"></a>방법: 데이터 개체 만들기
다음 예제에서 제공 하는 생성자를 사용 하 여 데이터 개체를 만드는 다양 한 방법을 보여 줍니다는 <xref:System.Windows.DataObject> 클래스입니다.  
  
## <a name="example"></a>예  
  
### <a name="description"></a>설명  
 다음 코드 예제에서는 새 데이터 개체를 만들고 오버 로드 된 생성자 중 하나를 사용 하 여 (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) 문자열이 있는 데이터 개체를 초기화 합니다.  이 경우 해당 데이터 형식이 자동으로 저장된 된 데이터 형식에 따라 결정 됩니다 하 고 저장된 된 데이터 자동 변환 기본적으로 허용 됩니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple)]  
  
### <a name="description"></a>설명  
 다음 예제 코드는 위에 나와 있는 코드의 압축 된 버전.  
  
### <a name="code"></a>코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple_condensed)]  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 코드 예제에서는 새 데이터 개체를 만들고 오버 로드 된 생성자 중 하나를 사용 하 여 (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) 문자열 및 지정 된 데이터 형식으로 데이터 개체를 초기화 합니다.  데이터 형식은 문자열;에 의해 지정은 경우 <xref:System.Windows.DataFormats> 클래스 미리 정의 된 형식 문자열의 집합을 제공 합니다. 기본적으로 저장된 된 데이터 자동 변환 허용 됩니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
### <a name="description"></a>설명  
 다음 예제 코드는 위에 나와 있는 코드의 압축 된 버전.  
  
### <a name="code"></a>코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring_condensed)]  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 코드 예제에서는 새 데이터 개체를 만들고 오버 로드 된 생성자 중 하나를 사용 하 여 (<xref:System.Windows.DataObject.%23ctor%2A>) 문자열 및 지정 된 데이터 형식으로 데이터 개체를 초기화 합니다.  데이터 format을 지정 하는 경우에 <xref:System.Type> 매개 변수입니다.  기본적으로 저장된 된 데이터 자동 변환 허용 됩니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type)]  
  
### <a name="description"></a>설명  
 다음 예제 코드는 위에 나와 있는 코드의 압축 된 버전.  
  
### <a name="code"></a>코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type_condensed)]  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 코드 예제에서는 새 데이터 개체를 만들고 오버 로드 된 생성자 중 하나를 사용 하 여 (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) 문자열 및 지정 된 데이터 형식으로 데이터 개체를 초기화 합니다.  데이터 형식은 문자열;에 의해 지정은 경우 <xref:System.Windows.DataFormats> 클래스 미리 정의 된 형식 문자열의 집합을 제공 합니다. 이 특정 생성자 오버 로드에는 자동 변환 허용 되는지 여부를 지정 하려면 호출자 수 있습니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert)]  
  
### <a name="description"></a>설명  
 다음 예제 코드는 위에 나와 있는 코드의 압축 된 버전.  
  
### <a name="code"></a>코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert_condensed)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.IDataObject>
