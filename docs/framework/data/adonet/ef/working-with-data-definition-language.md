---
title: 데이터 정의 언어로 작업
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec50083d-44f4-4093-9b23-5eacd601f96e
ms.openlocfilehash: 25d7f49644996d87ddb5d191dc313916c0ca6fbb
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45513964"
---
# <a name="working-with-data-definition-language"></a><span data-ttu-id="69dcf-102">데이터 정의 언어로 작업</span><span class="sxs-lookup"><span data-stu-id="69dcf-102">Working with Data Definition Language</span></span>
<span data-ttu-id="69dcf-103">부터 합니다 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 버전 4는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] DDL (데이터 정의 언어)을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="69dcf-103">Starting with the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] version 4, the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] supports data definition language (DDL).</span></span> <span data-ttu-id="69dcf-104">이렇게 하면 연결 문자열 및 저장소(SSDL) 모델의 메타데이터를 기반으로 데이터베이스 인스턴스를 만들거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69dcf-104">This allows you to create or delete a database instance based on the connection string and the metadata of the storage (SSDL) model.</span></span>  
  
 <span data-ttu-id="69dcf-105"><xref:System.Data.Objects.ObjectContext>의 다음 메서드는 연결 문자열과 SSDL 콘텐츠를 사용하여 데이터베이스를 만들거나 삭제하고, 데이터베이스가 있는지 확인하며, 생성된 DDL 스크립트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="69dcf-105">The following methods on the <xref:System.Data.Objects.ObjectContext> use the connection string and the SSDL content to accomplish the following: create or delete the database, check whether the database exists, and view the generated DDL script:</span></span>  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabaseScript%2A>  
  
> [!NOTE]
>  <span data-ttu-id="69dcf-106">DDL 명령을 실행하려면 충분한 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69dcf-106">Executing the DDL commands assumes sufficient permissions.</span></span>  
  
 <span data-ttu-id="69dcf-107">위에 나열된 메서드는 대부분의 작업을 기본 ADO.NET 데이터 공급자에 위임합니다.</span><span class="sxs-lookup"><span data-stu-id="69dcf-107">The methods previously listed delegate most of the work to the underlying ADO.NET data provider.</span></span> <span data-ttu-id="69dcf-108">데이터베이스 개체를 생성하는 데 사용되는 명명 규칙이 쿼리 및 업데이트에 사용되는 규칙과 일치하는지 확인하는 것은 공급자의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="69dcf-108">It is the provider’s responsibility to ensure that the naming convention used to generate database objects is consistent with conventions used for querying and updates.</span></span>  
  
 <span data-ttu-id="69dcf-109">다음 예제에서는 기존 모델을 기반으로 데이터베이스를 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="69dcf-109">The following example shows you how to generate the database based on the existing model.</span></span> <span data-ttu-id="69dcf-110">또한 새 엔터티 개체를 개체 컨텍스트에 추가한 다음 데이터베이스에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="69dcf-110">It also adds a new entity object to the object context and then saves it to the database.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="69dcf-111">절차</span><span class="sxs-lookup"><span data-stu-id="69dcf-111">Procedures</span></span>  
  
#### <a name="to-define-a-database-based-on-the-existing-model"></a><span data-ttu-id="69dcf-112">기존 모델을 기반으로 데이터베이스를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="69dcf-112">To define a database based on the existing model</span></span>  
  
1.  <span data-ttu-id="69dcf-113">콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="69dcf-113">Create a console application.</span></span>  
  
2.  <span data-ttu-id="69dcf-114">응용 프로그램에 기존 모델을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="69dcf-114">Add an existing model to your application.</span></span>  
  
    1.  <span data-ttu-id="69dcf-115">이라는 빈 모델을 추가 `SchoolModel`합니다.</span><span class="sxs-lookup"><span data-stu-id="69dcf-115">Add an empty model named `SchoolModel`.</span></span> <span data-ttu-id="69dcf-116">빈 모델을 만들려면 다음을 참조 합니다 [방법: 새.edmx 파일을 만들](https://msdn.microsoft.com/library/beb8189e-e51c-4051-839c-9902c224abf2) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="69dcf-116">To create an empty model, see the [How to: Create a New .edmx File](https://msdn.microsoft.com/library/beb8189e-e51c-4051-839c-9902c224abf2) topic.</span></span>  
  
     <span data-ttu-id="69dcf-117">SchoolModel.edmx 파일이 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="69dcf-117">The SchoolModel.edmx file is added to your project.</span></span>  
  
    1.  <span data-ttu-id="69dcf-118">개념적, 저장소, 복사 및 매핑에서 School 모델에 대 한 콘텐츠를 [School 모델](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="69dcf-118">Copy the conceptual, storage, and mapping content for the School model from the [School Model](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) topic.</span></span>  
  
    2.  <span data-ttu-id="69dcf-119">SchoolModel.edmx 파일을 열고 콘텐츠를 `edmx:Runtime` 태그 안에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="69dcf-119">Open the SchoolModel.edmx file and paste the content within the `edmx:Runtime` tags.</span></span>  
  
3.  <span data-ttu-id="69dcf-120">다음 코드를 main 함수에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="69dcf-120">Add the following code to your main function.</span></span> <span data-ttu-id="69dcf-121">이 코드에서는 데이터베이스 서버에 대한 연결 문자열을 초기화하고 DDL 스크립트를 확인하며, 데이터베이스를 만들고 새 엔터티를 컨텍스트에 추가한 다음 변경 내용을 데이터베이스에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="69dcf-121">The code initializes the connection string to your database server, views the DDL script, creates the database, adds a new entity to the context, and saves the changes to the database.</span></span>  
  
     [!code-csharp[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/csharp/VS_Snippets_Data/DP ObjectServices Concepts/CS/Source.cs#ddl)]
     [!code-vb[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP ObjectServices Concepts/VB/Source.vb#ddl)]
