---
title: XML에서 데이터 형식 클래스 생성
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: b99bb40105398dbd91b910c4a19828d069c3d9e7
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380216"
---
# <a name="generating-data-type-classes-from-xml"></a>XML에서 데이터 형식 클래스 생성
.NET framework 4.5에서 XML 데이터 형식 클래스를 생성 하는 새 기능이 포함 됩니다. 이 항목에서는.NET 블로그 RSS 피드를 자동으로 생성 하는 방법을 설명 합니다.  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a>피드.NET 블로그 rss에서 XML 가져오기  
  
1. Internet Explorer로 이동 합니다 [.NET 블로그 RSS 피드](https://devblogs.microsoft.com/dotnet/feed/)합니다.  
  
2. 페이지를 마우스 오른쪽 단추로 누르고 **소스 보기**합니다.  
  
3. 키를 눌러 피드의 텍스트를 복사 **Ctrl + A** 모든 텍스트를 선택 하 고 **Ctrl + C** 복사할 합니다.  
  
### <a name="creating-the-data-types"></a>데이터 형식 만들기  
  
1. 프록시를 사용할 코드 파일을 엽니다. 이 파일에는.NET Framework 4.5 프로젝트의 일부 여야 합니다.  
  
2. 커서를 기존 클래스 외부에 있는 파일의 한 위치에 배치합니다.  
  
3. 선택 **편집할**를 **하 여 붙여넣기**를 **XML을 클래스로 붙여넣기**합니다.  
  
4. 이라는 클래스 `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` 고 `rssChannelItemGuid` rss 피드에 요소에 액세스 하는 것에 대 한 필요한 멤버를 사용 하 여 만들어집니다.  
  
### <a name="using-the-generated-classes"></a>생성된 클래스 사용  
  
1. 생성된 클래스는 다른 클래스와 마찬가지로 코드에서 사용할 수 있습니다. 다음 코드 예제에서는 `rssChannelImage` 클래스의 새 인스턴스를 반환합니다.  
  
    ```  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
    ```
