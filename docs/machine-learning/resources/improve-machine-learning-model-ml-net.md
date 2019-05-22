---
title: '방법: 모델 정확도 향상'
description: 모델 정확도 향상 방법 알아보기
ms.date: 04/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc
ms.openlocfilehash: 6a2899b81fa165dc1bed759079c1ae8506b983e8
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65065556"
---
# <a name="improve-mlnet-model-accuracy"></a><span data-ttu-id="0c61a-103">ML.NET 모델 정확도 향상</span><span class="sxs-lookup"><span data-stu-id="0c61a-103">Improve ML.NET Model Accuracy</span></span>

<span data-ttu-id="0c61a-104">모델의 정확도를 높이는 방법에 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-104">Learn how to improve the accuracy of your model.</span></span>

## <a name="reframe-the-problem"></a><span data-ttu-id="0c61a-105">문제 재구성</span><span class="sxs-lookup"><span data-stu-id="0c61a-105">Reframe the problem</span></span>

<span data-ttu-id="0c61a-106">경우에 따라 모델 향상이 모델 학습에 사용된 데이터나 기법과는 아무런 관련이 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-106">Sometimes, improving a model may have nothing to do with the data or techniques used to train the model.</span></span> <span data-ttu-id="0c61a-107">그보다는 단순히 잘못된 질문 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-107">Instead, it may just be that the wrong question is being asked.</span></span> <span data-ttu-id="0c61a-108">문제를 다른 관점에서 보고 데이터를 활용하여 보이지 않는 지표와 숨겨진 관계를 추출해 질문을 구체화합니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-108">Consider looking at the problem from different angles and leverage the data to extract latent indicators and hidden relationships in order to refine the question.</span></span>

## <a name="provide-more-data-samples"></a><span data-ttu-id="0c61a-109">더 많은 데이터 샘플 제공</span><span class="sxs-lookup"><span data-stu-id="0c61a-109">Provide more data samples</span></span>

<span data-ttu-id="0c61a-110">사람과 마찬가지로 학습 알고리즘도 더 많이 알수록 성능이 높아질 가능성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-110">Like humans, the more training algorithms get, the likelihood of better performance increases.</span></span> <span data-ttu-id="0c61a-111">모델 성능을 높이는 한 가지 방법은 알고리즘에 더 많은 학습 데이터 샘플을 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-111">One way to improve model performance is to provide more training data samples to the algorithms.</span></span> <span data-ttu-id="0c61a-112">더 많은 데이터에서 학습할수록 정확히 식별하는 경우가 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-112">The more data it learns from, the more cases it is able to correctly identify.</span></span>

## <a name="add-context-to-the-data"></a><span data-ttu-id="0c61a-113">데이터에 컨텍스트 추가</span><span class="sxs-lookup"><span data-stu-id="0c61a-113">Add context to the data</span></span>

<span data-ttu-id="0c61a-114">단일 데이터 포인트의 의미는 다르게 해석될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-114">The meaning of a single data point can be difficult to interpret.</span></span> <span data-ttu-id="0c61a-115">데이터 포인트에 대한 컨텍스트를 구축하면 알고리즘과 사안 전문가들이 더 나은 의사 결정을 내리는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-115">Building context around the data points helps algorithms as well as subject matter experts better make decisions.</span></span> <span data-ttu-id="0c61a-116">유효한 자체 가격 지표가 없는 침실 세 개가 있는 집을 예로 들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-116">For example, the fact that a house has three bedrooms does not on its own give a good indication of its price.</span></span> <span data-ttu-id="0c61a-117">컨텍스트를 추가하고 평균 연령 38세, 평균 가계 소득은 $80,000이며 학군이 상위 20번째 백분위수인 대도시 근교에 위치한다는 점을 알고 있으면 알고리즘이 더 많은 정보를 바탕으로 의사 결정을 내릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-117">However, if you add context and now know that it is in a suburban neighborhood outside of a major metropolitan area where average age is 38, average household income is $80,000 and schools are in the top 20th percentile then the algorithm has more information to base its decisions on.</span></span> <span data-ttu-id="0c61a-118">이 모든 컨텍스트는 기계 학습 모델에 대한 입력에서 기능으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-118">All of this context can be added as input to the machine learning model as features.</span></span>

## <a name="use-meaningful-data-and-features"></a><span data-ttu-id="0c61a-119">의미 있는 데이터 및 기능 사용</span><span class="sxs-lookup"><span data-stu-id="0c61a-119">Use meaningful data and features</span></span>

<span data-ttu-id="0c61a-120">더 많은 데이터 샘플 및 기능은 모델 정확도를 높일 수 있지만 모든 데이터와 기능이 의미 있는 것은 아니므로 잡음도 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-120">Although more data samples and features can help improve the accuracy of the model, they may also introduce noise since not all data and features are meaningful.</span></span> <span data-ttu-id="0c61a-121">따라서 알고리즘에 의한 의사 결정에 가장 중대한 영향을 미치는 기능이 무엇인지 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-121">Therefore, it is important to understand which features are the ones that most heavily impact decisions made by the algorithm.</span></span> <span data-ttu-id="0c61a-122">PFI(순열 기능 중요도) 같은 기법을 사용하면 이런 중요한 기능을 파악할 수 있습니다. 또한 모델을 설명할 뿐 아니라 출력을 기능 선택 메서드로 사용하여 학습 프로세스에 발생하는 불필요한 기능의 규모를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-122">Using techniques like Permutation Feature Importance (PFI) can help identify those salient features and not only help explain the model but also use the output as a feature selection method to reduce the amount of noisy features going into the training process.</span></span>

<span data-ttu-id="0c61a-123">다음 [링크](../how-to-guides/explain-machine-learning-model-permutation-feature-importance-ml-net.md)에서 PFI 사용 알아보기</span><span class="sxs-lookup"><span data-stu-id="0c61a-123">Learn to use PFI by visiting the following [link](../how-to-guides/explain-machine-learning-model-permutation-feature-importance-ml-net.md)</span></span>

## <a name="cross-validation"></a><span data-ttu-id="0c61a-124">교차 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="0c61a-124">Cross-validation</span></span>

<span data-ttu-id="0c61a-125">교차 유효성 검사는 학습 데이터를 여러 파티션으로 분할하고 이 파티션에서 여러 알고리즘을 학습하는 학습 및 모델 평가 기법입니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-125">Cross-validation is a training and model evaluation technique that splits the data into several partitions and trains multiple algorithms on these partitions.</span></span> <span data-ttu-id="0c61a-126">이 기법은 학습 프로세스 밖에서 데이터를 유지하여 모델의 견고성을 높입니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-126">This technique improves the robustness of the model by holding out data from the training process.</span></span> <span data-ttu-id="0c61a-127">보이지 않는 관찰에 대한 성능 향상 외에도, 데이터 제약 환경에서 데이터 세트가 더 적은 학습 모델에 효과적인 도구가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-127">In addition to improving performance on unseen observations, in data-constrained environments it can be an effective tool for training models with a smaller dataset.</span></span>

<span data-ttu-id="0c61a-128">다음 링크에서 [ML.NET에서 교차 유효성 검사를 사용하는 방법](../how-to-guides/train-machine-learning-model-cross-validation-ml-net.md)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0c61a-128">Visit the following link to learn [how to use cross validation in ML.NET](../how-to-guides/train-machine-learning-model-cross-validation-ml-net.md)</span></span>

## <a name="hyperparameter-tuning"></a><span data-ttu-id="0c61a-129">하이퍼 매개 변수 조정</span><span class="sxs-lookup"><span data-stu-id="0c61a-129">Hyperparameter tuning</span></span>

<span data-ttu-id="0c61a-130">기계 학습 모델 교육은 반복적인 예비 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-130">Training machine learning models is an iterative and exploratory process.</span></span> <span data-ttu-id="0c61a-131">예를 들어, K-Means 알고리즘을 사용하여 모델을 학습할 때 최적 클러스터 수는 얼마일까요?</span><span class="sxs-lookup"><span data-stu-id="0c61a-131">For example, what is the optimal number of clusters when training a model using the K-Means algorithm?</span></span> <span data-ttu-id="0c61a-132">이 답은 데이터 구조 등, 여러 요인에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-132">The answer depends on many factors such as the structure of the data.</span></span> <span data-ttu-id="0c61a-133">이 값을 찾을 때는 여러 k 값을 통한 실험과 성능 평가를 통해 최적 값을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-133">Finding that number would require experimenting with different values for k and then evaluating performance to determine which value is best.</span></span> <span data-ttu-id="0c61a-134">이렇게 최적 모델을 찾기 위한 매개 변수 조정 작업을 하이퍼 매개 변수 조정이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-134">The practice of tuning these parameters to find an optimal model is known as hyper-parameter tuning.</span></span>

## <a name="choose-a-different-algorithm"></a><span data-ttu-id="0c61a-135">다른 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="0c61a-135">Choose a different algorithm</span></span>

<span data-ttu-id="0c61a-136">회귀 및 분류와 같은 기계 학습 작업에는 다양한 알고리즘 구현이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-136">Machine learning tasks like regression and classification contain various algorithm implementations.</span></span> <span data-ttu-id="0c61a-137">해결하려는 문제와 데이터가 구조화된 방식이 현재 알고리즘에 잘 맞지 않는 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-137">It may be the case that the problem you are trying to solve and the way your data is structured does not fit well into the current algorithm.</span></span> <span data-ttu-id="0c61a-138">이런 경우 작업에 다른 알고리즘을 사용하여 데이터에서 학습 성과가 더 좋은지 확인해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-138">In such case, consider using a different algorithm for your task to see if it learns better from your data.</span></span>

<span data-ttu-id="0c61a-139">다음 링크는 [알고리즘 선택을 위한 상세 지침](../how-to-choose-an-ml-net-algorithm.md)을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0c61a-139">The following link provides more [guidance on which algorithm to choose](../how-to-choose-an-ml-net-algorithm.md).</span></span>
