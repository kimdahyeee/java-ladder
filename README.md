# 사다리 게임
## 진행 방법
* 사다리 게임 게임 요구사항을 파악한다.
* 요구사항에 대한 구현을 완료한 후 자신의 github 아이디에 해당하는 브랜치에 Pull Request(이하 PR)를 통해 코드 리뷰 요청을 한다.
* 코드 리뷰 피드백에 대한 개선 작업을 하고 다시 PUSH한다.
* 모든 피드백을 완료하면 다음 단계를 도전하고 앞의 과정을 반복한다.

## 온라인 코드 리뷰 과정
* [텍스트와 이미지로 살펴보는 온라인 코드 리뷰 과정](https://github.com/nextstep-step/nextstep-docs/tree/master/codereview)

## 기능 요구사항
### Item :: 입력 값 객체
- [X] 입력 값은 null 이거나 빈문자열일 수 없다.
- [X] 입력 값은 최대 5글자까지 부여할 수 있다.
- [X] 입력 값은 5글자 너비로 출력한다.
- [X] 출력 시 Input 필드를 출력한다.

### Items :: 사다리 참여자 / 결과 값 객체 공통 사용 객체
- [X] Item의 List는 null이면 안된다.
- [X] Item은 2개 이상이어야한다.

### Players :: 사다리 참여자 객체
- [ ] Items 객체를 가진다.

### Results :: 결과 값 객체
- [ ] Items 객체를 가진다.

### Playing :: 게임 참여 객체
- [X] 게임 참여 객체는 Players(참여자), Results(결과) 객체를 가진다.
- [X] 참여자와 결과 객체의 갯수는 동일해야한다.

### Point :: 사다리 각 층의 지점
- [X] Point는 양 방향의 스텝의 유/무에 따라 true/false 를 가진다.
- [X] before/after은 동시에 true일 수 없다. (라인을 기준으로 양방향으로 가로 라인이 존재할 수 없다.)
- [X] Point 현재 상태에 따라 Movement 객체를 반환한다. (이동 방향을 알 수 있다.)

### Line :: 사다리 라인
- [X] User 객체 수 만큼 생성된다.
- [X] 디딤대는 true/false의 arrayList로 이루어져 있다.
    - 디딤대가 있는 경우 true
    - 디딤대가 없는 경우 false
- [X] 이 전에 디딤대가 있는 경우 연속해서 존재할 수 없다. (가로 라인이 겹치는 경우는 있을 수 없다.)
- [X] 사다리의 디딤대는 '-----' 로 출력한다.

### Ladder :: 사다리
- [X] 사다리는 LadderUsers와 Line을 가진다.
- [X] 사다리 높이 만큼 생성된다.
- [X] 사다리는 입력한 사다리 높이 만큼의 라인(`Line`)를 가진다.
- [X] 사다리의 다리는 '|' 로 출력한다.

### Game :: 사다리 게임 객체
- [X] 사다리 게임 객체는 게임 참여 객체(Playing)과 사다리 객체(Ladder)를 가진다.
- [ ] 결과를 확인할 수 있다.
    - [ ] 대상이 all인 경우, 전체 참여자의 실행 결과를 보여준다.
    - [ ] 대상이 개인의 이름인 경우, 개인의 실행 결과를 보여준다.
    - [ ] 대상이 포함되지 않은 경우, 존재하지 않는 사용자라는 exception 반환한다.

### Movement :: 이동 객체 (enum)
- [X] 이동 객체는 좌/우/전진에 대한 상태 값을 가진다.
- [X] left/right 상태에 따라 Movement 반환한다.

### ConvertUtil
- [X] 문자열을 쉽표(,) 기준으로 구분한다.
- [X] 빈 문자열이나 null 인 경우 IllegalArgument exception을 반환한다.

### InputView
- [X] 참여할 사람 이름을 입력받아 문자열 그대로 반환한다.
    - 참여할 사람은 ,로 구분된다.
- [X] 최대 사다리 높이(숫자)를 입력받아 그대로 반환한다.
- [X] 실행 결과를 입력받아 문자열 그대로 반환한다. 
    - 실행 결과는 ,로 구분된다.
- [ ] 결과를 보고 싶은 사람을 입력받는다.

### ResultView
- [X] 첫 째 줄에 헤더인 "실행결과"를 출력한다.
- [X] 참여한 사람 이름을 출력한다.
- [X] 만들어진 사다리를 출력한다.
- [X] 사다리 아래 결과를 출력한다.
- [ ] 실행 결과를 출력한다.