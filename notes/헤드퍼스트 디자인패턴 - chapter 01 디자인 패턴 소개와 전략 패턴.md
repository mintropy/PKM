---
type : knowledges
created : 2022-06-13 05:01
tags : #๐ฅ๏ธ
keywords : [๋์์ธํจํด, ์ ๋ตํจํด]
description : 
---

# ํค๋ํผ์คํธ ๋์์ธํจํด - chapter 01 ๋์์ธ ํจํด ์๊ฐ์ ์ ๋ต ํจํด

## ์ค๋ฆฌ ์๋ฎฌ๋ ์ด์ ๊ฒ์, SimUduck

- SimuDuck์ด๋ผ๋ ์ค๋ฆฌ ์๋ฎฌ๋ ์ด์ ๊ฒ์, Duck ์ํผํด๋์ค๋ฅผ ๋ง๋ค๊ณ  ํด๋์ค๋ฅผ ํ์ฅํด์ ๋ค๋ฅธ ์ข๋ฅ์ ์ค๋ฆฌ ๋ง๋ฌ

```mermaid
classDiagram
class Duck {
	quack()
	swim()
	display()
}
class MallardDuck {
	display()
}
class RedheadDuck {
	display()
}
Duck <|-- MallardDuck
Duck <|-- RedheadDuck
```

- `Duck` ํด๋์ค์ ์ค๋ฆฌ๊ฐ ๋  ์ ์๋ `fly()`๋ฉ์๋ ๋ฑ์ ์ถ๊ฐํ์ฌ ํ์ฅํ  ์ ์์
	- ๊ทธ๋ฐ๋ฐ ์๋ฆฌ๋ฅผ ๋ค๋ฅด๊ฒ ๋ด๊ณ , ๋ ์ง ์๋ ์ค๋ฆฌ๊ฐ ์๋ค๋ฉด?

```mermaid
classDiagram
class Duck {
	quack()
	swim()
	display()
}
class MallardDuck {
	display()
}
class RedheadDuck {
	display()
}
class RubberDuck {
	quack()
	display()
	fly()
}
Duck <|-- MallardDuck
Duck <|-- RedheadDuck
Duck <|-- RubberDuck
```

- ๊ธฐ์กด ๋ฉ์๋๋ค์ ์ค๋ฒ๋ผ์ด๋ํด์ ์์ฑ
	- ๋ง์ฝ ๋ ๋ค์ํ ์ค๋ฆฌ๊ฐ ์์ฑ๋๊ณ , ๊ณ์ ์ค๋ฒ๋ผ์ด๋๋ฅผ ํด์ผํ๋ค๋ฉด?
- ๋ง์ฝ ์ค๋ฆฌ์ ๊ฐ ๋์์ ์์์ ๋ฐ๋๋ก ์ง์ ํ๋ ๋ฐฉ์์ผ๋ก ์์ ํ๋ค๋ฉด?

```mermaid
classDiagram
class Duck {
	swim()
	display()
}
class Quackable {
	quack()
}
class Flyable {
	fly()
}
class MallardDuck {
	display()
	fly()
	quack()
}
class RedheadDuck {
	display()
	fly()
	quack()
}
class RubberDuck {
	quack()
	display()
}
Duck <|-- MallardDuck
Duck <|-- RedheadDuck
Duck <|-- RubberDuck
Quackable <.. MallardDuck
Quackable <.. RedheadDuck
Quackable <.. RubberDuck
Flyable <.. MallardDuck
Flyable <.. RedheadDuck
```

- Qucakable, Flyable ํด๋์ค๋ก ๋ถ๋ฅ, ์ํฉ์ ๋ฐ๋ผ ์ค๋ฒ๋ผ์ด๋
- ๋ ํธ๋ฆฌํ๊ฒ ๊ตฌํํ๊ธฐ ์ํด, ์ฝ๋ ์ค๋ณต์ด ๋ง์์ง
- ์์์ผ๋ก ๋ชจ๋ ๊ฒ์ ํด๊ฒฐํ  ์ ์์
	- ์๋ธํด๋์ค๋ง๋ค ํ๋์ด ๋ฐ๊ท๊ฒ ๋๋ค๋ฉด, ์ฌ๋ฐ๋ฅด๊ฒ ๊ตฌํํ์ง ๋ชปํจ
- **๋์์ธ ์์น** : ์ ํ๋ฆฌ์ผ์ด์์์ ๋ฌ๋ผ์ง๋ ๋ถ๋ถ์ ์ฐพ์๋ด๊ณ , ๋ฌ๋ผ์ง์ง ์๋ ๋ถ๋ถ๊ณผ ๋ถ๋ฆฌ
	- ๋ฐ๋๋ ๋ถ๋ถ์ ๋ฐ๋ก ๋ฝ์์ ์บก์ํ, ๋ฐ๋์ง ์๋ ๋ถ๋ถ์๋ ์ํฅ์ ๋ฏธ์น์ง ์๊ณ  ํ์ฅํ  ์ ์์
	- Duck ํด๋์ค๋ฅผ ๊ณ ๋ คํ๋ฉด, fly(), quack() ๋ถ๋ถ์ ์ ์ธํ๋ฉด ๋ฌธ์ ์์ด ์๋

## ์ค๋ฆฌ๋ฅผ ๋ค์ ๋์์ธํ๊ธฐ
- ์ค๋ฆฌ์ ํ๋ ๋์์ธ
	- **๋์์ธ ์์น** :  ๊ตฌํ๋ณด๋ค๋ ์ธํฐํ์ด์ค์ ๋ง์ถฐ์ ํ๋ก๊ทธ๋๋ฐ
- ์ค๋ฆฌ์ ํ๋์ Duck ํด๋์ค๊ฐ ์๋๋ผ ์๋ก ๊ตฌ์ฑํ ํ๋ ํด๋์ค์์ ๊ตฌํ

```mermaid
classDiagram
class FlyBehavior {
	fly()
}
class QuackBehavior {
	quack()
}
class FlyWithWings {
	fly()
}
class FlyNoWay {
	fly()
}
class Quack {
	quack()
}
class Squeak {
	quack()
}
class MuteQuack {
	quack()
}

FlyBehavior <|-- FlyWithWings
FlyBehavior <|-- FlyNoWay
QuackBehavior <|-- Quack
QuackBehavior <|-- Squeak
QuackBehavior <|-- MuteQuack
```

- ์ค๋ฆฌ๊ฐ ๋๋ ํ๋๊ณผ, ์ฐ๋ ํ๋์ ๊ฐ๊ฐ์ ํด๋์ค๋ก ๊ตฌ๋ถํ์ฌ ๋์์ธํ๊ณ , ๊ฐ ํ๋ ํด๋์ค๋ฅผ ํตํด ํ๋์ ์ง์ ํ  ์ ์์

## ์ค๋ฆฌํ๋ ํตํฉํ๊ธฐ
```mermaid
classDiagram
class Duck {
	FlyBehavior flyBehavior
	QuackBehavior quackBehavior
	performQuack()
	swim()
	display()
	performFly()
}
```

- Duck ํด๋์ค์ flyBehavior, quackBehavior ์ธํฐํ์ด์ค
	- ํน์  ๊ตฌ์ ํด๋์ค ํ์์ผ๋ก ์ ์ธํ๋ ๋์ , ์ธ์คํด์ค ๋ณ์ ์ถ๊ฐ

```java
public abstract class Duck {
	QuackBehavior quackBehavior
	// ๊ธฐํ ์ฝ๋
	public void performQuack() {
		quackBehavior.quack()
	}
}
```

- ์๋ฅผ ๊ธฐ๋ฐ์ผ๋ก ๊ตฌํ

```java
// MallardDuck.java
public class MallardDuck extends Duck {
	public MallardDuck() {
		quackBehavior = new Quack();
		flyBehavior = new FlyWithWings();
	}
	public void display() {
		System.out.println("์ ๋ ๋ฌผ์ค๋ฆฌ์๋๋ค")
	}
}
```

- Duck ํด๋์ค๋ฅผ ์์๋ฐ์ MallardDuck ํด๋์ค ์์ฑ

## ์ค๋ฆฌ ์ฝ๋ ํ์คํธ

```java
// Duck.java
public abstract class Duck {
	FlyBehavior flyBehavior;
	QuackBehavior quackBehavior;

	public Duck() {}
	public abstract void display();
	public void performFly() {
		flyBehavior.fly();
	}
	public void performQuack() {
		quackBehavior.quack();
	}
	public void swim() {
		System.out.println("๋ชจ๋  ์ค๋ฆฌ๋ ๋ฌผ์ ๋น๋๋ค. ๊ฐ์ง ์ค๋ฆฌ๋ ๋จ์ฃ ");
	}
}

public interface FlyBehavior {
	public void fly();
}

public interface QuackBehavior {
	public void quack();
}

// FlyWithWings.java
public class FlyWithWings implements FlyBehavior {
	public void fly() {
		System.out.println("๋ ๊ณ  ์์ด์!!");
	}
}

// FlyNoWay.java
public class FlyNoWay implements FlyBehavior {
	public void fly() {
		System.out.println("์ ๋ ๋ชป ๋ ์์");
	}
}

// Quack.java
public class Quack implements QuackBehavior {
	public void quack() {
		Systme.out.println("๊ฝฅ");
	}
}

// MuteQuack.java
public class MuteQuack implements QuackBehavior {
	public void quack() {
		System.out.println("<<์กฐ์ฉ~>>");
	}
}

// Squeak.java
public class Squeak implements QuackBehavior {
	public void queack() {
		System.out.println("์");
	}
}
```

```java
public class MiniDuckSimulator {
	public static void main(String[] args) {
		Duck mallard = new MallardDuck();
		mallard.performQuack();
		mallard.performFly();
	}
}
```

## ๋์ ์ผ๋ก ํ๋ ์ง์ ํ๊ธฐ
- ๋์ ์ผ๋ก ๋ง๋  ํ๋์ ํ์ฉํ๊ธฐ
- ์ค๋ฆฌ ํ๋ ํ์์ ์์ฑ์์์ ์ธ์คํด์ค๋ฅผ ๋ง๋๋ ๊ฒ์ด ์๋ Duck์ ์๋ธํด๋์ค์์ ์ธํฐ ๋ฉ์๋(setter method)๋ฅผ ํธ์ถํ๋ ๋ฐฉ๋ฒ?

```java
public void setFlyBehavior(FlyBehavior fb) {
	flyBehavior = fb;
}

public void setQuackBehavior(QuackBehavior qb) {
	quackBehavior = qb;
}
```

```mermaid
classDiagram
class Duck {
	FlyBehavior flyBehavior
	QuackBehavior quackBehavior
	performQuack()
	swim()
	display()
	performFly()
	setFlyBehavior()
	setQuackBehavior()
}
```

- Duck ํด๋์ค์ ๋ฉ์๋ 2๊ฐ ์ถ๊ฐ
	- ์ด ๋ ๋ฉ์๋๋ฅผ ํธ์ถํ๋ฉด ์ธ์ ๋ ์ง ํ๋์ ์ฆ์์ผ๋ก ๋ฐ๊ฟ ์ ์์

```java
// ModelDuck.java
public class ModelDuck extends Duck {
	public ModelDuck() {
		flyBehavior = new FlyNoWay();
		quackBehavior = new Quack();
	}

	public void display() {
		System.out.println("์ ๋ ๋ชจํ ์ค๋ฆฌ์๋๋ค");
	}
}
```

```java
// FlyRocketPowered.java
public class FlyRocketPowered implements FlyBehavior {
	public void fly() {
		Systme.out.println("๋ก์ผ ์ถ์ง์ผ๋ก ๋ ์๊ฐ๋๋ค");
	}
}
```

```java
// MiniDuckSimulator.java
public class MiniDuckSimulator {
	public static void main(String[] args) {
		Duck mallard = new MallardDuck();
		mallard.performQuack();
		mallard.perfomrFly();

		// ์ฝ๋ ์ถ๊ฐ
		Duck model = new ModelDuck();
		model.performFly();
		model.setFlyBehavior(new FlyRockerPowered());
		model.perfomrFly();
	}
}
```

- `ModelDuck`์ ์ถ๊ฐํ๊ณ , ๋ก์ผ ์ถ์ง ๊ธฐ๋ฅ ๋ถ์ฌ
	- `PerformFly()`๋ฅผ ์ฒ์ ํธ์ถํ๋ฉด ๊ธฐ๋ณธ ๋ฉ์๋์ธ `FlyNoWay()`๊ฐ ํธ์ถ
	- ์ดํ `setFlyBehavior()`๋ฅผ ํตํ์ฌ ๋ก์ผ ์ถ์ง ๋ถ์ฌ

```mermaid
flowchart LR
	subgraph client
		direction BT
		MallardDuck --> Duck
		RedheadDuck --> Duck
		RubberDuck --> Duck
		DecoyDuck --> Duck
	end
	subgraph fly
		direction BT
		FlyWithWings -.-> FlyBehavior
		FlyNoWay -.-> FlyBehavior
	end
	subgraph quack
		direction BT
		Quack -.-> QuackBehavior
		Squeak -.-> QuackBehavior
		MuteQuack -.-> QuackBehavior
	end
	Duck ==> FlyBehavior
	Duck ==> QuackBehavior
```

- ์ค๋ฆฌ์ ํ๋๋ค์ ์ผ๋ จ์ ํ๋์ผ๋ก ์๊ฐํ๋ ๋์ , ์๊ณ ๋ฆฌ์ฆ๊ตฐ(family of algorithms)์ผ๋ก ์๊ฐ
- ํด๋์ค ์ฌ์ด ๊ด๊ณ๋ ๊ณ ๋ฏผํ๊ธฐ
	- ํด๋์ค ์ฌ์ด๊ฐ ์ด๋ค ๊ด๊ณ์ธ์ง, A๋ B์ด๋ค, A์๋ B๊ฐ ์๋ค, A๊ฐ B๋ฅผ ๊ตฌํํ๋ค ๋ฑโฆ
- A์๋ B๊ฐ ์๋ค ๊ด๊ณ
	- ๊ฐ ์ค๋ฆฌ์ FlyBehavior, QuackBehavior๊ฐ ์์
	- ์ด๋ฐ ๋ฐฉ์์ผ๋ก ๋ ํด๋์ค๋ฅผ ํฉ์น๋ ๊ฒ์ `๊ตฌ์ฑ`์ ์ด์ฉํ๋ค๊ณ  ๋ถ๋ฆ
	- ์ค๋ฅด ํด๋์ค์์ ํ๋์ ์์๋ฐ๋ ๋์ , ์ฌ๋ฐ๋ฅธ ํ๋ ๊ฐ์ฒด๋ก ๊ตฌ์ฑ๋์ด ํ๋์ ๋ถ์ฌ ๋ฐ์
- **๋์์ธ ์์น** : ์์๋ณด๋ค๋ ๊ตฌ์ฑ์ ํ์ฉํ๋ค

> [!note] ์ ๋ต ํจํด(Strategy Pattern)
> ์๊ณ ๋ฆฌ์ฆ๊ตฐ์ ์ ์ํ๊ณ  ์บก์ํํด์ ๊ฐ๊ฐ์ ์๊ณ ๋ฆฌ์ฆ ๊ตฐ์ ์์ ํด์ ์ธ ์ ์๊ฒ ํด์ค
> ์ ๋ต ํจํด์ ์ฌ์ฉํ๋ฉด ํด๋ผ์ด์ธํธ๋ก๋ถํฐ ์๊ณ ๋ฆฌ์ฆ์ ๋ถ๋ฆฌํด์ ๋๋ฆฝ์ ์ผ๋ก ๋ณ๊ฒฝํ  ์ ์์

## ๋์์ธ ํจํด ํผ์ฆ

```mermaid
flowchart LR
subgraph client
	direction BT
	Queen --> Character[Character<br>setWeapon]
	King --> Character
	Troll --> Character
	Knight --> Character
end
subgraph Weapon
	direction BT
	KnifeBehavior -.-> WeaponBehavior
	BowAndArrowBehavior -.-> WeaponBehavior
	AxeBehavior -.-> WeaponBehavior
	SwordBehavior -.-> WeaponBehavior
end
Character ==> WeaponBehavior
```
