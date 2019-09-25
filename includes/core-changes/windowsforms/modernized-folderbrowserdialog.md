---
ms.openlocfilehash: a7cf6210e288d3521f1df248927f0e7cfaf45cab
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71119121"
---
### <a name="modernization-of-the-folderbrowserdialog"></a><span data-ttu-id="1506f-101">FolderBrowserDialog의 현대화</span><span class="sxs-lookup"><span data-stu-id="1506f-101">Modernization of the FolderBrowserDialog</span></span>

<span data-ttu-id="1506f-102">이 <xref:System.Windows.Forms.FolderBrowserDialog> 컨트롤은 .NET Core 용 Windows Forms 애플리케이션에서 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1506f-102">The <xref:System.Windows.Forms.FolderBrowserDialog> control has changed in Windows Forms applications for .NET Core.</span></span>

#### <a name="change-description"></a><span data-ttu-id="1506f-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="1506f-103">Change description</span></span>

<span data-ttu-id="1506f-104">.NET Framework에서 Windows Forms는 <xref:System.Windows.Forms.FolderBrowserDialog> 컨트롤에 대해 다음 대화 상자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1506f-104">In the .NET Framework, Windows forms uses the following dialog for the <xref:System.Windows.Forms.FolderBrowserDialog> control:</span></span>

![.NET Framework의 FolderBrowserDialogControl](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-framework.png)

<span data-ttu-id="1506f-106">.NET Core 3.0에서는 Windows Forms가 Windows Vista에서 도입된 최신 COM 기반 컨트롤을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1506f-106">In .NET Core 3.0, Windows Forms users a newer COM-based control that was introduced in Windows Vista:</span></span>

![.NET Core의 FolderBrowserDialogControl](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-core.png)

#### <a name="version-introduced"></a><span data-ttu-id="1506f-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="1506f-108">Version introduced</span></span>

<span data-ttu-id="1506f-109">3.0</span><span class="sxs-lookup"><span data-stu-id="1506f-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1506f-110">권장 작업</span><span class="sxs-lookup"><span data-stu-id="1506f-110">Recommended action</span></span>

<span data-ttu-id="1506f-111">대화 상자가 자동으로 업그레이드됩니다.</span><span class="sxs-lookup"><span data-stu-id="1506f-111">The dialog will be upgraded automatically.</span></span>

<span data-ttu-id="1506f-112">원래 대화 상자를 유지하려는 경우 다음 코드 조각에 나와 있듯이 대화 상자를 표시하기 전에 <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> 속성을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1506f-112">If you desire to retain the original dialog, set the <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> property to `false` before showing the dialog, as illustrated by the following code fragment:</span></span>

```csharp
var dialog = new FolderBrowserDialog();
dialog.AutoUpgradeEnabled = false;
dialog.ShowDialog();
```

#### <a name="category"></a><span data-ttu-id="1506f-113">범주</span><span class="sxs-lookup"><span data-stu-id="1506f-113">Category</span></span>

<span data-ttu-id="1506f-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1506f-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1506f-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="1506f-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>

<!-- 

### Affected APIs

- `System.Windows.Forms.FolderBrowserDialog`

-->