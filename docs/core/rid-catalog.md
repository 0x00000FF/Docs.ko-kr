---
title: .NET Core RID(런타임 식별자) 카탈로그
description: RID(런타임 식별자) 및 .NET Core에서 RID의 사용 방법에 관해 알아봅니다.
author: mairaw
ms.author: mairaw
ms.date: 07/19/2018
ms.openlocfilehash: ff0449f7c6f878131f0ec4b16d685d2c02d26719
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517381"
---
# <a name="net-core-rid-catalog"></a>.NET Core RID 카탈로그

RID는 *Runtime IDentifier(런타임 식별자)* 의 약어입니다. RID 값은 응용 프로그램을 실행하는 대상 플랫폼을 식별하는 데 사용됩니다.
NuGet 패키지에서 .NET 패키지의 플랫폼 관련 자산을 나타내는 데 사용됩니다. RID 값의 예로 `linux-x64`, `ubuntu.14.04-x64`, `win7-x64`, `osx.10.12-x64` 등을 들 수 있습니다.
기본 종속성이 있는 패키지의 경우 RID는 패키지를 복원할 수 있는 플랫폼을 지정합니다.

단일 RID는 프로젝트 파일의 `<RuntimeIdentifier>` 요소에 설정할 수 있습니다. 여러 RID는 프로젝트 파일의 `<RuntimeIdentifiers>` 요소에서 세미콜론으로 구분된 목록으로 정의할 수 있습니다. 다음과 같은 [.NET Core CLI 명령](./tools/index.md)을 사용하여 `--runtime` 옵션을 통해서도 사용됩니다.

- [dotnet build](./tools/dotnet-build.md)
- [dotnet clean](./tools/dotnet-clean.md)
- [dotnet pack](./tools/dotnet-pack.md)
- [dotnet publish](./tools/dotnet-publish.md)
- [dotnet restore](./tools/dotnet-restore.md)
- [dotnet run](./tools/dotnet-run.md)
- [dotnet store](./tools/dotnet-store.md)

구체적인 운영 체제를 나타내는 RID는 일반적으로 `[os].[version]-[architecture]-[additional qualifiers]`의 패턴을 따릅니다. 각각은 다음과 같습니다.

- `[os]` - 운영 체제/플랫폼 모니커입니다. 예를 들어, `ubuntu`을 입력합니다.

- `[version]` - 점으로 구분된(`.`) 버전 번호 형식의 운영 체제 버전입니다. 예를 들어, `15.10`을 입력합니다.

  - 버전은 마케팅 버전이어서는 **안 됩니다**. 마케팅 버전은 종종 다양한 플랫폼 API 노출 영역이 있는 운영 체제의 여러 개별 버전을 나타내기 때문입니다.

- `[architecture]` - 프로세서 아키텍처입니다. 예를 들면 `x86`, `x64`, `arm`, `arm64` 등입니다.

- `[additional qualifiers]` - 다른 플랫폼을 추가로 구분합니다. 예를 들면 `aot` 또는 `corert` 등입니다.

## <a name="rid-graph"></a>RID 그래프

RID 그래프 또는 런타임 Fallback 그래프는 서로 호환되는 RID 목록입니다. RID는 [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) 패키지에 정의되어 있습니다. 지원되는 RID 및 RID 그래프 목록은 CoreFX 리포지토리에 있는 [*runtime.json*](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) 파일에서 확인할 수 있습니다. 이 파일에서 기본 RID를 제외하고 모든 RID에 `"#import"` 문이 포함되어 있음을 알 수 있습니다. 이러한 문은 호환되는 RID를 나타냅니다.

NuGet에서 패키지를 복원할 때 지정된 런타임에 대한 정확한 일치를 찾으려고 합니다.
정확한 일치를 찾을 수 없는 경우 NuGet은 RID 그래프에 따라 가장 가까운 호환 시스템을 찾을 때까지 그래프를 다시 검색합니다.

다음 예제는 `osx.10.12-x64` RID의 실제 항목입니다.

```json
"osx.10.12-x64": {
    "#import": [ "osx.10.12", "osx.10.11-x64" ]
}
```

위의 RID는 `osx.10.12-x64`가 `osx.10.11-x64`를 가져오도록 지정합니다. 따라서 NuGet에서 패키지를 복원할 때 패키지에서 `osx.10.12-x64`와 정확히 일치하는 값을 찾으려고 합니다. NuGet이 특정 런타임을 찾을 수 없는 경우 예를 들어 `osx.10.11-x64` 런타임을 지정하는 패키지를 복원할 수 있습니다.

다음 예제에서는 마찬가지로 *runtime.json* 파일에 정의된 약간 더 큰 RID 그래프를 보여 줍니다.

```
    win7-x64    win7-x86
       |   \   /    |
       |   win7     |
       |     |      |
    win-x64  |  win-x86
          \  |  /
            win
             |
            any
```

모든 RID는 결국 루트 `any` RID에 다시 매핑됩니다.

RID를 사용할 때는 RID에 대한 다음과 같은 몇 가지 고려 사항을 알고 있어야 합니다.

- RID는 **불투명 문자열**이며 블랙 박스로 취급해야 합니다.
- RID를 프로그래밍 방식으로 빌드하지 마세요.
- 플랫폼에 대해 이미 정의된 RID를 사용합니다.
- RID는 구체적이어야 하므로 실제 RID 값에서 어느 것도 가정하지 마세요.

## <a name="using-rids"></a>RID 사용

RID를 사용할 수 있으려면 어떤 RID가 있는지 알아야 합니다. 새 값이 플랫폼에 정기적으로 추가됩니다.
최신의 완전한 버전을 보려면 CoreFX 리포지토리에서 [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) 파일을 참조하세요.

.NET Core 2.0 SDK에서는 이식 가능 RID라는 개념을 도입합니다. 이식 가능 RID란 RID 그래프에 추가된 새 값인데 아직 특정 버전 또는 OS 배포에 연결되지 않은 값입니다. 이 값은 여러 Linux 배포를 다룰 때 매우 유용합니다.

다음 목록에서는 각 OS에 사용되는 일반적인 RID를 보여 줍니다. `arm` 또는 `corert` 값은 다루지 않습니다.

## <a name="windows-rids"></a>Windows RID

- 이식 가능
  - `win-x86`
  - `win-x64`
- Windows 7 / Windows Server 2008 R2
  - `win7-x64`
  - `win7-x86`
- Windows 8 / Windows Server 2012
  - `win8-x64`
  - `win8-x86`
  - `win8-arm`
- Windows 8.1 / Windows Server 2012 R2
  - `win81-x64`
  - `win81-x86`
  - `win81-arm`
- Windows 10 / Windows Server 2016
  - `win10-x64`
  - `win10-x86`
  - `win10-arm`
  - `win10-arm64`

자세한 내용은 [Windows에서 .NET Core의 필수 구성 요소](windows-prerequisites.md)를 참조하세요.

## <a name="linux-rids"></a>Linux RID

- 이식 가능
  - `linux-x64`
- CentOS
  - `centos-x64`
  - `centos.7-x64`
- Debian
  - `debian-x64`
  - `debian.8-x64`
  - `debian.9-x64`(.NET Core 1.1 이상 버전)
- Fedora
  - `fedora-x64`
  - `fedora.27-x64`
  - `fedora.28-x64`(.NET Core 1.1 이상 버전)
- Gentoo(.NET Core 2.0 이상 버전)
  - `gentoo-x64`
- openSUSE
  - `opensuse-x64`
  - `opensuse.42.3-x64`
- Oracle Linux
  - `ol-x64`
  - `ol.7-x64`
  - `ol.7.0-x64`
  - `ol.7.1-x64`
  - `ol.7.2-x64`
  - `ol.7.3-x64`
  - `ol.7.4-x64`
- Red Hat Enterprise Linux
  - `rhel-x64`
  - `rhel.6-x64`(.NET Core 2.0 이상 버전)
  - `rhel.7-x64`
  - `rhel.7.1-x64`
  - `rhel.7.2-x64`
  - `rhel.7.3-x64`(.NET Core 2.0 이상 버전)
  - `rhel.7.4-x64`(.NET Core 2.0 이상 버전)
- Tizen(.NET Core 2.0 이상 버전)
  - `tizen`
  - `tizen.4.0.0`
  - `tizen.5.0.0`
- Ubuntu
  - `ubuntu-x64`
  - `ubuntu.14.04-x64`
  - `ubuntu.16.04-x64`
  - `ubuntu.17.10-x64`
  - `ubuntu.18.04-x64`
- Ubuntu 파생 제품
  - `linuxmint.17-x64`
  - `linuxmint.17.1-x64`
  - `linuxmint.17.2-x64`
  - `linuxmint.17.3-x64`
  - `linuxmint.18-x64`(.NET Core 2.0 이상 버전)
  - `linuxmint.18.1-x64`(.NET Core 2.0 이상 버전)
  - `linuxmint.18.2-x64`(.NET Core 2.0 이상 버전)
  - `linuxmint.18.3-x64`(.NET Core 2.0 이상 버전)
- SLES(SUSE Enterprise Linux)(.NET Core 2.0 이상 버전)
  - `sles-x64`
  - `sles.12-x64`
  - `sles.12.1-x64`
  - `sles.12.2-x64`
  - `sles.12.3-x64`
- Alpine Linux(.NET Core 2.1 이상 버전)
  - `alpine-x64`
  - `alpine.3.7-x64`

자세한 내용은 [Linux에서 .NET Core의 필수 구성 요소](linux-prerequisites.md)를 참조하세요.

## <a name="macos-rids"></a>macOS RID

macOS RID는 이전 "OSX" 브랜딩을 사용합니다.

- `osx-x64`(.NET Core 2.0 이상 버전, 최소 버전은 `osx.10.12-x64`)
- `osx.10.10-x64`
- `osx.10.11-x64`
- `osx.10.12-x64`(.NET Core 1.1 이상 버전)
- `osx.10.13-x64`

자세한 내용은 [macOS에서 .NET Core의 필수 구성 요소](macos-prerequisites.md)를 참조하세요.

## <a name="android-rids-net-core-20-or-later-versions"></a>Android RID(.NET Core 2.0 이상 버전)

- `android`
- `android.21`

## <a name="see-also"></a>참고 항목

* [런타임 ID](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/readme.md)
