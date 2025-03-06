---
title: قم بتعيين تنسيق التعبئة لعقدة شكل SmartArt في Java
linktitle: قم بتعيين تنسيق التعبئة لعقدة شكل SmartArt في Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تعيين تنسيق التعبئة لعقد أشكال SmartArt في Java باستخدام Aspose.Slides. عزز عروضك التقديمية بألوان نابضة بالحياة ومرئيات آسرة.
weight: 12
url: /ar/java/java-powerpoint-smartart-manipulation/set-fill-format-smartart-shape-node-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
في المشهد الديناميكي لإنشاء المحتوى الرقمي، تبرز Aspose.Slides for Java كأداة قوية لصياغة عروض تقديمية مذهلة بصريًا بسهولة وكفاءة. سواء كنت مطورًا متمرسًا أو بدأت للتو، فإن إتقان فن التعامل مع الأشكال داخل الشرائح يعد أمرًا بالغ الأهمية لإنشاء عروض تقديمية جذابة تترك انطباعًا دائمًا على جمهورك.
## المتطلبات الأساسية
قبل الخوض في عالم إعداد تنسيق التعبئة لعقد شكل SmartArt في Java باستخدام Aspose.Slides، تأكد من توفر المتطلبات الأساسية التالية:
1.  Java Development Kit (JDK): تأكد من تثبيت Java على نظامك. يمكنك تنزيل أحدث إصدار من JDK وتثبيته من Oracle[موقع إلكتروني](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides for Java Library: احصل على Aspose.Slides for Java Library من موقع Aspose الإلكتروني. يمكنك تنزيله من الرابط الموجود في البرنامج التعليمي[رابط التحميل](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): اختر IDE المفضل لديك لتطوير Java. تشمل الخيارات الشائعة IntelliJ IDEA وEclipse وNetBeans.

## حزم الاستيراد
في هذا البرنامج التعليمي، سنستخدم عدة حزم من مكتبة Aspose.Slides لمعالجة أشكال SmartArt وعقدها. قبل أن نبدأ، دعونا نستورد هذه الحزم إلى مشروع Java الخاص بنا:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## الخطوة 1: إنشاء كائن العرض التقديمي
قم بتهيئة كائن العرض التقديمي لبدء العمل مع الشرائح:
```java
Presentation presentation = new Presentation();
```
## الخطوة 2: الوصول إلى الشريحة
استرجع الشريحة التي تريد إضافة شكل SmartArt إليها:
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## الخطوة 3: إضافة شكل SmartArt والعقد
أضف شكل SmartArt إلى الشريحة وأدخل العقد فيه:
```java
ISmartArt chevron = slide.getShapes().addSmartArt(10, 10, 800, 60, SmartArtLayoutType.ClosedChevronProcess);
ISmartArtNode node = chevron.getAllNodes().addNode();
node.getTextFrame().setText("Some text");
```
## الخطوة 4: تعيين لون تعبئة العقدة
قم بتعيين لون التعبئة لكل شكل داخل عقدة SmartArt:
```java
for (ISmartArtShape item : node.getShapes()) {
    item.getFillFormat().setFillType(FillType.Solid);
    item.getFillFormat().getSolidFillColor().setColor(Color.RED);
}
```
## الخطوة 5: حفظ العرض التقديمي
احفظ العرض التقديمي بعد إجراء كافة التعديلات:
```java
presentation.save(dataDir + "FillFormat_SmartArt_ShapeNode_out.pptx", SaveFormat.Pptx);
```

## خاتمة
إن إتقان فن إعداد تنسيق التعبئة لعقد شكل SmartArt في Java باستخدام Aspose.Slides يمكّنك من إنشاء عروض تقديمية جذابة بصريًا تلقى صدى لدى جمهورك. باتباع هذا الدليل التفصيلي والاستفادة من الميزات القوية في Aspose.Slides، يمكنك فتح إمكانيات لا حصر لها لصياغة عروض تقديمية جذابة.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Slides لـ Java مع مكتبات Java الأخرى؟
نعم، يمكن دمج Aspose.Slides for Java بسلاسة مع مكتبات Java الأخرى لتحسين عملية إنشاء العرض التقديمي.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ Java؟
نعم، يمكنك الاستفادة من النسخة التجريبية المجانية من Aspose.Slides لـ Java من الرابط الموجود في البرنامج التعليمي.
### أين يمكنني العثور على الدعم لـ Aspose.Slides لـ Java؟
يمكنك العثور على موارد دعم شاملة، بما في ذلك المنتديات والوثائق، على موقع Aspose الإلكتروني.
### هل يمكنني تخصيص مظهر أشكال SmartArt بشكل أكبر؟
قطعاً! يوفر Aspose.Slides for Java نطاقًا واسعًا من خيارات التخصيص لتخصيص مظهر أشكال SmartArt وفقًا لتفضيلاتك.
### هل Aspose.Slides for Java مناسب لكل من المطورين المبتدئين وذوي الخبرة؟
نعم، Aspose.Slides for Java يلبي احتياجات المطورين من جميع مستويات المهارة، ويقدم واجهات برمجة التطبيقات البديهية والوثائق الشاملة لتسهيل التكامل والاستخدام السهل.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
