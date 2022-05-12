# 로또
## 진행 방법
* 로또 요구사항을 파악한다.
* 요구사항에 대한 구현을 완료한 후 자신의 github 아이디에 해당하는 브랜치에 Pull Request(이하 PR)를 통해 코드 리뷰 요청을 한다.
* 코드 리뷰 피드백에 대한 개선 작업을 하고 다시 PUSH한다.
* 모든 피드백을 완료하면 다음 단계를 도전하고 앞의 과정을 반복한다.

## 온라인 코드 리뷰 과정
* [텍스트와 이미지로 살펴보는 온라인 코드 리뷰 과정](https://github.com/next-step/nextstep-docs/tree/master/codereview)


---

## 기능 요구사항
- 로또 구입 금액을 입력하면 구입 금액에 해당하는 로또를 발급해야 한다.
- 로또 1장의 가격은 1000원이다.

## 프로그래밍 요구사항
- 모든 기능을 TDD로 구현해 단위 테스트가 존재해야 한다. 단, UI(System.out, System.in) 로직은 제외
  - 핵심 로직을 구현하는 코드와 UI를 담당하는 로직을 구분한다.
  - UI 로직을 InputView, ResultView와 같은 클래스를 추가해 분리한다.
- indent(인덴트, 들여쓰기) depth를 2를 넘지 않도록 구현한다. 1까지만 허용한다.
  - 예를 들어 while문 안에 if문이 있으면 들여쓰기는 2이다.
  - 힌트: indent(인덴트, 들여쓰기) depth를 줄이는 좋은 방법은 함수(또는 메소드)를 분리하면 된다.
- 함수(또는 메소드)의 길이가 15라인을 넘어가지 않도록 구현한다.
  - 함수(또는 메소드)가 한 가지 일만 잘 하도록 구현한다.
- 모든 로직에 단위 테스트를 구현한다. 단, UI(System.out, System.in) 로직은 제외
  - 핵심 로직을 구현하는 코드와 UI를 담당하는 로직을 구분한다.
  - UI 로직을 InputView, ResultView와 같은 클래스를 추가해 분리한다.
- 자바 코드 컨벤션을 지키면서 프로그래밍한다.
  - 참고문서: https://google.github.io/styleguide/javaguide.html 또는 https://myeonguni.tistory.com/1596
- else 예약어를 쓰지 않는다.
  - 힌트: if 조건절에서 값을 return하는 방식으로 구현하면 else를 사용하지 않아도 된다.
  - else를 쓰지 말라고 하니 switch/case로 구현하는 경우가 있는데 switch/case도 허용하지 않는다.

---

### 🔖 TDD를 위한 기능 목록 List
- [x] 구입 금액이 NULL & EMPTY 값이면 예외를 던진다.
- [x] 구입 금액이 숫자가 아닌 값이면 예외를 던진다.
- [x] 구입 금액이 음수 값이면 예외를 던진다.
- [x] 구입 금액이 로또 금액보다 작으면 예외를 던진다.
- [x] 구입 금액이 정상 값이면 로또 가격으로 나눈 값을 반환한다. 
- [x] 자동으로 중복되지 않도록 로또 숫자 6개(한 세트)를 뽑는다.
- [x] 한 세트의 숫자를 정렬한다.
- [x] 한 세트를 N번 뽑는다.
- [ ] 로또 두 세트 비교한다.
  - [ ] 0~2개 일치시 당첨금액은 0원이다.
  - [ ] 3개 일치시 당첨금액은 5000원이다.
  - [ ] 4개 일치시 당첨금액은 50000원이다.
  - [ ] 5개 일치시 당첨금액은 1500000원이다.
  - [ ] 6개 일치시 당첨금액은 2000000000원이다.
- [x] 지난 주 당첨 번호가 올바르지 않는 값이면 예외를 던진다.
- [ ] 지난 주 당첨 번호와 구매한 한 개 세트를 비교해 당첨 금액을 반환한다.
- [ ] 지난 주 당첨 번호와 구매한 N 개 세트를 비교해 당첨 금액을 반환한다. 
- [ ] 구매한 금액과 당첨금을 비교해 수익률을 출력한다. 

### 👍 처리하면 더 좋은 TODO List
- [ ] 화면 출력시 금액에 대한 부분은 자릿수 처리한다.
- [ ] 예외 던지면 재입력을 받도록 구현한다.
- [x] 인터페이스에 있는 List 처리 고민해보기 -> LottoNumber 클래스로 처리
