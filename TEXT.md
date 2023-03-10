
Atomic Design 설계 원칙대로 작업한다면 Page에서 시작하여 Atom까지 데이터를 주입받게 된다. 
때문에, 데이터를 전달하기 위해 매번 깊게 들어가야 하거나 매 페이지마다 호출해야 하는 API가 있다면 상당히 귀찮아진다.

중요한 것은 Atomic Design을 포함하여 다양한 방법론이나 패턴을 팀에 적용할 때 맹목적으로 따르면 안된다는 것이다. 
주로 대중적으로 알려진 것은 범용성을 위해 핵심적인 것만 다루기 때문에 이를 업무에 적용하기 위해선
 팀 구성원에 맞는 규칙을 새롭게 정의해야 한다. 

렇지만 계층과 컴포넌트의 카테고리를 분리하는 단위가 계층, 목적, 재사용성, 범위 등 여러 개로 존재하는 반면,
 폴더 구조는 하나이기에 때때로 개념과 폴더구조가 실제로 잘 일치하지 않게 됩니다

Atomic Design Pattern에서는 ‘디자인 부품을 만들어 조립한다’는 개념을 원자가 모여 분자가 되고 분자가 모여 유기체가 된다는 화학적 용어를 
이용해서 설명했습니다. 이때 원자는 절대로 쪼개지지 않는 최소 단위이며, 원자끼리 결합했을 때 분자가 되어 특정 행동을 할 수 있게 되고, 
이 분자들이 결합한 형태의 유기체가 모여서 의미 있는 하나의 단위가 되는 식으로 비유해 설명하고 있습니다.

moecules이냐? organisms이냐? 그것이 문제로다!
누구나 Atomic Design Pattern을 적용하면 다음의 난제에 부딪히게 됩니다.

하지만 현실은 그렇지 않습니다. 현실 세계의 컴포넌트 구조는 재사용이 되는 범위가 다양해서 명확히 어디에 속하는지 알기 어려우며
 분자와 유기체 사이에는 훨씬 더 많은 실제 계층이 존재합니다.


처음에는 5개의 계층을 만들고, 적절히 그 계층 안에 컴포넌트를 넣으면 자연스럽게 좋은 구조로 만들어지는 시스템이었습니다. 
프로젝트가 커지면서 고작 5개의 분류만으로는 그 많은 컴포넌트를 구분하는 것이 굉장히 어렵다는 것을 알게 되었습니다.

초기에 Atomic Design Pattern을 도입한 목적이 컴포넌트에 대해서 잘 분류하고 하기 쉽게 정리하는 것이 목적이었습니다.
 그렇지만 어디에 넣어야 할지 고민하고, 명확한 기준이 없는 방식은 좋은 패턴이라고 보기 힘들었습니다.

처음에는 몰랐지만 점차 시간이 가면서 컴포넌트 간의 계층이 눈에 보이지 않았습니다. 
계층이 눈에 보이지 않으니 엔트리 포인트를 찾기가 힘들어졌고요. 그렇지만 크게 문제가 될로 생각하지 않았습니다.

그러나 점점 프로젝트가 커지다 보면 컴포넌트들을 도메인이나 의미와 관계없이 계층으로만 5단계로 나누는 것에서 한계점을 느끼게 됩니다. 
그러면서 점점 모호해지는 구분으로 인해서 잘 만든 컨벤션과 새로운 구조가 필요하다는 것도 알게 되었습니다.
 사실 Atomic Design Pattern을 찾고 도입하는 과정에서 이러한 경고(?)에 대한 내용들은 많이 읽어보았지만
 사람은 역시 본인이 겪어봐야만 알고 느끼게 되는 것들이 있습니다.

분류기준을 많이 만들어 두고, 그에 맞는 좋은 이름을 붙이고, 여기에 명확한 규칙을 만들어보는 것이 방법



다섯 단계의 레벨
아토믹 디자인 패턴은 무엇을 위해 웹 애플리케이션 컴포넌트를 다섯 레벨로 나눈 것일까? 컴포넌트를 어떤 기준으로 나누고, 
어떻게 재사용 해야 하는지에 대한 명확한 기준이 없다보니, 기준을 잡는 대신 각 레벨마다 ‘제약’을 두어 일관성을 추구한 것은 아닐까?

컴포넌트의 재사용성은 도메인에 대한 맥락(context)가 있는지에 따라 크게 나뉘게 된다. 
당연히 컴포넌트에서 특정 도메인에 대해 의존하게 되는 순간 재사용성이 떨어지게 되는데, 
이 부분에 대한 계층이 따로 존재한다던가 등 고려하지 않은 부분 도 아쉬운 부분이다.


하지만, 너무 많은 props drilling

ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

Atom의 범위
디자인원칙에 따라 
요소와 속성(애니메이션, 폰트, 색상 등의 스타일)을 포함한 UI가 시각적으로 하나의 덩어리이며 한 가지 역할을 한다면 Atom으로 인정하기로 규칙을 정했다.

Molecule은 데이터를 표시하고 이벤트를 받을 수 있지만 "하나의 역할"만을 가진다.
Organism은 사용자에게 의미를 가지는 기능적 요구사항에 포함되는 경우에 해당되는 컴포넌트다.

배너영역은 사용자는 광고를 본다, 광고는 주기적으로 변경된다 
기능적 요구사항 관점,  단순히 데이터에 맞춰 UI를 표시하는 하나의 역할을 가진 컴포넌트라는 점이다.




-------------------------------------------------------------
그


Template vs Pages 그리고 데이터 바인딩 문제

Atomic Design Pattern에서는 데이터와 디자인의 분리를 강조합니다. 그래서 데이터가 없이 조립된 디자인을 Template이라고
 하고 데이터와 디자인이 합쳐진 결과물을 Page라고 하고 있습니다. 우리가 익숙하게 사용해왔던 Container-Presenter 패턴입니다. 

하지만 개인적으로는 props drill 문제로 인해 Container-Presenter보다는 상태 관리를 기본으로 하고, 
props를 통한 컴포넌트의 독립성보다는 moecules와 organisms에 적극적으로 데이터 바인딩을 하게 됐습니다. 
그래서 데이터 바인딩을 하는 기준을 moecules로 봐야 할지 organisms으로 봐야 할지 template으로 봐야 할지 헷갈리는 상황이 발생하였습니다.





폴더 구조는 책으로 치면 목차와도 같은 것이었습니다. 
사실 책을 읽는 동안에는 목차를 그리 신경을 쓰면서 읽지는 않지만, 
나중에 필요한 것을 찾으려고 할 때 목차가 없으면 내가 원하던 것들이 어딨는지 그리고 전체적인 구조가 눈에 보이지 않는 것이었습니다. 
폴더 구조는 곧 생각의 체계였습니다. 직관적이여야 한다.

Atomic Design Pattern의 컴포넌트를 의존성과 계층별로 나누는 장점과 영역별로 나누는 또 목적별로 나누는 성격별로 나누는
 여러 가지의 기준들을 함께 잘 섞을 방법이 필요했습니다. 우리가 분류할 수 있는 카테고리는 다양하지만 실제 폴더 구조는
 1개일 수 밖에 없으니까요.

2안) 요즘 유행하는 MSA(Micro Service Architecture, 마이크로 서비스 아키텍처)를 떠올려 보자. 
하나의 앱이 사실 작은 여러 가지의 앱의 집합이라고 생각한다면 각자의 앱마다 다른 컴포넌트들로 조립된 것으로 생각하지 않을까? 
우리가 어떤 컴포넌트를 말할 때 이름을 먼저 떠올리지, 계층을 먼저 떠올리지 않는다.

2안 명확하게 체계가 더 정리

최대한 프로젝트를 이해할 수 있는 구조로 만드는 것이 맞지 않을까?'

Atomic Design Pattern에서 moecules과 organisms이 문제가 되는 것은 명확한 분류기준이 없기 때문입니다.
 프로젝트의 규모마다 개인의 판단마다 다 달라서 여기에는 정답이라는 것은 없겠지요. 
그렇지만 계속 주관적인 판단으로 헷갈리지 않기 위해서 저희 팀은 기준을 세워야 했습니다.

일단 크게 컴포넌트를 2가지로 먼저 분리해보기로 하였습니다.
뷰 컴포넌트(공통 컴포넌트)
비즈니스 컴포넌트

뷰 컴포넌트는 Input, Radio, Checkbox 등 다른 프로젝트에서도 재사용이 할 수 있는 컴포넌트들입니다.

 비즈니스 컴포넌트는 그 프로젝트에서만 사용하는 데이터를 보여주기 위한 컴포넌트입니다.
 캘린더로 치면 일정 상세 팝업과 같은 컴포넌트입니다. 물론 비즈니스 컴포넌트들은 일부 뷰 컴포넌트의 조립을 통해서 만들어지지만, 
그 프로젝트에서만 쓰이는 경우가 대부분이고 내부 상태관리 데이터와 강하게 결합이 되어 있는 컴포넌트를 의미합니다.

뷰 컴포넌트(공통): props를 이용한 독립된 형태
비즈니스 컴포넌트: 상태관리를 이용한 데이터와 결합하여 있는 컴포넌트







---------------------



유용한 패턴인가?
아토믹 디자인 패턴은 웹 애플리케이션을 5단계로 구분한다. 이 5단계가 유용한가? 유용하다는 것은 무엇인가? 이야기해보려고 한다.

어떤 패턴의 유용함을 판단하려면 무엇을 고민해봐야 할까? 이것은 좋은 코드에 대한 고민에서 힌트를 얻을 수 있다. 
소프트웨어는 끊임없이 변하기 때문에 변경에 유연하게 대응하는 코드를 작성해야 한다. 자연스럽게 변경에 잘 대응하고
 변경에 따른 영향 범위를 최소화 할 수 있도록 컴포넌트를 디자인해야 하고 패턴으로부터 이 목적을 달성할 수 있으면 유용하다고 볼 수 있다.

이러한 이유로 ‘순수하지 않다.’ 라는 결론을 내렸고 오히려 혼란을 야기할 수 있다고 생각한다. 혼란을 합의로 이끌어내기 위한 커뮤니케이션,
 합의를 이루는 과정도 비용이라고 생각한다.


컴포넌트의 재사용성은 도메인에 대한 맥락(context)가 있는지에 따라 크게 나뉘게 된다. 
당연히 컴포넌트에서 특정 도메인에 대해 의존하게 되는 순간 재사용성이 떨어지게 되는데, 
이 부분에 대한 계층이 따로 존재한다던가 등 고려하지 않은 부분 도 아쉬운 부분이다.




https://jbee.io/etc/what-is-good-code/