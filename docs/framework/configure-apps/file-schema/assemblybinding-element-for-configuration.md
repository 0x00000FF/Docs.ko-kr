---
title: '&lt;assemblyBinding&gt; 요소에 대 한 &lt;구성&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 5693b92ac35a357ff1f8643d0eb9ec2105acecb4
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2018
ms.locfileid: "47193358"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="194d5-102">\<assemblyBinding > 요소에 대 한 \<구성 ></span><span class="sxs-lookup"><span data-stu-id="194d5-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="194d5-103">구성 수준에서 어셈블리 바인딩 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="194d5-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="194d5-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="194d5-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="194d5-105">&nbsp;&nbsp;**\<assemblyBinding >**</span><span class="sxs-lookup"><span data-stu-id="194d5-105">&nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="194d5-106">구문</span><span class="sxs-lookup"><span data-stu-id="194d5-106">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="194d5-107">특성</span><span class="sxs-lookup"><span data-stu-id="194d5-107">Attribute</span></span>

|           | <span data-ttu-id="194d5-108">설명</span><span class="sxs-lookup"><span data-stu-id="194d5-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="194d5-109">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="194d5-109">**xmlns**</span></span> | <span data-ttu-id="194d5-110">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="194d5-110">Required attribute.</span></span><br><br><span data-ttu-id="194d5-111">어셈블리 바인딩에 필요한 XML 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="194d5-111">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="194d5-112">문자열 string "urn:schemas-microsoft-com:asm.v1"을 값으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="194d5-112">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="194d5-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="194d5-113">Parent element</span></span>

|     | <span data-ttu-id="194d5-114">설명</span><span class="sxs-lookup"><span data-stu-id="194d5-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="194d5-115">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="194d5-115">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="194d5-116">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="194d5-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="194d5-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="194d5-117">Child element</span></span>

|     | <span data-ttu-id="194d5-118">설명</span><span class="sxs-lookup"><span data-stu-id="194d5-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="194d5-119">**\<linkedConfiguration >**</span><span class="sxs-lookup"><span data-stu-id="194d5-119">**\<linkedConfiguration>**</span></span>](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) | <span data-ttu-id="194d5-120">포함할 구성 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="194d5-120">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="194d5-121">설명</span><span class="sxs-lookup"><span data-stu-id="194d5-121">Remarks</span></span>

<span data-ttu-id="194d5-122">합니다 [  **\<linkedConfiguration >** ](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) 어셈블리를 포함 하도록 응용 프로그램 구성 파일의 구성 파일을 허용 하 여 구성 요소 어셈블리의 관리를 간소화 하는 요소 잘 알려진 위치 대신 복제 어셈블리 구성 설정.</span><span class="sxs-lookup"><span data-stu-id="194d5-122">The [**\<linkedConfiguration>**](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="194d5-123">합니다  **\<linkedConfiguration >** Windows side-by-side-매니페스트를 사용 하 여 응용 프로그램에 대 한 요소가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="194d5-123">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="194d5-124">예제</span><span class="sxs-lookup"><span data-stu-id="194d5-124">Example</span></span>

<span data-ttu-id="194d5-125">다음 예제에서는 로컬 하드 디스크의 구성 파일을 포함 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="194d5-125">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="194d5-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="194d5-126">See also</span></span>

[<span data-ttu-id="194d5-127">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="194d5-127">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
