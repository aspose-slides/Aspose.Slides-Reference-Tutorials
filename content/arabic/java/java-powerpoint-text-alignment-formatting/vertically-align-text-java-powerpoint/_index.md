---
title: محاذاة النص عموديًا في Java PowerPoint
linktitle: محاذاة النص عموديًا في Java PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية محاذاة النص عموديًا في عروض Java PowerPoint التقديمية باستخدام Aspose.Slides لتنسيق الشرائح بسلاسة.
type: docs
weight: 10
url: /ar/java/java-powerpoint-text-alignment-formatting/vertically-align-text-java-powerpoint/
---
## مقدمة
ستتعلم في هذا البرنامج التعليمي كيفية محاذاة النص رأسيًا داخل خلايا الجدول في عرض PowerPoint التقديمي باستخدام Aspose.Slides لـ Java. تعد محاذاة النص عموديًا جانبًا مهمًا في تصميم الشرائح، مما يضمن تقديم المحتوى الخاص بك بدقة واحترافية. يوفر Aspose.Slides ميزات قوية للتعامل مع العروض التقديمية وتنسيقها برمجيًا، مما يمنحك التحكم الكامل في كل جانب من جوانب شرائحك.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- المعرفة الأساسية ببرمجة جافا.
- JDK (Java Development Kit) مثبت على جهازك.
-  Aspose.Slides لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).
- تم تثبيت IDE (بيئة التطوير المتكاملة) مثل IntelliJ IDEA أو Eclipse.

## حزم الاستيراد
قبل متابعة البرنامج التعليمي، تأكد من استيراد حزم Aspose.Slides الضرورية إلى ملف Java الخاص بك:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## الخطوة 1: قم بإعداد مشروع Java الخاص بك
تأكد من أنك قمت بإعداد مشروع Java جديد في IDE المفضل لديك وقمت بإضافة مكتبة Aspose.Slides إلى مسار بناء مشروعك.
## الخطوة 2: تهيئة كائن العرض التقديمي
 إنشاء مثيل لـ`Presentation` الفصل الدراسي لبدء العمل باستخدام عرض تقديمي جديد لـ PowerPoint:
```java
Presentation presentation = new Presentation();
```
## الخطوة 3: الوصول إلى الشريحة الأولى
احصل على الشريحة الأولى من العرض التقديمي لإضافة محتوى إليها:
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## الخطوة 4: تحديد أبعاد الجدول وإضافة جدول
حدد عرض الأعمدة وارتفاع الصفوف لجدولك، ثم أضف شكل الجدول إلى الشريحة:
```java
double[] dblCols = {120, 120, 120, 120};
double[] dblRows = {100, 100, 100, 100};
ITable tbl = slide.getShapes().addTable(100, 50, dblCols, dblRows);
```
## الخطوة 5: تعيين محتوى النص في خلايا الجدول
تعيين محتوى النص لصفوف محددة في الجدول:
```java
tbl.getRows().get_Item(1).get_Item(0).getTextFrame().setText("10");
tbl.getRows().get_Item(2).get_Item(0).getTextFrame().setText("20");
tbl.getRows().get_Item(3).get_Item(0).getTextFrame().setText("30");
```
## الخطوة 6: الوصول إلى إطار النص وتنسيق النص
الوصول إلى إطار النص وتنسيق النص داخل خلية معينة:
```java
ITextFrame txtFrame = tbl.get_Item(0, 0).getTextFrame();
IParagraph paragraph = txtFrame.getParagraphs().get_Item(0);
IPortion portion = paragraph.getPortions().get_Item(0);
portion.setText("Text here");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## الخطوة 7: محاذاة النص عموديًا
تعيين المحاذاة العمودية للنص داخل الخلية:
```java
ICell cell = tbl.get_Item(0, 0);
cell.setTextAnchorType(TextAnchorType.Center);
cell.setTextVerticalType(TextVerticalType.Vertical270);
```
## الخطوة 8: احفظ العرض التقديمي
احفظ العرض التقديمي المعدل في موقع محدد على القرص الخاص بك:
```java
String dataDir = "Your Document Directory";
presentation.save(dataDir + "Vertical_Align_Text_out.pptx", SaveFormat.Pptx);
```
## الخطوة 9: تنظيف الموارد
 تخلص من`Presentation` كائن لتحرير الموارد:
```java
if (presentation != null) presentation.dispose();
```

## خاتمة
باتباع هذه الخطوات، يمكنك محاذاة النص عموديًا بشكل فعال داخل خلايا الجدول في عروض Java PowerPoint التقديمية باستخدام Aspose.Slides. تعمل هذه الإمكانية على تحسين المظهر البصري والوضوح لشرائحك، مما يضمن تقديم المحتوى الخاص بك بشكل احترافي.

## الأسئلة الشائعة
### هل يمكنني محاذاة النص عموديًا في أشكال أخرى إلى جانب الجداول؟
نعم، يوفر Aspose.Slides طرقًا لمحاذاة النص رأسيًا بأشكال مختلفة، بما في ذلك مربعات النص والعناصر النائبة.
### هل يدعم Aspose.Slides محاذاة النص أفقيًا أيضًا؟
نعم، يمكنك محاذاة النص أفقيًا باستخدام خيارات المحاذاة المختلفة التي يوفرها Aspose.Slides.
### هل Aspose.Slides متوافق مع كافة إصدارات PowerPoint؟
يدعم Aspose.Slides إنشاء عروض تقديمية متوافقة مع كافة الإصدارات الرئيسية لبرنامج Microsoft PowerPoint.
### أين يمكنني العثور على المزيد من الأمثلة والوثائق الخاصة بـ Aspose.Slides؟
 قم بزيارة[Aspose.Slides الوثائق](https://reference.aspose.com/slides/java/) للحصول على أدلة شاملة ومراجع واجهة برمجة التطبيقات ونماذج التعليمات البرمجية.
### كيف يمكنني الحصول على الدعم لـ Aspose.Slides؟
 للحصول على المساعدة الفنية ودعم المجتمع، قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).