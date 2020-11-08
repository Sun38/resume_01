# **이력서 (RESUME)**
## **소개**
----------------------------

<img src="image.jpg" alt="drawing" width="300"/>

- 이름 : 선민구

- 군필여부 : 미필

- Email : tjsalsrn6@naver.com

- GitHub : github.com/Sun38

```
맡은 일은 어떠한 일이라도 최선을 다하고자 합니다.
```

## 취미 및 특기 사항
-------------------------------
- **취미**
    + 기타 연주
    + 노래 부르기
    + 헬스
    + 농구

- **특기 사항**
    + 게임 제작
    + 역사 지식

# __개인 경력__
- CU 편의점 아르바이트 근무 (2019.02 ~ 2019.08)
- 베이커리 아르바이트 근무 (2018.07 ~ 2018.08)
- 뷔페 아르바이트 근무 (2018.02 ~ 2018. 05)
- 한림대학교 소프트웨어융학대학 교학팀 근로장학생 근무 (2019.12 ~ 2020.02)

## __단체경력__
---------------------------------------
- 소프트웨어융합대학 학술동아리 씨애랑 (2018.03 ~ 2018.08)

- 중앙동아리 락밴드 CODA (2018.03 ~ 2018.12)

- 네이버 커넥트재단 부스트 코딩뉴비 챌린지 2020 SUMMER: CS50 (2020.07 ~ 2020.08)

- 중앙동아리 JDM 찬양 연주 기타 담당 (2018.03 ~ 2018.12)

## **학력**
------------------------------------------
- 동국대학교사범대학부속고등학교 졸업 (2015.03 ~ 2018.02)

- 한림대학교 소프트웨어융합대학 빅데이터전공 3학년 재학 (2018.02 ~)
    + JAVA 프로그래밍
    + C 프로그래밍
    + C++ 프로그래밍
    + 파이썬과학프로그래밍기초
    + 자료구조
    + 알고리즘
    + 데이터베이스
    + 컴퓨터구조
    + VR/AR 게임제작기초
    + 데이터시각화
    + 운영체제
    + 윈도우프로그래밍
    + 프로그래밍어론
    + 소프트웨어개론
    + ...
## **보유자격증**
- 자동차운전면허증 2종 보통 (2018.02.07)
## **사용 기술**
---------------------------
- JAVA
- C
- C++
- C#
- Unity Engine
- Linux
- Python
- R

## **개인 프로젝트**
----------------------------
- **Python 게임 만들기**
    + 소개 : Python의 turtle 모듈을 사용하여 간단한 게임 만들기
    + 관련기술 : Python
    + 라이브러리 : random, turtle, time, sys
    
```python
import random                         
import turtle as t
import time
import sys


#변수 초기 설정
life=1
bspd=1
tspd=3
score=0
tablue=2
tbblue=2

#적 거북이 설정
tb=t.Turtle()
tb.shape("turtle")
tb.color("red")
tb.speed(0)
tb.up()
tb.goto(0,200)

#먹이 1 설정
tta=t.Turtle()
tta.shape("square")
tta.color("brown")
tta.turtlesize(0.5)
tta.speed(0)
tta.up()
tta.goto(random.randint(-210,210),random.randint(-210,210))

#먹이 2 설정
ttb=t.Turtle()
ttb.shape("square")
ttb.color("brown")
ttb.turtlesize(0.5)
ttb.speed(0)
ttb.up()
ttb.goto(random.randint(-210,210),random.randint(-210,210))

#플레이어 거북이 설정
t.shape("turtle")
t.speed(0)

#동선을 그리지 않음
t.up()

#방향 함수 설정
def right():
    t.setheading(0)
def up():
    t.setheading(90)
def left():
    t.setheading(180)
def down():
    t.setheading(270)
    
#화살표 키를 누르면 고개를 돌림
t.onkeypress(right,"Right")
t.onkeypress(up,"Up")
t.onkeypress(left,"Left")
t.onkeypress(down,"Down")

#
t.setup(500,500)
t.listen()
t.bgcolor("white")

#게임 설명
print("[ Turtle Survival -- 게임 규칙 ]")
print("1. 키보드의 방향키를 통해 움직입니다.")
print("2. 맵에 무작위로 놓여있는 작은 사각형(먹이)을 먹습니다.")
print("3. 빨간거북이를 피해 최대한 오래 살아남습니다.")
print("4. 빨간거북이와 부딫히면 게임이 끝나고 결과창이 뜨게됩니다.")
print("Tip: 가끔씩 파란색 먹이가 나타나는데, 점수를 2배로 줍니다.\n")


#플레이타임 측정 시작
time_a=time.time()

#게임 실행
while life==1:

    #적 거북이와 닿으면 게임 오버
    if t.distance(tb)<15:
        life=0  

    #프로그램 창 타이플 설정
    scorestr=str(score)
    gametitle="[ Tutrle Survival ] 현재 모은 먹이 수: "+scorestr+"개"
    t.title(gametitle)

    #맵 밖으로 탈출 방지
    xpos=t.xcor()
    ypos=t.ycor()
    if xpos>250:
        t.setx(230)
    if xpos<-250:
        t.setx(-230)
    if ypos>230:
        t.sety(230)
    if ypos<-230:
        t.sety(-230) 

    #적 거북이 이동 설정
    w=tb.towards(t.pos())
    tb.setheading(w)
    t.fd(tspd)
    tb.fd(bspd) 
    nspd=int(tspd)

    #먹이 1를 먹었을 때
    if t.distance(tta)<20:
        
        #랜덤한 위치로 이동시킴
        tax=random.randint(-210,210)
        tay=random.randint(-210,210)
        tta.goto(tax,tay)
        
        #먹이가 파란색일 때는 점수 2점 획득, 아니면 1
        if tablue==1:
            score=score+2
        else:
            score=score+1
            
        #다음 번에 랜덤으로 먹이를 파란색 혹은 갈색으로 결정
        tablue=random.randint(1,13-nspd)
        if tablue==1:
            tta.color(0,0,1)
        else:
            tta.color("brown")

    #먹이 2도 동일           
    if t.distance(ttb)<20:
        tbx=random.randint(-210,210)
        tby=random.randint(-210,210)
        ttb.goto(tbx,tby)
        if tbblue==1:
            score=score+2
        else:
            score=score+1
            tbblue=random.randint(1,13-nspd)
        if tbblue==1:
            ttb.color(0,0,1)
        else:
            ttb.color("brown")
            
    #플레이어 거북이 속도증가. 최대 속도 9
    if tspd<=9:
        tspd=tspd+0.001
        
    #적 거북이 속도증가. 최대속도 8.35
    if bspd<8.35:
        bspd=bspd+0.0011

    #속도가 빨라질 수록(시간이 지날수록) 배경이 어두워짐
    if nspd==4:
        t.bgcolor(0.85,0.85,0.85)
    if nspd==5:
        t.bgcolor(0.7,0.7,0.7)
    if nspd==6:
        t.bgcolor(0.5,0.5,0.5)
    if nspd==7:
        t.bgcolor(0.4,0.4,0.4)
    if nspd==8:
        t.bgcolor(0.25,0.25,0.25)

#게임 종료
        
#플레이타임 기록
time_b=time.time()
playtime=time_b-time_a

#오브젝트 숨김
t.ht()
tta.ht()
ttb.ht()
tb.ht()
t.bgcolor(1,1,1)

#결과 화면 출력
t.title("[ Tutrle Survival ] 게임이 종료되었습니다.")
print("\n――――――――――――< 게임 종료 >――――――――――――\n")
if score>=0:
    print("[ Result ] 당신은 총 ",score," 개의 먹이를 먹었습니다.")
gm=0
gs=0
if playtime>3600:
    print("[ Result ] 당신은... 도대체 게임을 얼마나 오랫동안 한 거죠?\n")
else:
    if playtime//60>0:
        gm=int(playtime//60)
        gs=int(playtime%60)
    if playtime//60==0:
        gs=int(playtime)
    print("[ Result ] 당신은", gm," 분 ",gs," 초 동안 생존하였습니다.\n")
finalscore=int(score*40+playtime*10)
print("[ Result ] 총 점수:", finalscore)
rank="F"
if finalscore>800:
    rank="E"
if finalscore>1500:
    rank="D"
if finalscore>3000:
    rank="C"
if finalscore>5000:
    rank="B"
if finalscore>10000:
    rank="A"
if finalscore>25000:
    rank="S"
if finalscore>50000:
    rank="SS"
if finalscore>999999:
    rank="SSS"

print("\n[ Result ] 랭크 ▶ ",rank," Rank")
print("\n          *엔터를 누르면 게임을 종료합니다.")
print("―――――――――――――――――――――――――――――――")
input()
sys.exit()
```

- **Unity Engine 게임 만들기**
    + 소개 : Unity Engine을 활용하여 간단한 농구 게임 만들기
    + 관련기술 : C#, Unity Engine 활용 능력

![Unity_image](image2.PNG)

- **해외 경험**

    어렸을 때부터 동북아시아의 역사에 관심이 많아서 동아시아 역사를 배경으로 한 게임을 만들겠다는 생각으로 컴퓨터공학과에 진학했다.

    지금까지 갔다 온 나라 중 대만과 일본이 가장 인상 깊었는데 두 나라 사이에는 공통점이 많았다. 대만은 일본과 문화적으로 닮은 점이 많은 나라이다. 사람들이 다들 예의 바르고 거리에 쓰레기가 없어서 잘 정돈이 된 모습이었다. 

    + **대만 타이페이 여행 (2019.02.18 ~ 2019.02.21)**

        대만 사람들은 우리나라와는 다르게 다들 아침을 사먹는 것 같다. 자취할 때 아침 해결이 매우 불편했는데 확실히 우리나라보다 아침 식사를 중시하는 듯했다. 

        역사에 관심이 많다 보니 그 나라의 유명한 박물관은 되도록 들러 보는 편이다. 때문에 국립고궁박물원을 방문하였다. 장제스가 국공내전에서 공산당에 패하고 대만으로 피신했을 때, 중국 대륙에서 가져온 엄청난 유물들이 보관되어 있어 세계 3대 박물관으로 불린다고 한다. 정말 엄청난 규모의 유물들이 있었지만, 한국어 설명이 없어서 영문 안내문에 의존해야 했다.

        중국은 자신들의 국부인 모택동에 대해 의견이 갈리지만 대만 사람들은 장제스에 대해 좋게 생각하는 것을 알 수 있었다. 숙소 근처의 공원과 시내에서도 장제스 동상을 종종 볼 수 있었다.

        이에 흥미를 느껴 중정기념당에 방문하게 되었다. 중앙홀에 들어가니 많은 인파가 붐볐다. 중앙에는 장제스가 앉아있는 동상이 있었고, 때마침 국기계양식이 시작되었다. 군인들이 홀을 한바퀴 돌고 계단을 내려가서 광장의 국기를 게양하는 것을 따라갔다. 일련의 과정이 엄숙하고 큰 규모로 진행이 되었다.  
        
    + **일본 후쿠오카 여행 (2019.08.20 ~ 2019.08.23)**

        일본은 가히 편의점의 나라라고 불릴 만큼 편의점의 종류도 많고 특히 취급 품목의 종류가 엄청 많았다. 또한, 교통비가 비싸서 그런지 자전거를 이용하는 사람들이 많고, 자판기의 수도 많았다. 그리고 사람들이 카드에 대해 불신이 많아서 현금 사용을 많이 한다고 해서, 카드 결제가 안되는 곳이 많아서 불편했다. 서비스업에 종사하는 사람들이 다들 정말 친절해서 우리나라에서 아르바이트를 하던 내 모습과 매우 대조되었다. 

        여행을 갔을 때, 먹는 것도 중요하지만 역사적인 장소를 방문하는 것도 중요하다고 생각해서 여러 역사적 장소를 방문하였다. 

        가장 기억에 남는 곳은 후쿠오카 성터와 쿠시다 신사이다. 예전부터 일본의 성 건축 양식이 아름다웠다고 생각해서 가보았는데, 후쿠오카의 초대 영주가 7년에 걸쳐 축성한 성이라고 한다. 일본은 길거리에 신사가 정말 많은 것을 볼 수 있었다. 신사는 혐한 신사들이 많다고 해서 왠만하면 가지 않으려고 했지만 명성황후를 시해할 당시 쓰인 칼이 보관된 장소라고 하여 방문하였다. 아쉽게도 실물로 볼 순 없었고, 신사의 아름다운 풍경을 만끽하고 나왔다.

    평소 나는 남들에게 말을 잘 걸지 못하고 새로운 곳에 적응을 잘 하지 못하고 내향적이다. 하지만, 해외에 나가게 되면 말이 통하지 않아서 그런지 다른 사람들이 신경 쓰이지 않아 나도 모르는 나의 새로운 모습들을 발견할 때가 있다. 예컨대 길을 물어볼 때도, 평소에는 어플을 켜서 찾아보는 등 어떻게든 혼자서 해결하려고 했지만, 해외에서는 사람들에게 말을 걸고 싶어서 일부러 물어보기도 한다. 이것이 내가 해외 여행을 좋아하는 이유인데, 언젠가는 해외 여행이라는 수단을 빌리지 않더라도 새로움에 대해서 거침없이 도전할 수 있는 사람이 되고 싶다.

