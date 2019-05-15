---
title: 네이티브 상호 운용성 - .NET
description: .NET에서 네이티브 구성 요소와 상호 작용하는 방법을 알아봅니다.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: b01ea9c17db6da32755309d9c1c2359cecaa1155
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65062718"
---
# <a name="native-interoperability"></a><span data-ttu-id="62f70-103">기본 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="62f70-103">Native interoperability</span></span>

<span data-ttu-id="62f70-104">다음 문서에서는 .NET에서 "네이티브 상호 운용성"을 수행하는 다양한 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="62f70-104">The following articles show the various ways of doing "native interoperability" in .NET.</span></span>

<span data-ttu-id="62f70-105">네이티브 코드를 호출하려는 이유 중 몇 가지는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="62f70-105">There are a few reasons why you'd want to call into native code:</span></span>

* <span data-ttu-id="62f70-106">운영 체제에서는 관리되는 클래스 라이브러리에 없는 많은 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="62f70-106">Operating systems come with a large volume of APIs that aren't present in the managed class libraries.</span></span> <span data-ttu-id="62f70-107">이러한 시나리오의 대표적인 예제로 하드웨어 또는 운영 체제 관리 기능에 대한 액세스를 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62f70-107">A prime example for this scenario would be access to hardware or operating system management functions.</span></span>
* <span data-ttu-id="62f70-108">포함된 다른 구성 요소와 통신하면 [JNI(Java 네이티브 인터페이스)](https://docs.oracle.com/javase/8/docs/technotes/guides/jni/) 또는 네이티브 구성 요소를 생성할 수 있는 다른 관리형 언어를 통해 노출된 Java 코드와 같은 C 스타일 ABI(네이티브 ABI)를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62f70-108">Communicating with other components that have or can produce C-style ABIs (native ABIs), such as Java code that is exposed via [Java Native Interface (JNI)](https://docs.oracle.com/javase/8/docs/technotes/guides/jni/) or any other managed language that could produce a native component.</span></span>
* <span data-ttu-id="62f70-109">Windows에서는 Microsoft Office 제품군 등 설치되는 대부분의 소프트웨어가 해당 프로그램을 나타내며 개발자가 해당 프로그램을 자동화하거나 사용할 수 있도록 하는 COM 구성 요소를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="62f70-109">On Windows, most of the software that gets installed, such as the Microsoft Office suite, registers COM components that represent their programs and allow developers to automate them or use them.</span></span> <span data-ttu-id="62f70-110">이 경우 기본 상호 운용성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="62f70-110">This also requires native interoperability.</span></span>

<span data-ttu-id="62f70-111">개발자가 기본 구성 요소를 조작하려 하거나 조작해야 하는 모든 잠재적인 상황 및 시나리오가 이전 목록에 포함된 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="62f70-111">The previous list doesn't cover all of the potential situations and scenarios in which the developer would want/like/need to interface with native components.</span></span> <span data-ttu-id="62f70-112">예를 들어 .NET 클래스 라이브러리는 기본 상호 운용성 지원을 사용하여 콘솔 지원 및 조작, 파일 시스템 액세스 등의 많은 API를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="62f70-112">.NET class library, for instance, uses the native interoperability support to implement a fair number of its APIs, like console support and manipulation, file system access and others.</span></span> <span data-ttu-id="62f70-113">그러나 필요한 경우 옵션이 있다는 점은 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="62f70-113">However, it's important to note that there's an option if needed.</span></span>

> [!NOTE]
> <span data-ttu-id="62f70-114">이 섹션의 예제는 대부분 .NET Core에 지원되는 세 가지 모두 플랫폼(Windows, Linux 및 macOS)에 대해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="62f70-114">Most of the examples in this section will be presented for all three supported platforms for .NET Core (Windows, Linux and macOS).</span></span> <span data-ttu-id="62f70-115">그러나 간략하고 명확한 일부 예제의 경우 Windows 파일 이름과 확장명(즉, 라이브러리의 경우 “dll”)을 사용하는 한 가지 샘플만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="62f70-115">However, for some short and illustrative examples, just one sample is shown that uses Windows filenames and extensions (that is, "dll" for libraries).</span></span> <span data-ttu-id="62f70-116">Linux 또는 macOS에서 해당 기능을 사용할 수 없다는 의미는 아니며, 단지 편의를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="62f70-116">This doesn't mean that those features aren't available on Linux or macOS, it was done merely for convenience sake.</span></span>

## <a name="see-also"></a><span data-ttu-id="62f70-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="62f70-117">See also</span></span>

- [<span data-ttu-id="62f70-118">P/Invoke(플랫폼 호출)</span><span class="sxs-lookup"><span data-stu-id="62f70-118">Platform Invoke (P/Invoke)</span></span>](pinvoke.md)
- [<span data-ttu-id="62f70-119">형식 마샬링</span><span class="sxs-lookup"><span data-stu-id="62f70-119">Type marshaling</span></span>](type-marshaling.md)
- [<span data-ttu-id="62f70-120">기본 상호 운용성 모범 사례</span><span class="sxs-lookup"><span data-stu-id="62f70-120">Native interoperability best practices</span></span>](best-practices.md)
