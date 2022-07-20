# 자바 final 의미 및 사용법

# 참고: https://coding-factory.tistory.com/525

## final 이란?
- final 필드는 초기값이 저장되면 최종적인 값이 되어 프로그램 실행 도중에 수정을 할 수 없다. 

## final 필드
- final 필드는 초기값을 줄 수 있는 방법이 단 두가지 밖에 없다.
```java
final int number = 1;
```
1) 필드 선언시 주는 방법
2) 생성자를 통해서 주는 방법: 생성자는 final 필드의 최종 초기화를 마쳐야 하는데 만약 초기화가 되지 않는 final 필드가 있다면 컴파일 에러가 발생한다. 

## final 객체 변수
```java
final Company company = new Company();
```
- 객체 변수에 final로 선언하면 그 변수에 다른 참조값을 지정할 수 없다. 즉 같은 타입으로 재생성이 불가능하다.
- 객체 자체는 변경이 불가능 하지만 내부는 setter로 변경 하능하다.

## final 클래스
```java
final class Company{
    String name = "회사명";
}
```
- 클래스에 final을 사용하게 되면 이 클래스는 최종상태가 되어 더 이상 상속이 불가능하다.
- 상속은 불가능 하지만 필드는 setter 함수로 변경할 수 있다.

## final 메소드
```java
public final void print() {
        System.out.println("회사 이름은 :"+name+" 입니다.");
    }

```

- 메소드에서 final을 사용하게 되면 상속받은 클래스에서 부모의 final 메소드를 재정의 할 수 없다.
- 시스템의 코어 부분에서 변경을 원치 않은 메소드에 많이 구현되어 있다. 


## 메소드의 인자값에 final 를 사용하는 경우
```java
public void setName(final String name) {
    	//name = "ex회사2"; //인자값으로 받은 final변수는 변경 불가능
        this.name = name;
    }

```
- 잘 사용하지는 않음. 코딩을 좀 더 명확하게 하고 싶을 때 씀
- final 필드와 마찬가지로 인자값에 final을 사용하는 경우 final 인자값의 변경이 불가능하다. 



