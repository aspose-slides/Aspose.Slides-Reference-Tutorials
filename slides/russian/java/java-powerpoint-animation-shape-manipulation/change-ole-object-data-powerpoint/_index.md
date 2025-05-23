---
"description": "Узнайте, как изменить данные объекта OLE в PowerPoint с помощью Aspose.Slides для Java. Пошаговое руководство для эффективных и простых обновлений."
"linktitle": "Изменение данных объекта OLE в PowerPoint"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Изменение данных объекта OLE в PowerPoint"
"url": "/ru/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Изменение данных объекта OLE в PowerPoint

## Введение
Изменение данных объектов OLE в презентациях PowerPoint может быть важной задачей, когда вам нужно обновить встроенный контент без ручного редактирования каждого слайда. Это всеобъемлющее руководство проведет вас через процесс с использованием Aspose.Slides для Java, мощной библиотеки, разработанной для обработки презентаций PowerPoint. Независимо от того, являетесь ли вы опытным разработчиком или только начинаете, вы найдете это руководство полезным и простым для понимания.
## Предпосылки
Прежде чем погрузиться в код, давайте убедимся, что у вас есть все необходимое для начала работы.
1. Java Development Kit (JDK): Убедитесь, что в вашей системе установлен JDK. Вы можете загрузить его с [Сайт Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides для Java: загрузите последнюю версию с сайта [Страница загрузки Aspose.Slides](https://releases.aspose.com/slides/java/).
3. Интегрированная среда разработки (IDE): вы можете использовать любую Java IDE, например IntelliJ IDEA, Eclipse или NetBeans.
4. Aspose.Cells для Java: Это необходимо для изменения встроенных данных в объекте OLE. Загрузите его с [Страница загрузки Aspose.Cells](https://releases.aspose.com/cells/java/).
5. Файл презентации: Имейте готовый файл PowerPoint со встроенным объектом OLE. Для этого урока давайте назовем его `ChangeOLEObjectData.pptx`.
## Импортные пакеты
Сначала давайте импортируем необходимые пакеты в ваш проект Java.
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

Теперь давайте разобьем процесс на простые и выполнимые шаги.
## Шаг 1: Загрузите презентацию PowerPoint.
Для начала вам необходимо загрузить презентацию PowerPoint, содержащую объект OLE.
```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## Шаг 2: Доступ к слайду, содержащему объект OLE
Далее получим слайд, на котором внедрен OLE-объект.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Шаг 3: Найдите объект OLE на слайде.
Просмотрите фигуры на слайде, чтобы найти объект OLE.
```java
OleObjectFrame ole = null;
// Обход всех форм для рамки Ole
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## Шаг 4: Извлечение встроенных данных из объекта OLE
Если объект OLE найден, извлеките его встроенные данные.
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## Шаг 5: Измените встроенные данные с помощью Aspose.Cells
Теперь используйте Aspose.Cells для чтения и изменения встроенных данных, которые в данном случае, скорее всего, представляют собой книгу Excel.
```java
    Workbook wb = new Workbook(msln);
    // Изменить данные рабочей книги
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## Шаг 6: Сохраните измененные данные обратно в объект OLE
После внесения необходимых изменений сохраните измененную книгу обратно в объект OLE.
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## Шаг 7: Сохраните обновленную презентацию.
Наконец, сохраните обновленную презентацию PowerPoint.
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Заключение
Обновление данных объектов OLE в презентациях PowerPoint с помощью Aspose.Slides for Java — это простой процесс, если разбить его на простые шаги. Это руководство провело вас через загрузку презентации, доступ и изменение встроенных данных OLE и сохранение обновленной презентации. С помощью этих шагов вы можете эффективно управлять и обновлять встроенный контент в слайдах PowerPoint программным способом.
## Часто задаваемые вопросы
### Что такое объект OLE в PowerPoint?
Объект OLE (Object Linking and Embedding) позволяет встраивать содержимое из других приложений, например электронных таблиц Excel, в слайды PowerPoint.
### Могу ли я использовать Aspose.Slides с другими языками программирования?
Да, Aspose.Slides поддерживает несколько языков, включая .NET, Python и C++.
### Нужен ли мне Aspose.Cells для изменения объектов OLE в PowerPoint?
Да, если объект OLE представляет собой электронную таблицу Excel, для его изменения вам понадобится Aspose.Cells.
### Существует ли пробная версия Aspose.Slides?
Да, вы можете получить [бесплатная пробная версия](https://releases.aspose.com/) для тестирования возможностей Aspose.Slides.
### Где я могу найти документацию по Aspose.Slides?
Подробную документацию вы можете найти на [Страница документации Aspose.Slides](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}