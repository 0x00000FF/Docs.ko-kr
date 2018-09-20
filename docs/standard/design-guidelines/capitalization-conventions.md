---
title: 대/소문자 표기법
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 070fc69728c2cb38e465dab9f6f591a77a857531
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/20/2018
ms.locfileid: "46473313"
---
# <a name="capitalization-conventions"></a><span data-ttu-id="82b07-102">대/소문자 표기법</span><span class="sxs-lookup"><span data-stu-id="82b07-102">Capitalization Conventions</span></span>
<span data-ttu-id="82b07-103">형식, 멤버 및 매개 변수를 읽기 쉽게 확인 식별자를 일관 되 게 적용 하는 경우의 지침에는 간단한 방법 사용 하 여이 장 레이아웃을 만드는 경우는입니다.</span><span class="sxs-lookup"><span data-stu-id="82b07-103">The guidelines in this chapter lay out a simple method for using case that, when applied consistently, make identifiers for types, members, and parameters easy to read.</span></span>  
  
## <a name="capitalization-rules-for-identifiers"></a><span data-ttu-id="82b07-104">식별자에 대 한 대/소문자 규칙</span><span class="sxs-lookup"><span data-stu-id="82b07-104">Capitalization Rules for Identifiers</span></span>  
 <span data-ttu-id="82b07-105">식별자에서 단어를 구별 하 식별자에서 각 단어의 첫 번째 글자를 대문자로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="82b07-105">To differentiate words in an identifier, capitalize the first letter of each word in the identifier.</span></span> <span data-ttu-id="82b07-106">단어를 구분 하기 위해 밑줄을 사용 하지 않는 또는 식별자 어디에서 나 해당 문제에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="82b07-106">Do not use underscores to differentiate words, or for that matter, anywhere in identifiers.</span></span> <span data-ttu-id="82b07-107">두 가지 적절 한 식별자의 사용에 따라 식별자를 활용 하려면:</span><span class="sxs-lookup"><span data-stu-id="82b07-107">There are two appropriate ways to capitalize identifiers, depending on the use of the identifier:</span></span>  
  
-   <span data-ttu-id="82b07-108">PascalCasing</span><span class="sxs-lookup"><span data-stu-id="82b07-108">PascalCasing</span></span>  
  
-   <span data-ttu-id="82b07-109">camelCasing</span><span class="sxs-lookup"><span data-stu-id="82b07-109">camelCasing</span></span>  
  
 <span data-ttu-id="82b07-110">매개 변수 이름 제외한 모든 식별자에 사용 되는 PascalCasing 규칙을 다음 예와에서 같이 (머리 글자어 길이가 두 문자를 통해) 각 단어의 첫 번째 문자를 대문자로 표시:</span><span class="sxs-lookup"><span data-stu-id="82b07-110">The PascalCasing convention, used for all identifiers except parameter names, capitalizes the first character of each word (including acronyms over two letters in length), as shown in the following examples:</span></span>  
  
 `PropertyDescriptor`  
 `HtmlTag`  
  
 <span data-ttu-id="82b07-111">다음 식별자에 표시 된 대로 특수 한 경우는 두 문자를 대문자로 표시, 2 자 약어에 대 한 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82b07-111">A special case is made for two-letter acronyms in which both letters are capitalized, as shown in the following identifier:</span></span>  
  
 `IOStream`  
  
 <span data-ttu-id="82b07-112">다음 예제와 같이 camelCasing 규칙, 매개 변수 이름에 대해서만 사용 되는 첫 번째 단어를 제외 하 고 각 단어의 첫 번째 문자를 대문자로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="82b07-112">The camelCasing convention, used only for parameter names, capitalizes the first character of each word except the first word, as shown in the following examples.</span></span> <span data-ttu-id="82b07-113">또한이 예제에서는, 카멜식 대 / 소문자 식별자를 시작 하는 2 자 약어는 모두 소문자입니다.</span><span class="sxs-lookup"><span data-stu-id="82b07-113">As the example also shows, two-letter acronyms that begin a camel-cased identifier are both lowercase.</span></span>  
  
 `propertyDescriptor`  
 `ioStream`  
 `htmlTag`  
  
 <span data-ttu-id="82b07-114">**✓ DO** PascalCasing 여러 단어로 구성 된 모든 public 멤버, 형식 및 네임 스페이스 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="82b07-114">**✓ DO** use PascalCasing for all public member, type, and namespace names consisting of multiple words.</span></span>  
  
 <span data-ttu-id="82b07-115">**✓ DO** camelCasing 매개 변수 이름에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="82b07-115">**✓ DO** use camelCasing for parameter names.</span></span>  
  
 <span data-ttu-id="82b07-116">다음 표에서 다양 한 유형의 식별자에 대 한 대/소문자 규칙을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="82b07-116">The following table describes the capitalization rules for different types of identifiers.</span></span>  
  
|<span data-ttu-id="82b07-117">식별자</span><span class="sxs-lookup"><span data-stu-id="82b07-117">Identifier</span></span>|<span data-ttu-id="82b07-118">대/소문자 구분</span><span class="sxs-lookup"><span data-stu-id="82b07-118">Casing</span></span>|<span data-ttu-id="82b07-119">예제</span><span class="sxs-lookup"><span data-stu-id="82b07-119">Example</span></span>|  
|----------------|------------|-------------|  
|<span data-ttu-id="82b07-120">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="82b07-120">Namespace</span></span>|<span data-ttu-id="82b07-121">Pascal</span><span class="sxs-lookup"><span data-stu-id="82b07-121">Pascal</span></span>|`namespace System.Security { ... }`|  
|<span data-ttu-id="82b07-122">형식</span><span class="sxs-lookup"><span data-stu-id="82b07-122">Type</span></span>|<span data-ttu-id="82b07-123">Pascal</span><span class="sxs-lookup"><span data-stu-id="82b07-123">Pascal</span></span>|`public class StreamReader { ... }`|  
|<span data-ttu-id="82b07-124">인터페이스</span><span class="sxs-lookup"><span data-stu-id="82b07-124">Interface</span></span>|<span data-ttu-id="82b07-125">Pascal</span><span class="sxs-lookup"><span data-stu-id="82b07-125">Pascal</span></span>|`public interface IEnumerable { ... }`|  
|<span data-ttu-id="82b07-126">메서드</span><span class="sxs-lookup"><span data-stu-id="82b07-126">Method</span></span>|<span data-ttu-id="82b07-127">Pascal</span><span class="sxs-lookup"><span data-stu-id="82b07-127">Pascal</span></span>|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|  
|<span data-ttu-id="82b07-128">속성</span><span class="sxs-lookup"><span data-stu-id="82b07-128">Property</span></span>|<span data-ttu-id="82b07-129">Pascal</span><span class="sxs-lookup"><span data-stu-id="82b07-129">Pascal</span></span>|`public class String {` <br />  `public int Length { get; }` <br /> `}`|  
|<span data-ttu-id="82b07-130">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="82b07-130">Event</span></span>|<span data-ttu-id="82b07-131">Pascal</span><span class="sxs-lookup"><span data-stu-id="82b07-131">Pascal</span></span>|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|  
|<span data-ttu-id="82b07-132">필드</span><span class="sxs-lookup"><span data-stu-id="82b07-132">Field</span></span>|<span data-ttu-id="82b07-133">Pascal</span><span class="sxs-lookup"><span data-stu-id="82b07-133">Pascal</span></span>|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|  
|<span data-ttu-id="82b07-134">열거형 값</span><span class="sxs-lookup"><span data-stu-id="82b07-134">Enum value</span></span>|<span data-ttu-id="82b07-135">Pascal</span><span class="sxs-lookup"><span data-stu-id="82b07-135">Pascal</span></span>|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|  
|<span data-ttu-id="82b07-136">매개 변수</span><span class="sxs-lookup"><span data-stu-id="82b07-136">Parameter</span></span>|<span data-ttu-id="82b07-137">카멜식 대 /</span><span class="sxs-lookup"><span data-stu-id="82b07-137">Camel</span></span>|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|  
  
## <a name="capitalizing-compound-words-and-common-terms"></a><span data-ttu-id="82b07-138">복합 단어 및 일반적인 용어를 활용 하세요.</span><span class="sxs-lookup"><span data-stu-id="82b07-138">Capitalizing Compound Words and Common Terms</span></span>  
 <span data-ttu-id="82b07-139">대부분의 복합 용어는 대/소문자의 목적을 위해 단일 단어로 취급 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82b07-139">Most compound terms are treated as single words for purposes of capitalization.</span></span>  
  
 <span data-ttu-id="82b07-140">**X DO NOT** 소위 닫힌 형식의 복합 단어 각 글자를 대문자로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="82b07-140">**X DO NOT** capitalize each word in so-called closed-form compound words.</span></span>  
  
 <span data-ttu-id="82b07-141">이들은 끝점 등 한 단어로 작성 하는 복합 단어입니다.</span><span class="sxs-lookup"><span data-stu-id="82b07-141">These are compound words written as a single word, such as endpoint.</span></span> <span data-ttu-id="82b07-142">대/소문자 구분 지침을 위해 단일 단어 닫힌 형식의 복합 단어를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="82b07-142">For the purpose of casing guidelines, treat a closed-form compound word as a single word.</span></span> <span data-ttu-id="82b07-143">현재 사전을 사용 하 여 복합 단어 닫힌 형태로 기록 됩니다 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="82b07-143">Use a current dictionary to determine if a compound word is written in closed form.</span></span>  
  
|<span data-ttu-id="82b07-144">Pascal</span><span class="sxs-lookup"><span data-stu-id="82b07-144">Pascal</span></span>|<span data-ttu-id="82b07-145">카멜식 대 /</span><span class="sxs-lookup"><span data-stu-id="82b07-145">Camel</span></span>|<span data-ttu-id="82b07-146">not</span><span class="sxs-lookup"><span data-stu-id="82b07-146">Not</span></span>|  
|------------|-----------|---------|  
|`BitFlag`|`bitFlag`|`Bitflag`|  
|`Callback`|`callback`|`CallBack`|  
|`Canceled`|`canceled`|`Cancelled`|  
|`DoNot`|`doNot`|`Don't`|  
|`Email`|`email`|`EMail`|  
|`Endpoint`|`endpoint`|`EndPoint`|  
|`FileName`|`fileName`|`Filename`|  
|`Gridline`|`gridline`|`GridLine`|  
|`Hashtable`|`hashtable`|`HashTable`|  
|`Id`|`id`|`ID`|  
|`Indexes`|`indexes`|`Indices`|  
|`LogOff`|`logOff`|`LogOut`|  
|`LogOn`|`logOn`|`LogIn`|  
|`Metadata`|`metadata`|`MetaData, metaData`|  
|`Multipanel`|`multipanel`|`MultiPanel`|  
|`Multiview`|`multiview`|`MultiView`|  
|`Namespace`|`namespace`|`NameSpace`|  
|`Ok`|`ok`|`OK`|  
|`Pi`|`pi`|`PI`|  
|`Placeholder`|`placeholder`|`PlaceHolder`|  
|`SignIn`|`signIn`|`SignOn`|  
|`SignOut`|`signOut`|`SignOff`|  
|`UserName`|`userName`|`Username`|  
|`WhiteSpace`|`whiteSpace`|`Whitespace`|  
|`Writable`|`writable`|`Writeable`|  
  
## <a name="case-sensitivity"></a><span data-ttu-id="82b07-147">대/소문자 구분</span><span class="sxs-lookup"><span data-stu-id="82b07-147">Case Sensitivity</span></span>  
 <span data-ttu-id="82b07-148">일부 있지만 CLR에서 실행할 수 있는 언어 대/소문자 구분을 지원할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="82b07-148">Languages that can run on the CLR are not required to support case-sensitivity, although some do.</span></span> <span data-ttu-id="82b07-149">언어를 지 원하는 경우에 프레임 워크에 액세스할 수 있는 다른 언어는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="82b07-149">Even if your language supports it, other languages that might access your framework do not.</span></span> <span data-ttu-id="82b07-150">따라서 외부에서 액세스할 수 있는 모든 Api는 동일한 컨텍스트에서 두 이름을 구별할 하려면 사례에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="82b07-150">Any APIs that are externally accessible, therefore, cannot rely on case alone to distinguish between two names in the same context.</span></span>  
  
 <span data-ttu-id="82b07-151">**X DO NOT** 모든 프로그래밍 언어는 대/소문자 구분 하는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="82b07-151">**X DO NOT** assume that all programming languages are case sensitive.</span></span> <span data-ttu-id="82b07-152">그러나 동일하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="82b07-152">They are not.</span></span> <span data-ttu-id="82b07-153">대/소문자만 다른 이름 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="82b07-153">Names cannot differ by case alone.</span></span>  
  
 <span data-ttu-id="82b07-154">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="82b07-154">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="82b07-155">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="82b07-155">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82b07-156">참고자료</span><span class="sxs-lookup"><span data-stu-id="82b07-156">See also</span></span>

- [<span data-ttu-id="82b07-157">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="82b07-157">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="82b07-158">명명 지침</span><span class="sxs-lookup"><span data-stu-id="82b07-158">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
