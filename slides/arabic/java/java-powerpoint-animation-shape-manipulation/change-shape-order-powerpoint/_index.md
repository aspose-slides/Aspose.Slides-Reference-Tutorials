---
title: تغيير ترتيب الشكل في PowerPoint
linktitle: تغيير ترتيب الشكل في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تغيير ترتيب الأشكال في PowerPoint باستخدام Aspose.Slides لـ Java من خلال هذا البرنامج التعليمي خطوة بخطوة. تعزيز مهارات العرض التقديمي الخاص بك دون عناء.
weight: 15
url: /ar/java/java-powerpoint-animation-shape-manipulation/change-shape-order-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
قد يكون إنشاء عروض تقديمية جذابة ومنظمة بشكل جيد مهمة شاقة. ومع ذلك، باستخدام الأدوات والتقنيات المناسبة، يمكنك جعل الأمر أسهل بكثير. Aspose.Slides for Java هي مكتبة قوية تساعدك على التعامل مع عروض PowerPoint التقديمية وإدارتها برمجياً. في هذا البرنامج التعليمي، سنرشدك خلال خطوات تغيير ترتيب الشكل في شريحة PowerPoint باستخدام Aspose.Slides for Java.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
1.  Java Development Kit (JDK): تأكد من تثبيت JDK على جهازك. يمكنك تنزيله من[موقع أوراكل](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides لمكتبة Java: قم بتنزيل أحدث إصدار من[صفحة تنزيل Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): استخدم IDE مثل IntelliJ IDEA أو Eclipse للبرمجة.
4. ملف العرض التقديمي: قم بإعداد ملف PowerPoint الذي تريد معالجته.
## حزم الاستيراد
للبدء، تحتاج إلى استيراد الحزم الضرورية من مكتبة Aspose.Slides. ستسمح لك هذه الواردات بالعمل مع العروض التقديمية والشرائح والأشكال.
```java
import com.aspose.slides.*;

```
في هذا الدليل، سنقوم بتقسيم عملية تغيير ترتيب الشكل إلى عدة خطوات لفهم أفضل وسهولة التنفيذ.
## الخطوة 1: قم بتحميل العرض التقديمي
 أولاً، تحتاج إلى تحميل ملف عرض PowerPoint التقديمي الذي تريد العمل معه. تتضمن هذه الخطوة تهيئة`Presentation` فئة مع المسار إلى ملف PowerPoint الخاص بك.
```java
String dataDir = "Your Document Directory";
Presentation presentation1 = new Presentation(dataDir + "HelloWorld.pptx");
```
## الخطوة 2: الوصول إلى الشريحة المطلوبة
بمجرد تحميل العرض التقديمي، قم بالوصول إلى الشريحة التي تريد إعادة ترتيب الأشكال فيها. تتم فهرسة الشرائح بدءًا من 0، لذا للوصول إلى الشريحة الأولى، استخدم الفهرس 0.
```java
ISlide slide = presentation1.getSlides().get_Item(0);
```
## الخطوة 3: إضافة الأشكال إلى الشريحة
بعد ذلك، قم بإضافة الأشكال إلى الشريحة. للتوضيح، سنضيف شكل مستطيل ومثلث إلى الشريحة.
```java
IAutoShape shp3 = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.getFillFormat().setFillType(FillType.NoFill);
shp3.addTextFrame(" ");
ITextFrame txtFrame = shp3.getTextFrame();
IParagraph para = txtFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("Watermark Text Watermark Text Watermark Text");
shp3 = slide.getShapes().addAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
```
## الخطوة 4: إعادة ترتيب الأشكال
 الآن، أعد ترتيب الأشكال على الشريحة. ال`reorder` يتيح لك هذا الأسلوب تحديد الموضع الجديد للشكل ضمن مجموعة الأشكال بالشريحة.
```java
slide.getShapes().reorder(2, shp3);
```
## الخطوة 5: احفظ العرض التقديمي المعدل
بعد إعادة ترتيب الأشكال، احفظ العرض التقديمي المعدل في ملف جديد. وهذا يضمن بقاء ملفك الأصلي دون تغيير.
```java
presentation1.save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
## الخطوة 6: تنظيف الموارد
وأخيراً، تخلص من كائن العرض التقديمي لتحرير الموارد.
```java
if (presentation1 != null) presentation1.dispose();
```
## خاتمة
باتباع هذه الخطوات، يمكنك بسهولة تغيير ترتيب الأشكال في شريحة PowerPoint باستخدام Aspose.Slides for Java. تعمل هذه المكتبة القوية على تبسيط العديد من المهام المرتبطة بعروض PowerPoint التقديمية، مما يتيح لك إنشاء الشرائح ومعالجتها برمجياً. سواء كنت تقوم بأتمتة إنشاء العروض التقديمية أو تحتاج فقط إلى إجراء تغييرات مجمعة، فإن Aspose.Slides for Java هي أداة لا تقدر بثمن.
## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java عبارة عن Java API لإنشاء عروض PowerPoint التقديمية ومعالجتها دون استخدام Microsoft PowerPoint.
### هل يمكنني استخدام Aspose.Slides لـ Java مع Java IDEs الأخرى؟
نعم، يمكنك استخدامه مع أي Java IDE مثل IntelliJ IDEA أو Eclipse أو NetBeans.
### هل Aspose.Slides for Java متوافق مع جميع تنسيقات PowerPoint؟
نعم، يدعم Aspose.Slides for Java تنسيقات PPT وPPTX وتنسيقات PowerPoint الأخرى.
### كيف يمكنني الحصول على نسخة تجريبية مجانية من Aspose.Slides لـ Java؟
 يمكنك تنزيل نسخة تجريبية مجانية من[صفحة تنزيل Aspose.Slides لـ Java](https://releases.aspose.com/).
### أين يمكنني العثور على مزيد من الوثائق حول Aspose.Slides لـ Java؟
 يمكنك العثور على وثائق مفصلة عن[Aspose.Slides لصفحة وثائق Java](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
