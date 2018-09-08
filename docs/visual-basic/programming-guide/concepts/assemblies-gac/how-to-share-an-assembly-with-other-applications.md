---
title: '방법: 다른 응용 프로그램 (Visual Basic)를 사용 하 여 어셈블리 공유'
ms.date: 07/20/2015
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
ms.openlocfilehash: 3d29a3558a64c02fc8c59035f2fee5c64c4a776f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44200144"
---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a><span data-ttu-id="da241-102">방법: 다른 응용 프로그램 (Visual Basic)를 사용 하 여 어셈블리 공유</span><span class="sxs-lookup"><span data-stu-id="da241-102">How to: Share an Assembly with Other Applications (Visual Basic)</span></span>
<span data-ttu-id="da241-103">어셈블리는 전용이거나 공유될 수 있습니다. 기본적으로 대부분의 간단한 프로그램은 다른 응용 프로그램에서 사용되지 않으므로 전용 어셈블리로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="da241-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="da241-104">다른 응용 프로그램과 어셈블리를 공유하려면 GAC([전역 어셈블리 캐시](../../../../framework/app-domains/gac.md))에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da241-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="da241-105">어셈블리 공유</span><span class="sxs-lookup"><span data-stu-id="da241-105">Sharing an assembly</span></span>  
  
1.  <span data-ttu-id="da241-106">어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="da241-106">Create your assembly.</span></span> <span data-ttu-id="da241-107">자세한 내용은 [어셈블리 만들기](../../../../framework/app-domains/create-assemblies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da241-107">For more information, see [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md).</span></span>  
  
2.  <span data-ttu-id="da241-108">어셈블리에 강력한 이름을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="da241-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="da241-109">자세한 내용은 [방법: 강력한 이름으로 어셈블리 서명](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da241-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
3.  <span data-ttu-id="da241-110">어셈블리에 버전 정보를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="da241-110">Assign version information to your assembly.</span></span> <span data-ttu-id="da241-111">자세한 내용은 [어셈블리 버전 관리](../../../../framework/app-domains/assembly-versioning.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da241-111">For more information, see [Assembly Versioning](../../../../framework/app-domains/assembly-versioning.md).</span></span>  
  
4.  <span data-ttu-id="da241-112">전역 어셈블리 캐시에 어셈블리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="da241-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="da241-113">자세한 내용은 [방법: 전역 어셈블리 캐시에 어셈블리 설치](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da241-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span></span>  
  
5.  <span data-ttu-id="da241-114">다른 응용 프로그램에서 어셈블리에 포함된 형식에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="da241-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="da241-115">자세한 내용은 [방법: 강력한 이름의 어셈블리 참조](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da241-115">For more information, see [How to: Reference a Strong-Named Assembly](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da241-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="da241-116">See also</span></span>

- [<span data-ttu-id="da241-117">프로그래밍 개념</span><span class="sxs-lookup"><span data-stu-id="da241-117">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="da241-118">어셈블리와 전역 어셈블리 캐시(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da241-118">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
- [<span data-ttu-id="da241-119">어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="da241-119">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)
