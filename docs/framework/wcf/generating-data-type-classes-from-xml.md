---
title: XML에서 데이터 형식 클래스 생성
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: 6b38a0aea3101c70b3c3ec0c8feb4ee88018b64e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498669"
---
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="83d0b-102">XML에서 데이터 형식 클래스 생성</span><span class="sxs-lookup"><span data-stu-id="83d0b-102">Generating Data Type Classes from XML</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<span data-ttu-id="83d0b-103">에는 XML에서 데이터 형식 클래스를 생성하는 새 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d0b-103"> includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="83d0b-104">이 항목에서는.NET 블로그 RSS 피드에 대 한 데이터 형식을 자동으로 생성 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="83d0b-104">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="83d0b-105">피드.NET 블로그 rss에서 XML 가져오기</span><span class="sxs-lookup"><span data-stu-id="83d0b-105">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1.  <span data-ttu-id="83d0b-106">Internet Explorer에서로 이동 된 [.NET 블로그 RSS 피드](https://blogs.msdn.microsoft.com/dotnet/feed/)합니다.</span><span class="sxs-lookup"><span data-stu-id="83d0b-106">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://blogs.msdn.microsoft.com/dotnet/feed/).</span></span>  
  
2.  <span data-ttu-id="83d0b-107">페이지를 마우스 오른쪽 단추로 클릭 하 고 선택 **소스 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="83d0b-107">Right-click the page and select **View Source**.</span></span>  
  
3.  <span data-ttu-id="83d0b-108">키를 눌러 피드의 텍스트를 복사 **Ctrl + A** 모든 텍스트를 선택 하 고 **Ctrl + C** 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="83d0b-108">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="83d0b-109">데이터 형식 만들기</span><span class="sxs-lookup"><span data-stu-id="83d0b-109">Creating the data types</span></span>  
  
1.  <span data-ttu-id="83d0b-110">프록시를 사용할 코드 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="83d0b-110">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="83d0b-111">이 파일은 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 프로젝트의 일부여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83d0b-111">This file should be part of a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="83d0b-112">커서를 기존 클래스 외부에 있는 파일의 한 위치에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="83d0b-112">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3.  <span data-ttu-id="83d0b-113">선택 **편집**, **하 여 붙여넣기**, **XML을 클래스로 붙여넣기**합니다.</span><span class="sxs-lookup"><span data-stu-id="83d0b-113">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4.  <span data-ttu-id="83d0b-114">이라는 클래스 `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` 및 `rssChannelItemGuid` RSS 피드의 요소에 액세스 하기 위해 필요한 멤버를 사용 하 여 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="83d0b-114">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="83d0b-115">생성된 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="83d0b-115">Using the generated classes</span></span>  
  
1.  <span data-ttu-id="83d0b-116">생성된 클래스는 다른 클래스와 마찬가지로 코드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d0b-116">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="83d0b-117">다음 코드 예제에서는 `rssChannelImage` 클래스의 새 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="83d0b-117">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
    ```
