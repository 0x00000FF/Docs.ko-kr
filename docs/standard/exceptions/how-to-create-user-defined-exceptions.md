---
title: "방법: 사용자 정의 예외 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- user-defined exceptions
- exceptions, examples
- exceptions, user-defined
ms.assetid: 25819a5a-f915-4fc8-b924-a76915674e04
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 68f2093e32fe2f9fbc0f826d2293a7b7f2e3c238
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2017
---
# <a name="how-to-create-user-defined-exceptions"></a>사용자 정의 예외를 만드는 방법

.NET에서는 기본 클래스 <xref:System.Exception>에서 최종적으로 파생되는 예외 클래스의 계층 구조를 제공합니다. 그러나 사용자 요구를 충족하는 미리 정의된 예외가 없는 경우 <xref:System.Exception> 클래스에서 파생하여 사용자 고유의 예외 클래스를 만들 수 있습니다.

사용자 고유의 예외를 만드는 경우 다음 예제와 같이 사용자 정의 예외의 클래스 이름을 "Exception" 단어로 끝내고 세 가지 공통 생성자를 구현합니다. 예제에서는 `EmployeeListNotFoundException`이라는 새 예외 클래스를 정의합니다. 클래스는 <xref:System.Exception>에서 파생되며 세 가지 생성자를 포함합니다.

[!code-cpp[dg_exceptionDesign#14](../../../samples/snippets/cpp/VS_Snippets_CLR/dg_exceptionDesign/cpp/example2.cpp#14)]
[!code-csharp[dg_exceptionDesign#14](../../../samples/snippets/csharp/VS_Snippets_CLR/dg_exceptionDesign/cs/example2.cs#14)]
[!code-vb[dg_exceptionDesign#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/dg_exceptionDesign/vb/example2.vb#14)]  

> [!NOTE]
> 원격을 사용하는 경우 사용자 정의 예외에 대한 메타데이터를 서버(호출 수신자) 및 클라이언트(프록시 개체 또는 호출자)에서 사용할 수 있는지 확인해야 합니다. 자세한 내용은 [예외에 대한 모범 사례](best-practices-for-exceptions.md)를 참조하세요.

## <a name="see-also"></a>참고 항목  
[예외](index.md)
