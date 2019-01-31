---
title: <clear>의 <configSections> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
author: guardrex
ms.author: mairaw
ms.openlocfilehash: d824ae828dd025f3292990facaa5e423add9c282
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254775"
---
# <a name="clear-element-for-configsections"></a><span data-ttu-id="26998-102">\<지우기 > 요소에 대 한 \<configSections ></span><span class="sxs-lookup"><span data-stu-id="26998-102">\<clear> element for \<configSections></span></span>

<span data-ttu-id="26998-103">모든 이전에 정의 된 섹션 및 섹션 그룹을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="26998-103">Clears all previously defined sections and section groups.</span></span>

<span data-ttu-id="26998-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="26998-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="26998-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="26998-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="26998-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="26998-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="26998-107">구문</span><span class="sxs-lookup"><span data-stu-id="26998-107">Syntax</span></span>

```xml
<clear/>
```

## <a name="attribute"></a><span data-ttu-id="26998-108">특성</span><span class="sxs-lookup"><span data-stu-id="26998-108">Attribute</span></span>

|           | <span data-ttu-id="26998-109">설명</span><span class="sxs-lookup"><span data-stu-id="26998-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="26998-110">**name**</span><span class="sxs-lookup"><span data-stu-id="26998-110">**name**</span></span>  | <span data-ttu-id="26998-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="26998-111">Required attribute.</span></span><br><br><span data-ttu-id="26998-112">섹션 또는 제거할 섹션 그룹의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="26998-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="26998-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="26998-113">Parent element</span></span>

|     | <span data-ttu-id="26998-114">설명</span><span class="sxs-lookup"><span data-stu-id="26998-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="26998-115">**\<configSections >** 요소</span><span class="sxs-lookup"><span data-stu-id="26998-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="26998-116">구성 섹션 및 네임 스페이스 선언을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="26998-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="26998-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="26998-117">Child elements</span></span>

<span data-ttu-id="26998-118">없음</span><span class="sxs-lookup"><span data-stu-id="26998-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="26998-119">설명</span><span class="sxs-lookup"><span data-stu-id="26998-119">Remarks</span></span>

<span data-ttu-id="26998-120">합니다  **\<지우기 >** 요소 또는 구성 파일 계층 구조의 상위 수준에 현재 구성 파일에서 이전에 정의 된 응용 프로그램에서 모든 섹션 및 섹션 그룹을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="26998-120">The **\<clear>** element removes all sections and section groups from your application that were defined earlier in the current configuration file or at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="26998-121">예제</span><span class="sxs-lookup"><span data-stu-id="26998-121">Example</span></span>

<span data-ttu-id="26998-122">이 예제에서는 컴퓨터 구성 파일 및 응용 프로그램 구성 파일을 정의 하 고 사용 하는 방법을 보여 줍니다 합니다  **\<지우기 >** 요소에서 이전에 정의 된 섹션의 선택을 취소 하는 응용 프로그램 구성 파일에는 컴퓨터 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="26998-122">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="26998-123">다음 컴퓨터 구성 파일 코드에는 두 섹션이 선언  **\<sampleSection >** 하 고  **\<anotherSampleSection >**, 응용 프로그램 전에 읽은 구성 파일:</span><span class="sxs-lookup"><span data-stu-id="26998-123">The following machine configuration file code declares two sections, **\<sampleSection>** and **\<anotherSampleSection>**, which are read before the application configuration file:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
    <section name="anotherSampleSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

<span data-ttu-id="26998-124">다음 응용 프로그램 구성 파일 코드는 이전에 선언 된 모든 섹션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="26998-124">The following application configuration file code clears all previously declared sections.</span></span> <span data-ttu-id="26998-125">응용 프로그램을 사용 하거나 컴퓨터 구성 파일에 선언 된 섹션 중 하나에서 설정을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26998-125">The application cannot use or retrieve settings in either of the sections that were declared in the machine configuration file.</span></span> <span data-ttu-id="26998-126">그러나 설정에서 사용할 수 있습니다  **\<anotherSection >** 후 있기 때문에  **\<지우기 >** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="26998-126">However, it can use settings from **\<anotherSection>** because it comes after the **\<clear>** element.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <clear/>
    <section name="anotherSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <anotherSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="26998-127">구성 파일</span><span class="sxs-lookup"><span data-stu-id="26998-127">Configuration file</span></span>

<span data-ttu-id="26998-128">응용 프로그램 구성 파일을 컴퓨터 구성 파일에서이 요소를 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="26998-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="26998-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="26998-129">See also</span></span>

- [<span data-ttu-id="26998-130">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="26998-130">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
