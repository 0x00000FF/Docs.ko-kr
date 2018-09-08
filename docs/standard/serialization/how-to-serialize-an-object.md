---
title: '방법: 개체 Serialize'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.assetid: a1207d05-32b2-4953-8582-959607991227
ms.openlocfilehash: e4d6e3edb15dbf5ba4b7ec7f8658fec1a618d315
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44194905"
---
# <a name="how-to-serialize-an-object"></a><span data-ttu-id="56c29-102">방법: 개체 Serialize</span><span class="sxs-lookup"><span data-stu-id="56c29-102">How to: Serialize an Object</span></span>
<span data-ttu-id="56c29-103">개체를 serialize하려면 먼저 serialize될 개체를 만들고 해당 public 속성과 필드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="56c29-103">To serialize an object, first create the object that is to be serialized and set its public properties and fields.</span></span> <span data-ttu-id="56c29-104">이렇게 하려면 XML 스트림이 저장될 전송 형식을 스트림 또는 파일 중에서 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="56c29-104">To do this, you must determine the transport format in which the XML stream is to be stored, either as a stream or as a file.</span></span> <span data-ttu-id="56c29-105">예를 들어 XML 스트림을 영구적 형태로 저장해야 하는 경우에는 <xref:System.IO.FileStream> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="56c29-105">For example, if the XML stream must be saved in a permanent form, create a <xref:System.IO.FileStream> object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56c29-106">XML serialization에 대한 다른 예제를 보려면 [XML Serialization 예제](../../../docs/standard/serialization/examples-of-xml-serialization.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56c29-106">For more examples of XML serialization, see [Examples of XML Serialization](../../../docs/standard/serialization/examples-of-xml-serialization.md).</span></span>  
  
### <a name="to-serialize-an-object"></a><span data-ttu-id="56c29-107">개체를 serialize하려면</span><span class="sxs-lookup"><span data-stu-id="56c29-107">To serialize an object</span></span>  
  
1.  <span data-ttu-id="56c29-108">개체를 만들고 해당 public 필드 및 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="56c29-108">Create the object and set its public fields and properties.</span></span>  
  
2.  <span data-ttu-id="56c29-109">개체의 형식을 사용하여 <xref:System.Xml.Serialization.XmlSerializer>를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="56c29-109">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object.</span></span> <span data-ttu-id="56c29-110">자세한 내용은 <xref:System.Xml.Serialization.XmlSerializer> 클래스 생성자를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="56c29-110">For more information, see the <xref:System.Xml.Serialization.XmlSerializer> class constructors.</span></span>  
  
3.  <span data-ttu-id="56c29-111"><xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> 메서드를 호출하여 개체의 public 속성 및 필드의 파일 표현 또는 XML 스트림을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="56c29-111">Call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> method to generate either an XML stream or a file representation of the object's public properties and fields.</span></span> <span data-ttu-id="56c29-112">다음 예제에서는 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="56c29-112">The following example creates a file.</span></span>  
  
    ```vb  
    Dim myObject As MySerializableClass = New MySerializableClass()  
    ' Insert code to set properties and fields of the object.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To write to a file, create a StreamWriter object.  
    Dim myWriter As StreamWriter = New StreamWriter("myFileName.xml")  
    mySerializer.Serialize(myWriter, myObject)  
    myWriter.Close()  
    ```  
  
    ```csharp  
    MySerializableClass myObject = new MySerializableClass();  
    // Insert code to set properties and fields of the object.  
    XmlSerializer mySerializer = new   
    XmlSerializer(typeof(MySerializableClass));  
    // To write to a file, create a StreamWriter object.  
    StreamWriter myWriter = new StreamWriter("myFileName.xml");  
    mySerializer.Serialize(myWriter, myObject);  
    myWriter.Close();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="56c29-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="56c29-113">See also</span></span>

- [<span data-ttu-id="56c29-114">XML serialization 소개</span><span class="sxs-lookup"><span data-stu-id="56c29-114">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
- [<span data-ttu-id="56c29-115">방법: 개체 deserialize</span><span class="sxs-lookup"><span data-stu-id="56c29-115">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
