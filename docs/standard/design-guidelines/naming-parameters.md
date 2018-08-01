---
title: 매개 변수 이름 지정
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed6b96bb05c52de4bfd8b6ad6b972c9d22ca66da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570489"
---
# <a name="naming-parameters"></a>매개 변수 이름 지정
가독성의 이유를 벗어나는 Intellisense 및 검색 기능을 하는 클래스를 제공 하는 비주얼 디자인 도구 매개 변수는 설명서 및 디자이너에 표시 되기 때문에 매개 변수 이름에 대 한 지침을 수행 해야 합니다.  
  
 **✓ DO** camelCasing 매개 변수 이름에 사용할 수 있습니다.  
  
 **✓ DO** 설명이 포함 된 매개 변수 이름을 사용 합니다.  
  
 **✓ CONSIDER** 매개 변수의 형식 보다는 매개 변수의 의미에 따라 이름을 사용 합니다.  
  
### <a name="naming-operator-overload-parameters"></a>연산자 오버 로드 매개 변수 이름 지정  
 **✓ DO** 사용 `left` 및 `right` 이항 연산자 오버 로드 매개 변수 이름은 매개 변수를 아무 의미가 없는 경우에 대 한 합니다.  
  
 **✓ DO** 사용 `value` 에 대 한 단항 연산자 오버 로드 매개 변수 이름은 매개 변수를 아무 의미가 없는 경우.  
  
 **✓ CONSIDER** 연산자에 대 한 의미 있는 이름을 추가 되므로 중요 한 가치 경우 매개 변수를 재정의 합니다.  
  
 **X DO NOT** 오버 로드 매개 변수 이름을 사용 하 여 약어 또는 연산자에 대 한 숫자 인덱스입니다.  
  
 *Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)  
 [명명 지침](../../../docs/standard/design-guidelines/naming-guidelines.md)
