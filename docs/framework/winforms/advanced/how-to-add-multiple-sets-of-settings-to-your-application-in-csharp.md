---
title: '방법: 응용 프로그램에 다중 설정 집합 추가C#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 5496d370890e019ae2b31835c95a9988f8d9bc18
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559413"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a><span data-ttu-id="5c409-102">방법: 응용 프로그램에 다중 설정 집합 추가C#</span><span class="sxs-lookup"><span data-stu-id="5c409-102">How To: Add Multiple Sets of Settings To Your Application in C#</span></span> #
<span data-ttu-id="5c409-103">경우에 따라 응용 프로그램의 여러 집합이 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5c409-103">In some cases, you might want to have multiple sets of settings in an application.</span></span> <span data-ttu-id="5c409-104">예를 들어 경우을 개발 하는 응용 프로그램 특정 그룹 설정에 자주 변경 하려면 필요한 수 있습니다 파일을 대량으로 바꿀 수 있도록 모든 단일 파일로 분리 하는 것이 좋습니다 다른 설정은 영향을 받지 않고 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c409-104">For example, if you are developing an application where a particular group of settings is expected to change frequently, it might be wise to separate them all into a single file so that the file can be replaced wholesale, leaving other settings unaffected.</span></span> <span data-ttu-id="5c409-105">Visual Studio를 사용 하면 여러 설정 집합을 프로젝트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c409-105">Visual Studio allows you to add multiple sets of settings to your project.</span></span> <span data-ttu-id="5c409-106">추가 설정 집합 Properties.Settings 개체를 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c409-106">Additional sets of settings can be accessed via the Properties.Settings object.</span></span>  
  
### <a name="to-add-an-additional-set-of-setting-to-your-application"></a><span data-ttu-id="5c409-107">응용 프로그램 설정의 추가 집합을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="5c409-107">To Add an Additional Set of Setting to your Application</span></span>  
  
1.  <span data-ttu-id="5c409-108">**프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c409-108">From the **Project** menu, choose **Add New Item**.</span></span> <span data-ttu-id="5c409-109">**새 항목 추가** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="5c409-109">The **Add New Item** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="5c409-110">에 **새 항목 추가** 대화 상자에서 **설정 파일**파일에 대 한 이름을 입력 하 고 클릭 **추가** 솔루션에 새 설정 파일을 추가 하려면.</span><span class="sxs-lookup"><span data-stu-id="5c409-110">In the **Add New Item** dialog box, select **Settings File**, type in a name for the file, and click **Add** to add a new settings file to your solution.</span></span>  
  
3.  <span data-ttu-id="5c409-111">**솔루션 탐색기**, 새 설정 파일을 끌어 합니다 **속성** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="5c409-111">In **Solution Explorer**, drag the new Settings file into the **Properties** folder.</span></span> <span data-ttu-id="5c409-112">이렇게 하면 새 설정을 코드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c409-112">This allows your new settings to be available in code.</span></span>  
  
4.  <span data-ttu-id="5c409-113">추가 하 고 설정을 사용 하 여이 파일의 다른 설정 파일.</span><span class="sxs-lookup"><span data-stu-id="5c409-113">Add and use settings in this file as you would any other settings file.</span></span> <span data-ttu-id="5c409-114">이 설정 그룹을 Properties.Settings 개체를 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c409-114">You can access this group of settings via the Properties.Settings object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c409-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="5c409-115">See also</span></span>
- [<span data-ttu-id="5c409-116">응용 프로그램 설정 및 사용자 설정 사용</span><span class="sxs-lookup"><span data-stu-id="5c409-116">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)
- [<span data-ttu-id="5c409-117">응용 프로그램 설정 개요</span><span class="sxs-lookup"><span data-stu-id="5c409-117">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
