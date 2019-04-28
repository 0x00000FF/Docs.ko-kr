---
title: <appSettings>에 대한 <remove> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
author: guardrex
ms.author: mairaw
ms.openlocfilehash: cf9a34e47b70aaff12b29b9c5cf944d5bb15fee9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705391"
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="6bc8c-102">\<제거 > 요소에 대 한 \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="6bc8c-102">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="6bc8c-103">사용자 지정 응용 프로그램 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc8c-103">Removes custom application settings.</span></span>

<span data-ttu-id="6bc8c-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="6bc8c-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="6bc8c-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="6bc8c-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="6bc8c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="6bc8c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="6bc8c-107">구문</span><span class="sxs-lookup"><span data-stu-id="6bc8c-107">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="6bc8c-108">특성</span><span class="sxs-lookup"><span data-stu-id="6bc8c-108">Attribute</span></span>

|         | <span data-ttu-id="6bc8c-109">설명</span><span class="sxs-lookup"><span data-stu-id="6bc8c-109">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="6bc8c-110">**key**</span><span class="sxs-lookup"><span data-stu-id="6bc8c-110">**key**</span></span> | <span data-ttu-id="6bc8c-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="6bc8c-111">Required attribute.</span></span><br><br><span data-ttu-id="6bc8c-112">제거할 키의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc8c-112">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="6bc8c-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6bc8c-113">Parent element</span></span>

|     | <span data-ttu-id="6bc8c-114">설명</span><span class="sxs-lookup"><span data-stu-id="6bc8c-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="6bc8c-115">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="6bc8c-115">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="6bc8c-116">파일 경로, XML Web services URL 또는 애플리케이션의 기타 사용자 지정 구성 정보와 같은 사용자 지정 애플리케이션 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bc8c-116">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="6bc8c-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6bc8c-117">Child elements</span></span>

<span data-ttu-id="6bc8c-118">없음</span><span class="sxs-lookup"><span data-stu-id="6bc8c-118">None</span></span>

## <a name="example"></a><span data-ttu-id="6bc8c-119">예제</span><span class="sxs-lookup"><span data-stu-id="6bc8c-119">Example</span></span>

<span data-ttu-id="6bc8c-120">다음 예제에 대 한 사용자 지정 구성 설정을 제거 하는 방법을 보여 줍니다 `ApplicationName`:</span><span class="sxs-lookup"><span data-stu-id="6bc8c-120">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="6bc8c-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="6bc8c-121">See also</span></span>

- [<span data-ttu-id="6bc8c-122">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="6bc8c-122">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
