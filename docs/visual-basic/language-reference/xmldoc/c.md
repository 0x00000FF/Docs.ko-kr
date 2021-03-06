---
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 857ea1ccca4d74daf65bba03845004561afefd55
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348506"
---
# <a name="c-visual-basic"></a>\<c > (Visual Basic)
설명의 텍스트가 코드 임을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---|---|  
|`text`|코드로 표시하려는 텍스트입니다.|  
  
## <a name="remarks"></a>주의  
 `<c>` 태그는 설명 내의 텍스트를 코드로 표시 하도록 지정 하는 방법을 제공 합니다. 여러 줄을 코드로 지정하려면 [\<code>](../../../visual-basic/language-reference/xmldoc/code.md)를 사용합니다.  
  
 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 요약 섹션의 `<c>` 태그를 사용 하 여 `Counter` 코드 임을 표시 합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>참고 항목

- [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/index.md)
