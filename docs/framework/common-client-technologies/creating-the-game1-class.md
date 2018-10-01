---
title: Game1 클래스 만들기
ms.date: 03/30/2017
ms.assetid: 47932ce3-2ba5-476f-a26b-3ddfd5226f27
ms.openlocfilehash: 368da9df4dffc7017abb02888bc2eb2641f04b8b
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2018
ms.locfileid: "47201025"
---
# <a name="creating-the-game1-class"></a><span data-ttu-id="68988-102">Game1 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="68988-102">Creating the Game1 Class</span></span>
<span data-ttu-id="68988-103">모든 Microsoft XNA 프로젝트와 마찬가지로 Game1 클래스는 XNA 게임에 대한 기본 그래픽 장치 초기화, 게임 논리 및 렌더링 코드를 제공하는 [Microsoft.Xna.Framework.Game](https://msdn.microsoft.com/library/microsoft.xna.framework.game.aspx) 클래스에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="68988-103">As with all Microsoft XNA projects, the Game1 class derives from the [Microsoft.Xna.Framework.Game](https://msdn.microsoft.com/library/microsoft.xna.framework.game.aspx) class, which provides basic graphics device initialization, game logic, and rendering code for XNA games.</span></span> <span data-ttu-id="68988-104">대부분의 작업이 GamePiece 및 GamePieceCollection 클래스에서 수행되기 때문에 Game1 클래스는 비교적 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="68988-104">The Game1 class is fairly simple because most of the work in done in the GamePiece and GamePieceCollection classes.</span></span>  
  
## <a name="creating-the-code"></a><span data-ttu-id="68988-105">코드 만들기</span><span class="sxs-lookup"><span data-stu-id="68988-105">Creating the Code</span></span>  
 <span data-ttu-id="68988-106">클래스의 private 멤버는 게임 피스를 저장할 **GamePieceCollection** 개체, [GraphicsDeviceManager](https://msdn.microsoft.com/library/microsoft.xna.framework.graphicsdevicemanager.aspx) 개체 및 게임 피스 렌더링에 사용되는 [SpriteBatch](https://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.aspx) 개체로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="68988-106">The private members for the class consist of a **GamePieceCollection** object to hold the game pieces, a [GraphicsDeviceManager](https://msdn.microsoft.com/library/microsoft.xna.framework.graphicsdevicemanager.aspx) object, and a [SpriteBatch](https://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.aspx) object used to render game pieces.</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_PrivateMembers](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_privatemembers)]  
  
 <span data-ttu-id="68988-107">게임 초기화 중에 이러한 개체가 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="68988-107">During game initialization, these objects are instantiated.</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_ConstructorInitialize](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_constructorinitialize)]  
  
 <span data-ttu-id="68988-108">[LoadContent](https://msdn.microsoft.com/library/microsoft.xna.framework.game.loadcontent.aspx) 메서드를 호출하면 게임 피스가 생성되고 **GamePieceCollection** 개체에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="68988-108">When the [LoadContent](https://msdn.microsoft.com/library/microsoft.xna.framework.game.loadcontent.aspx) method is called, the game pieces are created and assigned to the **GamePieceCollection** object.</span></span> <span data-ttu-id="68988-109">두 가지 유형의 게임 피스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68988-109">There are two types of game pieces.</span></span> <span data-ttu-id="68988-110">좀더 작은 피스와 좀더 큰 피스가 있으므로 피스에 대한 배율은 약간 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="68988-110">The scale factor for the pieces is changed slightly so that there are some smaller and some larger pieces.</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_LoadContent](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_loadcontent)]  
  
 <span data-ttu-id="68988-111">게임을 실행하는 동안 [Update](https://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) 메서드가 XNA Framework에서 반복적으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="68988-111">The [Update](https://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) method is called repeatedly by the XNA Framework while the game is running.</span></span> <span data-ttu-id="68988-112">[Update](https://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) 메서드는 게임 피스 컬렉션에 대해 **ProcessInertia** 및 **UpdateFromMouse** 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="68988-112">The [Update](https://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) method calls the **ProcessInertia** and the **UpdateFromMouse** methods on the game piece collection.</span></span> <span data-ttu-id="68988-113">이러한 메서드는 [GamePieceCollection 클래스 만들기](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68988-113">These methods are described in [Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_UpdateGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_updategame)]  
  
 <span data-ttu-id="68988-114">게임을 실행하는 동안 [Draw](https://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) 메서드도 XNA Framework에서 반복적으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="68988-114">The [Draw](https://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) method is also called repeatedly by the XNA Framework while the game is running.</span></span> <span data-ttu-id="68988-115">[Draw](https://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) 메서드는 **GamePieceCollection** 개체의 **Draw** 메서드를 호출하여 게임 피스 렌더링을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="68988-115">The [Draw](https://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) method performs the rendering of game pieces by calling the **Draw** method of the **GamePieceCollection** object.</span></span> <span data-ttu-id="68988-116">이 메서드는 [GamePieceCollection 클래스 만들기](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68988-116">This method is described in[Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_DrawGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_drawgame)]  
  
## <a name="see-also"></a><span data-ttu-id="68988-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68988-117">See Also</span></span>  
 [<span data-ttu-id="68988-118">조작 및 관성</span><span class="sxs-lookup"><span data-stu-id="68988-118">Manipulations and Inertia</span></span>](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)  
 [<span data-ttu-id="68988-119">XNA 응용 프로그램에서 조작 및 관성 사용</span><span class="sxs-lookup"><span data-stu-id="68988-119">Using Manipulations and Inertia in an XNA Application</span></span>](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)  
 [<span data-ttu-id="68988-120">GamePiece 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="68988-120">Creating the GamePiece Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
 [<span data-ttu-id="68988-121">GamePieceCollection 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="68988-121">Creating the GamePieceCollection Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
 [<span data-ttu-id="68988-122">전체 코드 목록</span><span class="sxs-lookup"><span data-stu-id="68988-122">Full Code Listings</span></span>](../../../docs/framework/common-client-technologies/full-code-listings.md)
