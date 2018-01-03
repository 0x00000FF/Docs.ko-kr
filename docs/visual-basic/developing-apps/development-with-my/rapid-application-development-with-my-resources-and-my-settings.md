---
title: "My.Resources 및 My.Settings를 사용한 신속한 응용 프로그램 개발(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7339afdc35341739b592b2a327094754031c346c
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a><span data-ttu-id="68922-102">My.Resources 및 My.Settings를 사용한 신속한 응용 프로그램 개발(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68922-102">Rapid Application Development with My.Resources and My.Settings (Visual Basic)</span></span>
<span data-ttu-id="68922-103">`My.Resources` 개체 응용 프로그램의 리소스에 대 한 액세스를 제공 하며, 응용 프로그램에 대 한 리소스를 동적으로 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68922-103">The `My.Resources` object provides access to the application's resources and allows you to dynamically retrieve resources for your application.</span></span>  
  
## <a name="retrieving-resources"></a><span data-ttu-id="68922-104">리소스 검색</span><span class="sxs-lookup"><span data-stu-id="68922-104">Retrieving Resources</span></span>  
 <span data-ttu-id="68922-105">다양 한 리소스 오디오 파일, 아이콘, 이미지, 문자열 등을 통해 검색할 수 있습니다는 `My.Resources` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="68922-105">A number of resources such as audio files, icons, images, and strings can be retrieved through the `My.Resources` object.</span></span> <span data-ttu-id="68922-106">예를 들어 응용 프로그램의 문화권 관련 리소스 파일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68922-106">For example, you can access the application's culture-specific resource files.</span></span> <span data-ttu-id="68922-107">다음 예제에서는 명명 된 아이콘을 폼의 아이콘 설정 `Form1Icon` 응용 프로그램의 리소스 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="68922-107">The following example sets the icon of the form to the icon named `Form1Icon` stored in the application's resource file.</span></span>  
  
 [!code-vb[VbVbcnMy#7](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/rapid-application-development-with-my-resources-and-my-settings_1.vb)]  
  
 <span data-ttu-id="68922-108">`My.Resources` 만 전역 리소스를 노출 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="68922-108">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="68922-109">폼과 연관 된 리소스 파일에 대 한 액세스를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68922-109">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="68922-110">폼에서 폼 리소스에 액세스 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68922-110">You must access the form resources from the form.</span></span>  
  
 <span data-ttu-id="68922-111">마찬가지로,는 `My.Settings` 개체 응용 프로그램의 설정에 대 한 액세스를 제공 하 고 동적으로 저장 하 고 속성 설정 및 응용 프로그램에 대 한 기타 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68922-111">Similarly, the `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="68922-112">자세한 내용은 참조 [My.Resources 개체](../../../visual-basic/language-reference/objects/my-resources-object.md) 및 [My.Settings 개체](../../../visual-basic/language-reference/objects/my-settings-object.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="68922-112">For more information, see [My.Resources Object](../../../visual-basic/language-reference/objects/my-resources-object.md) and [My.Settings Object](../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68922-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68922-113">See Also</span></span>  
 [<span data-ttu-id="68922-114">My.Resources 개체</span><span class="sxs-lookup"><span data-stu-id="68922-114">My.Resources Object</span></span>](../../../visual-basic/language-reference/objects/my-resources-object.md)  
 [<span data-ttu-id="68922-115">My.Settings 개체</span><span class="sxs-lookup"><span data-stu-id="68922-115">My.Settings Object</span></span>](../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [<span data-ttu-id="68922-116">응용 프로그램 설정 액세스</span><span class="sxs-lookup"><span data-stu-id="68922-116">Accessing Application Settings</span></span>](../../../visual-basic/developing-apps/programming/app-settings/accessing-application-settings.md)
