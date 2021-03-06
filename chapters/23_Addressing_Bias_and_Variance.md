## 23 Addressing Bias and Variance

다음은 편향과 분산이라는 문제를 풀어내기 위한 가장 간단한 공식이다:

- "피할 수 있는" 높은 편향이 있는 경우, 모델의 크기를 증가시켜보자. (예를 들어서, 더 많은 레이어 또는 뉴런을 추가하여 뉴럴넷의 크기를 증가)

- 높은 편향이 있는 경우, 학습 데이터셋에 더 많은 데이터를 추가해보자.

한계점 없이 뉴럴넷의 크기를 증가 시킬 수 있거나, 학습 데이터를 계속해서 추가할 수 있는 상황이라면, 많은 학습 문제들을 아주 잘 풀어나갈 수 있는 가능성이 있다.

그러나 현실적으로 보자면, 모델의 크기를 증가시키는것은 매우 큰 모델을 학습 시키는 것은 매우 시간이 오래 걸리기 때문에, 결과적으로 계산적인 문제를 일으키게 된다. 그리고 더 많은 학습 데이터를 얻는 것을 계속 수행하면, 스스로 기진맥진하게 될 수도 있을 것이며, 데이터 또한 고갈되고 말 것이다 (인터넷 상이라고 해도, 유한한 양의 데이터가 존재할 뿐이다).

다른 구조로 설계된 모델이 현재 직면한 문제에 대하여 다른 정도의 편향/분산을 보여줄 수 있을 것이다. 최근의 많은 딥러닝 연구로 많은 혁신적인 모델 구조들이 개발되었다. 그렇기 때문에, 문제 해결 방법으로 뉴럴넷을 사용 하는 것이라면, 아카데믹한 문헌이 아주 좋은 영감을 주는 자료가 될 수 있을 것이다. 또한, 혁신적인 모델 구조들에 대한 오픈소스로 구현된 사례를 GitHub에서 찾아보는 것도 가능하다. 하지만, 새로운 구조의 시도에 대한 결과 예측은 모델 크기를 증가 시키거나 학습 데이터를 추가하는 간단한 공식 보다는 덜 용이하다.

모델 크기를 증가시키면 일반적으로 편향치를 줄일 수 있지만, 이는 분산치를 증가시키고 과적합에 대한 위험성을 증가시킬 수도 있다. 그러나, 이때 발생하는 과적합의 문제는 일반적으로 정규화(Regularization)을 사용하지 않을때 발생한다. 아주 잘 디자인된 정규화 방법을 알고리즘에 포함시킨다면, 일반적으로 과적합률의 증가 없이 안전하게 모델의 크기를 증가시키는 것이 가능해진다.

개발 데이터셋에서 최고로 잘 작동하는 정규화 파라메터로 구성된 L2 정규화 또는 Dropout이 적용된 딥러닝 기술을 적용한다고 가정해 보자. 모델의 크기를 증가시키면, 보통 성능이 안정적으로 변함이 없거나 향상된다; 어떤 중대하게 악화되는 일은 일어날 확률이 적다. 큰 모델의 사용을 피해야하는 유일한 이유가 있다면, 그것은 증가하는 계산 비용이 될 것이다.