---
title: '방법: DBML 및 외부 매핑 파일 유효성 검사'
ms.date: 03/30/2017
ms.assetid: d9ea37f5-0a9e-4401-8fc3-1e6fd44c49f9
ms.openlocfilehash: 42cba5b9b686f5f94d4ebf8f889461e1bab009b5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54692732"
---
# <a name="how-to-validate-dbml-and-external-mapping-files"></a><span data-ttu-id="a1a14-102">방법: DBML 및 외부 매핑 파일 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="a1a14-102">How to: Validate DBML and External Mapping Files</span></span>
<span data-ttu-id="a1a14-103">수정한 외부 매핑 파일 및 .dbml 파일은 해당 스키마 정의에 대해 유효성이 검사되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-103">External mapping files and .dbml files that you modify must be validated against their respective schema definitions.</span></span> <span data-ttu-id="a1a14-104">이 항목에서는 유효성 검사 프로세스를 구현 하는 단계를 사용 하 여 Visual Studio 사용자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-104">This topic provides Visual Studio users with the steps to implement the validation process.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
### <a name="to-validate-a-dbml-or-xml-file"></a><span data-ttu-id="a1a14-105">.dbml 또는 XML 파일의 유효성을 검사하려면</span><span class="sxs-lookup"><span data-stu-id="a1a14-105">To validate a .dbml or XML file</span></span>  
  
1.  <span data-ttu-id="a1a14-106">Visual studio **파일** 메뉴에서 **열려**를 클릭 하 고 **파일**합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-106">On the Visual Studio **File** menu, point to **Open**, and then click **File**.</span></span>  
  
2.  <span data-ttu-id="a1a14-107">에 **열려 있는 파일** 대화 상자.dbml 또는 XML 매핑 파일 유효성을 검사 하려는 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-107">In the **Open File** dialog box, click the .dbml or XML mapping file that you want to validate.</span></span>  
  
     <span data-ttu-id="a1a14-108">파일이 열립니다는 **XML 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-108">The file opens in the **XML Editor**.</span></span>  
  
3.  <span data-ttu-id="a1a14-109">창을 마우스 오른쪽 단추로 누른 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-109">Right-click the window, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="a1a14-110">에 **속성** 창에 대 한 줄임표를 클릭 합니다 **스키마** 속성.</span><span class="sxs-lookup"><span data-stu-id="a1a14-110">In the **Properties** window, click the ellipsis for the **Schemas** property.</span></span>  
  
     <span data-ttu-id="a1a14-111">합니다 **XML 스키마** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-111">The **XML Schemas** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="a1a14-112">원하는 목적에 맞는 적절한 스키마 정의를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-112">Note the appropriate schema definition for your purpose.</span></span>  
  
    -   <span data-ttu-id="a1a14-113">DbmlSchema.xsd는 .dbml 파일의 유효성 검사를 위한 스키마 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-113">DbmlSchema.xsd is the schema definition for validating a .dbml file.</span></span> <span data-ttu-id="a1a14-114">자세한 내용은 [LINQ to SQL에서에서 코드 생성](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-114">For more information, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
    -   <span data-ttu-id="a1a14-115">LinqToSqlMapping.xsd는 외부 XML 매핑 파일의 유효성 검사를 위한 스키마 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-115">LinqToSqlMapping.xsd is the schema definition for validating an external XML mapping file.</span></span> <span data-ttu-id="a1a14-116">자세한 내용은 [외부 매핑](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-116">For more information, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
6.  <span data-ttu-id="a1a14-117">에 **사용 하 여** 클릭 드롭다운 상자를 연 다음을 클릭 하 여 원하는 스키마 정의 행의 열 **이 스키마를 사용 하 여**입니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-117">In the **Use** column of the desired schema definition row, click to open the drop-down box, and then click **Use this schema**.</span></span>  
  
     <span data-ttu-id="a1a14-118">이제 스키마 정의 파일이 DBML 또는 XML 매핑 파일과 연관됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-118">The schema definition file is now associated with your DBML or XML mapping file.</span></span>  
  
     <span data-ttu-id="a1a14-119">다른 스키마 정의가 선택되지 않았는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-119">Make sure no other schema definitions are selected.</span></span>  
  
7.  <span data-ttu-id="a1a14-120">에 **뷰** 메뉴에서 클릭 **오류 목록**합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-120">On the **View** menu, click **Error List**.</span></span>  
  
     <span data-ttu-id="a1a14-121">오류, 경고 또는 메시지가 생성되었는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-121">Determine whether errors, warnings, or messages have been generated.</span></span> <span data-ttu-id="a1a14-122">생성된 것이 없는 경우 스키마 정의에 대해 XML 파일이 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-122">If not, the XML file is valid against the schema definition.</span></span>  
  
## <a name="alternate-method-for-supplying-schema-definition"></a><span data-ttu-id="a1a14-123">스키마 정의 제공을 위한 대체 방법</span><span class="sxs-lookup"><span data-stu-id="a1a14-123">Alternate Method for Supplying Schema Definition</span></span>  
 <span data-ttu-id="a1a14-124">어떤 이유로 적절 한.xsd 파일에 나타나지 않으면 경우는 **XML 스키마** 대화 상자에서 도움말 항목에서.xsd 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-124">If for some reason the appropriate .xsd file does not appear in the **XML Schemas** dialog box, you can download the .xsd file from a Help topic.</span></span> <span data-ttu-id="a1a14-125">다음 단계를 Visual Studio XML 편집기를 통해 필요한 유니코드 형식으로 다운로드 한 파일을 저장 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-125">The following steps help you save the downloaded file in the Unicode format required by the Visual Studio XML Editor.</span></span>  
  
#### <a name="to-copy-a-schema-definition-file-from-a-help-topic"></a><span data-ttu-id="a1a14-126">도움말 항목에서 스키마 정의 파일을 복사하려면</span><span class="sxs-lookup"><span data-stu-id="a1a14-126">To copy a schema definition file from a Help topic</span></span>  
  
1.  <span data-ttu-id="a1a14-127">이 항목의 앞부분에서 설명한 대로 스키마 정의가 포함된 도움말 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-127">Locate the Help topic that contains the schema definition as described earlier in this topic.</span></span>  
  
    -   <span data-ttu-id="a1a14-128">.Dbml 파일을 참조 하세요 [LINQ to SQL에서에서 코드 생성](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-128">For .dbml files, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
    -   <span data-ttu-id="a1a14-129">외부 매핑 파일을 참조 하세요 [외부 매핑](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-129">For external mapping files, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
2.  <span data-ttu-id="a1a14-130">클릭 **코드 복사** 코드 파일을 클립보드에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-130">Click **Copy Code** to copy the code file to the Clipboard.</span></span>  
  
3.  <span data-ttu-id="a1a14-131">메모장을 시작하여 새 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-131">Start Notepad to create a new file.</span></span>  
  
4.  <span data-ttu-id="a1a14-132">클립보드에서 메모장 파일로 코드를 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-132">Paste the code from the clipboard into Notepad file.</span></span>  
  
5.  <span data-ttu-id="a1a14-133">메모장에서 **파일** 메뉴에서 클릭 **다른 이름으로 저장**합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-133">On the Notepad **File** menu, click **Save As**.</span></span>  
  
6.  <span data-ttu-id="a1a14-134">에 **Encoding** 상자에서 **유니코드**합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-134">In the **Encoding** box, select **Unicode**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a1a14-135">이렇게 하면 유니코드 16바이트 순서 마커(`FFFE`)가 텍스트 파일 앞에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-135">This selection guarantees that the Unicode-16 byte-order marker (`FFFE`) is prepended to the text file.</span></span>  
  
7.  <span data-ttu-id="a1a14-136">에 **파일 이름** 상자에서 확장명이.xsd 인 파일 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a1a14-136">In the **File name** box, create a file name with an .xsd extension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1a14-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="a1a14-137">See also</span></span>
- [<span data-ttu-id="a1a14-138">참조</span><span class="sxs-lookup"><span data-stu-id="a1a14-138">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
