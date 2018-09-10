---
title: .NET Core 응용 프로그램 배포
description: .NET Core 응용 프로그램 배포.
author: rpetrusha
ms.author: ronpet
ms.date: 09/03/2018
ms.openlocfilehash: 2ef63ebd737739b2c8e671d982c3844135689ab4
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44185651"
---
# <a name="net-core-application-deployment"></a>.NET Core 응용 프로그램 배포

.NET Core 응용 프로그램에 대해 두 가지 유형을 배포를 만들 수 있습니다.

- 프레임워크 종속 배포. 이름에서 알 수 있듯이 FDD(프레임워크 종속 배포)에서는 대상 시스템에 .NET Core의 공유 시스템 차원 버전이 있어야 합니다. .NET Core가 이미 존재하기 때문에 .NET Core 설치 간에 앱을 이식할 수 있습니다. 앱은 고유한 코드와 .NET Core 라이브러리 외부에 있는 타사 종속성만 포함합니다. FDD는 명령줄에서 [dotnet 유틸리티](../tools/dotnet.md)를 사용하여 시작할 수 있는 *.dll* 파일을 포함합니다. 예를 들어 `dotnet app.dll`은 `app`이라는 응용 프로그램을 실행합니다.

- 자체 포함 배포. FDD와 달리 SCD(자체 포함 배포)에서는 대상 시스템에 공유 구성 요소가 없어도 됩니다. .NET Core 라이브러리 및 .NET Core 런타임을 비롯한 모든 구성 요소가 응용 프로그램에 포함되며 다른 .NET Core 응용 프로그램에서는 격리됩니다. SCD는 플랫폼별 .NET Core 호스트의 이름이 변경된 버전인 실행 파일(예: Windows 플랫폼에서 `app`이라는 응용 프로그램에 대한 *app.exe*)과 실제 응용 프로그램인 *.dll* 파일(예: *app.dll*)을 포함합니다.

## <a name="framework-dependent-deployments-fdd"></a>프레임워크 종속 배포(FDD)

FDD에서는 앱과 타사 종속성만 배포합니다. 앱에서 대상 시스템에 있는 .NET Core 버전을 사용하므로 .NET Core를 배포할 필요가 없습니다. 이는 .NET Core를 대상으로 하는 .NET Core 및 ASP.NET Core 앱의 기본 배포 모델입니다.

### <a name="why-create-a-framework-dependent-deployment"></a>프레임워크 종속 배포를 만드는 이유

FDD 배포에는 다음과 같은 여러 가지 장점이 있습니다.

- .NET Core 앱이 실행될 대상 운영 체제를 미리 정의할 필요가 없습니다. .NET Core는 운영 체제에 관계없이 실행 파일 및 라이브러리에 공용 PE 파일 형식을 사용하므로 기본 운영 체제에 관계없이 앱을 실행할 수 있습니다. PE 파일 형식에 대한 자세한 내용은 [.NET 어셈블리 파일 형식](../../standard/assembly-format.md)을 참조하세요.

- 배포 패키지의 크기가 작습니다. 앱과 앱의 종속성만 배포하고 .NET Core 자체는 배포하지 않습니다.

- 여러 앱에서 동일한 .NET Core 설치를 사용하여 호스트 시스템에서 디스크 공간 및 메모리 사용량을 줄일 수 있습니다.

다음과 같은 몇 가지 단점도 있습니다.

- 대상으로 지정한 .NET Core의 버전이나 그 이상 버전이 호스트 시스템에 이미 설치된 경우에만 앱이 실행됩니다.

- .NET Core 런타임 및 라이브러리가 향후 릴리스에서 사용자 모르게 변경될 수 있습니다. 드문 경우지만 이로 인해 앱의 동작이 변경될 수 있습니다.

## <a name="self-contained-deployments-scd"></a>자체 포함 배포(SCD)

자체 포함 배포에서는 앱과 필요한 타사 종속성 외에도 앱을 빌드하는 데 사용한 .NET Core 버전도 배포합니다. SCD를 만들 때 다양한 플랫폼의 [.NET Core에 대한 기본 종속성](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md)을 포함하지 않으므로 앱을 실행하려면 이러한 종속성이 있어야 합니다. 런타임 시 버전 바인딩에 대한 자세한 내용은 [.NET Core의 버전 바인딩](../versions/selection.md)에 대한 문서를 참조하세요.

NET Core 2.1 SDK(버전 2.1.300)부터 .NET Core는 ‘패치 버전 롤포워드’를 지원합니다. 자체 포함 배포를 만들 때 .NET Core 도구는 응용 프로그램에서 대상으로 하는 .NET Core 버전의 최신 서비스 런타임을 자동으로 포함합니다. (최근 서비스 런타임에는 보안 패치 및 기타 버그 수정이 포함됩니다.) 서비스 런타임은 빌드 시스템에 존재하지 않아도 됩니다. NuGet.org에서 자동으로 다운로드됩니다. 패치 버전 롤포워드를 옵트아웃하는 방법을 비롯하여 자세한 내용은 [자체 포함 배포 런타임 롤포워드](runtime-patch-selection.md)를 참조하세요.

FDD 및 SCD 배포는 별도의 호스트 실행 파일을 사용하므로 게시자 서명이 있는 SCD에 대해 호스트 실행 파일에 서명할 수 있습니다.

### <a name="why-deploy-a-self-contained-deployment"></a>자체 포함 배포를 배포하는 이유

자체 포함 배포를 배포하면 다음과 같은 두 가지 주요 장점이 있습니다.

- 앱과 함께 배포되는 .NET Core 버전을 유일하게 제어할 수 있습니다. .NET Core만 제공할 수 있습니다.

- 앱이 실행될 .NET Core 버전을 제공하므로 대상 시스템에서 .NET Core 앱을 실행할 수 있다고 보장할 수 있습니다.

다음과 같은 여러 가지 단점도 있습니다.

- .NET Core가 배포 패키지에 포함되므로 배포 패키지를 빌드할 대상 플랫폼을 미리 선택합니다.

- .NET Core뿐만 아니라 앱과 해당 타사 종속성도 포함해야 하므로 배포 패키지의 크기가 상대적으로 큽니다.

  .NET Core 2.0부터 .NET Core [*globalization invariant mode*](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md)(세계화 고정 모드)를 사용하여 Linux 시스템에서 배포 크기를 약 28MB까지 줄일 수 있습니다. 일반적으로 Linux에서 .NET Core는 세계화 지원에 대해 [ICU 라이브러리](https://github.com/dotnet/docs/issues/http%22//icu-project.org)를 사용합니다. 고정 모드에서 라이브러리는 배포에 포함되지 않으며, 모든 문화권은 [고정 문화권](xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType)처럼 동작합니다.

- 다양한 자체 포함 .NET Core 앱을 시스템에 배포하면 각 앱에서 .NET Core 파일을 중복하므로 엄청나게 많은 디스크 공간을 사용합니다.

## <a name="step-by-step-examples"></a>단계별 예제

CLI 도구를 사용하여 .NET Core 앱을 배포하는 방법을 보여 주는 단계별 예제는 [Deploying .NET Core Apps with CLI Tools](deploy-with-cli.md)(CLI 도구를 사용하여 .NET Core 앱 배포)를 참조하세요. Visual Studio를 사용하여 .NET Core 앱을 배포하는 방법을 보여 주는 단계별 예제는 [Deploying .NET Core Apps with Visual Studio](deploy-with-vs.md)(Visual Studio를 사용하여 .NET Core 앱 배포)를 참조하세요. 각 항목에는 다음 배포에 대한 예제가 포함되어 있습니다.

- 프레임워크 종속 배포
- 타사 종속성이 있는 프레임워크 종속 배포
- 자체 포함 배포
- 타사 종속성이 있는 자체 포함 배포

## <a name="see-also"></a>참고 항목

* [CLI 도구를 사용하여 .NET Core 앱 배포](deploy-with-cli.md)
* [Visual Studio를 사용하여 .NET Core 앱 배포](deploy-with-vs.md)
* [패키지, 메타패키지 및 프레임워크](../packages.md)
* [.NET Core RID(런타임 식별자) 카탈로그](../rid-catalog.md)
