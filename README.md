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


MethodSpec main = MethodSpec.methodBuilder("main")
  .addStatement("int total = 0")
  .beginControlFlow("for (int i = 0; i < 10; i++)")
  .addStatement("total += i")
  .endControlFlow()
  .build();
  
private MethodSpec computeRange(String name, int from, int to, String op) {
  return MethodSpec.methodBuilder(name)
    .returns(int.class)
    .addStatement("int result = 1")
    .beginControlFlow("for (int i = " + from + "; i < " + to + "; i++)")
    .addStatement("result = result " + op + " i")
    .endControlFlow()
    .addStatement("return result")
    .build();
}

int multiply10to20() {
  int result = 1;
  for (int i = 10; i < 20; i++) {
    result = result * i;
  }
  return result;
}

MethodSpec main = MethodSpec.methodBuilder("main")
  .addStatement("long now = $T.currentTimeMillis()", System.class)
  .beginControlFlow("if ($T.currentTimeMillis() < now)", System.class)
  .addStatement("$T.out.println($S)", System.class, "Time travelling, woo hoo!")
  .nextControlFlow("else if ($T.currentTimeMillis() == now)", System.class)
  .addStatement("$T.out.println($S)", System.class, "Time stood still!")
  .nextControlFlow("else")
  .addStatement("$T.out.println($S)", System.class, "Ok, time still moving forward")
  .endControlFlow()
  .build();
  
void main() {
  long now = System.currentTimeMillis();
  if (System.currentTimeMillis() < now) {
    System.out.println("Time travelling, woo hoo!");
  } else if (System.currentTimeMillis() == now) {
    System.out.println("Time stood still!");
  } else {
    System.out.println("Ok, time still moving forward");
  }
}

```

```
```

```
```
