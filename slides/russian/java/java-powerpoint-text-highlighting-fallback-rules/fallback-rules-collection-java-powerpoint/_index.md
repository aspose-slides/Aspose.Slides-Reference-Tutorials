---
"description": "Узнайте, как управлять правилами резервного копирования шрифтов в презентациях PowerPoint с помощью Aspose.Slides для Java. Улучшайте совместимость между устройствами без усилий."
"linktitle": "Коллекция правил отката в Java PowerPoint"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Коллекция правил отката в Java PowerPoint"
"url": "/ru/java/java-powerpoint-text-highlighting-fallback-rules/fallback-rules-collection-java-powerpoint/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Коллекция правил отката в Java PowerPoint

## Введение
В этом уроке мы углубимся в то, как управлять правилами резервного копирования шрифтов с помощью Aspose.Slides для Java. Резервные шрифты имеют решающее значение для обеспечения корректного отображения ваших презентаций в различных средах, особенно когда определенные шрифты недоступны. Мы проведем вас через импорт необходимых пакетов, настройку среды и пошаговую реализацию резервных правил.
## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующее:
- Базовые знания программирования на Java.
- JDK (Java Development Kit) установлен в вашей системе.
- Библиотека Aspose.Slides for Java загружена и настроена. Вы можете скачать ее с [здесь](https://releases.aspose.com/slides/java/).
- Установленная IDE (интегрированная среда разработки), например IntelliJ IDEA или Eclipse.
## Импортные пакеты
Начните с импорта необходимых пакетов в ваш проект Java:
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.FontFallBackRulesCollection;
import com.aspose.slides.IFontFallBackRulesCollection;
import com.aspose.slides.Presentation;
```
## Настройка объекта презентации
Сначала инициализируйте объект Presentation, в котором вы определите правила резервного копирования шрифтов.
```java
Presentation presentation = new Presentation();
```
## Создание коллекции правил резервного копирования шрифтов
Затем создайте объект FontFallBackRulesCollection для управления пользовательскими правилами резервного копирования шрифтов.
```java
IFontFallBackRulesCollection userRulesList = new FontFallBackRulesCollection();
```
## Добавление правил резервного копирования шрифтов
Теперь добавьте определенные правила резервного шрифта, используя диапазоны Unicode и имена резервных шрифтов.
### Шаг 1: Определите диапазон и шрифт Unicode
```java
userRulesList.add(new FontFallBackRule(0x0B80, 0x0BFF, "Vijaya"));
```
Эта строка устанавливает резервное правило для диапазона Unicode от 0x0B80 до 0x0BFF, чтобы использовать шрифт «Vijaya», если основной шрифт недоступен.
### Шаг 2: Определите другой диапазон Unicode и шрифт
```java
userRulesList.add(new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic"));
```
Здесь правило указывает, что диапазон Unicode от 0x3040 до 0x309F должен использовать шрифты «MS Mincho» или «MS Gothic».
## Применение правил резервного копирования шрифтов к презентации
Примените созданную коллекцию правил резервного копирования шрифтов к FontsManager презентации.
```java
presentation.getFontsManager().setFontFallBackRulesCollection(userRulesList);
```
## Удалить объект презентации
Наконец, обеспечьте правильное управление ресурсами, поместив объект Presentation в блок try-finally.
```java
try {
    // Используйте объект презентации по мере необходимости.
} finally {
    if (presentation != null) presentation.dispose();
}
```
## Заключение
В этом уроке мы изучили, как управлять правилами резервного копирования шрифтов с помощью Aspose.Slides для Java. Понимание и реализация резервного копирования шрифтов обеспечивает согласованную и надежную визуализацию шрифтов на разных платформах и в разных средах. Выполнив эти шаги, вы сможете настроить поведение резервного копирования шрифтов для бесшовного соответствия определенным требованиям к презентации.

## Часто задаваемые вопросы
### Каковы правила резервного копирования шрифтов?
Правила резервного шрифта определяют альтернативные шрифты, которые будут использоваться, если указанный шрифт недоступен, обеспечивая единообразное отображение текста.
### Как загрузить Aspose.Slides для Java?
Вы можете скачать библиотеку с сайта [здесь](https://releases.aspose.com/slides/java/).
### Могу ли я попробовать Aspose.Slides для Java перед покупкой?
Да, вы можете получить бесплатную пробную версию. [здесь](https://releases.aspose.com/).
### Где я могу найти документацию по Aspose.Slides для Java?
Подробная документация доступна [здесь](https://reference.aspose.com/slides/java/).
### Как получить поддержку по Aspose.Slides для Java?
Для получения поддержки посетите форум Aspose.Slides [здесь](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}