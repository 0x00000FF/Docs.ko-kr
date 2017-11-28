---
title: "이벤트 로그에 대해 잘못된 이름을 지정했습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: b1b158bd-f13f-4371-a8af-31c0e86ae6be
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fc5a2e93541063a129efaa0ce08fc19a98372126
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="an-invalid-name-was-specified-for-the-event-log"></a>이벤트 로그에 대해 잘못된 이름을 지정했습니다.
이벤트 로그에 대해 잘못된 이름을 지정했습니다. 일반적으로 이름, 빈 파일 이름 또는 너무 긴 파일 이름에 잘못된 문자가 포함되어 발생합니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   지정된 이름이 8자보다 긴 경우 다른 이벤트 로그 이름과 충돌하지 않아야 합니다. 이름이 고유한지 확인할 때 처음 8자만 비교합니다.  
  
-   경로를 제공하는 경우 제대로 구문 분석되어야 합니다.  
  
-   이름에 잘못된 문자가 없는지 확인합니다. `<`, `>`, `:`, `"`, `/`, `\`및 `|`는 파일 이름에 사용할 수 없는 문자입니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 파일 경로의 구문 분석](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)  
 [방법: 파일 이름 바꾸기](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)  
 [방법: 만들기 및 사용자 지정 이벤트 로그 제거](http://msdn.microsoft.com/en-us/af9b7da0-80c7-46ac-b7f7-897063ddd503)
