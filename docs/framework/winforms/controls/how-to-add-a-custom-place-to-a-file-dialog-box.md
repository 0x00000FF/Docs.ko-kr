---
title: '방법: 파일 대화 상자에 사용자 지정 위치 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Custom Place to dialog box
- adding Custom Place to dialog box
- CustomPlaces collection
ms.assetid: 63f6469b-59cd-40f6-9e61-8b5831856780
ms.openlocfilehash: 79836dd260cb13912ccba43cfb4a0a3e0ad195fd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59087692"
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="4ee23-102">방법: 파일 대화 상자에 사용자 지정 위치 추가</span><span class="sxs-lookup"><span data-stu-id="4ee23-102">How To: Add a Custom Place to a File Dialog Box</span></span>
<span data-ttu-id="4ee23-103">[!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)]의 기본 열기 및 저장 대화 상자 왼쪽에는 **즐겨찾기 링크**라는 영역이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ee23-103">The default open and save dialog boxes on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] have an area on the left side of the dialog box titled **Favorite Links**.</span></span> <span data-ttu-id="4ee23-104">이 영역을 사용자 지정 위치라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ee23-104">This area is called custom places.</span></span> <span data-ttu-id="4ee23-105"><xref:System.Windows.Forms.OpenFileDialog> 하 고 <xref:System.Windows.Forms.SaveFileDialog> 클래스를 사용 하는 폴더를 추가 하면를 <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="4ee23-105">The <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes allow you to add folders to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ee23-106">에 표시할 사용자 지정 위치에 대 한 순서 대로 합니다 <xref:System.Windows.Forms.OpenFileDialog> 또는 <xref:System.Windows.Forms.SaveFileDialog>, <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> 속성으로 설정 되어 있어야 `true` (기본값).</span><span class="sxs-lookup"><span data-stu-id="4ee23-106">In order for a custom place to appear in the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog>, the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property must be set to `true` (the default).</span></span>  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="4ee23-107">파일 대화 상자에 사용자 지정 위치를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="4ee23-107">To add a custom place to a file dialog box</span></span>  
  
-   <span data-ttu-id="4ee23-108">알려진 폴더 GUID 경로 추가 또는 <xref:System.Windows.Forms.FileDialogCustomPlace> 개체는 <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> 컬렉션 대화 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="4ee23-108">Add a path, a Known Folder GUID, or a <xref:System.Windows.Forms.FileDialogCustomPlace> object to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection of the dialog box.</span></span>  
  
     <span data-ttu-id="4ee23-109">다음 코드 예제에서는 경로를 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4ee23-109">The following code example shows how to add a path:</span></span>  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4ee23-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="4ee23-110">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
- <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4ee23-111">파일 대화 상자의 사용자 지정 위치에 대한 알려진 폴더 GUID</span><span class="sxs-lookup"><span data-stu-id="4ee23-111">Known Folder GUIDs for File Dialog Custom Places</span></span>](known-folder-guids-for-file-dialog-custom-places.md)
