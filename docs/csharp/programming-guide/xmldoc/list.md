---
title: <list> - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- list
- <list>
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
ms.openlocfilehash: a127509d603ada952b3d48d4bbc417db64f607ea
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55290175"
---
# <a name="list-c-programming-guide"></a>\<list>(C# 프로그래밍 가이드)
## <a name="syntax"></a>구문  
  
```xml  
<list type="bullet" | "number" | "table">  
    <listheader>  
        <term>term</term>  
        <description>description</description>  
    </listheader>  
    <item>  
        <term>term</term>  
        <description>description</description>  
    </item>  
</list>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `term`  
 `description`에서 정의되는, 정의할 용어입니다.  
  
 `description`  
 글머리 기호 또는 번호 매기기 목록의 항목이나 `term`의 정의입니다.  
  
## <a name="remarks"></a>주의  
 \<listheader> 블록은 테이블 또는 정의 목록의 머리글 행을 정의하는 데 사용됩니다. 테이블을 정의할 때는 머리글에 용어 항목만 제공하면 됩니다.  
  
 목록의 각 항목은 \<item> 블록을 사용하여 지정됩니다. 정의 목록을 만들 때는 `term`과 `description`을 모두 지정해야 합니다. 그러나 테이블, 글머리 기호 목록 또는 번호 매기기 목록의 경우 `description` 항목만 제공하면 됩니다.  
  
 목록 또는 테이블에 \<item> 블록을 필요한 개수만큼 포함할 수 있습니다.  
  
 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예  
 [!code-csharp[csProgGuideDocComments#6](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/list_1.cs)]  
  
## <a name="see-also"></a>참고 항목

- [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)
- [문서 주석에 대한 권장 태그](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
