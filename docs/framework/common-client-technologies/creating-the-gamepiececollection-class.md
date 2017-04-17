---
title: "Creating the GamePieceCollection Class | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e4b037ee-1201-4a55-b198-0d6532ed6f35
caps.latest.revision: 8
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 8
---
# Creating the GamePieceCollection Class
**GamePieceCollection** 클래스는 제네릭 목록 클래스에서 파생되고 여러 **GamePiece** 개체를 더 쉽게 관리하도록 메서드를 도입합니다.  
  
## 코드 만들기  
 **GamePieceCollection** 클래스의 생성자는 개인 멤버 *capturedIndex*를 초기화합니다.  이 필드는 현재 마우스 캡처가 있는 게임 부분을 추적하는 데 사용됩니다.  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_PrivateMembersAndConstructor](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_privatemembersandconstructor)]  
  
 **ProcessInertia** 및 **Draw** 메서드는 컬렉션에서 모든 게임 부분을 열거하고 각 **GamePiece** 개체에서 각 메서드를 호출하여 게임 [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) 및 [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) 메서드에 필요한 코드를 간소화합니다.  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_ProcessInertiaAndDraw](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_processinertiaanddraw)]  
  
 게임 업데이트 중에 **UpdateFromMouse** 메서드도 호출됩니다.  먼저 현재 캡처\(있는 경우\)가 계속 적용되는지 확인하여 마우스 캡처가 한 게임 부분에만 포함되도록 할 수 있습니다.  그렇다면 다른 부분에 캡처가 있는지 확인할 수 없습니다.  
  
 현재 캡처가 포함된 부분이 없으면 **UpdateFromMouse** 메서드가 마지막부터 처음까지 각 게임 부분을 열거하고 해당 부분에서 마우스 캡처를 보고하는지를 확인합니다.  그렇다면 해당 부분은 현재 캡처된 부분이 되고 추가적인 처리가 수행되지 않습니다.  **UpdateFromMouse** 메서드는 컬렉션의 마지막 항목을 먼저 확인하므로 두 부분이 겹치면 더 높은 Z 순서를 가진 한 부분이 캡처를 획득합니다.  Z 순서는 명시적이지 않고 변경할 수 없습니다. 단순히 게임 부분이 컬렉션에 추가된 순서대로 제어됩니다.  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_UpdateFromMouse](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_updatefrommouse)]  
  
## 참고 항목  
 [Manipulations and Inertia](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)   
 [Using Manipulations and Inertia in an XNA Application](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)   
 [Creating the GamePiece Class](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)   
 [Creating the Game1 Class](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)   
 [Full Code Listings](../../../docs/framework/common-client-technologies/full-code-listings.md)