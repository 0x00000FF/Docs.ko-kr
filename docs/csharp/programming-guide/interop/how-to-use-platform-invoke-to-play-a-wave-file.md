---
title: '방법: 플랫폼 호출을 사용하여 웨이브 파일 재생(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
ms.openlocfilehash: f2234acb9d4eb3b436f3ccdad19525a5ebf26f7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-platform-invoke-to-play-a-wave-file-c-programming-guide"></a>방법: 플랫폼 호출을 사용하여 웨이브 파일 재생(C# 프로그래밍 가이드)
다음 C# 코드 예제에서는 플랫폼 호출 서비스를 사용하여 Windows 운영 체제에서 .wav 사운드 파일을 재생하는 방법을 설명합니다.  
  
## <a name="example"></a>예  
 이 예제 코드에서는 `DllImport`를 사용하여 `winmm.dll`의 `PlaySound` 메서드 진입점을 `Form1 PlaySound()`로 가져옵니다. 이 예제에는 단추를 포함하는 간단한 Windows Form이 있습니다. 단추를 클릭하면 재생할 파일을 열 수 있도록 표준 Windows <xref:System.Windows.Forms.OpenFileDialog> 대화 상자가 열립니다. 웨이브 파일을 선택하면 winmm.DLL 어셈블리 메서드의 `PlaySound()` 메서드를 사용하여 재생됩니다. winmm.dll의 `PlaySound` 메서드에 대한 자세한 내용은 [파형 오디오 파일과 함께 PlaySound 함수 사용](https://msdn.microsoft.com/library/aa910379.aspx)을 참조하세요. .wav 확장명을 가진 파일을 찾아서 선택한 다음 **열기**를 클릭하여 플랫폼 호출을 통해 웨이브 파일을 재생합니다. 텍스트 상자에 선택한 파일의 전체 경로가 표시됩니다.  
  
 **파일 열기** 대화 상자가 필터 설정을 통해 .wav 확장명을 가진 파일만 표시하도록 필터링됩니다.  
  
 [!code-csharp[csProgGuideInterop#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_1.cs)]  
  
 [!code-csharp[csProgGuideInterop#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_2.cs)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
### <a name="to-compile-the-code"></a>코드를 컴파일하려면  
  
1.  Visual Studio에서 새 C# Windows 응용 프로그램 프로젝트를 만들고 이름을 **WinSound**로 지정합니다.  
  
2.  위의 코드를 복사하여 `Form1.cs` 파일 내용 위에 붙여넣습니다.  
  
3.  다음 코드를 복사하여 `Form1.Designer.cs` 파일의 `InitializeComponent()` 메서드에서 기존 코드 뒤에 붙여넣습니다.  
  
     [!code-csharp[csProgGuideInterop#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_3.cs)]  
  
4.  코드를 컴파일하고 실행합니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 자세한 내용은 [.NET Framework 보안](https://technet.microsoft.com/en-us/security/)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [상호 운용성 개요](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 [플랫폼 호출 자세히 보기](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)  
 [플랫폼 호출을 사용하여 데이터 마샬링](../../../framework/interop/marshaling-data-with-platform-invoke.md)
