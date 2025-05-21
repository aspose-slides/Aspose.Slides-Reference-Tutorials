---
"description": "تعرّف على كيفية تخصيص زوايا دوران إطارات النصوص في جافا باوربوينت باستخدام Aspose.Slides. حسّن عروضك التقديمية بشكل ديناميكي."
"linktitle": "زاوية دوران مخصصة لإطار النص في Java PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "زاوية دوران مخصصة لإطار النص في Java PowerPoint"
"url": "/ar/java/java-powerpoint-text-box-manipulation/custom-rotation-angle-text-frame-java-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# زاوية دوران مخصصة لإطار النص في Java PowerPoint

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية التحكم بزوايا دوران إطار النص في عروض PowerPoint التقديمية بلغة جافا باستخدام Aspose.Slides. يُعد تخصيص زوايا الدوران أمرًا بالغ الأهمية لتحسين المظهر المرئي ووضوح النص داخل الشرائح. سواء كنت تُنشئ مخططات ديناميكية أو تُضيف عناوين مخصصة، فإن الدوران الدقيق لإطار النص يُحسّن بشكل كبير من جمالية العرض التقديمي.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك ما يلي:
- المعرفة الأساسية ببرمجة جافا.
- تم تثبيت JDK (Java Development Kit) على جهازك.
- مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).
- تم إعداد IDE (بيئة التطوير المتكاملة) مثل IntelliJ IDEA أو Eclipse.
## استيراد الحزم
تأكد من استيراد فئات Aspose.Slides الضرورية للعمل مع عروض PowerPoint في Java:
```java
import com.aspose.slides.*;
```
## الخطوة 1: إعداد مشروعك
أولاً، قم بإنشاء مشروع Java جديد في IDE الخاص بك وأضف مكتبة Aspose.Slides for Java إلى مسار بناء المشروع الخاص بك.
## الخطوة 2: تهيئة كائن العرض التقديمي
قم بتهيئة كائن العرض التقديمي للعمل مع عرض تقديمي جديد في PowerPoint:
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## الخطوة 3: إضافة مخطط إلى الشريحة
أضف مخططًا عموديًا مجمعًا إلى الشريحة الأولى:
```java
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 300);
```
## الخطوة 4: تخصيص تسميات بيانات الرسم البياني
تخصيص زاوية دوران تسميات البيانات في سلسلة المخططات:
```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getTextBlockFormat().setRotationAngle(65);
```
## الخطوة 5: ضبط زاوية دوران العنوان
أضف عنوانًا مخصصًا إلى الرسم البياني واضبط زاوية دورانه:
```java
chart.getChartTitle().addTextFrameForOverriding("Custom title").getTextFrameFormat().setRotationAngle(-30);
```
## الخطوة 6: حفظ العرض التقديمي
حفظ العرض التقديمي المعدل في الدليل المحدد:
```java
presentation.save(dataDir + "textframe-rotation_out.pptx", SaveFormat.Pptx);
```

## خاتمة
يُمكّن تخصيص زوايا دوران إطارات النصوص في عروض PowerPoint التقديمية بلغة Java باستخدام Aspose.Slides المطورين من إنشاء شرائح جذابة بصريًا واحترافية بكل سهولة. باتباع هذه الخطوات، يمكنك تحسين قابلية قراءة عروضك التقديمية وتصميمها بشكل ديناميكي.

## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java عبارة عن مكتبة قوية تتيح لمطوري Java إنشاء عروض PowerPoint وتعديلها وتحويلها برمجيًا.
### كيف يمكنني تنزيل نسخة تجريبية مجانية من Aspose.Slides لـ Java؟
يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Slides لـ Java من [هنا](https://releases.aspose.com/).
### أين يمكنني العثور على وثائق Aspose.Slides لـ Java؟
تتوفر وثائق مفصلة لـ Aspose.Slides for Java [هنا](https://reference.aspose.com/slides/java/).
### هل Aspose.Slides مناسب لتطبيقات المؤسسات؟
نعم، تم تصميم Aspose.Slides للتعامل مع متطلبات مستوى المؤسسة لإنشاء وإدارة عروض PowerPoint.
### كيف أحصل على الدعم لـ Aspose.Slides لـ Java؟
للحصول على الدعم الفني والتفاعل المجتمعي، قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}