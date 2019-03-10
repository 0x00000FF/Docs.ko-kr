---
title: '방법: Windows Form에서 소리 재생 반복'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sound loops
- SoundPlayer class [Windows Forms], play looping
- sounds [Windows Forms], looping
- playing sounds [Windows Forms], looping
ms.assetid: ea95dd46-10a3-46c0-8263-4b205f00df7f
ms.openlocfilehash: 43fcc472960cc3f2432d3872160d9ace4c617836
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719275"
---
# <a name="how-to-loop-a-sound-playing-on-a-windows-form"></a><span data-ttu-id="10241-102">방법: Windows Form에서 소리 재생 반복</span><span class="sxs-lookup"><span data-stu-id="10241-102">How to: Loop a Sound Playing on a Windows Form</span></span>
<span data-ttu-id="10241-103">다음 코드 예제에서는 반복해서 소리를 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="10241-103">The following code example plays a sound repeatedly.</span></span> <span data-ttu-id="10241-104">`stopPlayingButton_Click` 이벤트 처리기의 코드가 실행되면 현재 재생되는 모든 소리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="10241-104">When the code in the `stopPlayingButton_Click` event handler runs, any sound currently playing stops.</span></span> <span data-ttu-id="10241-105">소리가 재생되지 않으면 아무것도 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10241-105">If no sound is playing, nothing happens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10241-106">예제</span><span class="sxs-lookup"><span data-stu-id="10241-106">Example</span></span>  
 [!code-csharp[System.Media.SoundPlayer.PlayLooping#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.PlayLooping#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="10241-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="10241-107">Compiling the Code</span></span>  
 <span data-ttu-id="10241-108">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="10241-108">This example requires:</span></span>  
  
-   <span data-ttu-id="10241-109">System 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="10241-109">References to the System and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="10241-110">파일 이름 `"c:\Windows\Media\chimes.wav"`를 유효한 파일 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="10241-110">That you replace the file name `"c:\Windows\Media\chimes.wav"` with a valid file name.</span></span>  
  
 <span data-ttu-id="10241-111">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="10241-111">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="10241-112">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10241-112">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="10241-113">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="10241-113">Robust Programming</span></span>  
 <span data-ttu-id="10241-114">파일 작업을 적절한 예외 처리 블록 내에 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10241-114">File operations should be enclosed within appropriate exception-handling blocks.</span></span>  
  
 <span data-ttu-id="10241-115">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="10241-115">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="10241-116">경로 이름 형식이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="10241-116">The path name is malformed.</span></span> <span data-ttu-id="10241-117">예를 들어 잘못된 문자를 포함하거나 공백만 포함합니다(<xref:System.ArgumentException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="10241-117">For example, it contains characters that are not valid or it is only white space (<xref:System.ArgumentException> class).</span></span>  
  
-   <span data-ttu-id="10241-118">경로가 읽기 전용입니다(<xref:System.IO.IOException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="10241-118">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="10241-119">경로 이름이 `Nothing`입니다(<xref:System.ArgumentNullException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="10241-119">The path name is `Nothing` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="10241-120">경로 이름이 너무 깁니다(<xref:System.IO.PathTooLongException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="10241-120">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="10241-121">경로가 잘못되었습니다(<xref:System.IO.DirectoryNotFoundException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="10241-121">The path is invalid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
-   <span data-ttu-id="10241-122">경로가 콜론 “:”뿐입니다(<xref:System.NotSupportedException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="10241-122">The path is only a colon ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="10241-123">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="10241-123">.NET Framework Security</span></span>  
 <span data-ttu-id="10241-124">파일 이름을 바탕으로 파일 내용을 판단하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10241-124">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="10241-125">예를 들어 Form1.vb 파일이 Visual Basic 소스 파일이 아닐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10241-125">For example, the file Form1.vb may not be a Visual Basic source file.</span></span> <span data-ttu-id="10241-126">애플리케이션에서 데이터를 사용하기 전에 모든 입력을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10241-126">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10241-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="10241-127">See also</span></span>
- <xref:System.Media.SoundPlayer.PlayLooping%2A>
- [<span data-ttu-id="10241-128">방법: Windows Form에서 소리 재생</span><span class="sxs-lookup"><span data-stu-id="10241-128">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
- [<span data-ttu-id="10241-129">SoundPlayer 클래스 개요</span><span class="sxs-lookup"><span data-stu-id="10241-129">SoundPlayer Class Overview</span></span>](soundplayer-class-overview.md)
