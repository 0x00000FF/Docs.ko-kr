---
title: '방법: JPEG 압축 수준 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], changing encoder parameters
- JPEG images [Windows Forms], setting quality level
ms.assetid: 4b9a74e3-9504-43c1-9f28-ace651d0772e
ms.openlocfilehash: de9dce1b3c15070fda268c430ce5da641efef6f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003888"
---
# <a name="how-to-set-jpeg-compression-level"></a><span data-ttu-id="38d4e-102">방법: JPEG 압축 수준 설정</span><span class="sxs-lookup"><span data-stu-id="38d4e-102">How to: Set JPEG Compression Level</span></span>
<span data-ttu-id="38d4e-103">이미지를 디스크에 저장할 때 파일 크기를 최소화하거나 품질을 향상시키기 위해 이미지의 매개 변수를 수정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38d4e-103">You may want to modify the parameters of an image when you save the image to disk to minimize the file size or improve its quality.</span></span> <span data-ttu-id="38d4e-104">압축 수준을 수정하여 JPEG 이미지의 품질을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38d4e-104">You can adjust the quality of a JPEG image by modifying its compression level.</span></span> <span data-ttu-id="38d4e-105">JPEG 이미지를 저장할 때 압축 수준을 지정 하려면 만들어야 합니다는 <xref:System.Drawing.Imaging.EncoderParameters> 개체를 전달 하는 <xref:System.Drawing.Image.Save%2A> 메서드를 <xref:System.Drawing.Image> 클래스.</span><span class="sxs-lookup"><span data-stu-id="38d4e-105">To specify the compression level when you save a JPEG image, you must create an <xref:System.Drawing.Imaging.EncoderParameters> object and pass it to the <xref:System.Drawing.Image.Save%2A> method of the <xref:System.Drawing.Image> class.</span></span> <span data-ttu-id="38d4e-106">초기화 된 <xref:System.Drawing.Imaging.EncoderParameters> 하나로 구성 된 배열을 개체 <xref:System.Drawing.Imaging.EncoderParameter>합니다.</span><span class="sxs-lookup"><span data-stu-id="38d4e-106">Initialize the <xref:System.Drawing.Imaging.EncoderParameters> object so that it has an array that consists of one <xref:System.Drawing.Imaging.EncoderParameter>.</span></span> <span data-ttu-id="38d4e-107">만들 때 합니다 <xref:System.Drawing.Imaging.EncoderParameter>를 지정 합니다 <xref:System.Drawing.Imaging.Encoder.Quality> 인코더와 원하는 압축 수준을 합니다.</span><span class="sxs-lookup"><span data-stu-id="38d4e-107">When you create the <xref:System.Drawing.Imaging.EncoderParameter>, specify the <xref:System.Drawing.Imaging.Encoder.Quality> encoder, and the desired compression level.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38d4e-108">예제</span><span class="sxs-lookup"><span data-stu-id="38d4e-108">Example</span></span>  
 <span data-ttu-id="38d4e-109">다음 예제 코드에서는 <xref:System.Drawing.Imaging.EncoderParameter> 개체와 세 개의 JPEG 이미지를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="38d4e-109">The following example code creates an <xref:System.Drawing.Imaging.EncoderParameter> object and saves three JPEG images.</span></span> <span data-ttu-id="38d4e-110">각 JPEG 이미지를 수정 하 여 다른 품질 수준에 저장 됩니다는 `long` 에 전달 된 값을 <xref:System.Drawing.Imaging.EncoderParameter> 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="38d4e-110">Each JPEG image is saved with a different quality level, by modifying the `long` value passed to the <xref:System.Drawing.Imaging.EncoderParameter> constructor.</span></span> <span data-ttu-id="38d4e-111">품질 수준이 0이면 가장 많이 압축하고, 100이면 가장 적게 압축합니다.</span><span class="sxs-lookup"><span data-stu-id="38d4e-111">A quality level of 0 corresponds to the greatest compression, and a quality level of 100 corresponds to the least compression.</span></span>  
  
```csharp  
private void VaryQualityLevel()  
    {  
        // Get a bitmap. The using statement ensures objects  
        // are automatically disposed from memory after use.  
        using (Bitmap bmp1 = new Bitmap(@"C:\TestPhoto.jpg"))  
        {  
            ImageCodecInfo jpgEncoder = GetEncoder(ImageFormat.Jpeg);  
  
            // Create an Encoder object based on the GUID  
            // for the Quality parameter category.  
            System.Drawing.Imaging.Encoder myEncoder =  
                System.Drawing.Imaging.Encoder.Quality;  
  
            // Create an EncoderParameters object.  
            // An EncoderParameters object has an array of EncoderParameter  
            // objects. In this case, there is only one  
            // EncoderParameter object in the array.  
            EncoderParameters myEncoderParameters = new EncoderParameters(1);  
  
            EncoderParameter myEncoderParameter = new EncoderParameter(myEncoder, 50L);  
            myEncoderParameters.Param[0] = myEncoderParameter;  
            bmp1.Save(@"c:\TestPhotoQualityFifty.jpg", jpgEncoder, myEncoderParameters);  
  
            myEncoderParameter = new EncoderParameter(myEncoder, 100L);  
            myEncoderParameters.Param[0] = myEncoderParameter;  
            bmp1.Save(@"C:\TestPhotoQualityHundred.jpg", jpgEncoder, myEncoderParameters);  
  
            // Save the bitmap as a JPG file with zero quality level compression.  
            myEncoderParameter = new EncoderParameter(myEncoder, 0L);  
            myEncoderParameters.Param[0] = myEncoderParameter;  
            bmp1.Save(@"C:\TestPhotoQualityZero.jpg", jpgEncoder, myEncoderParameters);  
        }  
    }  
```  
  
```vb  
Private Sub VaryQualityLevel()  
    ' Get a bitmap. The Using statement ensures objects  
    ' are automatically disposed from memory after use.  
    Using bmp1 As New Bitmap("C:\test\TestPhoto.jpg")  
        Dim jpgEncoder As ImageCodecInfo = GetEncoder(ImageFormat.Jpeg)  
  
        ' Create an Encoder object based on the GUID  
        ' for the Quality parameter category.  
        Dim myEncoder As System.Drawing.Imaging.Encoder = System.Drawing.Imaging.Encoder.Quality  
  
        ' Create an EncoderParameters object.  
        ' An EncoderParameters object has an array of EncoderParameter  
        ' objects. In this case, there is only one  
        ' EncoderParameter object in the array.  
        Dim myEncoderParameters As New EncoderParameters(1)  
  
        Dim myEncoderParameter As New EncoderParameter(myEncoder, 50L)  
        myEncoderParameters.Param(0) = myEncoderParameter  
        bmp1.Save("c:\test\TestPhotoQualityFifty.jpg", jpgEncoder, myEncoderParameters)  
  
        myEncoderParameter = New EncoderParameter(myEncoder, 100L)  
        myEncoderParameters.Param(0) = myEncoderParameter  
        bmp1.Save("C:\test\TestPhotoQualityHundred.jpg", jpgEncoder, myEncoderParameters)  
  
        ' Save the bitmap as a JPG file with zero quality level compression.  
        myEncoderParameter = New EncoderParameter(myEncoder, 0L)  
        myEncoderParameters.Param(0) = myEncoderParameter  
        bmp1.Save("C:\test\TestPhotoQualityZero.jpg", jpgEncoder, myEncoderParameters)  
    End Using  
End Sub  
```  
  
```csharp  
private ImageCodecInfo GetEncoder(ImageFormat format)  
{  
    ImageCodecInfo[] codecs = ImageCodecInfo.GetImageDecoders();  
    foreach (ImageCodecInfo codec in codecs)  
    {  
        if (codec.FormatID == format.Guid)  
        {  
            return codec;  
        }  
    }  
    return null;  
}  
```  
  
```vb  
Private Function GetEncoder(ByVal format As ImageFormat) As ImageCodecInfo  
  
    Dim codecs As ImageCodecInfo() = ImageCodecInfo.GetImageDecoders()  
    Dim codec As ImageCodecInfo  
    For Each codec In codecs  
        If codec.FormatID = format.Guid Then  
            Return codec  
        End If  
    Next codec  
    Return Nothing  
  
End Function  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="38d4e-112">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="38d4e-112">Compiling the Code</span></span>  
 <span data-ttu-id="38d4e-113">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="38d4e-113">This example requires:</span></span>  
  
- <span data-ttu-id="38d4e-114">Windows Forms 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="38d4e-114">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="38d4e-115">A <xref:System.Windows.Forms.PaintEventArgs>에서의 매개 변수인 <xref:System.Windows.Forms.PaintEventHandler>합니다. </span><span class="sxs-lookup"><span data-stu-id="38d4e-115">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
- <span data-ttu-id="38d4e-116">**c:\\** 에 있는 `TestPhoto.jpg` 이미지 파일</span><span class="sxs-lookup"><span data-stu-id="38d4e-116">An image file that is named `TestPhoto.jpg` and located at **c:\\**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38d4e-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="38d4e-117">See also</span></span>

- [<span data-ttu-id="38d4e-118">방법: 인코더에서 지원 되는 매개 변수 확인</span><span class="sxs-lookup"><span data-stu-id="38d4e-118">How to: Determine the Parameters Supported by an Encoder</span></span>](how-to-determine-the-parameters-supported-by-an-encoder.md)
- [<span data-ttu-id="38d4e-119">비트맵의 유형</span><span class="sxs-lookup"><span data-stu-id="38d4e-119">Types of Bitmaps</span></span>](types-of-bitmaps.md)
- [<span data-ttu-id="38d4e-120">관리되는 GDI+에서 이미지 인코더 및 디코더 사용</span><span class="sxs-lookup"><span data-stu-id="38d4e-120">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
