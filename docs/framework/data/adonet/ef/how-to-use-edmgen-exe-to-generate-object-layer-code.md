---
title: '방법: EdmGen.exe를 사용하여 개체 계층 코드 생성'
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: b85bacff093c268cd35dca2ede36e6ceb74ca4d1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251402"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a><span data-ttu-id="48f5d-102">방법: EdmGen.exe를 사용하여 개체 계층 코드 생성</span><span class="sxs-lookup"><span data-stu-id="48f5d-102">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>
<span data-ttu-id="48f5d-103">이 항목에서는 [EDM 생성기 (edmgen.exe)](edm-generator-edmgen-exe.md) 도구를 사용 하 여 csdl 파일을 기반으로 개체 계층 코드를 생성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="48f5d-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](edm-generator-edmgen-exe.md) tool to generate object-layer code  based on the .csdl file.</span></span>  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a><span data-ttu-id="48f5d-104">EdmGen.exe를 사용하여 Visual Basic 프로젝트용 School 모델의 개체 계층 코드를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="48f5d-104">To generate object-layer code for the School model for a Visual Basic project using EdmGen.exe</span></span>  
  
1. <span data-ttu-id="48f5d-105">School 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="48f5d-105">Create the School database.</span></span> <span data-ttu-id="48f5d-106">자세한 내용은 [School 샘플 데이터베이스 만들기](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48f5d-106">For more information, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="48f5d-107">School 모델을 생성하거나 School.csdl 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="48f5d-107">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="48f5d-108">자세한 내용은 [방법: Edmgen.exe를 사용 하 여 모델 및 매핑 파일](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="48f5d-108">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3. <span data-ttu-id="48f5d-109">명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="48f5d-109">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a><span data-ttu-id="48f5d-110">EdmGen.exe를 사용하여 C# 프로젝트용 School 모델의 개체 계층 코드를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="48f5d-110">To generate object-layer code for the School model for a C# project using EdmGen.exe</span></span>  
  
1. <span data-ttu-id="48f5d-111">School 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="48f5d-111">Create the School database.</span></span> <span data-ttu-id="48f5d-112">자세한 내용은 [School 샘플 데이터베이스 만들기](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48f5d-112">For more information, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="48f5d-113">School 모델을 생성하거나 School.csdl 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="48f5d-113">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="48f5d-114">자세한 내용은 [방법: Edmgen.exe를 사용 하 여 모델 및 매핑 파일](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="48f5d-114">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3. <span data-ttu-id="48f5d-115">명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="48f5d-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="48f5d-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="48f5d-116">See also</span></span>

- [<span data-ttu-id="48f5d-117">모델링 및 매핑</span><span class="sxs-lookup"><span data-stu-id="48f5d-117">Modeling and Mapping</span></span>](modeling-and-mapping.md)
- <span data-ttu-id="48f5d-118">[방법: Entity Framework 프로젝트 수동 구성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="48f5d-118">[How to: Manually Configure an Entity Framework Project](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span></span>
- <span data-ttu-id="48f5d-119">[ADO.NET 엔터티 데이터 모델 도구](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="48f5d-119">[ADO.NET Entity Data Model  Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
- <span data-ttu-id="48f5d-120">[방법: 뷰를 미리 생성 하 여 쿼리 성능 향상](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="48f5d-120">[How to: Pre-Generate Views to Improve Query Performance](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span></span>
- [<span data-ttu-id="48f5d-121">방법: Edmgen.exe를 사용 하 여 모델 및 매핑 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="48f5d-121">How to: Use EdmGen.exe to Generate the Model and Mapping Files</span></span>](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
