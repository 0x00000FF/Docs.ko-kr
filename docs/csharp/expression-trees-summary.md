---
title: "식 트리 요약"
description: "식 트리를 사용하여 코드를 데이터로 해석하고 해당 코드를 기반으로 하는 새 기능을 빌드하는 동적 프로그램을 만드는 방법을 요약합니다."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: eb687ebd-1149-4453-9fc1-12a084495a66
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8088ce0c138cdb05a6e4a4fb6467e43efd252ba7
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="expression-trees-summary"></a>식 트리 요약

[이전 -- 식 변환](expression-trees-translating.md)

이 시리즈에서는 *식 트리*를 사용하여 코드를 데이터로 해석하고 해당 코드에 기반한 새 기능을 구축하는 동적 프로그램을 만드는 방법을 살펴보았습니다.

식 트리를 검사하여 알고리즘의 의도를 파악할 수 있습니다. 해당 코드 검사 이상을 수행할 수 있습니다. 원래 코드의 수정된 버전을 나타내는 새로운 식 트리를 작성할 수 있습니다.

또한 식 트리를 사용하여 알고리즘을 확인하고 해당 알고리즘을 다른 언어나 환경으로 변환할 수 있습니다. 

## <a name="limitations"></a>제한 사항

식 트리로 잘 변환되지 않는 최신 C# 언어 요소가 몇 가지 있습니다. 식 트리에는 `await` 식이나 `async` 람다 식이 포함될 수 없습니다. C# 6 릴리스에서 추가된 많은 기능이 식 트리에 작성된 대로 정확하게 나타나지 않습니다. 대신 최신 기능은 해당되는 이전 구문으로 식 트리에 노출됩니다. 생각만큼 큰 제한 사항이 아닐 수 있습니다. 실제로는 새로운 언어 기능이 도입되어도 식 트리를 해석하는 코드가 동일하게 작동할 수 있습니다.

이러한 제한 사항에도 불구하고 식 트리를 사용하면 데이터 구조로 표시되는 코드를 해석하고 수정하는 동적 알고리즘을 만들 수 있습니다. 식 트리는 강력한 도구이며 기능을 수행하기 위해 Entity Framework와 같은 풍부한 라이브러리를 사용하는 .NET 에코시스템의 기능 중 하나입니다.


