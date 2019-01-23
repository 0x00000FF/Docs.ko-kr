---
title: '&lt;추가&gt; NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 502f86e49d68e456d8e64e00e7632aa603cafbe9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523911"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="96cf4-102">\<추가 > NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="96cf4-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="96cf4-103">사용자 지정 응용 프로그램 설정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="96cf4-103">Adds custom application settings.</span></span> <span data-ttu-id="96cf4-104">각  **\<추가 >** 태그 키/값 쌍을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="96cf4-104">Each **\<add>** tag contains a key/value pair.</span></span>

<span data-ttu-id="96cf4-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="96cf4-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="96cf4-106">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="96cf4-106">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="96cf4-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span><span class="sxs-lookup"><span data-stu-id="96cf4-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="96cf4-108">구문</span><span class="sxs-lookup"><span data-stu-id="96cf4-108">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="96cf4-109">특성</span><span class="sxs-lookup"><span data-stu-id="96cf4-109">Attributes</span></span>

| <span data-ttu-id="96cf4-110">특성</span><span class="sxs-lookup"><span data-stu-id="96cf4-110">Attribute</span></span> | <span data-ttu-id="96cf4-111">설명</span><span class="sxs-lookup"><span data-stu-id="96cf4-111">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="96cf4-112">**key**</span><span class="sxs-lookup"><span data-stu-id="96cf4-112">**key**</span></span>   | <span data-ttu-id="96cf4-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="96cf4-113">Required attribute.</span></span><br><br><span data-ttu-id="96cf4-114">설정의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96cf4-114">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="96cf4-115">**value**</span><span class="sxs-lookup"><span data-stu-id="96cf4-115">**value**</span></span> | <span data-ttu-id="96cf4-116">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="96cf4-116">Required attribute.</span></span><br><br><span data-ttu-id="96cf4-117">설정의 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96cf4-117">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="96cf4-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="96cf4-118">Parent element</span></span>

| <span data-ttu-id="96cf4-119">요소</span><span class="sxs-lookup"><span data-stu-id="96cf4-119">Element</span></span> | <span data-ttu-id="96cf4-120">설명</span><span class="sxs-lookup"><span data-stu-id="96cf4-120">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="96cf4-121">**\<sectionName>** Element</span><span class="sxs-lookup"><span data-stu-id="96cf4-121">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="96cf4-122">사용 하는 사용자 지정 구성 섹션에 대 한 설정을 정의 합니다 <xref:System.Configuration.NameValueSectionHandler> 고 <xref:System.Configuration.DictionarySectionHandler> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="96cf4-122">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="96cf4-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="96cf4-123">Child elements</span></span>

<span data-ttu-id="96cf4-124">없음</span><span class="sxs-lookup"><span data-stu-id="96cf4-124">None</span></span>

## <a name="example"></a><span data-ttu-id="96cf4-125">예제</span><span class="sxs-lookup"><span data-stu-id="96cf4-125">Example</span></span>

<span data-ttu-id="96cf4-126">다음 예제에서는 사용자 지정 구성 섹션 정의 및 사용 방법에는  **\<추가 >** 요소 섹션으로 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="96cf4-126">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="96cf4-127">구성 파일</span><span class="sxs-lookup"><span data-stu-id="96cf4-127">Configuration file</span></span>

<span data-ttu-id="96cf4-128">응용 프로그램 구성 파일을 컴퓨터 구성 파일에서이 요소를 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="96cf4-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="96cf4-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="96cf4-129">See also</span></span>

- [<span data-ttu-id="96cf4-130">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="96cf4-130">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
