---
title: Windows Forms 구성 섹션
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
ms.openlocfilehash: 4a54df0b6301f1aae14d5561c91c6792cb0a1620
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109821"
---
# <a name="windows-forms-configuration-section"></a><span data-ttu-id="f32b9-102">Windows Forms 구성 섹션</span><span class="sxs-lookup"><span data-stu-id="f32b9-102">Windows Forms Configuration Section</span></span>
<span data-ttu-id="f32b9-103">Windows Forms 구성 설정을 통해 Windows Forms 앱에서 다중 모니터 지원, 높은 DPI 지원 및 기타 사용자 정의된 구성 설정 등의 사용자 지정된 애플리케이션 설정에 대한 정보를 저장하고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f32b9-103">Windows Forms configuration settings allow a Windows Forms app to store and retrieve information about customized application settings such as multi-monitor support, high DPI support, and other predefined configuration settings.</span></span>

<span data-ttu-id="f32b9-104">Windows Forms 애플리케이션 구성 설정은 애플리케이션 구성 파일의 `System.Windows.Forms.ApplicationConfigurationSection` 요소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f32b9-104">Windows Forms application configuration settings are stored in an application configuration file's `System.Windows.Forms.ApplicationConfigurationSection` element.</span></span>

## <a name="syntax"></a><span data-ttu-id="f32b9-105">구문</span><span class="sxs-lookup"><span data-stu-id="f32b9-105">Syntax</span></span>

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f32b9-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f32b9-106">Attributes and elements</span></span>

<span data-ttu-id="f32b9-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f32b9-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f32b9-108">특성</span><span class="sxs-lookup"><span data-stu-id="f32b9-108">Attributes</span></span>

<span data-ttu-id="f32b9-109">없음.</span><span class="sxs-lookup"><span data-stu-id="f32b9-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f32b9-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f32b9-110">Child elements</span></span>

<span data-ttu-id="f32b9-111">요소</span><span class="sxs-lookup"><span data-stu-id="f32b9-111">Element</span></span>  |<span data-ttu-id="f32b9-112">설명</span><span class="sxs-lookup"><span data-stu-id="f32b9-112">Description</span></span> |
---------|---------|
[`<add>`](windows-forms-add-configuration-element.md) | <span data-ttu-id="f32b9-113">지정된 된 값과 함께 구성 설정 키를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f32b9-113">Adds a configuration setting key with a specified value</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="f32b9-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f32b9-114">Parent elements</span></span>

<span data-ttu-id="f32b9-115">요소</span><span class="sxs-lookup"><span data-stu-id="f32b9-115">Element</span></span>  |<span data-ttu-id="f32b9-116">설명</span><span class="sxs-lookup"><span data-stu-id="f32b9-116">Description</span></span> |
---------|---------|
[<span data-ttu-id="f32b9-117">\<구성></span><span class="sxs-lookup"><span data-stu-id="f32b9-117">\<configuration></span></span>](../configuration-element.md) | <span data-ttu-id="f32b9-118">공용 언어 런타임 및 Windows Forms 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f32b9-118">The root element in every configuration file used by the common language runtime and Windows Forms applications</span></span> |

## <a name="remarks"></a><span data-ttu-id="f32b9-119">주의</span><span class="sxs-lookup"><span data-stu-id="f32b9-119">Remarks</span></span>

<span data-ttu-id="f32b9-120">.NET Framework 4.7부터는 `<System.Windows.Forms.ApplicationConfigurationSection>` 요소를 사용하여 Windows Forms 애플리케이션을 구성해 최신 .NET Framework 릴리스에 추가된 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f32b9-120">Starting with the .NET Framework 4.7, the `<System.Windows.Forms.ApplicationConfigurationSection>` element allows you to configure Windows Forms applications to take advantage of features added in recent releases of the .NET Framework.</span></span> 

<span data-ttu-id="f32b9-121">`<System.Windows.Forms.ApplicationConfigurationSection>` 요소는 각각 특정 구성 설정을 정의하는 하나 이상의 [`<add>`](windows-forms-add-configuration-element.md) 요소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f32b9-121">The `<System.Windows.Forms.ApplicationConfigurationSection>` element can include one or more child [`<add>`](windows-forms-add-configuration-element.md) elements, each of which defines a specific configuration setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="f32b9-122">참조</span><span class="sxs-lookup"><span data-stu-id="f32b9-122">See also</span></span>

- [<span data-ttu-id="f32b9-123">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="f32b9-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f32b9-124">Windows Forms의 높은 DPI 지원</span><span class="sxs-lookup"><span data-stu-id="f32b9-124">High DPI Support in Windows Forms</span></span>](../../../winforms/high-dpi-support-in-windows-forms.md)
