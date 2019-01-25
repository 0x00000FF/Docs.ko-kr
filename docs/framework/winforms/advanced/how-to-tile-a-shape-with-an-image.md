---
title: '방법: 타일 이미지를 사용 하 여 도형'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- texture brushes [Windows Forms], tiling images with
- images [Windows Forms], filling shapes with
- shapes [Windows Forms], tiling with images
- bitmaps [Windows Forms], filling shapes with
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
ms.openlocfilehash: f2edde7e78f996d4a7bfbc636210f315c0718f6d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693216"
---
# <a name="how-to-tile-a-shape-with-an-image"></a>방법: 타일 이미지를 사용 하 여 도형
층에 맞게 서로 옆에 있는 타일을 배치할 수 있습니다, 처럼 채우기 (타일) 셰이프를 서로 옆에 있는 사각형 이미지에 배치할 수 있습니다. 도형의 내부를 타일을 질감 브러시를 사용 합니다. 생성 하는 경우는 <xref:System.Drawing.TextureBrush> 개체 생성자에 전달 하는 인수 중 하나는 <xref:System.Drawing.Image> 개체입니다. 질감 브러시를 사용 하 여 도형의 내부를 그리는 경우 셰이프가이 이미지의 복사본을 반복적된으로 채워집니다.  
  
 랩 모드 속성을 <xref:System.Drawing.TextureBrush> 개체는 사각형 그리드 안의 반복적으로 이미지 방향는 방법을 결정 합니다. 그리드에서 타일에 있는 모든 같은 방향으로 만들거나 다음 그리드 위치에서 대칭 이동 이미지를 만들 수 있습니다. 대칭 이동의 가로, 수 세로 축 또는 둘 다. 다음 예에서는 대칭 이동 하는 다양 한 유형의 바둑판식 배열을 보여 줍니다.  
  
### <a name="to-tile-an-image"></a>이미지 타일  
  
-   이 예제에서는 200 × 200 사각형에 바둑판식으로 배열 하 다음 75 × 75 이미지를 사용 합니다.  
  
 ![1 타일](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")  
  
-   다음 그림에서는 이미지를 사용 하 여 사각형을 바둑판식으로 표시 하는 방법을 보여 줍니다. 모든 타일이 동일한 방향을;에 있는 참고 대칭 이동 안 있습니다.  
  
 ![Tile 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")  
  
 [!code-csharp[System.Drawing.UsingABrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a>가로 바둑판식 배열 하는 동안 이미지를 대칭 이동  
  
-   이 예제에서는 200 × 200 사각형에 맞게 동일한 75 × 75 이미지를 사용 합니다. 이미지를 가로로 대칭 이동 하려면 줄 바꿈 모드를 설정 됩니다. 다음 그림에서는 이미지를 사용 하 여 사각형을 바둑판식으로 표시 하는 방법을 보여 줍니다. 지정된 된 행의 다음 한 타일에서 이동 하면 이미지를 좌우 대칭는 참고 합니다.  
  
 ![3 타일](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")  
  
 [!code-csharp[System.Drawing.UsingABrush#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a>세로 바둑판식 배열 하는 동안 이미지를 대칭 이동  
  
-   이 예제에서는 200 × 200 사각형에 맞게 동일한 75 × 75 이미지를 사용 합니다. 이미지를 세로로 대칭 이동 하려면 줄 바꿈 모드를 설정 됩니다.  
  
     [!code-csharp[System.Drawing.UsingABrush#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a>바둑판식으로 배열 하는 동안 가로 및 세로로 이미지를 대칭 이동  
  
-   이 예제에서는 200 × 200 사각형에 바둑판식으로 배열 하 동일한 75 × 75 이미지를 사용 합니다. 줄 바꿈 모드는 이미지를 대칭으로 가로 세로 방향으로 설정 됩니다. 다음 그림에서는 이미지에서 사각형은 바둑판식으로 배열 하는 방법을 보여 줍니다. 타일이 하나만 지정된 된 행의 다음 단계로 이동 하면 이미지를 가로로 대칭는 및 이미지를 상하 대칭은 지정된 된 열 다음 한 타일에서 이동할 때.  
  
 ![Tile 5](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")  
  
 [!code-csharp[System.Drawing.UsingABrush#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>참고자료
- [브러시를 사용하여 도형 채우기](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
