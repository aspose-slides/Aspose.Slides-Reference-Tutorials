---
"description": "تعرّف على كيفية دمج الخلايا في جداول PowerPoint باستخدام Aspose.Slides لجافا. حسّن تصميم عرضك التقديمي باتباع هذا الدليل خطوة بخطوة."
"linktitle": "دمج الخلايا في جدول PowerPoint باستخدام Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "دمج الخلايا في جدول PowerPoint باستخدام Java"
"url": "/ar/java/java-powerpoint-table-manipulation/merge-cells-powerpoint-table-java/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# دمج الخلايا في جدول PowerPoint باستخدام Java

## مقدمة
في هذا البرنامج التعليمي، ستتعلم كيفية دمج الخلايا بفعالية ضمن جدول PowerPoint باستخدام Aspose.Slides لجافا. Aspose.Slides هي مكتبة فعّالة تُمكّن المطورين من إنشاء عروض PowerPoint التقديمية وتعديلها وتحويلها برمجيًا. بدمج الخلايا في جدول، يمكنك تخصيص تخطيط وهيكل شرائح العرض التقديمي، مما يُحسّن الوضوح والجاذبية البصرية.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- المعرفة الأساسية بلغة البرمجة جافا.
- تم تثبيت JDK (Java Development Kit) على جهازك.
- IDE (بيئة التطوير المتكاملة) مثل IntelliJ IDEA أو Eclipse.
- مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

## استيراد الحزم
للبدء، تأكد من استيراد الحزم اللازمة للعمل مع Aspose.Slides:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## الخطوة 1: إعداد مشروعك
أولاً، قم بإنشاء مشروع Java جديد في بيئة التطوير المتكاملة المفضلة لديك وأضف مكتبة Aspose.Slides for Java إلى تبعيات مشروعك.
## الخطوة 2: إنشاء كائن العرض التقديمي
إنشاء مثيل `Presentation` الفئة التي تمثل ملف PPTX الذي تعمل عليه:
```java
Presentation presentation = new Presentation();
```
## الخطوة 3: الوصول إلى الشريحة
انتقل إلى الشريحة التي تريد إضافة الجدول إليها. على سبيل المثال، للوصول إلى الشريحة الأولى:
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## الخطوة 4: تحديد أبعاد الجدول
حدّد أعمدة وصفوف جدولك. حدّد عرض الأعمدة وارتفاع الصفوف كمصفوفات. `double`:
```java
double[] dblCols = {70, 70, 70, 70};
double[] dblRows = {70, 70, 70, 70};
```
## الخطوة 5: إضافة شكل الجدول إلى الشريحة
أضف شكل جدول إلى الشريحة باستخدام الأبعاد المحددة:
```java
ITable table = slide.getShapes().addTable(100, 50, dblCols, dblRows);
```
## الخطوة 6: تخصيص حدود الخلايا
عيّن تنسيق الحدود لكل خلية في الجدول. هذا المثال يُعيّن حدودًا حمراء صلبة بعرض 5 لكل خلية:
```java
for (IRow row : table.getRows()) {
    for (ICell cell : (Iterable<ICell>) row) {
        // تعيين تنسيق الحدود لكل جانب من جوانب الخلية
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
لدمج الخلايا في الجدول، استخدم `mergeCells` الطريقة. يدمج هذا المثال الخلايا من (1، 1) إلى (2، 1) ومن (1، 2) إلى (2، 2):
```java
table.mergeCells(table.get_Item(1, 1), table.get_Item(2, 1), false);
table.mergeCells(table.get_Item(1, 2), table.get_Item(2, 2), false);
```
## الخطوة 8: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدّل في ملف PPTX على القرص لديك:
```java
String dataDir = "Your_Document_Directory_Path/";
presentation.save(dataDir + "MergeCells1_out.pptx", SaveFormat.Pptx);
```

## خاتمة
باتباع هذه الخطوات، تكون قد تعلمت بنجاح كيفية دمج الخلايا في جدول PowerPoint باستخدام Aspose.Slides لجافا. تتيح لك هذه التقنية إنشاء عروض تقديمية أكثر تعقيدًا وجاذبية بصريًا برمجيًا، مما يعزز إنتاجيتك وخيارات التخصيص لديك.
## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات Java لإنشاء عروض PowerPoint ومعالجتها وتحويلها برمجيًا.
### كيف يمكنني تنزيل Aspose.Slides لـ Java؟
يمكنك تنزيل Aspose.Slides لـ Java من [هنا](https://releases.aspose.com/slides/java/).
### هل يمكنني تجربة Aspose.Slides لـJava قبل الشراء؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Slides لـ Java من [هنا](https://releases.aspose.com/).
### أين يمكنني العثور على وثائق Aspose.Slides لـ Java؟
يمكنك العثور على الوثائق [هنا](https://reference.aspose.com/slides/java/).
### كيف يمكنني الحصول على الدعم لـ Aspose.Slides لـ Java؟
يمكنك الحصول على الدعم من منتدى مجتمع Aspose.Slides [هنا](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}