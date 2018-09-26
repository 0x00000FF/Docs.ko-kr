---
title: '&lt;컴파일러&gt; 요소'
ms.date: 08/14/2018
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
author: mcleblanc
ms.author: markl
ms.openlocfilehash: a26fc0bda341e85ca54f3dee4addd14e4164209c
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2018
ms.locfileid: "47193959"
---
# <a name="ltcompilergt-element"></a>&lt;컴파일러&gt; 요소

언어 공급자에 대한 컴파일러 구성 특성을 지정합니다.

\<구성 요소 > \<system.codedom 요소 > \<compilers 요소 > \<컴파일러 > 요소

## <a name="syntax"></a>구문

```xml
<compiler
  language="languageName[;...;...]"
  extension="fileExtension[;...;...]"
  type="typeName, assemblyName"
  warningLevel="number"
  compilerOptions="option1 option2"
/>
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

|특성|설명|
|---------------|-----------------|
|`compilerOptions`|선택적 특성입니다.<br /><br /> 컴파일에 추가 컴파일러 별 인수를 지정합니다. 에 대 한 값을 `compilerOptions` 특성 일반적으로 컴파일러에 대 한 컴파일러 옵션 항목에 나와 있습니다.|
|`extension`|필수 특성입니다.<br /><br /> 언어 공급자에 대 한 소스 파일에서 사용 하는 파일 이름 확장명의 세미콜론으로 구분 된 목록을 제공 합니다. 예를 들어, ".cs"가 있습니다.|
|`language`|필수 특성입니다.<br /><br /> 언어 공급자에서 지 원하는 언어 이름의 세미콜론으로 구분 된 목록을 제공 합니다. 예를 들어, "c#; cs; csharp"입니다.|
|`type`|필수 특성입니다.<br /><br /> 공급자 구현이 들어 있는 어셈블리의 이름을 포함 한 언어 공급자의 형식 이름을 지정 합니다. 형식 이름에 정의 된 요구 사항에 맞아야 [정규화 된 형식 이름 지정](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)합니다.|
|`warningLevel`|선택적 특성입니다.<br /><br /> 기본 컴파일러 경고 수준을;를 지정합니다. 컴파일 경고를 오류로 언어 공급자는 처리 수준을 결정 합니다.|

### <a name="child-elements"></a>자식 요소

|요소|설명|
|-------------|-----------------|
|[\<providerOption > 요소](../../../../../docs/framework/configure-apps/file-schema/compiler/provideroption-element.md)|언어 공급자에 대 한 컴파일러 버전 특성을 지정합니다.|

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|[\<configuration> 요소](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|
|[\<system.codedom > 요소](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|사용 가능한 언어 공급자에 대한 컴파일러 구성 설정을 지정합니다.|
|[\<컴파일러 > 요소](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|컴파일러 구성 요소에 대 한 컨테이너 0 개 이상 포함 `<compiler>` 요소입니다.|

## <a name="remarks"></a>설명

각 `<compiler>` 요소는 특정 언어 공급자에 대 한 컴파일러 구성 특성을 지정 합니다. 공급자 확장 합니다 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> ; 특정 언어에 대 한 클래스는 `<compiler>` 컴파일러 및 언어 공급자에 대 한 코드 생성기 설정 요소를 정의 합니다.

.NET Framework는 컴퓨터 구성 파일(Machine.config)의 초기 컴파일러 설정을 정의합니다. 개발자 및 컴파일러 공급업체는 새로운 <xref:System.CodeDom.Compiler.CodeDomProvider> 구현에 대한 구성 설정을 추가할 수 있습니다. <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> 메서드를 사용하여 컴퓨터에서 언어 공급자 및 컴파일러 구성 설정을 프로그래밍 방식으로 열거할 수 있습니다.

응용 프로그램 또는 웹 구성 파일에서 컴파일러 요소 보완 하거나 컴퓨터 구성 파일의 설정을 재정의할 수 있습니다. 동일한 언어 이름 또는 파일 확장명으로 둘 이상의 공급자 구현을 구성 된 경우 마지막으로 일치 하는 구성 해당 언어 이름 또는 파일 확장에 대 한 모든 이전 구성된 공급자를 재정의 합니다.

## <a name="configuration-file"></a>구성 파일

컴퓨터 구성 파일 및 응용 프로그램 구성 파일에서이 요소를 사용할 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 일반적인 컴파일러 구성 요소를 보여 줍니다.

```xml
<configuration>
  <system.codedom>
    <compilers>
      <!-- zero or more compiler elements -->
      <compiler
        language="c#;cs;csharp"
        extension=".cs"
        type="Microsoft.CSharp.CSharpCodeProvider, System,
          Version=2.0.3600.0, Culture=neutral,
          PublicKeyToken=b77a5c561934e089"
        compilerOptions="/optimize"
        warningLevel="1" />
    </compilers>
  </system.codedom>
</configuration>
```

## <a name="see-also"></a>참고 항목

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [\<컴파일러 > 요소](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)
- [지정 완전히 정규화 된 형식 이름]-(... /.. /.. /.. /.. / docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)
- [컴파일 (ASP.NET 설정 스키마)에 대 한 컴파일러에 대 한 compiler 요소](https://msdn.microsoft.com/library/f7d6b078-5d42-4134-b3f7-62e1aba1df1e(v=vs.100))
