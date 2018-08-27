---
title: My.Resources 및 My.Settings를 사용한 신속한 응용 프로그램 개발(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: 7dbb15c43d044e21c9823c4a1652b0408006e5c3
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932569"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a><span data-ttu-id="3d2e2-102">My.Resources 및 My.Settings를 사용한 신속한 응용 프로그램 개발(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d2e2-102">Rapid Application Development with My.Resources and My.Settings (Visual Basic)</span></span>
<span data-ttu-id="3d2e2-103">`My.Resources` 개체 응용 프로그램의 리소스에 대 한 액세스를 제공 하며, 응용 프로그램에 대 한 리소스를 동적으로 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2e2-103">The `My.Resources` object provides access to the application's resources and allows you to dynamically retrieve resources for your application.</span></span>  
  
## <a name="retrieving-resources"></a><span data-ttu-id="3d2e2-104">리소스 검색</span><span class="sxs-lookup"><span data-stu-id="3d2e2-104">Retrieving Resources</span></span>  
 <span data-ttu-id="3d2e2-105">다양 한 오디오 파일, 아이콘, 이미지 및 문자열 같은 리소스를 통해 검색할 수 있습니다는 `My.Resources` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2e2-105">A number of resources such as audio files, icons, images, and strings can be retrieved through the `My.Resources` object.</span></span> <span data-ttu-id="3d2e2-106">예를 들어, 응용 프로그램의 문화권 관련 리소스 파일을 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2e2-106">For example, you can access the application's culture-specific resource files.</span></span> <span data-ttu-id="3d2e2-107">다음 예제에서는 명명 된 아이콘을 폼의 아이콘 설정 `Form1Icon` 응용 프로그램의 리소스 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2e2-107">The following example sets the icon of the form to the icon named `Form1Icon` stored in the application's resource file.</span></span>  
  
 [!code-vb[VbVbcnMy#7](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/rapid-application-development-with-my-resources-and-my-settings_1.vb)]  
  
 <span data-ttu-id="3d2e2-108">`My.Resources` 개체는 전역 리소스만 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2e2-108">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="3d2e2-109">폼과 관련 된 리소스 파일에 대 한 액세스를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2e2-109">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="3d2e2-110">폼에서 폼 리소스에 액세스 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2e2-110">You must access the form resources from the form.</span></span>  
  
 <span data-ttu-id="3d2e2-111">마찬가지로,는 `My.Settings` 개체 응용 프로그램의 설정에 대 한 액세스를 제공 하 고 동적으로 저장 하 고 속성 설정 및 응용 프로그램에 대 한 다른 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2e2-111">Similarly, the `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="3d2e2-112">자세한 내용은 [My.Resources 개체](../../../visual-basic/language-reference/objects/my-resources-object.md) 하 고 [My.Settings 개체](../../../visual-basic/language-reference/objects/my-settings-object.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2e2-112">For more information, see [My.Resources Object](../../../visual-basic/language-reference/objects/my-resources-object.md) and [My.Settings Object](../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d2e2-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d2e2-113">See Also</span></span>  
 [<span data-ttu-id="3d2e2-114">My.Resources 개체</span><span class="sxs-lookup"><span data-stu-id="3d2e2-114">My.Resources Object</span></span>](../../../visual-basic/language-reference/objects/my-resources-object.md)  
 [<span data-ttu-id="3d2e2-115">My.Settings 개체</span><span class="sxs-lookup"><span data-stu-id="3d2e2-115">My.Settings Object</span></span>](../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [<span data-ttu-id="3d2e2-116">응용 프로그램 설정 액세스</span><span class="sxs-lookup"><span data-stu-id="3d2e2-116">Accessing Application Settings</span></span>](../../../visual-basic/developing-apps/programming/app-settings/index.md)
