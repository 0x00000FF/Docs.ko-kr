---
title: '방법: EdmGen.exe를 사용하여 개체 계층 코드 생성'
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: c15ceec66ad5b1c9ef414c3e57e3b6e49c372e7a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43416266"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a><span data-ttu-id="fa609-102">방법: EdmGen.exe를 사용하여 개체 계층 코드 생성</span><span class="sxs-lookup"><span data-stu-id="fa609-102">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>
<span data-ttu-id="fa609-103">이 항목에서는 사용 하는 [EDM 생성기 (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) .csdl 파일을 기반으로 하는 개체 계층 코드를 생성 하는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="fa609-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to generate object-layer code  based on the .csdl file.</span></span>  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a><span data-ttu-id="fa609-104">EdmGen.exe를 사용하여 Visual Basic 프로젝트용 School 모델의 개체 계층 코드를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="fa609-104">To generate object-layer code for the School model for a Visual Basic project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="fa609-105">School 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa609-105">Create the School database.</span></span> <span data-ttu-id="fa609-106">자세한 내용은 [School 샘플 데이터베이스 만들기](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0)합니다.</span><span class="sxs-lookup"><span data-stu-id="fa609-106">For more information, see [Creating the School Sample Database](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="fa609-107">School 모델을 생성하거나 School.csdl 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fa609-107">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="fa609-108">자세한 내용은 [방법: 모델 및 매핑 파일 생성을 사용 하 여 EdmGen.exe](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fa609-108">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="fa609-109">명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fa609-109">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a><span data-ttu-id="fa609-110">EdmGen.exe를 사용하여 C# 프로젝트용 School 모델의 개체 계층 코드를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="fa609-110">To generate object-layer code for the School model for a C# project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="fa609-111">School 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa609-111">Create the School database.</span></span> <span data-ttu-id="fa609-112">자세한 내용은 [School 샘플 데이터베이스 만들기](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0)합니다.</span><span class="sxs-lookup"><span data-stu-id="fa609-112">For more information, see [Creating the School Sample Database](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="fa609-113">School 모델을 생성하거나 School.csdl 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fa609-113">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="fa609-114">자세한 내용은 [방법: 모델 및 매핑 파일 생성을 사용 하 여 EdmGen.exe](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fa609-114">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="fa609-115">명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fa609-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fa609-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa609-116">See Also</span></span>  
 [<span data-ttu-id="fa609-117">모델링 및 매핑</span><span class="sxs-lookup"><span data-stu-id="fa609-117">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)  
 [<span data-ttu-id="fa609-118">방법: Entity Framework 프로젝트 수동 구성</span><span class="sxs-lookup"><span data-stu-id="fa609-118">How to: Manually Configure an Entity Framework Project</span></span>](https://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)  
 [<span data-ttu-id="fa609-119">ADO.NET 엔터티 데이터 모델 도구</span><span class="sxs-lookup"><span data-stu-id="fa609-119">ADO.NET Entity Data Model  Tools</span></span>](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)  
 [<span data-ttu-id="fa609-120">방법: 쿼리 성능을 개선 하는 뷰를 미리 생성</span><span class="sxs-lookup"><span data-stu-id="fa609-120">How to: Pre-Generate Views to Improve Query Performance</span></span>](https://msdn.microsoft.com/library/b18a9d16-e10b-4043-ba91-b632f85a2579)  
 [<span data-ttu-id="fa609-121">방법: EdmGen.exe를 사용하여 모델 생성 및 파일 매핑</span><span class="sxs-lookup"><span data-stu-id="fa609-121">How to: Use EdmGen.exe to Generate the Model and Mapping Files</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
