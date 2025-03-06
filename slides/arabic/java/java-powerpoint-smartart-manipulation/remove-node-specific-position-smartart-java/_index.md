---
title: قم بإزالة العقدة في موضع محدد في SmartArt
linktitle: قم بإزالة العقدة في موضع محدد في SmartArt
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إزالة عقدة في موضع معين داخل SmartArt باستخدام Aspose.Slides لـ Java. تعزيز تخصيص العرض التقديمي دون عناء.
weight: 15
url: /ar/java/java-powerpoint-smartart-manipulation/remove-node-specific-position-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قم بإزالة العقدة في موضع محدد في SmartArt

## مقدمة
في مجال تطوير Java، يظهر Aspose.Slides كأداة قوية لمعالجة العروض التقديمية برمجيًا. سواء كان الأمر يتعلق بإنشاء الشرائح أو تعديلها أو إدارتها، يوفر Aspose.Slides for Java مجموعة قوية من الميزات لتبسيط هذه المهام بكفاءة. إحدى هذه العمليات الشائعة هي إزالة عقدة في موضع محدد داخل كائن SmartArt. يتعمق هذا البرنامج التعليمي في عملية تنفيذ ذلك خطوة بخطوة باستخدام Aspose.Slides لـ Java.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من إعداد المتطلبات الأساسية التالية:
1.  Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيله من[هنا](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides لـ Java: احصل على مكتبة Aspose.Slides لـ Java. يمكنك تنزيله من[هذا الرابط](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): قم بتثبيت IDE مثل IntelliJ IDEA أو Eclipse لكتابة تعليمات Java البرمجية وتنفيذها بسلاسة.

## حزم الاستيراد
في مشروع Java الخاص بك، قم بتضمين الحزم اللازمة للاستفادة من وظائف Aspose.Slides:
```java
import com.aspose.slides.*;
```
## الخطوة 1: قم بتحميل العرض التقديمي
ابدأ بتحميل ملف العرض التقديمي حيث يوجد كائن SmartArt:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "RemoveNodeSpecificPosition.pptx");
```
## الخطوة 2: اجتياز أشكال SmartArt
قم بالتنقل عبر كل شكل في العرض التقديمي لتحديد كائنات SmartArt:
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes()) {
    if (shape instanceof ISmartArt) {
        ISmartArt smart = (ISmartArt) shape;
```
## الخطوة 3: الوصول إلى عقدة SmartArt
قم بالوصول إلى عقدة SmartArt في الموضع المطلوب:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## الخطوة 4: إزالة العقدة التابعة
قم بإزالة العقدة الفرعية في الموضع المحدد:
```java
((ISmartArtNodeCollection) node.getChildNodes()).removeNode(1);
```
## الخطوة 5: حفظ العرض التقديمي
وأخيرا، احفظ العرض التقديمي المعدل:
```java
pres.save(dataDir + "RemoveSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## خاتمة
باستخدام Aspose.Slides for Java، تصبح معالجة كائنات SmartArt داخل العروض التقديمية مهمة واضحة. باتباع الخطوات الموضحة، يمكنك إزالة العقد في مواضع محددة بسلاسة، مما يعزز إمكانات تخصيص العرض التقديمي الخاص بك.
## الأسئلة الشائعة
### هل Aspose.Slides لـ Java مجاني للاستخدام؟
 Aspose.Slides for Java هي مكتبة تجارية، ولكن يمكنك استكشاف وظائفها من خلال نسخة تجريبية مجانية. يزور[هذا الرابط](https://releases.aspose.com/) للبدء.
### أين يمكنني العثور على الدعم للاستفسارات المتعلقة بـ Aspose.Slides؟
 للحصول على أي مساعدة أو استفسارات، يمكنك زيارة منتدى Aspose.Slides[هنا](https://forum.aspose.com/c/slides/11).
### هل يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
 نعم يمكنك الحصول على ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/) لأغراض التقييم.
### كيف يمكنني شراء Aspose.Slides لجافا؟
 لشراء Aspose.Slides لـ Java، قم بزيارة صفحة الشراء[هنا](https://purchase.aspose.com/buy).
### أين يمكنني العثور على وثائق مفصلة عن Aspose.Slides لـ Java؟
 يمكنك الوصول إلى الوثائق الشاملة[هنا](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
