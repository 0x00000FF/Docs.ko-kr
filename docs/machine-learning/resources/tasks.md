---
title: 기계 학습 작업
description: ML.NET에서 지원되는 다양한 기계 학습 작업을 살펴봅니다.
ms.date: 06/04/2018
author: aditidugar
ms.author: johalex
ms.openlocfilehash: 875006a9cddb87b5f9436b78773420858fd842dd
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207728"
---
# <a name="machine-learning-tasks"></a>기계 학습 작업

기계 학습 모델을 빌드할 때 먼저 데이터로 무엇을 달성하려고 하는지 정의해야 합니다. 그런 다음, 상황에 맞는 올바른 기계 학습 작업을 선택할 수 있습니다. 다음 목록은 사용자가 선택할 수 있는 다양한 기계 학습 작업과 몇 가지 일반적인 사용 사례에 대해 설명합니다. 

> [!NOTE]
> ML.NET은 현재 미리 보기로 제공됩니다. 일부 기계 학습 작업은 현재 지원되지 않습니다. 특정 작업에 대한 요청을 제출하려면 [dotnet/machinelearning 리포지토리](https://github.com/dotnet/machinelearning/issues)에서 문제를 엽니다.

> [!NOTE]
> 현재 ML.NET은 이미지가 포함된 기계 학습 작업을 지원하지 않습니다. 향후 릴리스에 지원이 추가될 예정입니다. 

## <a name="binary-classification"></a>이진 분류

두 클래스(범주) 중에 데이터의 인스턴스가 속한 클래스를 예측하는 데 사용되는 [감독된 기계 학습](glossary.md#supervised-machine-learning) 작업입니다. 분류 알고리즘의 입력은 레이블이 지정된 예제 집합입니다. 여기서 각 레이블은 0 또는 1의 정수입니다. 이진 분류 알고리즘의 출력은 분류자로, 레이블이 없는 새 인스턴스의 클래스를 예측하는 데 사용할 수 있습니다. 이진 분류 시나리오의 예는 다음과 같습니다.

* “긍정적” 또는 “부정적”으로 [Twitter 댓글의 감정 이해](../tutorials/sentiment-analysis.md).
* 환자에게 특정 질병이 있는지 여부 진단.
* 전자 메일을 “스팸”으로 표시할지 여부 결정.

자세한 내용은 Wikipedia에서 [Binary classification](https://en.wikipedia.org/wiki/Binary_classification)(이진 분류) 문서를 참조하세요.

## <a name="multiclass-classification"></a>다중 클래스 분류

데이터 인스턴스의 클래스(범주)를 예측하는 데 사용되는 [감독된 기계 학습](glossary.md#supervised-machine-learning) 작업입니다. 분류 알고리즘의 입력은 레이블이 지정된 예제 집합입니다. 각 레이블은 0~k-1 사이의 정수입니다. 여기서 k는 클래스 수입니다. 분류 알고리즘의 출력은 분류자로, 레이블이 없는 새 인스턴스의 클래스를 예측하는 데 사용할 수 있습니다. 다중 클래스 분류 시나리오의 예는 다음과 같습니다.

* 개의 품종을 “시베리안 허스키”, “골든 리트리버”, “푸들” 등으로 결정.
* 동영상 리뷰를 “긍정적”, “중립” 또는 “부정적”으로 이해.
* 호텔 리뷰를 “위치”, “가격”, “청결도” 등으로 범주화.

자세한 내용은 Wikipedia에서 [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification)(다중 클래스 분류) 문서를 참조하세요.

## <a name="regression"></a>재발

관련 기능 집합에서 레이블 값을 예측하는 데 사용되는 [감독된 기계 학습](glossary.md#supervised-machine-learning) 작업입니다. 레이블은 실제 값일 수 있고, 분류 작업과 같이 한정된 값 집합에 속하지 않습니다. 회귀 알고리즘 모델은 기능 값이 달라질 때 레이블이 변경되는 방식을 결정하기 위한 관련 기능에 대한 레이블의 종속성입니다. 회귀 알고리즘의 입력은 알려진 값의 레이블이 포함된 예제 집합입니다. 회귀 알고리즘의 출력은 새 입력 기능 집합의 레이블 값을 예측하는 데 사용할 수 있는 함수입니다. 회귀 시나리오의 예는 다음과 같습니다.

* 침실 수, 위치 또는 규모와 같은 주택 특성을 기반으로 주택 가격 예측.
* 과거 데이터 및 현재 시장 추세를 기반으로 미래 재고 가격 예측.
* 광고 예산을 기반으로 제품 판매 예측.

> [!NOTE]
> 현재 ML.NET은 시계열이 포함된 회귀 작업에 대한 지원을 빌드하고 있습니다.

## <a name="clustering"></a>클러스터링

데이터 인스턴스를 비슷한 특성을 포함하는 클러스터로 그룹화하는 데 사용되는 [감독되지 않는 기계 학습](glossary.md#unsupervised-machine-learning) 작업입니다. 클러스터링을 사용하여 검색 또는 단순 관찰을 통해 논리적으로 파생될 수 없는 데이터 집합의 관계를 식별할 수도 있습니다. 클러스터링 알고리즘의 입력 및 출력은 선택한 방법에 따라 다릅니다. 분산, 중심, 연결 또는 밀도 기반 방법을 사용할 수 있습니다. 현재 ML.NET은 K-평균 클러스터링을 사용하는 중심 기반 방법을 지원합니다. 클러스터링 시나리오의 예는 다음과 같습니다.

* 호텔 선택의 습관과 특성을 기반으로 호텔 투숙객 세그먼트 이해.
* 대상 광고 캠페인을 구축하는 데 도움이 되는 고객 세그먼트 및 인구 통계 식별.
* 제조 메트릭을 기반으로 인벤토리 범주화.

## <a name="anomaly-detection-coming-soon"></a>변칙 검색(‘출시 예정’)

## <a name="ranking-coming-soon"></a>순위 지정(‘출시 예정’)

## <a name="recommendation-coming-soon"></a>권장 사항(‘출시 예정’)

