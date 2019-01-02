---
title: 기계 학습 용어집 - ML.NET
description: ML.NET에서 사용자 지정 모델을 빌드할 때 유용한 중요한 기계 학습 용어 모음입니다.
ms.custom: seodec18
ms.date: 12/20/2018
ms.openlocfilehash: ac0671bbecda93c411d3be82c789f53beb10fbca
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2018
ms.locfileid: "53760395"
---
# <a name="machine-learning-glossary-of-important-terms"></a><span data-ttu-id="00a3e-103">중요한 용어가 포함된 기계 학습 용어집</span><span class="sxs-lookup"><span data-stu-id="00a3e-103">Machine learning glossary of important terms</span></span>

<span data-ttu-id="00a3e-104">다음 목록은 ML.NET에서 사용자 지정 모델을 빌드할 때 유용한 중요한 기계 학습 용어 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-104">The following list is a compilation of important machine learning terms that are useful as you build your custom models in ML.NET.</span></span>

## <a name="accuracy"></a><span data-ttu-id="00a3e-105">정확도</span><span class="sxs-lookup"><span data-stu-id="00a3e-105">Accuracy</span></span>

<span data-ttu-id="00a3e-106">[분류](#classification)에서 정확도는 올바르게 분류된 항목 수를 테스트 집합의 총 항목 수로 나눈 값입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-106">In [classification](#classification), accuracy is the number of correctly classified items divided by the total number of items in the test set.</span></span> <span data-ttu-id="00a3e-107">범위는 0(가장 덜 정확함)에서 -1(가장 정확함)까지입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-107">Ranges from 0 (least accurate) to 1 (most accurate).</span></span> <span data-ttu-id="00a3e-108">정확도는 모델 성능에 대한 평가 메트릭 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-108">Accuracy is one of evaluation metrics of the performance of your model.</span></span> <span data-ttu-id="00a3e-109">[정밀도](#precision), [재현율](#recall) 및 [F 점수](#f-score)와 함께 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-109">Consider it in conjunction with [precision](#precision), [recall](#recall), and [F-score](#f-score).</span></span>

<span data-ttu-id="00a3e-110">관련 ML.NET API: <xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.Accuracy?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="00a3e-110">Related ML.NET API: <xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.Accuracy?displayProperty=nameWithType>.</span></span>

## <a name="area-under-the-curve-auc"></a><span data-ttu-id="00a3e-111">AUC(Area Under the Curve)</span><span class="sxs-lookup"><span data-stu-id="00a3e-111">Area under the curve (AUC)</span></span>

<span data-ttu-id="00a3e-112">[이진 분류](#binary-classification)에서 거짓 긍정 비율(x축)을 기준으로 참 긍정 비율(y축)을 표시하는 곡선 아래의 영역 값을 나타내는 평가 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-112">In [binary classification](#binary-classification), an evaluation metric that is the value of the area under the curve that plots the true positives rate (on the y-axis) against the false positives rate (on the x-axis).</span></span> <span data-ttu-id="00a3e-113">범위는 0.5(최악)에서 1(최상)까지입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-113">Ranges from 0.5 (worst) to 1 (best).</span></span> <span data-ttu-id="00a3e-114">ROC 곡선(수신기 운용 특성 곡선) 아래 영역이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-114">Also known as the area under the ROC curve, i.e., receiver operating characteristic curve.</span></span> <span data-ttu-id="00a3e-115">자세한 내용은 Wikipedia에서 [Receiver operating characteristic](https://en.wikipedia.org/wiki/Receiver_operating_characteristic)(수신기 운영 특성) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00a3e-115">For more information, see the [Receiver operating characteristic](https://en.wikipedia.org/wiki/Receiver_operating_characteristic) article on Wikipedia.</span></span>

## <a name="binary-classification"></a><span data-ttu-id="00a3e-116">이진 분류</span><span class="sxs-lookup"><span data-stu-id="00a3e-116">Binary classification</span></span>

<span data-ttu-id="00a3e-117">[레이블](#label)이 두 클래스 중 하나에만 해당하는 [분류](#classification) 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-117">A [classification](#classification) case where the [label](#label) is only one out of two classes.</span></span> <span data-ttu-id="00a3e-118">자세한 내용은 [기계 학습 작업](tasks.md) 항목의 [이진 분류](tasks.md#binary-classification) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00a3e-118">For more information, see the [Binary classification](tasks.md#binary-classification) section of the [Machine learning tasks](tasks.md) topic.</span></span>

## <a name="classification"></a><span data-ttu-id="00a3e-119">분류</span><span class="sxs-lookup"><span data-stu-id="00a3e-119">Classification</span></span>

<span data-ttu-id="00a3e-120">데이터가 범주를 예측하는 데 사용되는 경우 [감독된 기계 학습](#supervised-machine-learning) 작업을 분류라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-120">When the data is used to predict a category, [supervised machine learning](#supervised-machine-learning) task is called classification.</span></span> <span data-ttu-id="00a3e-121">[이진 분류](#binary-classification)는 두 개의 범주만 예측하는 것을 나타냅니다(예: 이미지를 ‘고양이’ 또는 ‘개’의 그림으로 분류).</span><span class="sxs-lookup"><span data-stu-id="00a3e-121">[Binary classification](#binary-classification) refers to predicting only two categories (for example, classifying an image as a picture of either a 'cat' or a 'dog').</span></span> <span data-ttu-id="00a3e-122">[다중 클래스 분류](#multiclass-classification)는 여러 범주를 예측하는 것을 나타냅니다(예: 이미지를 개의 특정 품종 그림으로 분류하는 경우).</span><span class="sxs-lookup"><span data-stu-id="00a3e-122">[Multiclass classification](#multiclass-classification) refers to predicting multiple categories (for example, when classifying an image as a picture of a specific breed of dog).</span></span>

## <a name="coefficient-of-determination"></a><span data-ttu-id="00a3e-123">결정 계수</span><span class="sxs-lookup"><span data-stu-id="00a3e-123">Coefficient of determination</span></span>

<span data-ttu-id="00a3e-124">[회귀](#regression)에서 데이터가 모델에 얼마나 잘 맞는지를 나타내는 평가 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-124">In [regression](#regression), an evaluation metric that indicates how well data fits a model.</span></span> <span data-ttu-id="00a3e-125">범위는 0에서 1까지입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-125">Ranges from 0 to 1.</span></span> <span data-ttu-id="00a3e-126">값 0은 데이터가 무작위이거나 모델에 맞지 않음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-126">A value of 0 means that the data is random or otherwise cannot be fit to the model.</span></span> <span data-ttu-id="00a3e-127">값 1은 모델이 데이터와 정확히 일치함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-127">A value of 1 means that the model exactly matches the data.</span></span> <span data-ttu-id="00a3e-128">이를 r<sup>2</sup>, R<sup> 2</sup> 또는 r 제곱이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-128">This is often referred to as r<sup>2</sup>, R<sup>2</sup>, or r-squared.</span></span>

## <a name="feature"></a><span data-ttu-id="00a3e-129">기능</span><span class="sxs-lookup"><span data-stu-id="00a3e-129">Feature</span></span>

<span data-ttu-id="00a3e-130">측정 중인 현상의 측정 가능한 속성입니다(일반적으로 숫자(double) 값).</span><span class="sxs-lookup"><span data-stu-id="00a3e-130">A measurable property of the phenomenon being measured, typically a numeric (double) value.</span></span> <span data-ttu-id="00a3e-131">다양한 기능을 **기능 벡터**라고 하며 일반적으로 `double[]`로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-131">Multiple features are referred to as a **Feature vector** and typically stored as `double[]`.</span></span> <span data-ttu-id="00a3e-132">기능은 측정 중인 현상의 중요한 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-132">Features define the important characteristics of the phenomenon being measured.</span></span> <span data-ttu-id="00a3e-133">자세한 내용은 Wikipedia에서 [Feature](https://en.wikipedia.org/wiki/Feature_(machine_learning))(기능) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00a3e-133">For more information, see the [Feature](https://en.wikipedia.org/wiki/Feature_(machine_learning)) article on Wikipedia.</span></span>

## <a name="feature-engineering"></a><span data-ttu-id="00a3e-134">기능 엔지니어링</span><span class="sxs-lookup"><span data-stu-id="00a3e-134">Feature engineering</span></span>

<span data-ttu-id="00a3e-135">기능 엔지니어링은 [기능](#feature) 집합을 정의하고 사용 가능한 현상 데이터에서 기능 벡터를 생성하는(기능 추출) 소프트웨어를 개발하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-135">Feature engineering is the process that involves defining a set of [features](#feature) and developing software that produces feature vectors from available phenomenon data, i.e., feature extraction.</span></span> <span data-ttu-id="00a3e-136">자세한 내용은 Wikipedia에서 [Feature engineering](https://en.wikipedia.org/wiki/Feature_engineering)(기능 엔지니어링) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00a3e-136">For more information, see the [Feature engineering](https://en.wikipedia.org/wiki/Feature_engineering) article on Wikipedia.</span></span>

## <a name="f-score"></a><span data-ttu-id="00a3e-137">F 점수</span><span class="sxs-lookup"><span data-stu-id="00a3e-137">F-score</span></span>

<span data-ttu-id="00a3e-138">[분류](#classification)에서 [정밀도](#precision) 및 [재현율](#recall)을 균형을 맞추는 평가 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-138">In [classification](#classification), an evaluation metric that balances [precision](#precision) and [recall](#recall).</span></span>

## <a name="hyperparameter"></a><span data-ttu-id="00a3e-139">하이퍼 매개 변수</span><span class="sxs-lookup"><span data-stu-id="00a3e-139">Hyperparameter</span></span>

<span data-ttu-id="00a3e-140">기계 학습 알고리즘의 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-140">A parameter of a machine learning algorithm.</span></span> <span data-ttu-id="00a3e-141">예로는 의사 결정 포리스트에서 학습할 트리 수 또는 그라데이션 하강 알고리즘의 단계 크기가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-141">Examples include the number of trees to learn in a decision forest or the step size in a gradient descent algorithm.</span></span> <span data-ttu-id="00a3e-142">‘하이퍼 매개 변수’의 값은 모델 학습 전에 설정되고 예측 함수의 매개 변수(예: 의사 결정 트리의 비교 지점 또는 선형 회귀 모델의 가중치)를 찾는 프로세스를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-142">Values of *Hyperparameters* are set before training the model and govern the process of finding the parameters of the prediction function, for example, the comparison points in a decision tree or the weights in a linear regression model.</span></span> <span data-ttu-id="00a3e-143">자세한 내용은 Wikipedia에서 [Hyperparameter](https://en.wikipedia.org/wiki/Hyperparameter_(machine_learning))(하이퍼 매개 변수) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00a3e-143">For more information, see the [Hyperparameter](https://en.wikipedia.org/wiki/Hyperparameter_(machine_learning)) article on Wikipedia.</span></span>

## <a name="label"></a><span data-ttu-id="00a3e-144">레이블</span><span class="sxs-lookup"><span data-stu-id="00a3e-144">Label</span></span>

<span data-ttu-id="00a3e-145">기계 학습 모델로 예측되는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-145">The element to be predicted with the machine learning model.</span></span> <span data-ttu-id="00a3e-146">예를 들어 개의 품종 또는 미래 재고 가격이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-146">For example, the breed of dog or a future stock price.</span></span>

## <a name="log-loss"></a><span data-ttu-id="00a3e-147">로그 손실</span><span class="sxs-lookup"><span data-stu-id="00a3e-147">Log loss</span></span>

<span data-ttu-id="00a3e-148">[분류](#classification)에서 분류자의 정확도를 분류하는 평가 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-148">In [classification](#classification), an evaluation metric that characterizes the accuracy of a classifier.</span></span> <span data-ttu-id="00a3e-149">로그 손실이 작을수록 분류자의 정확도가 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-149">The smaller log loss is, the more accurate a classifier is.</span></span>

## <a name="mean-absolute-error-mae"></a><span data-ttu-id="00a3e-150">MAE(절대 평균 오차)</span><span class="sxs-lookup"><span data-stu-id="00a3e-150">Mean absolute error (MAE)</span></span>

<span data-ttu-id="00a3e-151">[회귀](#regression)에서 모든 모델 오차의 평균을 나타내는 평가 메트릭입니다. 여기서 모델 오차는 예측된 [레이블](#label) 값과 올바른 레이블 값 사이의 거리입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-151">In [regression](#regression), an evaluation metric that is the average of all the model errors, where model error is the distance between the predicted [label](#label) value and the correct label value.</span></span>

## <a name="model"></a><span data-ttu-id="00a3e-152">모델</span><span class="sxs-lookup"><span data-stu-id="00a3e-152">Model</span></span>

<span data-ttu-id="00a3e-153">일반적으로 예측 함수에 대한 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-153">Traditionally, the parameters for the prediction function.</span></span> <span data-ttu-id="00a3e-154">예를 들어 선형 회귀 모델의 가중치 또는 의사 결정 트리의 분할 지점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-154">For example, the weights in a linear regression model or the split points in a decision tree.</span></span> <span data-ttu-id="00a3e-155">ML.NET에서 모델에는 도메인 개체의 [레이블](#label)을 예측하는 데 필요한 모든 정보가 포함됩니다(예: 이미지 또는 텍스트).</span><span class="sxs-lookup"><span data-stu-id="00a3e-155">In ML.NET, a model contains all the information necessary to predict the [label](#label) of a domain object (for example, image or text).</span></span> <span data-ttu-id="00a3e-156">이는 ML.NET 모델에 예측 함수의 매개 변수뿐만 아니라 필요한 기능화 단계가 포함됨을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-156">This means that ML.NET models include the featurization steps necessary as well as the parameters for the prediction function.</span></span>

## <a name="multiclass-classification"></a><span data-ttu-id="00a3e-157">다중 클래스 분류</span><span class="sxs-lookup"><span data-stu-id="00a3e-157">Multiclass classification</span></span>

<span data-ttu-id="00a3e-158">[레이블](#label)이 세 개 이상의 클래스 중 하나인 [분류](#classification) 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-158">A [classification](#classification) case where the [label](#label) is one out of three or more classes.</span></span> <span data-ttu-id="00a3e-159">자세한 내용은 [다중 클래스 작업](tasks.md) 항목의 [이진 분류](tasks.md#multiclass-classification) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00a3e-159">For more information, see the [Multiclass classification](tasks.md#multiclass-classification) section of the [Machine learning tasks](tasks.md) topic.</span></span>

## <a name="n-gram"></a><span data-ttu-id="00a3e-160">N-gram</span><span class="sxs-lookup"><span data-stu-id="00a3e-160">N-gram</span></span>

<span data-ttu-id="00a3e-161">텍스트 데이터에 대한 기능 추출 체계: N 단어 시퀀스가 [기능](#feature) 값으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-161">A feature extraction scheme for text data: any sequence of N words turns into a [feature](#feature) value.</span></span>

## <a name="numerical-feature-vector"></a><span data-ttu-id="00a3e-162">숫자 기능 벡터</span><span class="sxs-lookup"><span data-stu-id="00a3e-162">Numerical feature vector</span></span>

<span data-ttu-id="00a3e-163">숫자 값만으로 구성된 [기능](#feature) 벡터입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-163">A [feature](#feature) vector consisting only of numerical values.</span></span> <span data-ttu-id="00a3e-164">이는 `double[]`과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-164">This is similar to `double[]`.</span></span>

## <a name="pipeline"></a><span data-ttu-id="00a3e-165">파이프라인</span><span class="sxs-lookup"><span data-stu-id="00a3e-165">Pipeline</span></span>

<span data-ttu-id="00a3e-166">데이터 집합에 모델을 맞추는 데 필요한 모든 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-166">All of the operations needed to fit a model to a data set.</span></span> <span data-ttu-id="00a3e-167">파이프라인은 데이터 가져오기, 변환, 기능화 및 학습 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-167">A pipeline consists of data import, transformation, featurization, and learning steps.</span></span> <span data-ttu-id="00a3e-168">파이프라인은 학습된 후 모델로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-168">Once a pipeline is trained, it turns into a model.</span></span>

## <a name="precision"></a><span data-ttu-id="00a3e-169">전체 자릿수</span><span class="sxs-lookup"><span data-stu-id="00a3e-169">Precision</span></span>

<span data-ttu-id="00a3e-170">[분류](#classification)에서 클래스의 정밀도는 해당 클래스에 속하는 것으로 올바르게 예측된 항목 수를 클래스에 속하는 것으로 예측된 총 항목 수로 나눈 값입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-170">In [classification](#classification), the precision for a class is the number of items correctly predicted as belonging to that class divided by the total number of items predicted as belonging to the class.</span></span>

<span data-ttu-id="00a3e-171">관련 ML.NET API: <xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.NegativePrecision?displayProperty=nameWithType>, <xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.PositivePrecision?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="00a3e-171">Related ML.NET API: <xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.NegativePrecision?displayProperty=nameWithType>, <xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.PositivePrecision?displayProperty=nameWithType>.</span></span>

## <a name="recall"></a><span data-ttu-id="00a3e-172">재현율</span><span class="sxs-lookup"><span data-stu-id="00a3e-172">Recall</span></span>

<span data-ttu-id="00a3e-173">[분류](#classification)에서 클래스의 재현율은 해당 클래스에 속하는 것으로 올바르게 예측된 항목 수를 실제로 클래스에 속하는 총 항목 수로 나눈 값입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-173">In [classification](#classification), the recall for a class is the number of items correctly predicted as belonging to that class divided by the total number of items that actually belong to the class.</span></span>

## <a name="regression"></a><span data-ttu-id="00a3e-174">재발</span><span class="sxs-lookup"><span data-stu-id="00a3e-174">Regression</span></span>

<span data-ttu-id="00a3e-175">출력이 실제 값(예: double)인 [감독된 기계 학습](#supervised-machine-learning) 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-175">A [supervised machine learning](#supervised-machine-learning) task where the output is a real value, for example, double.</span></span> <span data-ttu-id="00a3e-176">예로는 재고 가격 예측이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-176">Examples include predicting stock prices.</span></span> <span data-ttu-id="00a3e-177">자세한 내용은 [다중 클래스 작업](tasks.md) 항목의 [회귀](tasks.md#regression) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00a3e-177">For more information, see the [Regression](tasks.md#regression) section of the [Machine learning tasks](tasks.md) topic.</span></span>

## <a name="relative-absolute-error"></a><span data-ttu-id="00a3e-178">상대 절대 오차</span><span class="sxs-lookup"><span data-stu-id="00a3e-178">Relative absolute error</span></span>

<span data-ttu-id="00a3e-179">[회귀](#regression)에서 모든 절대 오차의 합계를 올바른 [레이블](#label) 값과 모든 올바른 레이블 값의 평균 간 거리의 합계로 나눈 값을 나타내는 평가 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-179">In [regression](#regression), an evaluation metric that is the sum of all absolute errors divided by the sum of distances between correct [label](#label) values and the average of all correct label values.</span></span>

## <a name="relative-squared-error"></a><span data-ttu-id="00a3e-180">상대 제곱 오차</span><span class="sxs-lookup"><span data-stu-id="00a3e-180">Relative squared error</span></span>

<span data-ttu-id="00a3e-181">[회귀](#regression)에서 모든 절대 제곱 오차의 합계를 올바른 [레이블](#label) 값과 모든 올바른 레이블 값의 평균 간 거리 제곱의 합계로 나눈 값을 나타내는 평가 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-181">In [regression](#regression), an evaluation metric that is the sum of all squared absolute errors divided by the sum of squared distances between correct [label](#label) values and the average of all correct label values.</span></span>

## <a name="root-of-mean-squared-error-rmse"></a><span data-ttu-id="00a3e-182">RMSE(평균 제곱 오차의 제곱근)</span><span class="sxs-lookup"><span data-stu-id="00a3e-182">Root of mean squared error (RMSE)</span></span>

<span data-ttu-id="00a3e-183">[회귀](#regression)에서 오차 제곱 평균의 제곱근인 평가 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-183">In [regression](#regression), an evaluation metric that is the square root of the average of the squares of the errors.</span></span>

## <a name="supervised-machine-learning"></a><span data-ttu-id="00a3e-184">감독된 기계 학습</span><span class="sxs-lookup"><span data-stu-id="00a3e-184">Supervised machine learning</span></span>

<span data-ttu-id="00a3e-185">원하는 모델이 아직 확인되지 않은 데이터에 대한 레이블을 예측하는 기계 학습의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-185">A subclass of machine learning in which a desired model predicts the label for yet-unseen data.</span></span> <span data-ttu-id="00a3e-186">예로는 분류, 회귀 및 구조화된 예측이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-186">Examples include classification, regression, and structured prediction.</span></span> <span data-ttu-id="00a3e-187">자세한 내용은 Wikipedia에서 [Supervised learning](https://en.wikipedia.org/wiki/Supervised_learning)(감독된 학습) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00a3e-187">For more information, see the  [Supervised learning](https://en.wikipedia.org/wiki/Supervised_learning) article on Wikipedia.</span></span>

## <a name="training"></a><span data-ttu-id="00a3e-188">학습</span><span class="sxs-lookup"><span data-stu-id="00a3e-188">Training</span></span>

<span data-ttu-id="00a3e-189">지정된 학습 데이터 집합에 대한 [모델](#model)을 식별하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-189">The process of identifying a [model](#model) for a given training data set.</span></span> <span data-ttu-id="00a3e-190">선형 모델의 경우 가중치를 찾는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-190">For a linear model, this means finding the weights.</span></span> <span data-ttu-id="00a3e-191">트리의 경우 분할 지점을 식별하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-191">For a tree, it involves the identifying the split points.</span></span>

## <a name="transform"></a><span data-ttu-id="00a3e-192">변형</span><span class="sxs-lookup"><span data-stu-id="00a3e-192">Transform</span></span>

<span data-ttu-id="00a3e-193">데이터를 변환하는 [파이프라인](#pipeline) 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-193">A [pipeline](#pipeline) component that transforms data.</span></span> <span data-ttu-id="00a3e-194">예를 들어 텍스트에서 숫자의 벡터까지입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-194">For example, from text to vector of numbers.</span></span>

## <a name="unsupervised-machine-learning"></a><span data-ttu-id="00a3e-195">감독되지 않는 기계 학습</span><span class="sxs-lookup"><span data-stu-id="00a3e-195">Unsupervised machine learning</span></span>

<span data-ttu-id="00a3e-196">원하는 모델이 데이터에서 숨겨진(또는 잠재적) 구조를 찾는 기계 학습의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-196">A subclass of machine learning in which a desired model finds hidden (or latent) structure in data.</span></span> <span data-ttu-id="00a3e-197">예로는 클러스터링, 항목 모델링 및 차원 감소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a3e-197">Examples include clustering, topic modeling, and dimensionality reduction.</span></span> <span data-ttu-id="00a3e-198">자세한 내용은 Wikipedia에서 [Unsupervised learning](https://en.wikipedia.org/wiki/Unsupervised_learning)(감독되지 않는 학습) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00a3e-198">For more information, see the [Unsupervised learning](https://en.wikipedia.org/wiki/Unsupervised_learning) article on Wikipedia.</span></span>
