### 1. `final` 변수

- **정의**: 한 번만 설정할 수 있는 변수. 런타임 상수 변수
- **예시**:
    
    ```dart
    final name = 'Bob'; // 타입 명시 없이 사용
    final String nickname = 'Bobby'; // 타입 명시와 함께 사용
    
    ```
    
- **변경 불가**: `final` 변수는 한 번 설정된 후 변경할 수 없음.
    
    ```dart
    name = 'Alice'; // 오류: final 변수는 한 번만 설정 가능
    
    ```
    

### 2. `const` 변수

- **정의**: 컴파일 타임 상수 변수(컴파일 단계에서 상수가 됨)로, `final`을 내포함.
- **클래스 레벨**: 클래스 레벨에서는 `static const`로 선언.
- **예시**:
    
    ```dart
    const bar = 1000000; // 압력 단위 (dynes/cm²)
    const double atm = 1.01325 * bar; // 표준 대기압
    
    ```
    
- **불변성**: `const` 변수는 설정 후 값을 변경할 수 없음.
    
    ```dart
    baz = [42]; // 오류: const 변수는 값을 변경할 수 없음
    
    ```
    

### 3. `const` 값 생성 및 사용

- **값 생성**: `const`는 상수 값을 생성하는 데도 사용.
- **예시**:
    
    ```dart
    var foo = const [];
    final bar = const [];
    const baz = []; // const []와 동일
    
    ```
    
- **변경 가능**: `final`,  `const` 변수가 아닐 때, 초기 `const` 값을 가질 수 있지만 나중에 변경 가능.
    
    ```dart
    foo = [1, 2, 3]; // 이전 값은 const []
    
    ```
    

### 4. `const`를 사용한 타입 검사 및 컬렉션

- **타입 검사와 캐스팅**:
    
    ```dart
    const Object i = 3; // i는 int 값을 가진 const Object
    const list = [i as int]; // 타입 캐스팅 사용
    const map = {if (i is int) i: 'int'}; // is와 collection if 사용
    const set = {if (list is List<int>) ...list}; // 스프레드 연산자 사용
    
    ```
    

### 5. 불변 객체

- **`final` 객체**: 객체 자체는 변경 불가하지만 필드는 변경 가능.
- **`const` 객체**: 객체와 필드 모두 변경 불가, 완전히 불변.
