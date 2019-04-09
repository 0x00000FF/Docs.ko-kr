---
title: '방법: 모델 및 매핑 파일을 포함 리소스로 만들기'
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: b00ccdd0a1fc1cb22cf7cc0d0a3177dcc0e8017f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138595"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a><span data-ttu-id="e2f28-102">방법: 모델 및 매핑 파일을 포함 리소스로 만들기</span><span class="sxs-lookup"><span data-stu-id="e2f28-102">How to: Make Model and Mapping Files Embedded Resources</span></span>
<span data-ttu-id="e2f28-103">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 모델 및 매핑 파일을 응용 프로그램의 포함 리소스로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2f28-103">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enables you to deploy model and mapping files as embedded resources of an application.</span></span> <span data-ttu-id="e2f28-104">포함된 모델 및 매핑 파일이 있는 어셈블리는 엔터티 연결과 동일한 응용 프로그램 도메인에 로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2f28-104">The assembly with the embedded model and mapping files must be loaded in the same application domain as the entity connection.</span></span> <span data-ttu-id="e2f28-105">자세한 내용은 [연결 문자열](../../../../../docs/framework/data/adonet/ef/connection-strings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2f28-105">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span> <span data-ttu-id="e2f28-106">기본적으로 [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] 도구는 모델과 매핑 파일을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e2f28-106">By default, the [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] tools embed the model and mapping files.</span></span> <span data-ttu-id="e2f28-107">모델 및 매핑 파일을 수동으로 정의하는 경우 이 절차를 사용하여 파일을 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 응용 프로그램과 함께 포함 리소스로 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2f28-107">When you manually define the model and mapping files, use this procedure to ensure that the files are deployed as embedded resources together with an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2f28-108">포함 리소스를 유지하려면 모델 및 매핑 파일이 수정될 때마다 이 절차를 반복해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2f28-108">To maintain embedded resources, you must repeat this procedure whenever the model and mapping files are modified.</span></span>  
  
### <a name="to-embed-model-and-mapping-files"></a><span data-ttu-id="e2f28-109">모델 및 매핑 파일을 포함하려면</span><span class="sxs-lookup"><span data-stu-id="e2f28-109">To embed model and mapping files</span></span>  
  
1.  <span data-ttu-id="e2f28-110">**솔루션 탐색기**, 개념 (.csdl) 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2f28-110">In **Solution Explorer**, select the conceptual (.csdl) file.</span></span>  
  
2.  <span data-ttu-id="e2f28-111">에 **속성** 창에서 **빌드 작업** 에 **포함 된 리소스**합니다.</span><span class="sxs-lookup"><span data-stu-id="e2f28-111">In the **Properties** pane, set **Build Action** to **Embedded Resource**.</span></span>  
  
3.  <span data-ttu-id="e2f28-112">저장소 파일(.ssdl) 및 매핑 파일(.msl)에 대해 1단계와 2단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="e2f28-112">Repeat steps 1 and 2 for the storage (.ssdl) file and the mapping (.msl) file.</span></span>  
  
4.  <span data-ttu-id="e2f28-113">**솔루션 탐색기**, App.config 파일을 두 번 클릭 한 다음 수정 합니다 `Metadata` 의 매개 변수는 `connectionString` 다음 형식 중 하나에 따라 특성:</span><span class="sxs-lookup"><span data-stu-id="e2f28-113">In **Solution Explorer**, double-click the App.config file and then modify the `Metadata` parameter in the `connectionString` attribute based on one of the following formats:</span></span>  
  
    -   `Metadata=` `res://<assemblyFullName>/<resourceName>;`  
  
    -   `Metadata=` `res://*/<resourceName>;`  
  
    -   `Metadata=res://*;`  
  
     <span data-ttu-id="e2f28-114">자세한 내용은 [연결 문자열](../../../../../docs/framework/data/adonet/ef/connection-strings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2f28-114">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2f28-115">예제</span><span class="sxs-lookup"><span data-stu-id="e2f28-115">Example</span></span>  
 <span data-ttu-id="e2f28-116">다음 연결 문자열에 포함 된 모델 및 매핑 파일에 대 한 참조를 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)합니다.</span><span class="sxs-lookup"><span data-stu-id="e2f28-116">The following connection string references embedded model and mapping files for the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span> <span data-ttu-id="e2f28-117">이 연결 문자열은 프로젝트의 App.config 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2f28-117">This connection string is stored in the project's App.config file.</span></span>  

## <a name="see-also"></a><span data-ttu-id="e2f28-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="e2f28-118">See also</span></span>

- [<span data-ttu-id="e2f28-119">모델링 및 매핑</span><span class="sxs-lookup"><span data-stu-id="e2f28-119">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [<span data-ttu-id="e2f28-120">방법: 연결 문자열 정의</span><span class="sxs-lookup"><span data-stu-id="e2f28-120">How to: Define the Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)
- [<span data-ttu-id="e2f28-121">방법: EntityConnection 연결 문자열 빌드</span><span class="sxs-lookup"><span data-stu-id="e2f28-121">How to: Build an EntityConnection Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)
- [<span data-ttu-id="e2f28-122">ADO.NET 엔터티 데이터 모델 도구</span><span class="sxs-lookup"><span data-stu-id="e2f28-122">ADO.NET Entity Data Model Tools</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
