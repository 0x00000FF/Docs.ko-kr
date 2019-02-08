---
title: 모델 선언 함수
ms.date: 03/30/2017
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
ms.openlocfilehash: 31efbab4b8323ff8cec9498fa20fa40b1efb819e
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55904069"
---
# <a name="model-declared-function"></a>모델 선언 함수
A *모델 선언 함수* 함수 개념적 모델에서 선언 되었지만 해당 개념적 모델에 정의 되지 않은입니다. 호스팅 또는 저장소 환경에서 함수를 정의할 수도 있습니다. 예를 들어, 모델 선언 함수를 데이터베이스에 정의된 함수에 매핑하여 개념적 모델에 서버 쪽 기능을 노출할 수 있습니다.  
  
 모델 선언 함수의 선언에는 다음 정보가 들어 있습니다.  
  
-   함수의 이름. (필수)  
  
-   반환 값의 형식 이 매개 변수는 선택 사항입니다.  
  
    > [!NOTE]
    >  반환 값을 지정하지 않으면 반환 형식은 void입니다.  
  
-   매개 변수 이름과 형식을 포함하는 매개 변수 정보 이 매개 변수는 선택 사항입니다.  
  
## <a name="example"></a>예제  
 합니다 [ADO.NET Entity Framework](./ef/index.md) 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 (DSL)를 사용 하 여 ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) 개념적 모델을 정의 합니다. CSDL 모델 선언 함수의 구현 하는 하나는 function import (사용 하는 [FunctionImport 요소](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)). 다음 CSDL에서는 함수 가져오기 정의를 사용하여 엔터티 컨테이너를 정의합니다. 반환 형식을 지정하지 않았으므로 함수의 반환 형식은 void입니다.  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a>참고자료
- [엔터티 데이터 모델의 주요 개념](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)
