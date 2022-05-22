# Object Mapper
## @JsonProperty, @JsonNaming
- 사용 목적 : PSOT, PUT으로 넘어오는 JSON 데이터는 스네이크 케이스다 하지만 자바 엔티티는 카멜 케이스로 이루어져 있어
이를 매핑 시켜주기 위해 사용하는 어노테이션이 @JsonProperty, @JsonNaming 이다. 
<br>

- 사용법 : com.fasterxml.jackson.core 패키지를 Gradle dependencies에 주입해주면 사용 가능 하다.
<br>

### Gradle 추가
```gradle
dependencies {
    // https://mvnrepository.com/artifact/com.fasterxml.jackson.core/jackson-databind
    implementation group: 'com.fasterxml.jackson.core', name: 'jackson-databind', version: '2.12.1'
    testImplementation 'org.junit.jupiter:junit-jupiter-api:5.7.0'
    testRuntimeOnly 'org.junit.jupiter:junit-jupiter-engine:5.7.0'
}
````
<br>

### java 어노테이션 사용 (카멜 케이스 = 스네이크 케이스)
```java
    @JsonProperty("car_number")
    private String carNumber;

    @JsonProperty("TYPE")
    private String type;
```
<br>

### json design

```json
{
    "name":"홍길동",
    "age":29,
    "cars":[
        {
            "name":"K5",
            "car_number":"11가 1111",
            "TYPE":"sedan"
        },
        {
            "name":"Q5",
            "car_number":"22가 2222",
            "TYPE":"SUV"
        }
    ]
}
```

