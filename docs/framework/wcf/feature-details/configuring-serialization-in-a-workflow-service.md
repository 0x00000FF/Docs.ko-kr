---
title: 워크플로 서비스에서 Serialization 구성
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: 63a5860bd428fd4ce7fe01d7901427c85b2d5609
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53154114"
---
# <a name="configuring-serialization-in-a-workflow-service"></a><span data-ttu-id="335c7-102">워크플로 서비스에서 Serialization 구성</span><span class="sxs-lookup"><span data-stu-id="335c7-102">Configuring Serialization in a Workflow Service</span></span>
<span data-ttu-id="335c7-103">워크플로 서비스는 Windows Communication Foundation (WCF) 서비스 및 중 하나를 사용 하 여는 옵션이 있으므로 합니다 <xref:System.Runtime.Serialization.DataContractSerializer> (기본값) 또는 <xref:System.Xml.Serialization.XmlSerializer>합니다.</span><span class="sxs-lookup"><span data-stu-id="335c7-103">Workflow services are Windows Communication Foundation (WCF) services and so have the option of using either the <xref:System.Runtime.Serialization.DataContractSerializer> (the default) or the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="335c7-104">워크플로가 아닌 서비스를 작성할 때 사용할 직렬화기 형식은 서비스 또는 작업 계약에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="335c7-104">When writing non-workflow services the type of serializer to use is specified on the service or operation contract.</span></span> <span data-ttu-id="335c7-105">WCF 워크플로 서비스를 만들 때 코드에서 이러한 계약을 지정 하지 않으면 하지만 계약 유추를 통해 런타임에 생성 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="335c7-105">When creating WCF workflow services you don’t specify these contracts in code, but rather they are generated at runtime by contract inference.</span></span> <span data-ttu-id="335c7-106">계약 유추에 대 한 자세한 내용은 참조 하세요. [워크플로에서 계약 사용 하 여](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="335c7-106">For more information about contract inference, see  [Using Contracts in Workflow](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span></span>  <span data-ttu-id="335c7-107">직렬화기는 <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> 속성을 사용하여 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="335c7-107">The serializer is specified using the <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> property.</span></span> <span data-ttu-id="335c7-108">다음 그림과 같이 디자이너에서 이 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="335c7-108">This can be set in the designer as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="335c7-109">![직렬 변환기 설정](../../../../docs/framework/wcf/feature-details/media/settingserialzier.png "SettingSerialzier")</span><span class="sxs-lookup"><span data-stu-id="335c7-109">![Setting the serializer](../../../../docs/framework/wcf/feature-details/media/settingserialzier.png "SettingSerialzier")</span></span>  
  
 <span data-ttu-id="335c7-110">다음 예제와 같이 코드에서 직렬화기를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="335c7-110">The serializer can also be set in code as shown in the following example,</span></span>  
  
```csharp  
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
```  
  
 <span data-ttu-id="335c7-111">워크플로 서비스에서 알려진 형식도 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="335c7-111">Known types can be specified on Workflow services as well.</span></span> <span data-ttu-id="335c7-112">알려진 형식에 대 한 자세한 내용은 참조 하세요 [데이터 계약 알려진 형식을](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="335c7-112">For more information about Known Types see [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span> <span data-ttu-id="335c7-113">디자이너나 코드에서 알려진 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="335c7-113">Known types can be specified in the designer or in code.</span></span> <span data-ttu-id="335c7-114">디자이너에서 알려진 형식을 지정하려면 다음 그림과 같이 <xref:System.ServiceModel.Activities.Receive> 작업에 대한 속성 창에서 KnownTypes 속성 옆에 있는 줄임표 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="335c7-114">To specify known types in the designer, click the ellipsis button next to the KnownTypes property in the properties window for a <xref:System.ServiceModel.Activities.Receive> activity as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="335c7-115">![KnownTypes 속성](../../../../docs/framework/wcf/feature-details/media/knowntypes.png "KnownTypes")</span><span class="sxs-lookup"><span data-stu-id="335c7-115">![KnownTypes property](../../../../docs/framework/wcf/feature-details/media/knowntypes.png "KnownTypes")</span></span>  
  
 <span data-ttu-id="335c7-116">알려진 형식을 검색하고 지정할 수 있는 형식 컬렉션 편집기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="335c7-116">This will display the Type Collections Editor that will allow you to search for and specify known types.</span></span>  
  
 <span data-ttu-id="335c7-117">![알려진된 형식을 추가](../../../../docs/framework/wcf/feature-details/media/typecollectionseditor.gif "TypeCollectionsEditor")</span><span class="sxs-lookup"><span data-stu-id="335c7-117">![Adding Known Types](../../../../docs/framework/wcf/feature-details/media/typecollectionseditor.gif "TypeCollectionsEditor")</span></span>  
  
 <span data-ttu-id="335c7-118">클릭 합니다 **새 유형을 추가** 에 연결 하 고 선택 하거나 검색 유형에 대 한 드롭다운을 사용 하 여 알려진된 형식 컬렉션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="335c7-118">Click the **Add new type** link and use the drop down to select or search for a type to add to the known types collection.</span></span> <span data-ttu-id="335c7-119">코드에서 알려진 형식을 지정하려면 다음 예제와 같이 <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="335c7-119">To specify known types in code use the <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> property as shown in the following example.</span></span>  
  
```csharp
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
            approveExpense.KnownTypes.Add(typeof(Travel));  
            approveExpense.KnownTypes.Add(typeof(Meal));  
```
