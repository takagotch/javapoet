### jvapoet
---
https://github.com/square/javapoet

```java
package com.example.helloworld;

public final class HelloWorld {
  public static void main(String[] args) {
    System.out.println("Hello, JavaPoet!");
  }
}

MethodSpec main = MethodSpec.methodBuilder("main")
  .addModifiers(Modifier.PUBLIC, Modifier.STATIC)
  .returns(void.class)
  .addParameter(String[].class, "args")
  .addStatement("$T.out.println($S)", System.class, "Hello, JavaPoet!")
  .build();
  
TypeSpec helloWorld = TypeSpec.classBuilder("HelloWorld")
  .addModifiers(Modifier.PUBLIC, Modifier.FINAL)
  .addMethod(main)
  .build();
  
JavaFile javaFile = JavaFile.builder("com.example.helloworld", helloWorld)
  .addModifiers(Modifier.PUBLIC, Modifier.FINAL)
  .addMethod(main)
  .build();
  
JavaFile javaFile = JavaFile.builder("com.example.helloworld", helloWorld)
  .build();

MethodSpec main = MethodSpec.methodBuilder("main")
  .addCode(""
    + "int total = 0;\n"
    + "for (int i = 0; i < 10; i++) {\n"
    + " total += i;\n"
    + "}\n")
  .build();

void main() {
  int total = 0;
  for (int i = 0; i < 10; i++) {
    total += i;
  }
}



```

```
```

```
```
