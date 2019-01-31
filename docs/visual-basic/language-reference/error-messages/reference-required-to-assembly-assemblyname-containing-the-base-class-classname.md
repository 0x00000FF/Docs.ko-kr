---
title: 기본 클래스 '<assemblyname>'을(를) 포함하는 '<classname>' 어셈블리에 대한 참조가 필요합니다.
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: 54848fdbd2547fe021f0386843f9666760396cb0
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273282"
---
# <a name="reference-required-to-assembly-assemblyname-containing-the-base-class-classname"></a><span data-ttu-id="584bb-102">참조 어셈블리에 필요한 '\<assemblyname >' 기본 클래스의 포함 된\<응용 프로그램 이름 >'</span><span class="sxs-lookup"><span data-stu-id="584bb-102">Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'</span></span>
<span data-ttu-id="584bb-103">참조 어셈블리에 필요한 '\<assemblyname >' 기본 클래스의 포함 된\<classname >'입니다.</span><span class="sxs-lookup"><span data-stu-id="584bb-103">Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'.</span></span> <span data-ttu-id="584bb-104">하나를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="584bb-104">Add one to your project.</span></span>  
  
 <span data-ttu-id="584bb-105">클래스는 프로젝트에서 직접 참조하지 않는 어셈블리 또는 DLL(동적 연결 라이브러리)에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="584bb-105">The class is defined in a dynamic-link library (DLL) or assembly that is not directly referenced in your project.</span></span> <span data-ttu-id="584bb-106">Visual Basic 컴파일러는 클래스는 둘 이상의 DLL 또는 어셈블리에서 정의 되는 경우 모호성을 방지 하기에 대 한 참조가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="584bb-106">The Visual Basic compiler requires a reference to avoid ambiguity in case the class is defined in more than one DLL or assembly.</span></span>  
  
 <span data-ttu-id="584bb-107">**오류 ID:** BC30007</span><span class="sxs-lookup"><span data-stu-id="584bb-107">**Error ID:** BC30007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="584bb-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="584bb-108">To correct this error</span></span>  
  
-   <span data-ttu-id="584bb-109">참조되지 않은 DLL 또는 어셈블리 이름을 프로젝트 참조에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="584bb-109">Include the name of the unreferenced DLL or assembly in your project references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="584bb-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="584bb-110">See also</span></span>

- [<span data-ttu-id="584bb-111">프로젝트의 참조 관리</span><span class="sxs-lookup"><span data-stu-id="584bb-111">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="584bb-112">끊어진 참조 문제 해결</span><span class="sxs-lookup"><span data-stu-id="584bb-112">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
