---
title: '방법: 상속 계층 구조 매핑'
ms.date: 03/30/2017
ms.assetid: b27c779b-9355-4dc7-b95f-7dfd504b6e48
dev_langs:
- csharp
- vb
ms.openlocfilehash: 6f437b7f7ae6a414971edb497bc2c84c03674fe8
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59331834"
---
# <a name="how-to-map-inheritance-hierarchies"></a>방법: 상속 계층 구조 매핑
[!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]에서 상속 매핑을 구현하려면 다음 단계의 설명과 같이 상속 계층 구조의 루트 클래스에 특성 및 특성 속성을 지정해야 합니다. Visual Studio를 사용 하 여 개발자가 사용할 수는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 상속 계층 구조를 매핑할 수 있습니다. [방법: O/R 디자이너를 사용하여 상속 구성](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)을 참조하세요.  
  
> [!NOTE]
>  서브클래스에는 특수 특성 또는 속성이 필요 없습니다. 특히 서브클래스에는 <xref:System.Data.Linq.Mapping.TableAttribute> 특성이 없습니다.  
  
### <a name="to-map-an-inheritance-hierarchy"></a>상속 계층 구조를 매핑하려면  
  
1. 루트 클래스에 <xref:System.Data.Linq.Mapping.TableAttribute> 특성을 추가합니다.  
  
2. 또한 루트 클래스에 계층 구조의 각 클래스에 대한 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 특성을 추가합니다.  
  
3. 각 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 특성에 대해 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> 속성을 정의합니다.  
  
     이 속성에는 이 데이터 행이 속한 클래스 또는 서브클래스를 나타내기 위해 데이터베이스 테이블의 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> 열에 표시되는 값이 저장됩니다.  
  
4. 또한 각 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 특성에 대해 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A> 속성을 추가합니다.  
  
     이 속성에는 키 값이 의미하는 클래스 또는 서브클래스를 지정하는 값이 저장됩니다.  
  
5. <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 특성 중 하나의 특성에만 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A> 속성을 추가합니다.  
  
     지정 하는 데 사용 되는이 속성을 *대체* 판별자 값을 데이터베이스 테이블에서 모든 일치 하지 않는 경우 매핑 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> 상속 매핑의 값입니다.  
  
6. <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> 특성에 대해 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.  
  
     이 속성은 열에 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> 값이 저장됨을 의미합니다.  
  
## <a name="example"></a>예제  
  
> [!NOTE]
>  Visual Studio를 사용 하는 경우 사용할 수 있습니다는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 상속을 구성 하려면. [방법: O/R 디자이너를 사용하여 상속 구성](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)  
  
 다음 코드 예제에서는 `Vehicle`이 루트 클래스로 정의되어 있으며 이전 단계는 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]의 계층 구조를 설명하기 위해 구현되었습니다.  
  
 [!code-csharp[DLinqCustomize#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#4)]
 [!code-vb[DLinqCustomize#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>참고자료

- [상속 지원](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md)
- [방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
