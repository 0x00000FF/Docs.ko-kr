---
title: '방법: Windows Form에서 소리 재생'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- playing sounds [Windows Forms], Windows Forms
- sounds [Windows Forms], playing
- sounds
- My.Computer.Audio object [Windows Forms], playing sounds
- examples [Windows Forms], sounds
ms.assetid: 3d3350b7-1ebd-4e05-a738-48ca1160a19d
ms.openlocfilehash: 02b0cb2952e11946f994819bb09a55167781137c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607253"
---
# <a name="how-to-play-a-sound-from-a-windows-form"></a><span data-ttu-id="67da6-102">방법: Windows Form에서 소리 재생</span><span class="sxs-lookup"><span data-stu-id="67da6-102">How to: Play a Sound from a Windows Form</span></span>
<span data-ttu-id="67da6-103">이 예제에서는 런타임에 지정된 경로에서 소리를 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="67da6-103">This example plays a sound at a given path at run time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67da6-104">예제</span><span class="sxs-lookup"><span data-stu-id="67da6-104">Example</span></span>  
  
```vb  
Sub PlaySimpleSound()  
    My.Computer.Audio.Play("c:\Windows\Media\chimes.wav")  
End Sub  
```  
  
```csharp  
private void playSimpleSound()  
{  
    SoundPlayer simpleSound = new SoundPlayer(@"c:\Windows\Media\chimes.wav");  
    simpleSound.Play();  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="67da6-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="67da6-105">Compiling the Code</span></span>  
 <span data-ttu-id="67da6-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="67da6-106">This example requires:</span></span>  
  
-   <span data-ttu-id="67da6-107">파일 이름 `"c:\Windows\Media\chimes.wav"`를 유효한 파일 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="67da6-107">That you replace the file name `"c:\Windows\Media\chimes.wav"` with a valid file name.</span></span>  
  
-   <span data-ttu-id="67da6-108">(C#)에 대 한 참조를 <xref:System.Media?displayProperty=nameWithType> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="67da6-108">(C#) A reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="67da6-109">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="67da6-109">Robust Programming</span></span>  
 <span data-ttu-id="67da6-110">파일 작업은 적절한 구조적 예외 처리 블록 내에 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67da6-110">File operations should be enclosed within appropriate structured exception handling blocks.</span></span>  
  
 <span data-ttu-id="67da6-111">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="67da6-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="67da6-112">경로 이름 형식이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="67da6-112">The path name is malformed.</span></span> <span data-ttu-id="67da6-113">예를 들어 잘못된 문자를 포함하거나 공백만으로 이루어져 있습니다(<xref:System.ArgumentException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="67da6-113">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException> class).</span></span>  
  
-   <span data-ttu-id="67da6-114">경로가 읽기 전용입니다(<xref:System.IO.IOException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="67da6-114">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="67da6-115">경로 이름이 `null`입니다(<xref:System.ArgumentNullException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="67da6-115">The path name is `null` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="67da6-116">경로 이름이 너무 깁니다(<xref:System.IO.PathTooLongException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="67da6-116">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="67da6-117">경로가 잘못되었습니다(<xref:System.IO.DirectoryNotFoundException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="67da6-117">The path is invalid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
-   <span data-ttu-id="67da6-118">경로가 콜론 ":" (<xref:System.NotSupportedException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="67da6-118">The path is only a colon, ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="67da6-119">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="67da6-119">.NET Framework Security</span></span>  
 <span data-ttu-id="67da6-120">파일 이름을 바탕으로 파일 내용을 판단하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67da6-120">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="67da6-121">예를 들어 `Form1.vb` 파일이 Visual Basic 소스 파일이 아닐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67da6-121">For example, the file `Form1.vb` may not be a Visual Basic source file.</span></span> <span data-ttu-id="67da6-122">애플리케이션에서 데이터를 사용하기 전에 모든 입력을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67da6-122">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67da6-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="67da6-123">See also</span></span>
- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="67da6-124">방법: Windows Form에서 비동기적으로 소리 로드</span><span class="sxs-lookup"><span data-stu-id="67da6-124">How to: Load a Sound Asynchronously within a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-load-a-sound-asynchronously-within-a-windows-form.md)

