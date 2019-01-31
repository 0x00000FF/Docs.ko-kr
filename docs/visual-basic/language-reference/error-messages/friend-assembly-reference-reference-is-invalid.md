---
title: Friend 어셈블리 참조 <reference>이(가) 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: ff2cdbebe13f6224209ef8da62600c99348c911b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286821"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a>Friend 어셈블리 참조 \<참조 > 올바르지 않습니다
Friend 어셈블리 참조 \<참조 > 올바르지 않습니다. 강력한 이름의 서명된 어셈블리는 InternalsVisibleTo 선언에 공개 키를 지정해야 합니다.  
  
 어셈블리 이름을 전달 합니다 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성 생성자에는 강력한 이름의 어셈블리를 식별 하지만 포함 되지 않습니다는 `PublicKey` 특성입니다.  
  
 **오류 ID:** BC31535  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  Friend 강력한 이름의 어셈블리에 대 한 공개 키를 결정 합니다. 어셈블리 이름의 부분에 전달 된 공개 키를 포함 합니다 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성 생성자를 사용 하 여는 `PublicKey` 특성입니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Reflection.AssemblyName>
- [Friend 어셈블리](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)


