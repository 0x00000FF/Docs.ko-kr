---
title: '방법: BMP 이미지를 PNG 이미지로 변환'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BMP images [Windows Forms], converting to PNG
- image formats [Windows Forms], converting between
ms.assetid: 9d4a692d-73ac-4ce3-9e05-9ec321e8fbd6
ms.openlocfilehash: 3072c07781a8e8e57b64b48e5b4c304c2a0a0efb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937763"
---
# <a name="how-to-convert-a-bmp-image-to-a-png-image"></a><span data-ttu-id="27910-102">방법: BMP 이미지를 PNG 이미지로 변환</span><span class="sxs-lookup"><span data-stu-id="27910-102">How to: Convert a BMP image to a PNG image</span></span>
<span data-ttu-id="27910-103">이미지 파일 형식 간에 변환하려는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="27910-103">Oftentimes, you will want to convert from one image file format to another.</span></span> <span data-ttu-id="27910-104"><xref:System.Drawing.Image> 클래스의 <xref:System.Drawing.Image.Save%2A> 메서드를 호출하고 원하는 이미지 파일 형식에 대해 <xref:System.Drawing.Imaging.ImageFormat>을 지정하여 이 변환을 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27910-104">You can do this conversion easily by calling the <xref:System.Drawing.Image.Save%2A> method of the <xref:System.Drawing.Image> class and specifying the <xref:System.Drawing.Imaging.ImageFormat> for the desired image file format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27910-105">예제</span><span class="sxs-lookup"><span data-stu-id="27910-105">Example</span></span>  
 <span data-ttu-id="27910-106">다음 예제에서는 형식에서 BMP 이미지를 로드하고 PNG 형식으로 이미지를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="27910-106">The following example loads a BMP image from a type, and saves the image in the PNG format.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#4](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#4)]
 [!code-vb[UsingImageEncodersDecoders#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="27910-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="27910-107">Compiling the Code</span></span>  
 <span data-ttu-id="27910-108">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="27910-108">This example requires:</span></span>  
  
- <span data-ttu-id="27910-109">Windows Forms 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="27910-109">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="27910-110">`System.Drawing.Imaging` 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="27910-110">A reference to the `System.Drawing.Imaging` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27910-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="27910-111">See also</span></span>

- [<span data-ttu-id="27910-112">방법: 설치 된 인코더 나열</span><span class="sxs-lookup"><span data-stu-id="27910-112">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="27910-113">관리되는 GDI+에서 이미지 인코더 및 디코더 사용</span><span class="sxs-lookup"><span data-stu-id="27910-113">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
- [<span data-ttu-id="27910-114">비트맵의 유형</span><span class="sxs-lookup"><span data-stu-id="27910-114">Types of Bitmaps</span></span>](types-of-bitmaps.md)
