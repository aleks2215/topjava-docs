# Онлайн-проект <a href="https://github.com/JavaWebinar/topjava">Topjava</a>
- Не стоит стремиться прочитать все ссылки урока, их можно использовать как справочник. Гораздо важнее пройти основной материал урока и сделать Домашнее Задание
- Обязательно посмотри <a href="https://github.com/JavaOPs/topjava/wiki/Git#Правила-работы-с-патчами-на-проекте">правила работы с патчами на проекте</a>
- Делать Apply Patch лучше по одному, непосредственно перед видео на эту тему, а при просмотре видео сразу отслеживать все изменения кода проекта по изменению в патче (`Version Control->Local Changes-> Ctrl+D`)
- **При первом Apply удобнее выбрать имя локального ченджлиста Name: Default**. Далее все остальные патчи также будут в него попадать.
- **Код проекта обновляется и не всегда совпадает с видео (можно увидеть как развивался проект). Изменения в проекте указываю после соответствующего патча.** 

- [x] Принял

## Материалы занятия

<a href="https://drive.google.com/drive/u/0/folders/0B9Ye2auQ_NsFfm5hSHEtbmxmN2kxb0NocVRwWl9KanowWXVCVXRZTlhaM09wQUswZkRidTA">Материалы занятия</a> (скачать все патчи можно через `Download/Скачать` папки patch)
![image](https://cloud.githubusercontent.com/assets/13649199/18330295/5f2ca214-7560-11e6-8e1e-c0494f798c37.png)

- [x] Сделал

### Рефакторинг проекта
![correction](https://cloud.githubusercontent.com/assets/13649199/13672935/ef09ec1e-e6e7-11e5-9f79-d1641c05cbe6.png) Рефакторинг проекта

#### Apply 1_0_rename.patch
- переименовал классы `UserMeal*` в более красивые `Meal*`
- преименовал `MealWithExceed` transfer object класс (что это такое пройдем позже)  в `MealTo` ([data transfer object naming convention](https://stackoverflow.com/questions/1724774/java-data-transfer-object-naming-convention))

- [x] Сделал. Патч не содержитал ардейт - смержил вручную из HW2
          
      public static boolean isBetweenInclusive(LocalTime lt, LocalTime startTime, LocalTime endTime) {
          return lt.compareTo(startTime) >= 0 && lt.compareTo(endTime) <= 0;
      }

## Разбор домашнего задания HW0
![hw](https://cloud.githubusercontent.com/assets/13649199/13672719/09593080-e6e7-11e5-81d1-5cb629c438ca.png) Разбор домашнего задания HW0:
- [x] Прошел

### Optional: реализация getFilteredMealsWithExcess через Stream API
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 1. <a href="https://drive.google.com/file/d/1hXU8VUKVxrayyQ6Xu7f3OGZWCSdK9Pyi">Optional: реализация getFilteredMealsWithExcess через Stream API</a>
#### Apply 1_1_HW0_streams.patch

- [Презентация Java 8](https://docs.google.com/presentation/d/1oltLkHK60FqIdsXjUdm4pPLSeC6KpNYjDsM0ips-qBw)

### Работа с git в IDEA. Реализация через цикл.
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 2. <a href="https://drive.google.com/open?id=1K0kan7TEUeOAe_qcdCtRF9rsqD-NwFZ7">Работа с git в IDEA. Реализация через цикл.</a>
**ВНИМАНИЕ! Патчей `1_2_HW0_cycles` и `1_3_HW0_optional2` не будет в проекте! Делаем в отдельной ветке (у меня `MealsUtil_opt`). Это варианты решений, которые не идут в `master`.**

#### Apply 1_2_HW0_cycles.patch

### Вопросы по HW0
![question](https://cloud.githubusercontent.com/assets/13649199/13672858/9cd58692-e6e7-11e5-905d-c295d2a456f1.png) Вопросы по HW0

> почему не использовать в `TimeUtil` методы `isBefore/isAfter` ?

это строгие (excluded) сравнения, а нам также нужны краевые значения

> В `MealsUtil` у нас где-то есть ключевое слово `final`, где-то нет. В чем разница?

Я участвовал в одном  проекте, где `final` был обязательным (в сеттингах IDEA галочка стояла). Но это скорее исключение, чем правило в проектах java (в Java 8 вообще ввели эффективный final, те по факту). Во всех новомодных языках переменные final по умолчанию, а в java нужно помнить и везде добавлять, утомительно. Но если приучитесь - хуже не будет. Я обычно ставлю там, где важно по смыслу (если не забываю).

    В Java 8 ввели понятие effectively final - это переменные, которые не имеют модификатора final , но могут использоваться в анонимных классах и лямбда-выражениях

### HW0 Optional 2: реализация в один проход и одной строкой Stream API
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 3. <a href="https://drive.google.com/open?id=1aq3hDmUUdWJujsX6zTqookJjXWOD3PBJ">HW0 Optional 2: реализация в один проход и одной строкой Stream API</a>
- [x] Прошел

#### Apply 1_3_HW0_optional2.patch
- [VK: Java программист: от новичка до профессионала](https://vk.com/javawebinar)
- Дополнительно:
  - [Первое занятие MasterJava: многопоточность](https://github.com/JavaOPs/masterjava)
  - [Обзор java.util.concurrent.*](https://habr.com/ru/company/luxoft/blog/157273/)

#### Аннотация видео

    0829

    Отложенные операция 
    Supplier

    Передаем лямбду, 
      при этом, 
        вычиления производятся 
          на основании переменных, находящихся 
          за пределами этой лямбды
    Это называется замыканием функции closure

    0926

    Можем внутри замыканий использовать 
    final переменные снаружи или effectively final в 8-ой, которые по факту не меняются

    0951

    Решение, совместимое с текущим
    Тоже связано с отложенными операциями

    MealTo можно не модифицировать

    1229

    Решение в один цикл с потоками

    1235

    Следующее решение Валерии

    1347

    Решение от Григория через синхронизатор

    CountDownLatch
    Синхронизация выполнения программы в зависимости от его состояния

    await ожидает, пока счетчик не станет равным нулю

    1424

    еще решение

    На основе предиката

    можем связывать предикаты в цепочки

## Занятие 1

### Обзор используемых в проекте технологий. Интеграция ПО
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 4. <a href="https://drive.google.com/open?id=0B9Ye2auQ_NsFRmo0YkVVaDJPTVE">Обзор используемых в проекте технологий. Интеграция ПО.</a>
- [x] Просмотрел видео

- [2020 Java Technology Report](https://www.jrebel.com/blog/2020-java-technology-report)
- <a href="http://zeroturnaround.com/rebellabs/java-tools-and-technologies-landscape-2016/">Обзор популярности инструментов и технологий Java за 2016 г.</a>
-  <a href="http://zeroturnaround.com/rebellabs/java-tools-and-technologies-landscape-for-2014/">Обзор популярности инструментов и технологий Java за 2014 г.</a>
-  <a href="http://www.youtube.com/watch?v=rJZHerwi8R0">Видео "Приложение Spring Pet Clinic"</a> 
-  Приложение <a href="https://github.com/spring-projects/spring-petclinic">Spring Pet Clinic</a>. 

### Обзор языка Java и его инфраструктуры
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 5. [Обзор языка Java и его инфраструктуры](https://www.youtube.com/watch?v=jWfqopZwcNs)
- [x] Просмотрел

- [Tiobe index](https://www.tiobe.com/tiobe-index/)
- [RebelLabs Developer Productivity Report 2017: Why do you use the Java tools you use](https://zeroturnaround.com/rebellabs/developer-productivity-report-2017-why-do-you-use-java-tools-you-use/)
- [The State of Java in 2018](https://www.baeldung.com/java-in-2018)
- [2018 JDK, Tools, Platform and Application, processes and you reports](https://snyk.io/blog/jvm-ecosystem-report-2018/)

### Maven
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 6. <a href="https://drive.google.com/open?id=0B9Ye2auQ_NsFSlZMTXBJRXJpakU">Maven.</a>
- [x] Просмотрел

- Среда сборки проектов <a href="http://www.apache-maven.ru/" target="_blank">Maven</a>.
- <a href="http://search.maven.org/#browse">The Central Repository</a>
- <a href="http://maven.apache.org/guides/mini/guide-multiple-modules.html">The Reactor</a>. Snapshots
- <a href="http://habrahabr.ru/blogs/java/106717/" target="_blank">Недостатки Maven</a>. Другие инструменты сборки.
- Справочник:
  - <a href="https://www.youtube.com/watch?v=21qdRgFsTy0">Видео: Maven vs Gradle vs SBT (Архипов, Борисов, Садогурский)</a>
  - <a href="http://habrahabr.ru/post/77333/">Автоматизация сборки проекта</a>
  - <a href="http://maven.apache.org/">Home Page</a>
  - <a href="http://books.sonatype.com/mvnref-book/reference/index.html">Maven: The Complete Reference</a>
  - <a href="http://study-and-dev.com/blog/build_management_maven_1/">Разработка ПО вместе с maven</a>
  - <a href="http://maven.apache.org/guides/introduction/introduction-to-the-lifecycle.html">Build Lifecycle</a>
  - <a href="http://maven.apache.org/guides/introduction/introduction-to-dependency-mechanism.html">Dependency Mechanism</a>
  - <a href="http://habrahabr.ru/post/111408/">Создание своих архетипов и каталогов в Maven</a>
  - <a href="http://www.ibm.com/developerworks/ru/library/j-5things13/">Зависимости, профили</a>
  - <a href="http://blog.bintray.com/2014/02/11/bintray-as-pain-free-gateway-to-maven-central/">Bintray: gateway to Maven Central</a>

### WAR. Веб-контейнер Tomcat. Сервлеты
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 7. <a href="https://drive.google.com/open?id=0B9Ye2auQ_NsFT3pWNkMzWVVybnc">WAR. Веб-контейнер Tomcat. Сервлеты.</a>

##### Аннотация видео

    1407

    Добавляем 1_5_add_servlet_api.patch

    IDEA 
    Ctrl D - чекин проверить merge

    Alt L R можем переходить по файлам

    2343

    Maven

    install - для многомодульных проектов, котоые зависят д от д

    у нас одномодульный проект

    2522

    Деплой WAR в Tomcat через /manager

    3152

    Настройка дебага 8000

    %CATALINA_HOME%\bin\catalina.bat jpda start

    Tomcat Remote Debug

    4045

    Включение автообновление ресурсов

    IDEA 

    передеплой при изменеии класса
    добавляем редирект
    Ctrl Shift F9

    JVM в режиме дебага может автоматом подхватывать

    если структурные изменения
      добавили метод
        или поменяли параметр в методе, то не подхватит

        JRocket подхватывает, но она платная

    response.sendRedirect("users.jsp");
      запрос при редиректе проходит через браузер

    http://www.skipy.ru/philosophy/beginning.html

> - Обновил зависимость до Servlet 4.0. Установите себе [Tomcat 9.x](https://tomcat.apache.org/download-90.cgi)
> - Устанавливать Tomcat лучше простым скачиванием архива `xxx.zip` и копированием из него в **каталог без пробелов и русских букв** (пример `С:\java\apache-tomcat-9.0.30`)

**ВНИМАНИЕ! далее патчи идут после `1_1_HW0_streams` в ветку `master`**

#### Apply 1_4_switch_to_war.patch
> - Обновил сервлеты до версии 4.0 (Tomcat 9 использует это API, хотя для нас не принципиально, т.к. мы никакие <a href="https://ru.wikipedia.org/wiki/Сервлет_(Java)">фичи 3.x и 4.x Servlet API</a> не используем)
> - Переименовал `userList.jsp` в `users.jsp`
> - Сервлет добавляется в следующем патче, те **в `web.xml` он будет подчеркиваться красным.**

#### Apply 1_5_add_servlet_api.patch

> - Если зависимость `servlet-api` не подтянулась, сделай `Reimport All Maven Projects` (см. [Обновить зависимости в maven проекте](https://github.com/JavaOPs/topjava/wiki/IDEA#Обновить-зависимости-в-maven-проекте)).
**Все зависимости в Maven прект подтягиваются ТОЛЬКО через Maven**. 
> - [Проверка, кто занял порт](https://stackoverflow.com/a/38953356/548473) (в случае проблем с запуском и дебагом на портах 8080, 8000)</a>
> - [**Деплой war в Tomcat с Application context**](https://github.com/JavaOPs/topjava/wiki/IDEA#Деплой-war-в-tomcat-application-context-должен-быть-тот-же-что-и-url-приложения-деплоить-надо-war-exploded)
> - [**Динамическое обновление без передеплоя**](https://github.com/JavaOPs/topjava/wiki/IDEA#Для-динамической-перегрузки-ресурсов-кнопка-нажмите-кнопку-update-resource-on-frame-deactivation)

#### Apply 1_6_forward_to_redirect.patch

- [ ] <a href="http://tomcat.apache.org/">Tomcat Home Page</a>
- [x] <a href="http://java-course.ru/student/book1/servlet/">Сервлеты</a>
- <a href="https://devcolibri.com/как-создать-servlet-полное-руководство/">Руководство: как создать servlet</a>
- Томкат менеджер: [http://localhost:8080/manager](http://localhost:8080/manager)
  - в `TOMCAT_HOME\conf\tomcat-users.xml` нужно добавить 
```
<user username="tomcat" password="tomcat" roles="tomcat,manager-gui,admin-gui"/>
```
- Если проблема с Tomcat debug и работает Dr.Web- нужно его отключить, либо добавить в исключения путь к  `.IntelliJIdea2019.3/`
- Наше приложение: [http://localhost:8080/topjava](http://localhost:8080/topjava)
- Наш сервлет:     [http://localhost:8080/topjava/users](http://localhost:8080/topjava/users)
- [Настройки Remote Debug в новой IDEA](https://github.com/JavaOPs/topjava/wiki/IDEA#remote-debug-в-новой-idea)
- Справочник:
  - [HTTP](https://developer.mozilla.org/ru/docs/Web/HTTP)
  - <a href="http://info.javarush.ru/idea_help/2014/01/22/Руководство-пользователя-IntelliJ-IDEA-Отладчик-.html">Отладчик IntelliJ IDEA</a>
  - <a href="https://www.youtube.com/watch?v=tN8K1y-HSws&list=PLkKunJj_bZefB1_hhS68092rbF4HFtKjW&index=14">Yakov Fain: Intro to Java EE. Glassfish. Servlets (по-русски)</a>
  - <a href="https://www.youtube.com/watch?v=Vumy_fbo-Qs&list=PLkKunJj_bZefB1_hhS68092rbF4HFtKjW&index=15">Yakov Fain: HTTP Sessions, Cookies, WAR deployments, JSP (по-русски)</a>
  - <a href="https://www.youtube.com/playlist?list=PLoij6udfBncjHaO5s7Ln4w4BLj5FVc49P">Golovach Courses: Junior.February2014.Servlets</a>
  - <a href="http://blog.trifork.com/2014/07/14/how-to-remotely-debug-application-running-on-tomcat-from-within-intellij-idea">Remotely debug on tomcat from IDEA</a>
  - <a href="http://java-online.ru/jsp.xhtml">Java Server Page</a>
  - <a href="http://stackoverflow.com/questions/1890438/how-to-get-parameters-from-the-url-with-jsp#1890462">Java объекты, доступные в JSP</a>

### Логирование
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 8. <a href="https://drive.google.com/open?id=0B9Ye2auQ_NsFaTdYUnpLNFFUeXM">Логирование.</a>

#### Аннотация видео

    Meven

    scope

    compile
    кладем в пакет

    provided
    не тянем в пакет

    log4j
      нужен адаптер для slf4j, т.к. не реализует

    slf4j
      интерфейс
        jul
        logback
          современные фреймворки

    jmx
      удаленно можем менять уровень логирования
        без выключения JVM

#### Apply 1_7_logging.patch
 
> **Установите переменную окружения на TOPJAVA_ROOT на корень проекта и перезапустите IDEA. Слеши в пути должны быть в стиле unix (/)**
- [Set environment for Win/Mac/Unix](https://www.xenovation.com/blog/development/java/how-to-set-java-home)
- [Set environment for UNIX](https://askubuntu.com/a/849954)
- Или простой вариант (не забудте добавить в Run и Debug)![image](https://user-images.githubusercontent.com/13649199/76862707-8af21180-686f-11ea-9f8c-2bb30ef4c3b2.png)

> - изменения в проекте: убрал `LoggerWrapper` и логирую напрямую в логгер SLF4J. При логгировании через вспомогательный класс, в логе теряется имя исходного класса.
> - удалил зависимость `jul-to-slf4j`. Она нам не нужна и, согласно <a href="https://www.youtube.com/watch?v=qzqAUUgB3v8">видео Владимира Красильщика про логирование</a>, она замедляет работу
> - удалил зависимость `jcl-over-slf4j`. Используем Spring 5, который напрямую использует `slf4j` без `common-logging`. Про миграцию на Spring 5 будет видео в следующих занятиях.
> - Не делать конкатенацию строк при логгировании сообщений, если уровень логирования в конфигурации выставлен выше уровня логирования в коде
>   - [slf4j formatting with {}](http://stackoverflow.com/a/10596390/548473)
>   - [What is the fastest way of (not) logging](https://www.slf4j.org/faq.html#logging_performance)

- [x] <a href="http://habrahabr.ru/post/113145/">Java Logging: история кошмара</a>
- [x] <a href="http://skipy.ru/useful/logging.html">Ведение лога приложения</a>

      java.util.logging появился в JavaSE в версии 1.4, в 2001 году

      https://logging.apache.org/log4j/2.x/

      Apache Commons Logging
        Самое неприятное – при некоторых условиях4 у этого фреймворка есть проблемы с загрузчиком классов
        https://www.examclouds.com/ru/java/java-core-russian/classpath-russian

      SLF4J - Simple Logging Facade for Java

- <a href="http://logging.apache.org/log4j/2.x/index.html">Log4j</a>, <a href="http://logback.qos.ch/">Logback</a>
- <a href="http://www.slf4j.org/legacy.html">Добавление зависимостей логирования</a> в проект.
- <a href="http://logback.qos.ch/manual/configuration.html#variableSubstitution">Logback variable substitution</a>

#### Проверочные вопросы:
- Что нужно изменить в `pom.xml`, чтобы перейти с logback на log4j ?

### Ваши вопросы
![question](https://cloud.githubusercontent.com/assets/13649199/13672858/9cd58692-e6e7-11e5-905d-c295d2a456f1.png) Ваши вопросы

> Почему `private static final Logger log` а не `LOG` ?

Это [правило именования констант, которые не "deeply immutable"](https://google.github.io/styleguide/javaguide.html#s5.2.4-constant-names), те если их содержимое можно изменить.

>  Используются ли еще где-то в реальной разработке JSP, или это уже устаревшая технология? Заменит ли ее JSF (https://javatalks.ru/topics/38037)?

JSF и JSP- разные ниши и задачи.
JSP- шаблонизатор, JSF - МVС фреймворк. Из моего опыта- с JSP сталкивался в 60% проектов. Его прямая замена: http://www.thymeleaf.org (в Spring-Boot по умолчанию), но в уже запущенных проектах встречается достаточно редко. JSP не умирает, потому что просто и дешево. Кроме того включается в большинство веб-контейнеров (в Tomcat его реализация Jasper)

JSF- sun-овский еще фреймворк, с которым я ни разу не сталкивался и особого желания нет. Вот он как раз, по моему мнению, активно замещается хотя бы javascript фреймворками (angular, react, vue).

> А зачем мы использовали logback? Почему SLF4J нас не устроило? Почему реализация логирования не log4j?

`SLF4J-API` это API. Там есть только пустая реализация `org.slf4j.helpers.NOPLogger` (можно посмотреть в исходниках). Logback для новых проектов стал стандарт. *spring-petclinic* и *spring-boot* используют его по умолчанию.
- http://logback.qos.ch/reasonsToSwitch.html

---------

## Домашнее задание HW01
![hw](https://cloud.githubusercontent.com/assets/13649199/13672719/09593080-e6e7-11e5-81d1-5cb629c438ca.png) Домашнее задание HW01 (делаем ветку HW01 от последнего патча в master) 

> **ОСНОВНОЕ, чему мы учимся на проекте: мыслить и работать как Java разработчики уже сейчас**, потом это будет гораздо сложнее и стоить дороже.
Вот на мой взгляд [хорошие советы новичкам](http://blog.csssr.ru/2016/09/19/how-to-be-a-beginner-developer). От себя я добавлю:
> - Учись грамотно формулировать проблему. Проблема "у меня не работает" может иметь тысячи причин. В процессе формулирования очень часто приходит ее решение. 
>    - что я делаю (подробно, чтобы понял человек, который не копался в этом совсем)
>    - что получаю (обычно верх самого последнего эксепшена)
>    - мои попытки решения проблемы

> - Учись исследовать проблему. Внимательное чтение логов и [умение дебажить](http://info.javarush.ru/idea_help/2014/01/22/Руководство-пользователя-IntelliJ-IDEA-Отладчик-.html) - основные навыки разработчика. Обычно самый верх самого нижнего эксепшена- причина ошибки, туда нужно ставить брекпойнт.
> - Грамотно уделяй время каждой проблеме. Две крайности - сразу бросаться за помощью и биться над ней часами. Пробуй решить ее сам и в зависимости от проблемы выделяй на это разумное время.

#### 1. Реализовать сервлет с отображением в таблице списка еды (в памяти и БЕЗ учета пользователя)

> Деплоиться в Tomcat лучше как `war exploded`: нет упаковки в war и при нажатой кнопке `Update Resources on Frame Deactivation` можно обновляться css, html, jsp без передеплоя. При изменении `web.xml`, добавлении методов, классов необходим redeploy.

- 1.1 По аналогии с `UserServlet` добавить `MealServlet` и `meals.jsp`
  - Задеплоить приложение (war) в Tomcat c `applicationContext=topjava` (приложение должно быть доступно по <a href="http://localhost:8080/topjava">http://localhost:8080/topjava</a>)
  - Попробовать разные деплои в Tomcat, remote и local debug
- 1.2 Сделать отображения списка еды в JSP, цвет записи в таблице зависит от параметра `excess` (красный/зеленый).
  - 1.2.1 Список еды захардкодить (те проинициализировать в коде, желательно чтобы в проекте инициализация была только в одном месте)
  - 1.2.2 Время выводить без 'T'
  - 1.2.3 Список выводим БЕЗ фильтрации по `startTime/endTime`
  - 1.2.4 С обработкой исключений пока можно не заморачиваться, мы будем красиво обрабатывать в конце стажировки
  - 1.2.5 Вариант реализации:
    - из сервлета преобразуете еду в `List<MealTo>`;
    - кладете список в запрос (`request.setAttribute`);
    - делаете `forward` на jsp для отрисовки таблицы (при `redirect` атрибуты теряются).
    - в `JSP` для цикла можно использовать `JSTL tag forEach`. Для подключения `JSTL` в `pom.xml` и шапку JSP нужно добавить:
```
    <dependency>
       <groupId>javax.servlet</groupId>
       <artifactId>jstl</artifactId>
       <version>1.2</version>
    </dependency>

    <%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
    ...
```

  - [x] <a href="http://java-course.ru/student/book1/servlet/">Интернет-приложения на JAVA</a>
  - [x] <a href="http://java-course.ru/student/book1/jsp/">JSP</a>

        http://java-online.ru/servlet-context.xhtml
        ServletContext

        https://dev64.wordpress.com/2012/03/23/simple-servlet-using-maven/

        java-my-experiments

        http://java-online.ru/servlet-context.xhtml
          По сути JSP при первом обращении преобразуется в сервлет и работает уже как сервлет. Это очень важно понять. 
          
          JSP НЕ ЯВЛЯЕТСЯ страницей наподобие HTML-страницы — начинающему програмисту важно четко осознавать, 
          что это еще один сервлет — просто его вывод не надо программировать

          JSP имеет в своем составе несколько предопределенных объектов. 
          Т.е. их надо воспринимать, как уже готовые объекты, которые могут быть использованы. 
          Это request, response, out, session, application, config, pageContext и page.

        https://www.examclouds.com/java/java-core-russian/potoki-dannih
        Потоки

        https://ru.wikipedia.org/wiki/HTTP

        https://metanit.com/java/javaee/4.4.php

        https://proselyte.net/tutorials/servlets/
          Закончил весь туториал

          Попутно
            volatile java
              https://www.ibm.com/developerworks/ru/library/j-5things15/index.html

              https://proselyte.net/tutorials/spring-tutorial-full-version/introduction/

              https://vertex-academy.com/tutorials/ru/bloki-inicializacii-v-java-chast-1/

              https://javarush.ru/groups/posts/1946-neizmennoe-v-java-final-konstantih-i-immutable

              https://ru.bmstu.wiki/Java_Persistence_API

              Транзакция (информатика)
              https://ru.m.wikipedia.org/wiki/%D0%A2%D1%80%D0%B0%D0%BD%D0%B7%D0%B0%D0%BA%D1%86%D0%B8%D1%8F_(%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%82%D0%B8%D0%BA%D0%B0)
                Свойства транзакций
                  https://ru.m.wikipedia.org/wiki/ACID

              https://javarush.ru/groups/posts/857-peredacha-parametrov-v-java

              http://www.c-cpp.ru/books/operatory-ukazaniya-i
                Указатель - это адрес переменной в памяти
                
                Переменные, содержащие адреса или указатели, должны объявляться путем помещения *

                Оператор & можно запомнить как «взятие адреса»
                m = &count;

                Операция * может быть запомнена как «по адресу»
                q = *m;

                Разыменование указателя - получение данных, на которые он ссылается

              http://ermak.cs.nstu.ru/cprog/html/052.htm
                терминология  
                  ссылка (адрес памяти, указатель), 
                  значение 
                касается фундаментальных свойств переменных в языках программирования. 
                Имя переменной 
                  в различных контекстах может восприниматься как ее 
                    значение (содержимое памяти), так и 
                    ссылка на нее (адрес памяти, указатель)(см. 1.3). 
                    Например, при присваивании левая часть рассматривается как ссылка, а правая – как значение (см. 1.4);
              
              http://ermak.cs.nstu.ru/cprog/html/013.htm
                Имеется дуализм (двойственность) в использовании имени переменной (кстати, во всех языках программирования): в одних случаях имя обозначает хранимое значение, а в других – память, его хранящее (адрес, ссылка, место размещения). Наиболее яркий пример – присваивание. Выражение a=b в правой части подразумевает значение переменной b, а в левой части – ссылку на a. В программировании на Си/Си++ имеется большая свобода выбора при передаче переменных в процессе их обработки между модулями программы как по ссылке, так и по значению, поэтому понимание двойственности, заложенной в имени переменной, здесь крайне важно.

              Java передает параметры по значению. Всегда.

              https://ppt-online.org/96735

              Указатель (тип данных)
              https://ru.wikipedia.org/wiki/%D0%A3%D0%BA%D0%B0%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D1%8C_(%D1%82%D0%B8%D0%BF_%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85)
              Указатель (англ. pointer) — 
                переменная, диапазон значений которой состоит из адресов ячеек памяти или специального значения — нулевого адреса.

              Ссылка (программирование)
              https://ru.wikipedia.org/wiki/%D0%A1%D1%81%D1%8B%D0%BB%D0%BA%D0%B0_(%D0%BF%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5)
              Ссылка в программировании — 
                это объект, указывающий на определенные данные, но не хранящий их. Получение объекта по ссылке называется разыменованием
              Ссылка не является указателем, а просто является другим именем для объекта. 

              Java и C# - В этих языках понятие указателя отсутствует, 
              а вместо него используется понятие ссылки. 
                Разыменование ссылок и 
                взятие адресов объектов для присваивания их ссылкам 
                не требует специального оператора.

              Ссылки в Java — указатели на объекты. 
              Другими словами, ссылка — 
                это переменная, 
                  содержащая адрес ячейки памяти, 
                    в которой хранится объект. 
                Подробнее: http://cyclowiki.org/wiki/%D0%A1%D1%81%D1%8B%D0%BB%D0%BA%D0%B0_(Java)

                Как я понял:
                Указатель - переменная, хранящая адрес памяти

              https://proft.me/2014/06/7/kak-java-hranit-dannye-v-pamyati/
              https://topjava.ru/blog/stack-and-heap-in-java

              Stack
                Используется только потоками
                Освобождается автоматически, без GC, по мере выполнения методов
                Потокобезопасная,
                  для каждого Потока - свой стек
                StackOverFlowError
                Хранит ссылки на объекты, массивы в Heap
                Хранит значения локальных переменных методов примитивных типов 
                  (Escape-анализ с 6 версии - объекты не покидающие метода тоже на стеке
                  https://habr.com/ru/company/jugru/blog/322348/)
                Быстрее только регистры процессора, LIFO
                Память меньше Heap
              
              Heap
                Используется всеми частями программы
                GC
                PermGen/MetaSpace
                String Pool
                OutOfMemoryError
                Хранит объекты, массивы
                  https://ru.stackoverflow.com/questions/980439/%D0%92-%D0%BA%D0%B0%D0%BA%D0%BE%D0%B9-%D0%BE%D0%B1%D0%BB%D0%B0%D1%81%D1%82%D0%B8-%D0%BF%D0%B0%D0%BC%D1%8F%D1%82%D0%B8-%D1%85%D1%80%D0%B0%D0%BD%D1%8F%D1%82%D1%81%D1%8F-%D0%BF%D0%B5%D1%80%D0%B5%D0%BC%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B2-java
                    Хранит поля
                Сильно медленнее Stack

                PermGen
                  Метаданные загруженных классов
                  Вся статика
                  String Pool
                    интернирование
                  
              https://habr.com/ru/post/456318/

              http://www.mstu.edu.ru/study/materials/java/02.htm

              https://foxford.ru/wiki/informatika/ssylochnyy-tip-v-java

              https://ppt-online.org/552671

              http://www.quizful.net/interview/java/java-local-variables

              https://ravesli.com/urok-88-ssylki/
                & - «ссылка на»

              https://ravesli.com/urok-80-ukazateli-vvedenie/#toc-0
                & - Оператор адреса ()

              https://ravesli.com/urok-98-peredacha-argumentov-po-ssylke/

                int value = 7; // обычная переменная
                int &ref = value; // ссылка на переменную value

                int value = 7;
                int *ptr = &value;

              http://cyclowiki.org/wiki/%D0%A1%D1%81%D1%8B%D0%BB%D0%BA%D0%B0_(Java)

  - [x] [Как создать Servlet? Полное руководство](https://devcolibri.com/как-создать-servlet-полное-руководство)
  - [x] [JSTL для написания JSP страниц](https://devcolibri.com/jstl-для-написания-jsp-страниц/)
***
HEAD
***
  - [ ] <a href="http://javatutor.net/articles/jstl-patterns-for-developing-web-application-1">JSTL: Шаблоны для разработки веб-приложений в java</a>

        <c:out value="${12+56*2}" />
        Есть список предопределенных контекстов:
          Контекст	Комментарий
          pageScope	Контекст страницы (т.е. переменные объявленные на этой странице и доступные только для этой страницы).
          requestScope	Доступ к таким переменным имеют все страницы, сервлеты обслуживающие один, текущий, вот этот самый, запрос пользователя.
          sessionScope	Доступ к переменным сохраняется на протяжении всего сеанса пользователя (пока не закроет браузер или не истечет предельное время бездействия).
          applicationScope	Доступ к переменным сохраняется изо всех страниц размещенных внутри веб-приложения (самый глобальный контекст).
          param	В этом контексте находятся все переменные, полученные страницей от пользователя либо как параметры адресной строки, либо как поля html-формы.
          paramValues	Список значений тех переменных, которые были переданы в страницу пользователем, правда, формат отличен от предыдущего случая. Если там param фактически имел тип HashMap<String, String>, то здесь HashMap<String, String [] >.
          header	В этом объекте хранится информация об http-заголовках которые были переданы от браузера клиента вашему веб-серверу.
          headerValues	Список значений http-заголовков.
          initParam	Конфигурационные параметры, указанные для вашей страницы, сервлета в файле web.xml
          cookie	Список переменных помещенных внутрь cookie.
          pageContext	Ссылка на объект pageContext (см. описание служебных объектов автоматически создаваемых внутри jsp-страницы).

        <c:out value="${param.fio}" />
        <c:out value="${param['fio']}" />

        <c:out value="${param.fio}" default="NO DATA" escapeXml="true" />

        <c:set var="vasyano" scope="session" value="Вася Тапкин" />
  
        set
          <c:set var="petyano" scope="page">
            Петька Козлов на странице
          </c:set>

          <c:set var="petyano" scope="request">
            Петька Козлов в запросе
          </c:set>

          <c:set var="petyano" scope="session">
            Петька Козлов в сессии
          </c:set>

          <c:set var="petyano" scope="application">
            Петька Козлов в приложении
          </c:set>

        out
          vasyano: <c:out value="${sessionScope.vasyano}" />
          
          <br />
          
          petyano: <c:out value="${petyano}" />
            ищем переменную внутри pageScope, если не найдено внутри 
            requestScope, если опять не найдено внутри 
            sessionScope и, наконец, внутри 
            applicationScope
          
        DSL

        



  - <a href="http://stackoverflow.com/questions/35606551/jstl-localdatetime-format">JSTL LocalDateTime format</a>

### Optional
#### 2. Реализуем в ПАМЯТИ CRUD (create/read/update/delete) для еды
**Пример: <a href="http://danielniko.com/2012/04/17/simple-crud-using-jsp-servlet-and-mysql/">Simple CRUD using Servlet/JSP</a>**
https://web.archive.org/web/20190718152346/http://danielniko.com/2012/04/17/simple-crud-using-jsp-servlet-and-mysql/
> - Пример нужно САМОСТОЯТЕЛЬНО переделать: вместо хранения в MySql нужно хранить в ПАМЯТИ (задание упрощается).
> - Классы: сервлет, инрерфейс хранения, его реализация для хранения в памяти
- 2.1 Хранение в памяти будет одна из наших CRUD реализаций (позже будет JDBC, JPA и DATA-JPA).
- 2.2 Работать с реализацией CRUD через интерфейс, который не должен ничего знать о деталях реализации (Map, DB или что-то еще).
- 2.3 Добавить поле `id` в `Meal/ MealTo` и реализовать генерацию счетчика, УЧЕСТЬ МНОГОПОТОЧНОСТЬ СЕРВЛЕТОВ
    - [обзор java.util.concurrent](https://habrahabr.ru/company/luxoft/blog/157273/)
- 2.4 Сделать форму редактирования в JSP: AJAX/JavaScript использовать НЕ надо, делаем через `<form method="post">` и `doPost()` в сервлете.
- 2.5 Для ввода дат и времени можно использовать <a href="https://webref.ru/html/input/type">html5 типы</a>, хотя они поддерживаются не всеми браузерами (<a href="https://robertnyman.com/html5/forms/input-types.html">протестировать свой браузер</a>). В конце курса мы добавим <a href="http://xdsoft.net/jqplugins/datetimepicker/">DateTimePicker jQuery plugin</a>, который будет работать на всех браузерах.

## После выполнения ДЗ обязательно <a href="lesson01.md#-Типичные-ошибки">проверьте решение на ошибки</a>

### Вопросы по HW1
![question](https://cloud.githubusercontent.com/assets/13649199/13672858/9cd58692-e6e7-11e5-905d-c295d2a456f1.png) Вопросы по HW1

> Не попадаю на страничку/брекпойнт в сервлете.

- внимательно проверь url и applicationContext (Application Context должен быть тот же, что и url приложения: <a href="https://github.com/JavaOPs/topjava/wiki/IDEA#%D0%94%D0%B5%D0%BF%D0%BB%D0%BE%D0%B9-war-%D0%B2-tomcat-application-context-%D0%B4%D0%BE%D0%BB%D0%B6%D0%B5%D0%BD-%D0%B1%D1%8B%D1%82%D1%8C-%D1%82%D0%BE%D1%82-%D0%B6%D0%B5-%D1%87%D1%82%D0%BE-%D0%B8-url-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%B5%D0%BF%D0%BB%D0%BE%D0%B8%D1%82%D1%8C-%D0%BD%D0%B0%D0%B4%D0%BE-war-exploded">wiki IDEA</a>)
- посмотрите в task manager: возможно запущено несколько JVM и они мешают друг другу. Лишние java приложения убить.

> Приложение не видит TOPJAVA_ROOT.

**После выставления переменной окружения IDEA нужно рестартовать. Слеши в пути должны быть в стиле unix (/)**. Проверить, видит ли java переменную окружения можно так: `System.getenv("TOPJAVA_ROOT")`. Еще вариант: добавить `-DTOPJAVA_ROOT=...` в опции запуска приложения, тогда она доступна из java как `System.getProperty("TOPJAVA_ROOT")`.

> Проблемы с кодировкой в POST (кракозябры). 

Возможное решение - выставьте кодировку ДО первого чтения из request:
```
protected void doPost(HttpServletRequest request, ...) {
    request.setCharacterEncoding("UTF-8");
```

> Если сервлет тыкают несколько пользователей / несколько браузеров, какого должно быть поведение? Нужно ли что-то делать с сессиями?

В Optional нужно делать реализацию хранения  многопоточной. Cессии пока не используем  (начнутся, когда будет прикручивать авторизацию).

> Для чего нам нужна многопоточная реализация коллекции, если каждый пользователь видит только себя?

Реализация хранения в памяти у нас одна на всех. Те коллекция шарится между пользователями, а они в разных потоках ее дергают. Если несколько потоков одновременно будут изменять коллекцию без учета многопоточности (например один будет удалять, второй вставлять), мы получим `ConcurrentModificationException`

> Предпочтительнее ли создавать новый объект `Meal` при каждом update?

Если при обновлении не создавать копию, то сохраненный в памяти объект может кто-то попортить. Вопрос скорее доверия к коду- если проект большой и людей над ним трудится много, то вероятнее нужно копировать.

> Почему теряются атрибуты при передаче на сервлет: `http://localhost:8080/topjava/meals?action=add&...` и `req.getAttribute("action")` = null ?

См. <a href="http://stackoverflow.com/questions/5243754/difference-between-getattribute-and-getparameter">Difference between getAttribute() and getParameter()</a>. Отсюда также следует, что при редиректе атрибуты теряются.

> Зачем нужен в jsp `<jsp:useBean id=".." scope="request" type=".."/>` ?

<a href="http://www.java2ee.ru/jsp/useBean.html">jsp:useBean</a> нужен IDEA для автодополнений - она понимает тип переменной, которая уже доступна в JSP (например через setAttribute). И еще эта переменная становится доступной в java вставках. Для вывода в JSP это тэг не обязателен. Если тип переменной JSP не совпадает с тем, что в `jsp:useBean`, будет ошибка.

----------------------------
### Типичные ошибки
![error](https://cloud.githubusercontent.com/assets/13649199/13672935/ef09ec1e-e6e7-11e5-9f79-d1641c05cbe6.png) Типичные ошибки
- 1 **Если в названии класса есть `Meal`, не нужно использовать слово meal в методах класса.**
- 2 Привыкайте писать комментарии к чекину: одной фразой что вы сделали в нем. Например: *Meals CRUD implementation*. См.
[Как писать сообщения коммитов](https://habr.com/ru/post/416887/)
- 3 Хранение в памяти и операции с ней должны выполняться просто и эффективно
- 4 Хранить нужно `Meal` и конвертировать ее в `MealTo` когда отдаем список на отображение в JSP. Иначе при редактировании любой записи или изменении юзером своей нормы `caloriesPerDay` нужно будет пересчитывать все записи юзера.
- 5 Стили `color` можно применять ко всей строке таблицы `tr`, а не каждой ячейке.
- 6 `DateTimeFormatter` можно сделать один заранее (он потокобезопасный в отличие от `SimpleDateFormatter`), а не создавать новый при каждом запросе.
- 7 Работать с CRUD надо через интерфейс. 
- 8 Реализаций хранения будет несколько, нужно учитывать это в названии класса имплементации работы в памяти.
- 9 В `web.xml` принято группировать сервлет со своим маппингом
- 10 Не размещайте никакую логику (форматирование, счетчики) в бинах, где хранятся только данные (`Meal, MealTo`)
- 11 Еще раз: детали реализации в памяти не должны быть никому видны. Те НЕ НАДО счетчик размещать в `Meal` или `MealServlet` или `MealsUtil`, в базе же он будет по другому генерится. 
- 12 `volatile` при ++ не помогает от многопоточности. Почему? 
- 13 Обратите также внимание на то, чтобы реализация вашей коллекции для хранения еды была также многопоточной.
- 14 Не делайте дублирование кода `MealsUtil`. Возможно вам пригодятся константы `LocalTime.MIN` и `LocalTime.MAX`
- 15 Не дублируйте строки в `jsp`. Посмотрите на <a href="https://steveswinsburg.wordpress.com/2008/09/04/the-ternary-operator-and-jsp/">тернарный оператор</a>.
- 16 После операции `delete` в браузере должен быть url `http:\\localhost:8080\topjava\meals`
- 17 Перед чекином проверяйте свой ченджлист (`Ctrl+D` на файле из `Local Changes` - посмотреть что поменялось). Если там только пробелы/переводы строк, не надо его комитить - делайте файлу `Git->revert`.
- 18 Учтите в названии реализации CRUD, что
  - 18.1 у нас будет несколько реализаций (не только в памяти)
  - 18.2 у нас будет 2 CRUD (для еды и пользователей). А в реальном проекте их намного больше.
- 19 Сессии НЕ использовать! При редиректе все атрибуты (`req.getAttribute()`) теряются (см. вопрос выше). Сценарий редиректа:
  - 1 из сервлета делаем редирект (снова на сервлет, не на JSP!)
  - 2 снова заходим в сервлет
  - 3 кладем нужные атрибуты и делаем forward на jsp
  - 4 если очень хочется передать параметры из 1. в 2. можно сделать их через параметры запроса (например `meals?id=5`) и доставать через `reg.getParameter(id)`. В моей реализации такого не потребовалось.


