---
title: goto 문(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
ms.openlocfilehash: d4fd9f1f26b82b409d704c45e4bcf18cceef8282
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507525"
---
# <a name="goto-c-reference"></a>goto(C# 참조)

`goto` 문은 레이블 지정된 문으로 직접 프로그램 컨트롤을 전송합니다.

`goto`는 일반적으로 `switch` 문에서 switch-case 레이블 또는 기본 레이블로 컨트롤을 전송하는 데 사용됩니다.

`goto` 문은 많이 중첩된 루프를 회피하는 데도 유용합니다.

## <a name="example"></a>예

다음 예제에서는 [switch](switch.md) 문에서 `goto`의 사용 방법을 보여 줍니다.

[!code-csharp[csrefKeywordsJump#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#4)]

## <a name="example"></a>예

다음 예제에서는 `goto`를 사용하여 중첩된 루프에서 벗어나는 방법을 보여 줍니다.

[!code-csharp[csrefKeywordsJump#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#5)]

## <a name="c-language-specification"></a>C# 언어 사양

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)  
- [C# 프로그래밍 가이드](../../programming-guide/index.md)  
- [C# 키워드](index.md)  
- [goto 문(C++)](/cpp/cpp/goto-statement-cpp)  
- [점프 문](jump-statements.md)  
