# GradleEx01
## 0.	gradle 이해
gradle은 소포트웨어 개발 프로젝트를 위한 오픈 소스 빌드 자동화 도구이다. 단순히 여러 작업들을 자동화하여 처리해주는 도구라고 생각하자.

gradle을 하기 전 ant와 maven을 해봤다. gradle은 그 둘의 장점을 결합한 형태라고 할 수 있다.

gradle은 ant의 유연성과 maven의 자동화 기능을 결합하여 제공한다.

## 1.	gradle install

gradle을 다운로드 하기 위해선 아래 링크로 접속하여 원하는 version의 complete을 원하는 위치에 다운 받는다.

[gradle down](https://gradle.org/releases/)

down 받은 gradle의 bin 폴더를 path 환경 변수에 추가하여 어느 위치에서든 사용할 수 있도록한다.

![image](https://github.com/auspicious0/GradleEx01/assets/108572025/152c65d1-11ec-406e-a6fe-f95cce7c61c3)


이제 cmd를 열어 gradle –v를 입력해 변수가 잘 잡혀있는지 확인한다.

![image](https://github.com/auspicious0/GradleEx01/assets/108572025/8e8e7db5-7886-4e36-9c6d-179e531273c4)

이제 java-applicaton type 템플릿을 만들어보자.

## 2.	HelloGradle

원하는 위치에 directory를 추가하고 gradle init을 수행한다.

Select해야 할 것들은 모두 enter를 눌러 default로 처리한다.
![image](https://github.com/auspicious0/GradleEx01/assets/108572025/52474b0f-b2da-442e-a8be-8d02ad087f73)
![image](https://github.com/auspicious0/GradleEx01/assets/108572025/1cb47a2d-ef2e-4d62-aa52-7a4274e5ab42)
![image](https://github.com/auspicious0/GradleEx01/assets/108572025/3b0ae669-1050-4a49-9683-620a30e0e252)
![image](https://github.com/auspicious0/GradleEx01/assets/108572025/34b2edfd-d4d1-48d4-b738-c86c8c899513)
![image](https://github.com/auspicious0/GradleEx01/assets/108572025/a9980dce-413f-42a5-97b6-d5ea680d6ce2)

 
   
이제 해당 폴더로 이동해 App.java파일을 확인해 본다.

![image](https://github.com/auspicious0/GradleEx01/assets/108572025/b304034a-2b16-440f-a86e-596a7a93c254)

![image](https://github.com/auspicious0/GradleEx01/assets/108572025/0edc5244-9ed7-4ec7-9149-47d88fbc2d0e)

 
 

해당 파일을 컴파일해 보자.

작업하던 cmd 창으로 이동해 
아래 코드를 순차적으로 실행한다.
```
gradle compileJava
gradle run
```

다음과 같은 결과가 나온다면 성공이다.

![image](https://github.com/auspicious0/GradleEx01/assets/108572025/88c134a6-4ec9-40c6-ac1f-169a4f5ef1de)

 

## 3.	Eclipse Gradle


이제 Ecipse에서 gradle 프로젝트를 만들어보자.

우선 아래 사진과 같이 GradleProject를 생성한다.

![image](https://github.com/auspicious0/GradleEx01/assets/108572025/750a1030-24a1-4910-81d6-0b705a1cd72a)

 
생성된 폴더에 src/main/java에 GradleTEST class를 추가한다.

 ![image](https://github.com/auspicious0/GradleEx01/assets/108572025/aff3c8e7-e8fd-4899-b9e2-10aae8c55b85)


해당 클래스는 다음과 같이 작성한다.

```
package Gradle;

public class GradleTest {
	public static void main(String[] args) {
		System.out.println("Gradle Test");
	}
}
```

위 클래스를 jar로 만들고 실행하기 위해서 build.gradle에 다음과 같은 내용을 추가한다.

```
jar{
	manifest{
		attributes 'Main-Class':'Gradle.GradleTest'
	}
}
```
간략히 설명하자면 main class를 우리가 생성한 클래스로 만들겠다는 의미이다.

오른쪽 혹은 아래에 Gradle Tasks를 찾아 jar을 더블클릭한 후 다음으로 이동한다.

자신의 레포지토리\lib\build\libs

해당 위치에서 cmd를 실행시킨 후 생성된 jar파일을 실행시킨다.

아래와 같은 결과가 나왔다면 성공이다.
 

![image](https://github.com/auspicious0/GradleEx01/assets/108572025/a2284f1d-a8ee-4e13-a2e8-5dda097c108d)
