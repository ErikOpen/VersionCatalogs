# Build-logic构建

- 初始创建项目要选择在Building Configuration Language中选择带有 version catalogs的选项

- 创建Java/Kotlin Library 模块（build-logic）

- 在build-logic模块底下创建convention模块

- App下的settings.gradle.kts下添加build-logic

```Java
dependencyResolutionManagement {
    includeBuild("build-logic")
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        google()
        mavenCentral()
    }
}
```

- build-logic的构建按照该项目中的处理

- convention下主要是创建的插件（plugin），可以用来构建不同的依赖
    -例如Compose、hilt等，可以分成多个plugin，也可以集合，本例子是集合在一起
