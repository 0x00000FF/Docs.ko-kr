---
title: 참조 어셈블리에 필요한 &#39; &lt;assemblyidentity&gt; &#39; 형식이 포함 된 &#39; &lt;typename&gt;&#39;, 하지만 간의 모호성으로 인해 적합 한 참조를 찾을 수 없습니다 프로젝트 &#39; &lt;projectname1&gt; &#39; 및 &#39; &lt;projectname2&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30969
- vbc30969
helpviewer_keywords:
- BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
ms.openlocfilehash: 1a0c2a2fd235026729901153a0c0c300f914a78f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54553011"
---
# <a name="reference-required-to-assembly-39ltassemblyidentitygt39-containing-type-39lttypenamegt39-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-39ltprojectname1gt39-and-39ltprojectname2gt39"></a>참조 어셈블리에 필요한 &#39; &lt;assemblyidentity&gt; &#39; 형식이 포함 된 &#39; &lt;typename&gt;&#39;, 하지만 간의 모호성으로 인해 적합 한 참조를 찾을 수 없습니다 프로젝트 &#39; &lt;projectname1&gt; &#39; 및 &#39; &lt;projectname2&gt;&#39;
식은 프로젝트 외부에 정의된 클래스, 구조체, 인터페이스, 열거형 또는 대리자와 같은 형식을 사용합니다. 그러나 해당 형식을 정의하는 둘 이상의 어셈블리에 대한 프로젝트 참조가 있습니다.  
  
 인용된 프로젝트는 이름이 동일한 어셈블리를 생성합니다. 따라서 컴파일러에서 사용자가 액세스하려는 형식에 사용할 어셈블리를 확인할 수 없습니다.  
  
 다른 어셈블리에 정의 된 형식에 액세스 하려면 해당 어셈블리에 대 한 참조를 Visual Basic 컴파일러에 있어야 합니다. 이 참조는 프로젝트 간의 순환 참조를 발생시키지 않는 명확한 단일 참조여야 합니다.  
  
 **오류 ID:** BC30969  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  참조할 프로젝트에 가장 적합한 어셈블리를 생성하는 프로젝트를 결정합니다. 이러한 결정을 위해 파일 접근성 및 업데이트 빈도 등의 조건을 사용할 수 있습니다.  
  
2.  프로젝트 속성에서 사용 중인 형식을 정의하는 어셈블리가 포함된 파일에 대한 참조를 추가합니다.  
  
## <a name="see-also"></a>참고자료
- [프로젝트의 참조 관리](/visualstudio/ide/managing-references-in-a-project)
- [선언된 요소 참조](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties)
- [끊어진 참조 문제 해결](/visualstudio/ide/troubleshooting-broken-references)
