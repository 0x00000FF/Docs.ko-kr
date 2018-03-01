---
title: "&lt;지우기&gt; NameValueSectionHandler 및 DictionarySectionHandler 요소"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 57ee634c987d344d81f1ca099fe55e633bfbf659
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="fba63-102">\<지우기 > NameValueSectionHandler 및 DictionarySectionHandler 요소</span><span class="sxs-lookup"><span data-stu-id="fba63-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="fba63-103">섹션에서 이전에 정의 된 모든 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="fba63-103">Clears all previously defined settings in a section.</span></span>

<span data-ttu-id="fba63-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="fba63-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="fba63-105">&nbsp;&nbsp;[**\<sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="fba63-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="fba63-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<지우기 >**</span><span class="sxs-lookup"><span data-stu-id="fba63-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="fba63-107">구문</span><span class="sxs-lookup"><span data-stu-id="fba63-107">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="fba63-108">특성</span><span class="sxs-lookup"><span data-stu-id="fba63-108">Attributes</span></span>

<span data-ttu-id="fba63-109">없음</span><span class="sxs-lookup"><span data-stu-id="fba63-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="fba63-110">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fba63-110">Parent element</span></span>

|     | <span data-ttu-id="fba63-111">설명</span><span class="sxs-lookup"><span data-stu-id="fba63-111">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="fba63-112">**\<sectionName >** 요소</span><span class="sxs-lookup"><span data-stu-id="fba63-112">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="fba63-113">설정을 사용 하는 사용자 지정 구성 섹션에 대 한 정의 <xref:System.Configuration.NameValueSectionHandler> 및 <xref:System.Configuration.DictionarySectionHandler> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fba63-113">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="fba63-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fba63-114">Child elements</span></span>

<span data-ttu-id="fba63-115">없음</span><span class="sxs-lookup"><span data-stu-id="fba63-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="fba63-116">설명</span><span class="sxs-lookup"><span data-stu-id="fba63-116">Remarks</span></span>

<span data-ttu-id="fba63-117">사용할 수 있습니다는  **\<지우기 >** 모든 설정이 구성 파일 계층 구조에서 더 높은 수준에서 정의 된 응용 프로그램에서 제거할 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fba63-117">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="fba63-118">예</span><span class="sxs-lookup"><span data-stu-id="fba63-118">Example</span></span>

<span data-ttu-id="fba63-119">이 예제에서는 컴퓨터 구성 파일 및 응용 프로그램 구성 파일을 정의 하 고 사용 하는 방법을 보여 줍니다.는  **\<지우기 >** 에 이전에 정의 된 섹션을 정리 하는 응용 프로그램 구성 파일의 요소는 컴퓨터 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="fba63-119">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="fba63-120">다음 컴퓨터 구성 파일 코드 선언 섹션  **\<mySection >**:</span><span class="sxs-lookup"><span data-stu-id="fba63-120">The following machine configuration file code declares the section **\<mySection>**:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

<span data-ttu-id="fba63-121">다음 응용 프로그램 구성 파일 코드에서 모든 설정이 제거  **\<mySection >**합니다.</span><span class="sxs-lookup"><span data-stu-id="fba63-121">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="fba63-122">응용 프로그램에 선언 된 설정을 검색할 수 없습니다는에  **\<mySection >** 컴퓨터 구성 파일의 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="fba63-122">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="fba63-123">구성 파일</span><span class="sxs-lookup"><span data-stu-id="fba63-123">Configuration file</span></span>

<span data-ttu-id="fba63-124">이 요소는 응용 프로그램 구성 파일을 컴퓨터 구성 파일에 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="fba63-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="fba63-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fba63-125">See also</span></span>

[<span data-ttu-id="fba63-126">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="fba63-126">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
