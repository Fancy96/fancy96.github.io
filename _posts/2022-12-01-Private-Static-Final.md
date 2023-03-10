---
layout: post
title:  " Private static final "
categories: AlgorithmSkill
author: fancy96
---
* content
{:toc}

## static 이란?

* static은 '정적인', '움직임이 없는'으로 해석할 수 있는데, 이 static을 사용하면 메모리 jvm의 static 메모리(해당 영역은 프로그램이 시작하고 종료될 때까지 살아있는다)에 올라간다.

* static 메모리에 올라가기 때문에 초기화 과정이 필요 없어 static이 선언된 변수, 메서드에 곧장 접근이 가능하다.

* static을 사용한다는 의미는 해당 객체를 `공유`하겠다는 의미이다.

---

## final 이란?

* final은 불변하도록 만드는 것이 아니라 **재할당할 수 없도록** 만드는 것이다. 기본 데이터 타입인 int, boolean, char 등등에서는 재할당이 안되니 값을 변경할 수 있는 방법이 없다.

* 하지만, Collections타입(Map, List, Set)에서는 재할당이 안되지만, 값은 변할 수 있다.

* 상속을 하거나, 최초 초기화 이후 다시 초기화를 할 수 없다.

* final로 필드를 선언하면 필드는 상수가 된다.

---

## private static final 이란?

* private static final을 선언한 변수를 사용하면 재할당하지 못하며, 메모리에 한 번 올라가면 같은 값을 클래스 내부의 전체 필드, 메서드에서 `공유`한다.

* private final을 선언한 변수를 사용하면 재할당하지 못하며, 해당 필드, 메서드 별로 호출할 때마다 새로이 값이 할당(인스턴스화) 한다.

* 실제 예시

![](/assets/img/algorithm/Private-Static-Final-1.png)

* 위의 예시는 우아한테크코스5기 프리코스 미션 중 다리 건너기 게임에서 직접 구현한 BridgeGame 클래스를 가져왔다.

* 해당 클래스에서 `private static final`로 선언한 변수들은 **다리 건너기 게임이 시작할 때부터 종료할 때까지 값이 변하지 않아야 하며 클래스 내부의 필드, 메서드에서 공유**한다.

---