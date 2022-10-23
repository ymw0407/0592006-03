## 중간고사 정리

### 1. 피지컬 컴퓨팅 시스템 및 센서 & 엑추에이터 개념
- 컴퓨터에서 실행되는 프로그램(논리 세계 - logical world)이 현실 세계(physical world)의 사물과 소통하는 시스템

- 임베디드 컴퓨팅 시스템
  - __저비용__ / __경량__ / __저전력__ / __풍부한 입출력 단자__ 가 중요함! 
  - 라즈베리파이, 아두이노, 젯슨나노 등이 그 예시
  
- 센서(Sensor): 현실세계로부터의 __입력__
  - 거리: 초음파, 전파, 레이저
  - 영상: 웹캠, 열화상 카메라, X-Ray 센서
  - 위치정보: GPS, 가속도, 회전속도, 기울기
  - 온도, 습도, 미세먼지, 가스농도, 소리, 진동, 움직임, ...
  
- 액추에이터(Actuator): 현실세계를 향한 __출력__ 
  - 회전운동: DC모터, 스텝모터, 서보모터
  - 직선운동: 리니어 액추에이터
  - 소리: 스피커, 초음파 발신기
  - 빛/시각정보: 레이저 발신기, LED모듈, LCD 디스플레이
  - 진동: 진동모터
  
<br>

### 2. 나사 조립방법
이건... 글쎄요...

<br>

### 3. 브레드보드 사용 및 회로 구성 방법
- 전자회로 프로토타이핑 도구로 납땜 없이 회로 구성 가능하다는 장점이 있지만, 고속 동작 회로는 구현하지 못한다.
- 전원 레일(power rail)과 터미널 스트립(terminal strip)으로 이루어져있고, 터미너 스트립은 5개가 한 묶음이다.
- 각 rail/strip의 hole은 전기적으로 연결되어있다.

<br>

### 4. 아두이노의 setup() 및 loop() 함수의 이해
```C++
#define PIN_LED 13
unsigned int count, toggle;
// 전처리 및 전역변수 선언부로 각종 주변장치나 확장 기능에 대한 헤더파일 추가
// #define이나 typedef 등의 각종 전처리 선언
// 각종 상태값, 제어값들에 대한 전역변수 선언

void setup(){
  Serial.begin(115200);
  Serial.println("아두이노 전원을 켠 직후, 혹은 리셋 버튼을 누른 직후 자동으로 최초 1회만 실행된다. 각종 변수 및 장치 초기화 용도로 사용한다.");
}

void loop(){
  Serial.println("본문으로 setup함수가 실행된 이후 계속 반복적으로 실행된다. 계속 변화하는 외부 입력에 반응하여 출력을 갱신하는 인지-판단-제어 동작 구현에 적합하다.")
}
```

<br>

### 5. int, char, unsigned int 등 자료형 이해
- 1 byte: bool, (unsigned) char
- 2 bytes: (unsigned) int
- 4 bytes: (unsigned) long

<a href="https://codingrun.com/92">아두이노 자료형</a>

<br>

### 6. 시리얼 모니터 설정 방법 이해
```C++
void setup(){
  Serial.begin(115200); // serial 포트를 115200bps로 초기화한다.
  while(!Serial){
    ; // serial port가 연결될 때까지 기다린다. 하지만 이것은 UNO 버전에서는 불필요하다.
  }
}

void loop(){
  Serial.println("Hello World!"); // serial 포트로 메시지 출력
}
```
