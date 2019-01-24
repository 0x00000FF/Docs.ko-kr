---
title: SingleTagSectionHandler에 대 한 사용자 지정 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 232ad7527e65fd38fa471cccc917752aef766a88
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628840"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="a7bdf-102">SingleTagSectionHandler에 대 한 사용자 지정 요소</span><span class="sxs-lookup"><span data-stu-id="a7bdf-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="a7bdf-103">정의한 사용자 지정 구성 섹션에서 설정을 정의</span><span class="sxs-lookup"><span data-stu-id="a7bdf-103">Defines settings in a custom configuration section that is defined by a</span></span> <section> <span data-ttu-id="a7bdf-104">사용 하 여 요소를 <xref:System.Configuration.SingleTagSectionHandler> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdf-104">element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="a7bdf-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="a7bdf-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="a7bdf-106">&nbsp;&nbsp;*\<sectionName>*</span><span class="sxs-lookup"><span data-stu-id="a7bdf-106">&nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="a7bdf-107">구문</span><span class="sxs-lookup"><span data-stu-id="a7bdf-107">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="a7bdf-108">특성</span><span class="sxs-lookup"><span data-stu-id="a7bdf-108">Attributes</span></span>

<span data-ttu-id="a7bdf-109">특성과 특성 값에는 사용자 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdf-109">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="a7bdf-110">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a7bdf-110">Parent element</span></span>

|     | <span data-ttu-id="a7bdf-111">설명</span><span class="sxs-lookup"><span data-stu-id="a7bdf-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="a7bdf-112">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="a7bdf-112">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="a7bdf-113">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdf-113">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="a7bdf-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a7bdf-114">Child elements</span></span>

<span data-ttu-id="a7bdf-115">없음</span><span class="sxs-lookup"><span data-stu-id="a7bdf-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="a7bdf-116">설명</span><span class="sxs-lookup"><span data-stu-id="a7bdf-116">Remarks</span></span>

<span data-ttu-id="a7bdf-117">합니다  **\<sectionName >** 정의한 사용자 지정 요소입니다를 [  **\<섹션 >** ](~/docs/framework/configure-apps/file-schema/section-element.md) 태그를 [  **\<configSections >** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdf-117">The **\<sectionName>** element is a custom element defined by a [**\<section>**](~/docs/framework/configure-apps/file-schema/section-element.md) tag in the [**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="a7bdf-118">구성 시스템을 반환 합니다는 <xref:System.Collections.IDictionary> 개체를 호출할 때 <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdf-118">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="a7bdf-119">예제</span><span class="sxs-lookup"><span data-stu-id="a7bdf-119">Example</span></span>

<span data-ttu-id="a7bdf-120">다음 예제에서는 라는 사용자 지정 요소 선언  **\<sampleSection >** 읽은 설정을 포함 하는 <xref:System.Configuration.SingleTagSectionHandler> 클래스:</span><span class="sxs-lookup"><span data-stu-id="a7bdf-120">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection" 
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="a7bdf-121">구성 파일</span><span class="sxs-lookup"><span data-stu-id="a7bdf-121">Configuration file</span></span>

<span data-ttu-id="a7bdf-122">응용 프로그램 구성 파일을 컴퓨터 구성 파일에서이 요소를 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdf-122">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7bdf-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="a7bdf-123">See also</span></span>

- [<span data-ttu-id="a7bdf-124">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="a7bdf-124">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
