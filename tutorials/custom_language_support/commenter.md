---
title: 17. Commenter
---

A commenter enables the user to comment-out a line of code at the cursor or selected code automatically.
The [`Commenter`](upsource:///platform/core-api/src/com/intellij/lang/Commenter.java) defines support for "Comment with Line Comment" and "Comment with Block Comment" actions. 

* bullet list
{:toc}

## 17.1. Define a Commenter
The Simple Language commenter subclasses `Commenter`.
This commenter defines the line comment prefix as "#".
```java
{% include /code_samples/simple_language_plugin/src/main/java/org/intellij/sdk/language/SimpleCommenter.java %}
```

## 17.2. Register the Commenter
The `SimpleCommenter` implementation is registered with the IntelliJ Platform in the plugin configuration file using the `com.intellij.lang.commenter` extension point. 
```xml
  <extensions defaultExtensionNs="com.intellij">
    <lang.commenter language="Simple" implementationClass="org.intellij.sdk.language.SimpleCommenter"/>
  </extensions>
```

## 17.3. Run the Project
Open the example Simple Language [properties file ](/tutorials/custom_language_support/lexer_and_parser_definition.md#47-run-the-project) in the IDE Development Instance.
Place the cursor at the `website` line.
Select **Code \| Comment with Line Comment**.
The line is converted to a comment.
Select **Code \| Comment with Line Comment** again, and the comment is converted back to active code.

![Commenter](img/commenter.png){:width="800px"}