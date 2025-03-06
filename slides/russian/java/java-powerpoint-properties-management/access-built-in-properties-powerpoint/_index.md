---
title: Доступ к встроенным свойствам в PowerPoint
linktitle: Доступ к встроенным свойствам в PowerPoint
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как получить доступ к встроенным свойствам PowerPoint с помощью Aspose.Slides для Java. В этом руководстве вы узнаете, как узнать автора, дату создания и многое другое.
weight: 10
url: /ru/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Доступ к встроенным свойствам в PowerPoint

## Введение
В этом уроке мы рассмотрим, как получить доступ к встроенным свойствам презентаций PowerPoint с помощью Aspose.Slides для Java. Aspose.Slides — это мощная библиотека, которая позволяет разработчикам Java программно работать с презентациями PowerPoint, легко выполняя такие задачи, как чтение и изменение свойств.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
1.  Java Development Kit (JDK): убедитесь, что в вашей системе установлен JDK. Вы можете скачать его с[здесь](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides для Java: Загрузите и установите Aspose.Slides для Java с сайта[эта ссылка](https://releases.aspose.com/slides/java/).

## Импортировать пакеты
Сначала вам необходимо импортировать необходимые пакеты в ваш Java-проект. Добавьте следующий оператор импорта в начало вашего Java-файла:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## Шаг 1. Настройте объект презентации
Начните с настройки объекта Presentation, который будет представлять презентацию PowerPoint, с которой вы хотите работать. Вот как вы можете это сделать:
```java
// Путь к каталогу, содержащему файл презентации.
String dataDir = "path_to_your_presentation_directory/";
// Создайте экземпляр класса Presentation
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## Шаг 2. Доступ к свойствам документа
После настройки объекта «Презентация» вы можете получить доступ к встроенным свойствам презентации с помощью интерфейса IDocumentProperties. Вот как вы можете получить различные свойства:
### Категория
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### Текущее состояние
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### Дата создания
```java
System.out.println("Creation Date : " + documentProperties.getCreatedTime());
```
### Автор
```java
System.out.println("Author : " + documentProperties.getAuthor());
```
### Описание
```java
System.out.println("Description : " + documentProperties.getComments());
```
### Ключевые слова
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### Последнее изменение кем
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### Руководитель
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### Дата изменения
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### Формат презентации
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### Дата последней печати
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### Совместно между продюсерами
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### Предмет
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### Заголовок
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## Заключение
В этом уроке мы узнали, как получить доступ к встроенным свойствам презентаций PowerPoint с помощью Aspose.Slides для Java. Выполнив описанные выше шаги, вы можете легко программно получить различные свойства, такие как автор, дата создания и название.
## Часто задаваемые вопросы
### Могу ли я изменить эти встроенные свойства с помощью Aspose.Slides для Java?
Да, вы можете изменить эти свойства с помощью Aspose.Slides. Просто используйте соответствующие методы установки, предоставляемые интерфейсом IDocumentProperties.
### Совместим ли Aspose.Slides с различными версиями PowerPoint?
Aspose.Slides поддерживает широкий спектр версий PowerPoint, обеспечивая совместимость с различными платформами.
### Могу ли я также получить пользовательские свойства?
Да, помимо встроенных свойств, вы также можете получать и изменять пользовательские свойства с помощью Aspose.Slides для Java.
### Предлагает ли Aspose.Slides документацию и поддержку?
 Да, вы можете найти подробную документацию и получить доступ к форумам поддержки на[Веб-сайт Aspose](https://reference.aspose.com/slides/java/).
### Доступна ли пробная версия Aspose.Slides для Java?
 Да, вы можете скачать бесплатную пробную версию с сайта[здесь](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
