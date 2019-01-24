---
title: 내부 오류로 인해 전체 작업 시스템 이름을 가져올 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: df7a91ea5763c0fe4b7a1993bec29f1b1bb43fcc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54723297"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a>내부 오류로 인해 전체 작업 시스템 이름을 가져올 수 없습니다.
내부 오류로 인해 전체 작업 시스템 이름을 가져올 수 없습니다. 이는 현재 컴퓨터에 존재하지 않는 WMI에 의해 발생할 수 있습니다.  
  
 `My.Computer.Info.OSFullName` 속성 호출이 실패했습니다. 현재 컴퓨터에 WMI(Windows Management Instrumentation)가 설치되지 않아서 이 오류가 발생했을 수 있습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  `Try...Catch` 속성을 호출하는 주변에 `My.Computer.Info.OSFullName` 블록을 추가합니다.  
  
2.  WMI 및 설치 하는 방법에 대 한 자세한 내용은 이동한 후 "Windows Management Instrumentation Core"를 검색 합니다.  
  
## <a name="see-also"></a>참고자료
- [My.Computer.Info.OSFullName](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)
- [Visual Basic에서 예외 및 오류 처리](https://msdn.microsoft.com/library/3e351e73-cf23-40ab-8b60-05794160529e)
- [Try...Catch...Finally 문](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
