---
title: زاوية دوران مخصصة لإطار النص في Java PowerPoint
linktitle: زاوية دوران مخصصة لإطار النص في Java PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تخصيص زوايا التدوير لإطارات النص في Java PowerPoint باستخدام Aspose.Slides. تعزيز العروض التقديمية الخاصة بك بشكل حيوي.
weight: 14
url: /ar/java/java-powerpoint-text-box-manipulation/custom-rotation-angle-text-frame-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية التعامل مع زوايا دوران إطار النص في عروض Java PowerPoint التقديمية باستخدام Aspose.Slides. يعد تخصيص زوايا التدوير أمرًا بالغ الأهمية لتعزيز المظهر البصري ووضوح النص داخل الشرائح. سواء كنت تقوم بإنشاء مخططات ديناميكية أو إضافة عناوين مخصصة، فإن التدوير الدقيق لإطار النص يمكن أن يؤدي إلى تحسين جماليات العرض التقديمي بشكل كبير.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك ما يلي:
- المعرفة الأساسية ببرمجة جافا.
- JDK (Java Development Kit) مثبت على جهازك.
-  Aspose.Slides لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).
- إعداد IDE (بيئة التطوير المتكاملة) مثل IntelliJ IDEA أو Eclipse.
## حزم الاستيراد
تأكد من استيراد فئات Aspose.Slides اللازمة للعمل مع عروض PowerPoint التقديمية في Java:
```java
import com.aspose.slides.*;
```
## الخطوة 1: قم بإعداد مشروعك
أولاً، قم بإنشاء مشروع Java جديد في IDE الخاص بك وأضف مكتبة Aspose.Slides for Java إلى مسار بناء مشروعك.
## الخطوة 2: تهيئة كائن العرض التقديمي
تهيئة كائن عرض تقديمي للعمل مع عرض تقديمي جديد لـ PowerPoint:
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## الخطوة 3: إضافة مخطط إلى الشريحة
أضف مخططًا عموديًا متفاوت المسافات إلى الشريحة الأولى:
```java
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 300);
```
## الخطوة 4: تخصيص تسميات بيانات المخطط
تخصيص زاوية الاستدارة لتسميات البيانات في سلسلة المخططات:
```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getTextBlockFormat().setRotationAngle(65);
```
## الخطوة 5: ضبط زاوية دوران العنوان
أضف عنوانًا مخصصًا إلى المخطط واضبط زاوية دورانه:
```java
chart.getChartTitle().addTextFrameForOverriding("Custom title").getTextFrameFormat().setRotationAngle(-30);
```
## الخطوة 6: احفظ العرض التقديمي
احفظ العرض التقديمي المعدل في دليل محدد:
```java
presentation.save(dataDir + "textframe-rotation_out.pptx", SaveFormat.Pptx);
```

## خاتمة
يتيح تخصيص زوايا التدوير لإطارات النص في عروض Java PowerPoint التقديمية باستخدام Aspose.Slides للمطورين إنشاء شرائح جذابة بصريًا وذات مظهر احترافي دون عناء. باتباع هذه الخطوات، يمكنك تحسين إمكانية قراءة عروضك التقديمية وتصميمها بشكل ديناميكي.

## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java هي مكتبة قوية تمكن مطوري Java من إنشاء عروض PowerPoint التقديمية وتعديلها وتحويلها برمجياً.
### كيف يمكنني تنزيل نسخة تجريبية مجانية من Aspose.Slides لـ Java؟
 يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Slides لـ Java من[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على وثائق Aspose.Slides لـ Java؟
 الوثائق التفصيلية لـ Aspose.Slides لـ Java متاحة[هنا](https://reference.aspose.com/slides/java/).
### هل Aspose.Slides مناسب لتطبيقات المؤسسات؟
نعم، تم تصميم Aspose.Slides للتعامل مع المتطلبات على مستوى المؤسسة لإنشاء عروض PowerPoint التقديمية وإدارتها.
### كيف يمكنني الحصول على دعم Aspose.Slides لـ Java؟
 للحصول على الدعم الفني والتفاعل المجتمعي، قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
