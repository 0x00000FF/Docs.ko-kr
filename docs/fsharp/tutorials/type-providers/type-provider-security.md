---
title: "형식 공급자 보안"
description: "형식 공급자에 대 한 트러스트 설정을 변경 하는 방법을 포함 하 여 F # 형식 공급자 보안에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9c5a8a1f-5a31-490d-83c0-8beabda75c78
ms.openlocfilehash: c8f03ee90d4dce1d3484a9dfe8951d500d509a2b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="type-provider-security"></a>형식 공급자 보안

형식 공급자는 (Dll) F # 프로젝트 또는 스크립트에서 참조 하는 어셈블리 외부 데이터 원본에 연결 하 고 F # 형식 환경에이 형식 정보를 노출 하는 코드가 들어 있습니다. 일반적으로 참조 된 어셈블리의 코드에서에서 컴파일 및 다음 코드를 실행 (또는 스크립트의 경우 코드는 F # Interactive로 보내기) 하는 경우에 실행 됩니다. 그러나 형식 공급자 어셈블리의 코드 편집기에서 단순히 찾아볼 때 Visual Studio 내 실행 됩니다. 이 형식 공급자 등 및 요약 정보 도구 설명, IntelliSense 완성 등 편집기에 추가 정보를 추가 하기 위해 실행 해야 하기 때문에 발생 합니다. 결과적으로, 추가 보안 고려 사항이 형식에 대 한 공급자 어셈블리를 Visual Studio 프로세스 내부에 자동으로 실행 하기 때문입니다.


## <a name="security-warning-dialog"></a>보안 경고 대화 상자
특정 형식 공급자 어셈블리를 사용 하 여 처음으로, Visual Studio 형식 공급자가 실행 되려고 함을 경고 하는 보안 대화 상자를 표시 합니다. Visual Studio에서 형식 공급자를 로드 하기 전에이 특정 공급자를 신뢰 하는 경우 수를 제공 합니다. ""형식 공급자의 소스를 신뢰 하는 경우 다음 I 트러스트 선택이 형식 공급자입니다. 형식 공급자의 소스를 신뢰 하지 않는 경우 다음 선택 "I" 신뢰 하지 않습니다이 형식 공급자입니다. 공급자를 신뢰를 사용 하면 Visual Studio 내에서 실행 하 고 IntelliSense를 제공 하 고 기능을 작성 합니다. 하지만 악성 자체 형식 공급자 인 경우 해당 코드 실행을 손상 시킬 수 컴퓨터.

프로젝트가 형식 공급자를 신뢰 하지 대화 상자에서 선택한를 참조 하는 코드를 포함 하는 경우 다음 컴파일 타임에 경우 컴파일러는 보고 형식 공급자를 신뢰할 수 있는지 여부를 나타내는 오류가 발생 합니다. 신뢰할 수 없는 형식 공급자에 의존 하는 모든 형식은 빨간색 물결선으로 표시 됩니다. 편집기에서 코드를 찾아보려면 안전 합니다.

Visual Studio에서 직접 신뢰 설정을 변경 하려는 경우 다음 단계를 수행 합니다.


#### <a name="to-change-the-trust-settings-for-type-providers"></a>형식 공급자에 대 한 트러스트 설정을 변경 하려면

1. 에 `Tools` 메뉴 선택 `Options`, 확장의 `F# Tools` 노드.
<br />

2. 선택 `Type Providers`, 형식 공급자의 목록에서 신뢰 하는 형식 공급자에 대 한 확인란을 선택 하 고 신뢰 하지 않는 것에 대 한 확인란의 선택을 취소 하 고 있습니다.
<br />


## <a name="see-also"></a>참고 항목
[형식 공급자](index.md)
