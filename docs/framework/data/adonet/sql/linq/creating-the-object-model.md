---
title: 개체 모델 만들기
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 27afce86-9b1d-45fb-8e0b-636bf671a236
caps.latest.revision: 3
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 8686b46545699ab8c07b5d3b5f3ea26080261036
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="creating-the-object-model"></a><span data-ttu-id="2d825-102">개체 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="2d825-102">Creating the Object Model</span></span>
<span data-ttu-id="2d825-103">기존 데이터베이스에서 개체 모델을 만들어 해당 모델을 기본 상태로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d825-103">You can create your object model from an existing database and use the model in its default state.</span></span> <span data-ttu-id="2d825-104">또한 모델의 많은 부분과 동작을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d825-104">You can also customize many aspects of the model and its behavior.</span></span>  
  
 <span data-ttu-id="2d825-105">Visual Studio를 사용 하는 경우 사용할 수 있습니다는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 개체 모델을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2d825-105">If you are using Visual Studio, you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create your object model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2d825-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="2d825-106">In This Section</span></span>  
 [<span data-ttu-id="2d825-107">방법: Visual Basic 또는 C#에서 개체 모델 생성</span><span class="sxs-lookup"><span data-stu-id="2d825-107">How to: Generate the Object Model in Visual Basic or C#</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)  
 <span data-ttu-id="2d825-108">SQLMetal 명령줄 도구 사용법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2d825-108">Describes how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="2d825-109">또한에 대 한 링크를 제공 된 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] Visual Studio 사용자에 대 한</span><span class="sxs-lookup"><span data-stu-id="2d825-109">Also provides a link to the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] for Visual Studio users</span></span>  
  
 [<span data-ttu-id="2d825-110">방법: 외부 파일로 개체 모델 생성</span><span class="sxs-lookup"><span data-stu-id="2d825-110">How to: Generate the Object Model as an External File</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-as-an-external-file.md)  
 <span data-ttu-id="2d825-111">특성 기반 매핑을 사용하는 대신에 외부 매핑 파일을 생성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2d825-111">Describes how to generate an external mapping file instead of using attribute-based mapping.</span></span>  
  
 [<span data-ttu-id="2d825-112">방법: DBML 파일을 수정하여 사용자 지정된 코드 생성</span><span class="sxs-lookup"><span data-stu-id="2d825-112">How to: Generate Customized Code by Modifying a DBML File</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-customized-code-by-modifying-a-dbml-file.md)  
 <span data-ttu-id="2d825-113">DBML 메타 데이터 파일에서 Visual Basic 또는 C# 코드를 생성 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d825-113">Describes how to generate Visual Basic or C# code from a DBML metadata file.</span></span>  
  
 [<span data-ttu-id="2d825-114">방법: DBML 및 외부 매핑 파일 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="2d825-114">How to: Validate DBML and External Mapping Files</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-validate-dbml-and-external-mapping-files.md)  
 <span data-ttu-id="2d825-115">수정한 매핑 파일의 유효성을 검사하는 방법에 대해 설명합니다(고급).</span><span class="sxs-lookup"><span data-stu-id="2d825-115">Describes how to validate mapping files that you have modified (advanced).</span></span>  
  
 [<span data-ttu-id="2d825-116">방법: 엔터티를 직렬화 가능하도록 만들기</span><span class="sxs-lookup"><span data-stu-id="2d825-116">How to: Make Entities Serializable</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-make-entities-serializable.md)  
 <span data-ttu-id="2d825-117">적절한 특성을 추가하여 엔터티를 serialize할 수 있게 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2d825-117">Describes how to add appropriate attributes to make entities serializable.</span></span>  
  
 [<span data-ttu-id="2d825-118">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="2d825-118">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)  
 <span data-ttu-id="2d825-119">코드 편집기를 사용하여 고유한 매핑 코드를 작성하거나 자동으로 생성된 코드를 사용자 지정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2d825-119">Describes how to use the code editor to write your own mapping code, or customize code that has been autogenerated.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2d825-120">관련 단원</span><span class="sxs-lookup"><span data-stu-id="2d825-120">Related Sections</span></span>  
 [<span data-ttu-id="2d825-121">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="2d825-121">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 <span data-ttu-id="2d825-122">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 개체 모델에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2d825-122">Provides details about the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="2d825-123">LINQ to SQL 사용을 위한 일반 단계</span><span class="sxs-lookup"><span data-stu-id="2d825-123">Typical Steps for Using LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md)  
 <span data-ttu-id="2d825-124">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 응용 프로그램을 구현하는 일반적인 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2d825-124">Explains the typical steps that you follow to implement a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] application.</span></span>
