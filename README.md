## 아토믹 디자인의 한계
Atomic design은 brad frost가 '어떻게 하면 좋은 디자인시스템을 구축할 수 있을까?'에 대해 다른 산업분야 (ex 유기화학, 항공기제작, 빌딩건축 등..)의 적용사례에서 얻은 영감이자 한 방법론이다.

복잡하고 규모있는 무언가를 어떻게 설계 해야할지에 대한 모든 산업분야에서 통용되는 한 모듈개념의 방법일 뿐이다.

웹디자이너인 brad frost는 이 방법론으로 "영감"을 받았다고 했다. 유기화학(Organic Chemistry), 항공기제작, 웹 디자인시스템은 엄밀히 다르고 갖고있는 환경에서의 문제점이 다르기 때문에 Atomic design을 고려하여 그만의 디자인 시스템을 구축했을 것이다.

애초에 소프트웨어 개발을 위해 만들어진 개념이 아니고 
더더욱 컴포넌트를 구분하기 위한 폴더 구조를 위한 게 아니므로 이를 실제 업무에 적용하기 위해선 팀 구성원에 맞는 규칙을 새롭게 정의해야 한다. 

## Molecule?? Organism?? 
Atomic Design 방법론으로 컴포넌트 시스템을 구성하다 보면 어느 순간 반드시 Molecule로 둘지 Organism에 둘지 고민하는 순간이 온다.

Molecule
페이지 내 중복되는 컴포넌트 (Card, ListItem 등..)
"한 가지 일을 한다"라는 원칙 준수.
prop 으로 데이터를 주입받는다.

Organism
상태관리를 이용한 데이터와 결합하여 있는 컴포넌트
사용자에게 의미 있는 정보를 제공하거나 인터렉션 할 수 있는 UI를 제공하는 등 서비스로서 의미를 가지는 인터페이스

- [Effective Atomic Design](https://kciter.so/posts/effective-atomic-design)
- [Atomic Design Pattern의 Best Practice 여정기](https://yozm.wishket.com/magazine/detail/1531/)
- [Atomic Design Methodology](https://atomicdesign.bradfrost.com/chapter-2/)