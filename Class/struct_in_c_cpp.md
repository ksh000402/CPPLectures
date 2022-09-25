# C 구조체와 C++ 구조체 비교

구조체(struct)는 동일한 맥락(context)상 에서 함께 관리가 되어야 하는 (다른 자료형 또는 같은 자료형의) 데이터를 그룹화하여 새로운 자료형을 만드는데 사용된다. 즉 구조체가 새로운 사용자 정의 자료형을 만들 수 있기 때문에 구조체에 해당하는 변수를 선언할 수 있고 메모리에 그룹화된 모든 데이터들을 저장할 수 있는 저장공간을 한번에 활당할 수 있다.
같은 맥락으로 관리되어야 하는 데이터들의 그룹의 생성을 **구조체 정의(struct definition)** 이라 한다.

구조체의 개념은 C 언어 뿐 아니라 C++ 언어에도 존재한다. C++에서는 클래스가 존재하기 때문에 구조체를 사용할 필요성은 많지 않으나 C 언어와의 호환성을 제공하기 위해서 사용되고 있다. 

C 언어의 구조체에는 그룹화 대상이 데이터인데 C++ 언어의 구조체에는 데이터뿐만 아니라 데이터와 관련된 기능을 수행하는 함수도 대상이 된다. 
그리고 구조체 변수를 선언할 때 사용되는 자료형의 이름은 C++ 언어에서는 구조체 이름이 자료형이 되나 C 언어에서는 struct 키워드와 구조체 이름의 함께 자료형을 결정한다.

## 구조체의 정의 

여러 데이터의 집함으로 구조체를 정의하는 모습은 아래와 같이 C 언어와 C++ 언어 모두 동일하다. 이름, 학번, 나이, 학과 정보를 가지는 학생 정보를 표현하는 구조체를 정의하면 다음과 같다. 

```c++
struct Student {
  char name[20];
  char id[10];
  int age;
  int department;
};
```

## 구조체 변수 선언 및 사용예

C++ 언어에서의 구조체 번수의 선언과 사용예는 다음과 같다. 앞에서도 언급한 것과 같이 구조체 이름이 새로운 자료형의 이름이 된다.   

```c++
// C++에서의 구조체 선언 

Student s1;   // Student 구조체의 변수 s1 선언 (C++ 언어)

strcpy(s1.name, "이순신");
strcpy(s1.id, "20221234");
s1.age = 20;
s1.department = 21;
```

C 언어에서의 구조체 변수의 선언과 다음과 같다. C 언어에서 구조체 변수를 선언하기 위해 사용되는 자료형 이름은 **struct <구조체 이름>** 형태를 가진다. 

```c
// C 언어에서의 구조체 선언

struct Student s1;   // Student 구조체의 변수 s1 선언 (C 언어)

strcpy(s1.name, "이순신");
strcpy(s1.id, "20221234");
s1.age = 20;
s1.department = 21;
```

C 언어에서 구조체 번수를 선언할 때 자료형의 이름이 길어 C++와 같이 구조체 이름을 구조체 자료형의 이름으로 하기 위해서 **typedef** 를 사용한다.
```typedef```의 사용 예는 다음과 같다. typedef 키워드를 사용하여 <기존 자료형>을 <새로운 자료형>의 이름으로 새롭게 정의를 한다. 

```
typedef <기존 자료형> <새로운 자료형>
```

```c
typedef struct Student Student; // struct Student 자료형 이름을 새로운 Student 자료형을 정의한다.  
```

```c
// C 언어에서의 구조체 선언

typedef struct Student Student; // struct Student 자료형을 Student 자료형으로 재 정의
Student s1;   // Student 구조체의 변수 s1 선언 (C 언어)

strcpy(s1.name, "이순신");
strcpy(s1.id, "20221234");
s1.age = 20;
s1.department = 21;
```
