---
tags:
  - java
  - spring
  - springboot
draft: true
---
# SimpleMappingExceptionResolver
> 에러의 종류에 따라 반환할 view를 설정할 수 있음


### Syntax
```Java
Properties props = new Properties();  
props.setProperty("java.lang.NullPointerException","error/nullPointer");  
props.setProperty("MemberRegistException","error/memberRegist");
```