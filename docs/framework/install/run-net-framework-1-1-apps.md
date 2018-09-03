---
title: Windows 8, Windows 8.1 또는 Windows 10에서 .NET Framework 1.1 앱 실행
ms.date: 05/26/2017
helpviewer_keywords:
- Windows 8, running .NET Framework 1.1 apps
- .NET Framework 1.1, running on Windows 8
ms.assetid: fb14e195-fea5-4561-b9a8-60a67283edb9
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f3a7331d4488f4a0eeac71b0b866bc4b6864eed6
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2018
ms.locfileid: "43469936"
---
# <a name="run-net-framework-11-apps-on-windows-8-windows-81-or-windows-10"></a>Windows 8, Windows 8.1 또는 Windows 10에서 .NET Framework 1.1 앱 실행

.NET Framework 1.1은 [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] 또는 Windows 10 운영 체제에서 지원되지 않습니다. 앱을 실행하는 데 특별히 .NET Framework 1.1이 필요하다고 확인될 수도 있습니다. 이 경우 ISV(Independent Software Vendor)에 문의하여 [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] 이상의 버전에서 실행되도록 앱을 업그레이드해야 합니다. 자세한 내용은 [.NET Framework 1.1에서 마이그레이션](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)을 참조하세요.

## <a name="install-the-net-framework-11-from-a-cd-or-download-center"></a>CD 또는 다운로드 센터에서 .NET Framework 1.1 설치

.NET Framework 1.1을 [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] 또는 Windows 10에 수동으로 설치할 수는 없습니다. 더 이상 지원되지 않습니다. 패키지를 설치하려고 하면 다음과 같은 오류 메시지가 표시됩니다. "이 버전의 .NET Framework가 이전에 설치된 버전과 호환되지 않으므로 설치를 계속할 수 없습니다." 이 문제를 해결하려면 [.NET Framework 3.5 SP1](https://www.microsoft.com/download/details.aspx?id=22)을 설치합니다. 이 버전에는 [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)] 및 Windows 10에서 지원되는 .NET Framework 2.0(.NET Framework 1.1 후속 릴리스)이 포함되어 있습니다. 항상 먼저 앱을 설치하여 .NET Framework의 이후 버전으로 자동으로 업데이트되는지 확인해야 합니다. 그러지 않으면 ISV에 앱 업데이트에 대해 문의하세요.

## <a name="see-also"></a>참고 항목

[.NET Framework 1.1에서 마이그레이션](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)
[Windows 10, Windows 8.1 및 Windows 8에 .NET Framework 3.5 설치](../../../docs/framework/install/dotnet-35-windows-10.md)
