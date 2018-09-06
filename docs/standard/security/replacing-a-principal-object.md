---
title: Principal 개체 바꾸기
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- principal objects, replacing
- security [.NET Framework], replacing principal objects
- security [.NET Framework], principals
ms.assetid: c323687e-b196-487b-beba-f38f9b3f961b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bfcd912fc16aa8d4b89a4f455d65b0294593cead
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43886528"
---
# <a name="replacing-a-principal-object"></a>Principal 개체 바꾸기
인증 서비스를 제공하는 응용 프로그램은 지정된 스레드에 대해 **Principal** 개체(<xref:System.Security.Principal.IPrincipal>)를 대체할 수 있어야 합니다. 또한 보안 시스템은 **Principal** 개체를 대체하는 기능을 보호할 수 있어야 합니다. 악의적으로 연결된 잘못된 **Principal** 은 허위 ID 또는 역할을 요청함으로써 응용 프로그램의 보안을 손상시킵니다. 따라서 있는 필요한 응용 프로그램 대체 하는 기능 **주체** 개체를 부여 해야 합니다는 <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> 보안 주체 컨트롤에 대 한 개체입니다. (이 사용 권한은 역할을 기반으로 하는 보안 검사를 수행하거나 **Principal** 개체를 만들 때는 필요하지 않습니다.)  
  
 현재 **Principal** 개체는 다음과 같은 작업을 수행하여 대체할 수 있습니다.  
  
1.  대체 **Principal** 개체 및 연결된 **Identity** 개체를 만듭니다.  
  
2.  새 **Principal** 개체를 호출 컨텍스트에 연결합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 일반적인 보안 주체 개체를 만들고 이 개체를 사용하여 스레드의 보안 주체를 설정하는 방법을 보여줍니다.  
  
 [!code-csharp[SetCurrentPrincipal#1](../../../samples/snippets/csharp/VS_Snippets_CLR/SetCurrentPrincipal/CS/program.cs#1)]
 [!code-vb[SetCurrentPrincipal#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/SetCurrentPrincipal/VB/program.vb#1)]  
  
## <a name="see-also"></a>참고자료

- <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType>  
- [Principal 개체 및 Identity 개체](../../../docs/standard/security/principal-and-identity-objects.md)
