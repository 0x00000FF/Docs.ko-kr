---
title: 연결 형식
ms.date: 03/30/2017
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
ms.openlocfilehash: 7fbdc0316b1f9fd0bb282fd466857b1426c41df1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64583727"
---
# <a name="association-type"></a>연결 형식
*연결 형식* (연결이 라고도 함)는 엔터티 데이터 모델 (EDM)에서 관계를 설명 하기 위한 기본적인 빌딩 블록입니다. 개념적 모델에서 연결은 두 간의 관계를 나타냅니다 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md) (같은 `Customer` 고 `Order`). 응용 프로그램에서 연결 인스턴스는 특정 연결(예: `Customer` 인스턴스와 `Order` 인스턴스 간의 연결)을 나타냅니다. 연결 인스턴스는 논리적으로 그룹화 되는 [연결 집합](../../../../docs/framework/data/adonet/association-set.md)합니다.  
  
 연결 정의에는 다음 정보가 들어 있습니다.  
  
- 고유한 이름 (필수)  
  
- 두 개의 [연결 end](../../../../docs/framework/data/adonet/association-end.md), 관계의 각 엔터티 형식에 대 한 합니다. (필수)  
  
    > [!NOTE]
    >  연결은 셋 이상 엔터티 형식 간의 관계를 나타낼 수 없습니다. 그러나 연결은 각 연결 End에 같은 엔터티 형식을 지정하여 자체 관계를 정의할 수 있습니다.  
  
- A [참조 무결성 제약 조건](../../../../docs/framework/data/adonet/referential-integrity-constraint.md)합니다. 이 매개 변수는 선택 사항입니다.  
  
 각 연결 end를 지정 해야 합니다는 [연결 end 복합성](../../../../docs/framework/data/adonet/association-end-multiplicity.md) 연결의 한 end에 있을 수 있는 엔터티 형식 인스턴스 수를 나타내는입니다. 연결 end 복합성 하나 (1), 0 개 이상의 값 (0..1) 또는 여러 열에 있을 수 있습니다 (\*). 연결의 한쪽 end에 엔터티 형식 인스턴스를 통해 액세스할 수 있습니다 [탐색 속성](../../../../docs/framework/data/adonet/navigation-property.md) 또는 엔터티 형식에서 노출 된 경우 외래 키입니다. 자세한 내용은 참조 하세요. [엔터티 데이터 모델: 외래 키](../../../../docs/framework/data/adonet/foreign-key-property.md)합니다.  
  
## <a name="example"></a>예제  
 다음 다이어그램에서는 두 연결 `PublishedBy` 및 `WrittenBy`의 개념적 모델을 보여 줍니다. `PublishedBy` 연결의 연결 End는 `Book` 및 `Publisher` 엔터티 형식입니다. 다중성 합니다 `Publisher` 끝이 한 개 (1)이 고는 `Book` 끝이 많은 (\*)는 발행자가 많은 책을 책은 하나의 게시자에서 게시를 나타내는입니다.  
  
 ![세 가지 엔터티 형식을 사용 하 여 예제 모델](./media/association-type/example-model-three-entity-types.gif)  
  
 합니다 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 (DSL)를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다. 다음 CSDL에서는 위의 다이어그램에 표시된 `PublishedBy` 연결을 정의합니다.  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>참고자료

- [엔터티 데이터 모델의 주요 개념](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)
