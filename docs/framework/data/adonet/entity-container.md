---
title: 엔터티 컨테이너(entity container)
ms.date: 03/30/2017
ms.assetid: 16e80405-2c75-42fc-b0e4-b1df53b1c584
ms.openlocfilehash: 4a629a800df63c67dc17d3fc1531a9862861e9c4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144068"
---
# <a name="entity-container"></a>엔터티 컨테이너(entity container)
*엔터티 컨테이너* 의 논리적 그룹인 [엔터티 집합](../../../../docs/framework/data/adonet/entity-set.md), [연결 집합](../../../../docs/framework/data/adonet/association-set.md), 및 [imports 함수](../../../../docs/framework/data/adonet/model-declared-function.md)합니다.  
  
 개념적 모델에 정의된 엔터티 컨테이너에 대해 다음 조건이 충족되어야 합니다.  
  
-   각 개념적 모델에 엔터티 컨테이너가 하나 이상 정의되어 있어야 합니다.  
  
-   각 개념적 모델 내에서 엔터티 컨테이너의 이름이 고유해야 합니다.  
  
 엔터티 컨테이너는 하나 이상의 네임스페이스에 정의된 엔터티 형식이나 연결을 사용하는 엔터티 집합 또는 연결 집합을 정의할 수 있습니다. 자세한 내용은 참조 하세요. [엔터티 데이터 모델: 네임 스페이스](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md)합니다.  
  
## <a name="example"></a>예제  
 다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다.  자세한 내용은 다음 예제를 참조하세요.  
  
 ![세 가지 엔터티 형식을 사용 하 여 예제 모델](./media/entity-container/example-model-three-entity-types.gif)  
  
 다이어그램에는 엔터티 컨테이너 정보가 표시되지 않지만 개념적 모델에서 엔터티 컨테이너를 정의해야 합니다. 합니다 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어 이라고 하는 DSL을 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다. 다음 CSDL에서는 위의 다이어그램에 표시된 개념적 모델의 엔터티 컨테이너를 정의합니다. 엔터티 컨테이너 이름은 XML 특성에 정의되어 있습니다.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a>참고자료

- [엔터티 데이터 모델의 주요 개념](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)
