---
"date": "2025-04-18"
"description": "Узнайте, как улучшить свои презентации, настроив маркеры SmartArt с изображениями с помощью Aspose.Slides для Java. Следуйте этому пошаговому руководству для профессионального вида."
"title": "Как настроить маркеры SmartArt с изображениями с помощью Aspose.Slides для Java | Пошаговое руководство"
"url": "/ru/java/smart-art-diagrams/customize-smartart-bullets-images-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как настроить маркеры SmartArt с изображениями с помощью Aspose.Slides для Java

## Введение

Создание визуально привлекательных презентаций имеет решающее значение для привлечения внимания аудитории и эффективной передачи вашего сообщения. Одной из распространенных проблем при разработке слайдов является улучшение пунктов списка в графических элементах SmartArt с помощью пользовательских изображений. Это руководство проведет вас через установку изображения в качестве формата заполнения маркера в узлах SmartArt с помощью Aspose.Slides для Java, что позволит вам вывести свои презентации на профессиональный уровень.

**Что вы узнаете:**
- Настройка и использование Aspose.Slides для Java
- Настройка пунктов списка с изображениями в графических элементах SmartArt
- Практическое применение этой настройки
- Устранение распространенных проблем

Прежде чем приступить к реализации, убедитесь, что у вас все готово.

## Предпосылки

Чтобы следовать этому руководству, убедитесь, что выполнены следующие предварительные условия:

1. **Библиотеки и зависимости**Вам понадобится библиотека Aspose.Slides для Java версии 25.4 или более поздней.
2. **Настройка среды**:
   - Совместимая IDE, например IntelliJ IDEA или Eclipse
   - JDK 16 установлен на вашем компьютере
3. **Необходимые знания**: Знакомство с программированием на Java и базовой структурой презентаций PowerPoint.

## Настройка Aspose.Slides для Java

Для начала включите библиотеку Aspose.Slides в свой проект одним из следующих способов:

### Знаток

Добавьте эту зависимость к вашему `pom.xml` файл:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Градл

Включите это в свой `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Прямая загрузка

Либо загрузите библиотеку напрямую с [Aspose.Slides для релизов Java](https://releases.aspose.com/slides/java/).

**Этапы получения лицензии**: Aspose предлагает бесплатную пробную лицензию, идеально подходящую для тестирования ее функций. Вы можете запросить временную лицензию или купить ее, чтобы снять ограничения оценки.

Чтобы инициализировать и настроить вашу среду, создайте экземпляр `Presentation` класс, как показано:

```java
Presentation presentation = new Presentation();
```

## Руководство по внедрению

В этом разделе процесс будет разбит на управляемые этапы и будет объяснено, как достичь желаемой функциональности.

### Добавление SmartArt с пользовательской заливкой маркеров

#### Обзор

Начнем с добавления фигуры SmartArt на слайд и настройки ее пунктов с помощью заливки изображением.

#### Пошаговые инструкции

**1. Инициализация объекта презентации**

```java
Presentation presentation = new Presentation();
```

*Цель*: Инициализирует новый экземпляр презентации, в который вы добавите графику SmartArt.

**2. Добавить фигуру SmartArt**

```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```

*Объяснение*: Эта строка добавляет новую фигуру SmartArt к первому слайду в позиции (x=10, y=10) с размерами 500x400 пикселей. `VerticalPictureList` макет используется для вертикального выравнивания.

**3. Доступ и настройка заполнения маркеров**

```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);

if (node.getBulletFillFormat() != null) {
    IImage img = Images.fromFile("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg");
    IPPImage image = presentation.getImages().addImage(img);
    
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```

*Цель*: Проверяет, имеет ли узел `BulletFillFormat` свойство. Если да, то загружает изображение и устанавливает его в качестве заливки для маркеров.
*Параметры*:
  - `"YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg"`: Путь к файлу изображения.
  - `PictureFillMode.Stretch`: обеспечивает полное заполнение области маркера изображением.

**4. Сохраните презентацию**

```java
presentation.save("YOUR_OUTPUT_DIRECTORY/out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}