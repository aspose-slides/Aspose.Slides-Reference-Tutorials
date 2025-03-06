---
title: دمج الخلايا في جدول PowerPoint باستخدام Java
linktitle: دمج الخلايا في جدول PowerPoint باستخدام Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية دمج الخلايا في جداول PowerPoint باستخدام Aspose.Slides لـ Java. قم بتحسين تخطيط العرض التقديمي الخاص بك باستخدام هذا الدليل المفصّل خطوة بخطوة.
weight: 17
url: /ar/java/java-powerpoint-table-manipulation/merge-cells-powerpoint-table-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
ستتعلم في هذا البرنامج التعليمي كيفية دمج الخلايا بشكل فعال داخل جدول PowerPoint باستخدام Aspose.Slides لـ Java. Aspose.Slides هي مكتبة قوية تسمح للمطورين بإنشاء عروض PowerPoint التقديمية ومعالجتها وتحويلها برمجياً. من خلال دمج الخلايا في جدول، يمكنك تخصيص تخطيط وبنية شرائح العرض التقديمي، مما يعزز الوضوح والجاذبية البصرية.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- المعرفة الأساسية بلغة البرمجة جافا.
- JDK (Java Development Kit) مثبت على جهازك.
- IDE (بيئة التطوير المتكاملة) مثل IntelliJ IDEA أو Eclipse.
-  Aspose.Slides لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

## حزم الاستيراد
للبدء، تأكد من استيراد الحزم اللازمة للعمل مع Aspose.Slides:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## الخطوة 1: قم بإعداد مشروعك
أولاً، قم بإنشاء مشروع Java جديد في IDE المفضل لديك وأضف مكتبة Aspose.Slides for Java إلى تبعيات مشروعك.
## الخطوة 2: إنشاء كائن العرض التقديمي
 إنشاء مثيل`Presentation` فئة لتمثيل ملف PPTX الذي تعمل معه:
```java
Presentation presentation = new Presentation();
```
## الخطوة 3: الوصول إلى الشريحة
قم بالوصول إلى الشريحة التي تريد إضافة الجدول إليها. على سبيل المثال، للوصول إلى الشريحة الأولى:
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## الخطوة 4: تحديد أبعاد الجدول
 حدد الأعمدة والصفوف لجدولك. حدد عرض الأعمدة وارتفاع الصفوف كمصفوفات`double`:
```java
double[] dblCols = {70, 70, 70, 70};
double[] dblRows = {70, 70, 70, 70};
```
## الخطوة 5: إضافة شكل الجدول إلى الشريحة
أضف شكل جدول إلى الشريحة باستخدام الأبعاد المحددة:
```java
ITable table = slide.getShapes().addTable(100, 50, dblCols, dblRows);
```
## الخطوة 6: تخصيص حدود الخلية
قم بتعيين تنسيق الحدود لكل خلية في الجدول. يعين هذا المثال حدًا أحمرًا خالصًا بعرض 5 لكل خلية:
```java
for (IRow row : table.getRows()) {
    for (ICell cell : (Iterable<ICell>) row) {
        // قم بتعيين تنسيق الحدود لكل جانب من جوانب الخلية
        cell.getCellFormat().getBorderTop().getFillFormat().setFillType(FillType.Solid);
        cell.getCellFormat().getBorderTop().getFillFormat().getSolidFillColor().setColor(Color.RED);
        cell.getCellFormat().getBorderTop().setWidth(5);
        cell.getCellFormat().getBorderBottom().getFillFormat().setFillType(FillType.Solid);
        cell.getCellFormat().getBorderBottom().getFillFormat().getSolidFillColor().setColor(Color.RED);
        cell.getCellFormat().getBorderBottom().setWidth(5);
        cell.getCellFormat().getBorderLeft().getFillFormat().setFillType(FillType.Solid);
        cell.getCellFormat().getBorderLeft().getFillFormat().getSolidFillColor().setColor(Color.RED);
        cell.getCellFormat().getBorderLeft().setWidth(5);
        cell.getCellFormat().getBorderRight().getFillFormat().setFillType(FillType.Solid);
        cell.getCellFormat().getBorderRight().getFillFormat().getSolidFillColor().setColor(Color.RED);
        cell.getCellFormat().getBorderRight().setWidth(5);
    }
}
```
## الخطوة 7: دمج الخلايا في الجدول
 لدمج الخلايا في الجدول، استخدم`mergeCells` طريقة. يدمج هذا المثال الخلايا من (1، 1) إلى (2، 1) ومن (1، 2) إلى (2، 2):
```java
table.mergeCells(table.get_Item(1, 1), table.get_Item(2, 1), false);
table.mergeCells(table.get_Item(1, 2), table.get_Item(2, 2), false);
```
## الخطوة 8: احفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدل في ملف PPTX على القرص لديك:
```java
String dataDir = "Your_Document_Directory_Path/";
presentation.save(dataDir + "MergeCells1_out.pptx", SaveFormat.Pptx);
```

## خاتمة
باتباع هذه الخطوات، تكون قد تعلمت بنجاح كيفية دمج الخلايا داخل جدول PowerPoint باستخدام Aspose.Slides for Java. تسمح لك هذه التقنية بإنشاء عروض تقديمية أكثر تعقيدًا وجاذبية برمجيًا، مما يعزز إنتاجيتك وخيارات التخصيص.
## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات Java لإنشاء عروض PowerPoint التقديمية ومعالجتها وتحويلها برمجيًا.
### كيف يمكنني تنزيل Aspose.Slides لنظام Java؟
 يمكنك تنزيل Aspose.Slides لـ Java من[هنا](https://releases.aspose.com/slides/java/).
### هل يمكنني تجربة Aspose.Slides لـ Java قبل الشراء؟
 نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Slides لـ Java من[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على وثائق Aspose.Slides لـ Java؟
 يمكنك العثور على الوثائق[هنا](https://reference.aspose.com/slides/java/).
### كيف يمكنني الحصول على الدعم لـ Aspose.Slides لـ Java؟
 يمكنك الحصول على الدعم من منتدى مجتمع Aspose.Slides[هنا](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
