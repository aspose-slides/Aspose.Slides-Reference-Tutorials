---
title: إنشاء ملخص التكبير في PowerPoint
linktitle: إنشاء ملخص التكبير في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إنشاء ملخص تكبير في PowerPoint باستخدام Aspose.Slides لـ Java من خلال هذا البرنامج التعليمي الشامل خطوة بخطوة.
weight: 16
url: /ar/java/java-powerpoint-shape-thumbnail-creation/create-summary-zoom-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
مرحبًا بك في برنامجنا التعليمي الشامل حول إنشاء تكبير ملخص في PowerPoint باستخدام Aspose.Slides لـ Java. إذا كنت تتطلع إلى إضافة عنصر ديناميكي وتفاعلي إلى عروضك التقديمية، فإن Summary Zoom هي ميزة رائعة. فهو يسمح لك بإنشاء شريحة واحدة يمكنها تكبير أقسام مختلفة من العرض التقديمي الخاص بك، مما يوفر تجربة أكثر جاذبية وقابلية للتنقل لجمهورك.
في هذا الدليل التفصيلي، سنرشدك خلال العملية بأكملها، بدءًا من إعداد بيئة التطوير الخاصة بك وحتى إنشاء إطار تكبير/تصغير ملخص وتخصيصه. سواء كنت مطور Java متمرسًا أو بدأت للتو، ستجد هذا الدليل سهل المتابعة ومليئًا بالرؤى القيمة.
## المتطلبات الأساسية
قبل الغوص في الكود، دعنا نتأكد من أن لديك كل ما تحتاجه للبدء:
1.  Java Development Kit (JDK): تأكد من تثبيت JDK على جهازك. يمكنك تنزيله من[موقع أوراكل](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java: قم بتنزيل المكتبة من ملف[صفحة الإصدارات Aspose](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): استخدم IDE مثل IntelliJ IDEA أو Eclipse أو NetBeans للحصول على تجربة تطوير أكثر سلاسة.
4. المعرفة الأساسية بـ Java: الإلمام بمفاهيم برمجة Java سيساعدك على فهم وتنفيذ الخطوات الواردة في هذا الدليل.
## حزم الاستيراد
قبل أن نبدأ، تحتاج إلى استيراد الحزم اللازمة. تأكد من تضمين Aspose.Slides for Java في تبعيات مشروعك.
```java
import com.aspose.slides.*;

import java.awt.*;
```
## الخطوة 1: قم بإعداد مشروعك
أولاً، تأكد من إعداد بيئة التطوير لديك بشكل صحيح. اتبع هذه الخطوات لتكوين مشروعك:
### إنشاء مشروع جديد
1. افتح بيئة تطوير متكاملة (IDE) الخاصة بك.
2. إنشاء مشروع جافا جديد.
3.  أضف مكتبة Aspose.Slides for Java إلى مسار بناء مشروعك. يمكنك تنزيل ملف JAR من[صفحة الإصدارات Aspose](https://releases.aspose.com/slides/java/) وإدراجه في مشروعك.
### تهيئة العرض التقديمي
بعد ذلك، قم بتهيئة كائن العرض التقديمي الجديد حيث ستضيف الشرائح والأقسام الخاصة بك.
```java
Presentation pres = new Presentation();
```
## الخطوة 2: إضافة الشرائح والأقسام
في هذه الخطوة، سنقوم بإضافة شرائح إلى العرض التقديمي وتنظيمها في أقسام. هذه المنظمة ضرورية لإنشاء تكبير ملخص.
### أضف شريحة وقسمًا جديدًا
1. إضافة شريحة فارغة: أضف شريحة جديدة إلى العرض التقديمي.
2. تخصيص خلفية الشريحة: قم بتعيين لون تعبئة خالص لخلفية الشريحة.
3. إضافة قسم: قم بتجميع الشريحة في قسم.
إليك الكود لتحقيق ذلك:
```java
// أضف الشريحة الأولى
ISlide slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
slide.getBackground().setType(BackgroundType.OwnBackground);
// أضف القسم الأول
pres.getSections().addSection("Section 1", slide);
```
### كرر لأقسام إضافية
كرر العملية لإضافة المزيد من الشرائح والأقسام:
```java
// أضف الشريحة الثانية والقسم
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.CYAN);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 2", slide);
// أضف الشريحة الثالثة والقسم
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.MAGENTA);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 3", slide);
// أضف الشريحة الرابعة والقسم
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 4", slide);
```
## الخطوة 3: إنشاء إطار التكبير/التصغير الملخص
الآن، سنقوم بإنشاء إطار تكبير ملخص على الشريحة الأولى. سيكون هذا الإطار بمثابة العنصر التفاعلي الذي يسمح للمستخدمين بتكبير الأقسام المختلفة.

1. حدد موقع الشريحة الأولى: استرجع الشريحة الأولى حيث ستضيف إطار تكبير الملخص.
2.  إضافة إطار التكبير/التصغير الملخص: استخدم`addSummaryZoomFrame` طريقة إضافة الإطار.
```java
ISummaryZoomFrame summaryZoomFrame = pres.getSlides().get_Item(0).getShapes().addSummaryZoomFrame(150, 50, 300, 200);
```
## الخطوة 4: احفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي في الموقع الذي تريده. تضمن هذه الخطوة كتابة جميع تغييراتك في ملف.
### حفظ الملف
1. تحديد مسار الإخراج: حدد المسار الذي سيتم حفظ العرض التقديمي فيه.
2.  حفظ العرض التقديمي: استخدم`save` طريقة حفظ الملف بصيغة PPTX.
```java
String resultPath = "Your Output Directory" + "SummaryZoomPresentation.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
### تخلص من كائن العرض التقديمي
تخلص من كائن العرض التقديمي لتحرير أي موارد يستخدمها:
```java
if (pres != null) pres.dispose();
```
## خاتمة
 تهانينا! لقد نجحت في إنشاء تكبير ملخص في PowerPoint باستخدام Aspose.Slides لـ Java. تعمل هذه الميزة على تحسين العروض التقديمية الخاصة بك عن طريق جعلها أكثر تفاعلية وجاذبية. باتباع هذا الدليل، لديك الآن المهارات اللازمة لتنفيذ هذه الميزة في مشاريعك الخاصة. تذكر أن تستكشف[Aspose.Slides لتوثيق جافا](https://reference.aspose.com/slides/java/)لمزيد من الميزات المتقدمة وخيارات التخصيص.
## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java هي مكتبة قوية تسمح للمطورين بإنشاء عروض PowerPoint التقديمية وتعديلها ومعالجتها برمجياً باستخدام Java.
### هل يمكنني استخدام Aspose.Slides لـ Java لإنشاء أنواع أخرى من المحتوى في PowerPoint؟
نعم، يدعم Aspose.Slides for Java مجموعة واسعة من الميزات، بما في ذلك إنشاء الشرائح وإضافة الأشكال والمخططات والجداول وغير ذلك الكثير.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ Java؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Slides لـ Java من[موقع إلكتروني](https://releases.aspose.com/).
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ Java؟
 يمكنك الحصول على ترخيص مؤقت من[Aspose صفحة الشراء](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على المزيد من الأمثلة والدعم لـ Aspose.Slides لـ Java؟
 يمكنك العثور على المزيد من الأمثلة وطلب الدعم على[منتدى دعم Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
