---
title: تقسيم الخلايا في جدول PowerPoint باستخدام Java
linktitle: تقسيم الخلايا في جدول PowerPoint باستخدام Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرّف على كيفية تقسيم خلايا جدول PowerPoint ودمجها وتنسيقها برمجياً باستخدام Aspose.Slides لـ Java. تصميم العرض الرئيسي.
type: docs
weight: 11
url: /ar/java/java-powerpoint-table-manipulation/split-cells-powerpoint-table-java/
---
## مقدمة
ستتعلم في هذا البرنامج التعليمي كيفية التعامل مع جداول PowerPoint في Java باستخدام Aspose.Slides. تعد الجداول عنصرًا أساسيًا في العروض التقديمية، وغالبًا ما تستخدم لتنظيم البيانات وعرضها بشكل فعال. يوفر Aspose.Slides إمكانات قوية لإنشاء الجداول وتعديلها وتحسينها برمجيًا، مما يوفر المرونة في التصميم والتخطيط.
## المتطلبات الأساسية
قبل أن تبدأ هذا البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- المعرفة الأساسية ببرمجة جافا.
- JDK (Java Development Kit) مثبت على جهازك.
-  Aspose.Slides لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).
- بيئة التطوير المتكاملة (IDE) مثل Eclipse أو IntelliJ IDEA أو أي شيء آخر من اختيارك.

## حزم الاستيراد
لبدء العمل مع Aspose.Slides for Java، تحتاج إلى استيراد الحزم الضرورية إلى مشروع Java الخاص بك:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## الخطوة 1: إعداد العرض التقديمي
 أولاً، قم بإنشاء مثيل`Presentation` فئة لإنشاء عرض تقديمي جديد ل PowerPoint.
```java
// المسار إلى الدليل الذي تريد حفظ العرض التقديمي الناتج فيه
String dataDir = "Your_Document_Directory/";
// إنشاء فئة العرض التقديمي التي تمثل ملف PPTX
Presentation presentation = new Presentation();
```
## الخطوة 2: الوصول إلى الشريحة وإضافة جدول
قم بالوصول إلى الشريحة الأولى وأضف شكل جدول إليها. حدد الأعمدة بالعرض والصفوف بالارتفاع.
```java
try {
    // الوصول إلى الشريحة الأولى
    ISlide slide = presentation.getSlides().get_Item(0);
    // حدد الأعمدة بالعرض والصفوف بالارتفاع
    double[] dblCols = {70, 70, 70, 70};
    double[] dblRows = {70, 70, 70, 70};
    // إضافة شكل الجدول إلى الشريحة
    ITable table = slide.getShapes().addTable(100, 50, dblCols, dblRows);
```
## الخطوة 3: تحديد تنسيق الحدود لكل خلية
قم بالتكرار خلال كل خلية في الجدول وقم بتعيين تنسيق الحدود (اللون والعرض وما إلى ذلك).
```java
    // تعيين تنسيق الحدود لكل خلية
    for (IRow row : table.getRows()) {
        for (ICell cell : (Iterable<ICell>) row) {
            cell.getCellFormat().getBorderTop().getFillFormat().setFillType(FillType.Solid);
            cell.getCellFormat().getBorderTop().getFillFormat().getSolidFillColor().setColor(Color.RED);
            cell.getCellFormat().getBorderTop().setWidth(5);
            // تعيين تنسيق مماثل للحدود الأخرى (أسفل، يسار، يمين)
            // ...
        }
    }
```
## الخطوة 4: دمج الخلايا
دمج الخلايا في الجدول حسب الحاجة. على سبيل المثال، دمج الخلايا (1،1) إلى (2،1) و (1،2) إلى (2،2).
```java
    // دمج الخلايا (1، 1) × (2، 1)
    table.mergeCells(table.get_Item(1, 1), table.get_Item(2, 1), false);
    // دمج الخلايا (1، 2) × (2، 2)
    table.mergeCells(table.get_Item(1, 2), table.get_Item(2, 2), false);
```
## الخطوة 5: تقسيم الخلايا
تقسيم خلية معينة إلى خلايا متعددة بناءً على العرض.
```java
    // انقسام الخلية (1، 1)
    table.get_Item(1, 1).splitByWidth(table.get_Item(2, 1).getWidth() / 2);
```
## الخطوة 6: حفظ العرض التقديمي
احفظ العرض التقديمي المعدل على القرص.
```java
    // اكتب PPTX على القرص
    presentation.save(dataDir + "CellSplit_out.pptx", SaveFormat.Pptx);
} finally {
    // التخلص من كائن العرض التقديمي
    if (presentation != null) presentation.dispose();
}
```

## خاتمة
توفر معالجة جداول PowerPoint برمجيًا باستخدام Aspose.Slides for Java طريقة قوية لتخصيص العروض التقديمية بكفاءة. باتباع هذا البرنامج التعليمي، تعلمت كيفية تقسيم الخلايا ودمجها وتعيين حدود الخلايا ديناميكيًا، مما يعزز قدرتك على إنشاء عروض تقديمية جذابة برمجيًا.

## الأسئلة الشائعة
### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ Java؟
 يمكنك العثور على الوثائق[هنا](https://reference.aspose.com/slides/java/).
### كيف يمكنني تنزيل Aspose.Slides لجافا؟
 يمكنك تنزيله من[هذا الرابط](https://releases.aspose.com/slides/java/).
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ Java؟
 نعم، يمكنك الحصول على نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### أين يمكنني الحصول على الدعم لـ Aspose.Slides لـ Java؟
 يمكنك الحصول على الدعم من منتدى Aspose.Slides[هنا](https://forum.aspose.com/c/slides/11).
### هل يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ Java؟
 نعم يمكنك الحصول على ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/).