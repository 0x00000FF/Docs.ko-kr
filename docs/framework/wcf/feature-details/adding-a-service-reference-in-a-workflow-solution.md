---
title: 워크플로 솔루션에 서비스 참조 추가
ms.date: 03/30/2017
ms.assetid: 83574cf3-9803-49bc-837f-432936dc9c76
ms.openlocfilehash: 9dcbf779d948f6d295c2a23f5a09efc5ac989cdd
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2018
ms.locfileid: "45972402"
---
# <a name="adding-a-service-reference-in-a-workflow-solution"></a>워크플로 솔루션에 서비스 참조 추가

워크플로 응용 프로그램에서 서비스 참조를 추가하는 작업은 일반적인 WCF 응용 프로그램과 약간 다르게 작동합니다. 선택 하면 **추가 > 서비스 참조** 및 서비스에 URL 지정, 메타 데이터를 다운로드 하 고 사용자 지정 활동에 대 한 참조를 추가 하는 WCF 워크플로 서비스를 WCF 서비스를 호출할 수 있도록 하 여 생성 됩니다. 서비스 참조를 추가한 후 생성된 활동이 빌드되도록 솔루션을 다시 빌드합니다. 솔루션을 다시 빌드한 후 생성된 활동이 워크플로 디자이너 도구 상자에 나타납니다. 그러나 워크플로 솔루션 내에서 서비스 참조를 추가하는 경우에만 이러한 과정이 진행됩니다. 다음 웹 캐스트에 다른 형식의 프로젝트에서 서비스 참조를 추가 하는 방법을 보여 줍니다. [웹 프로젝트의 워크플로에서 WCF 서비스 호출](https://go.microsoft.com/fwlink/?LinkId=207725)합니다.

동일한 작업 이름이 포함된 서비스에 대한 서비스 참조를 둘 이상 추가하면 문제가 발생합니다. 생성된 활동이 첫 번째 서비스 작업만 호출합니다. 이 문제를 해결하려면 해당 서비스 작업을 구분하도록 서비스 작업의 이름을 변경하거나 생성된 각 활동에서 엔드포인트 구성 이름을 변경합니다.

## <a name="see-also"></a>참고 항목

- [워크플로 서비스](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [방법: 다른 워크플로 서비스를 호출하는 워크플로 서비스 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-that-calls-another-workflow-service.md)
- [웹 프로젝트의 워크플로에서 WCF 서비스 호출](https://go.microsoft.com/fwlink/?LinkId=207725)
