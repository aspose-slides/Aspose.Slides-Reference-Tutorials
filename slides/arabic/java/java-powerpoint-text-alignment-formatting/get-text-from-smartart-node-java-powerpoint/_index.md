---
title: الحصول على نص من SmartArt Node في Java PowerPoint
linktitle: الحصول على نص من SmartArt Node في Java PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية استخراج النص من عقد SmartArt في عروض Java PowerPoint التقديمية باستخدام Aspose.Slides. دليل سهل خطوة بخطوة للمطورين.
weight: 14
url: /ar/java/java-powerpoint-text-alignment-formatting/get-text-from-smartart-node-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# الحصول على نص من SmartArt Node في Java PowerPoint

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية استخراج النص من عقد SmartArt في عروض Java PowerPoint التقديمية باستخدام Aspose.Slides. Aspose.Slides هي مكتبة Java قوية تسمح للمطورين بإنشاء عروض PowerPoint التقديمية ومعالجتها وتحويلها برمجياً. يمكن أن يكون استخراج النص من عقد SmartArt مفيدًا للعديد من التطبيقات مثل استخراج البيانات وتحليل المحتوى والمزيد. بنهاية هذا الدليل، سيكون لديك فهم واضح لكيفية استرداد النص من عقد SmartArt بكفاءة باستخدام Aspose.Slides في Java.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. Java Development Kit (JDK): يتطلب Aspose.Slides لـ Java الإصدار JDK 8 أو أعلى.
2.  Aspose.Slides لمكتبة Java: يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): استخدم IntelliJ IDEA أو Eclipse أو أي بيئة تطوير متكاملة من اختيارك مع دعم Java.
4. ملف العرض التقديمي: لديك ملف PowerPoint (.pptx) باستخدام SmartArt الذي تريد استخراج النص منه.
## حزم الاستيراد
للبدء، قم باستيراد فئات Aspose.Slides الضرورية في ملف Java الخاص بك:
```java
import com.aspose.slides.*;
```
## الخطوة 1: قم بإعداد مشروعك
ابدأ بإعداد مشروع Java الخاص بك وتضمين Aspose.Slides for Java في تبعيات مشروعك. تأكد من إضافة ملف Aspose.Slides JAR إلى مسار البناء أو تبعيات Maven/Gradle.
## الخطوة 2: قم بتحميل العرض التقديمي
قم بتحميل ملف عرض PowerPoint التقديمي باستخدام Aspose.Slides.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Presentation.pptx");
```
## الخطوة 3: الوصول إلى SmartArt على الشريحة
قم باسترجاع الشريحة الأولى من العرض التقديمي وقم بالوصول إلى كائن SmartArt.
```java
ISlide slide = presentation.getSlides().get_Item(0);
ISmartArt smartArt = (ISmartArt) slide.getShapes().get_Item(0);
```
## الخطوة 4: استرداد عقد SmartArt
قم بالوصول إلى جميع العقد داخل SmartArt للتكرار عبر أشكال كل عقدة.
```java
ISmartArtNodeCollection smartArtNodes = smartArt.getAllNodes();
for (ISmartArtNode smartArtNode : (Iterable<ISmartArtNode>) smartArtNodes) {
    for (ISmartArtShape nodeShape : smartArtNode.getShapes()) {
        if (nodeShape.getTextFrame() != null)
            System.out.println(nodeShape.getTextFrame().getText());
    }
}
```
## الخطوة 5: التخلص من كائن العرض التقديمي
من الممارسات الجيدة التخلص من كائن العرض التقديمي بمجرد الانتهاء من استخدامه.
```java
finally {
    if (presentation != null) presentation.dispose();
}
```
## خاتمة
في هذا البرنامج التعليمي، تناولنا كيفية استخراج النص من عقد SmartArt في عروض Java PowerPoint التقديمية باستخدام Aspose.Slides. باتباع هذه الخطوات، يمكنك استرداد محتوى النص بشكل فعال من كائنات SmartArt برمجيًا، مما يسهل مهام معالجة المستندات المختلفة في تطبيقات Java الخاصة بك.

## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات قوية تمكن المطورين من إنشاء عروض PowerPoint التقديمية ومعالجتها وتحويلها برمجيًا باستخدام Java.
### كيف يمكنني تنزيل Aspose.Slides لجافا؟
 يمكنك تنزيل Aspose.Slides لـ Java من[هنا](https://releases.aspose.com/slides/java/).
### هل Aspose.Slides for Java مناسب للاستخدام التجاري؟
 نعم، يمكن استخدام Aspose.Slides for Java تجاريًا. يمكنك شراء التراخيص[هنا](https://purchase.aspose.com/buy).
### هل يقدم Aspose.Slides for Java نسخة تجريبية مجانية؟
 نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Slides لـ Java[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على الدعم لـ Aspose.Slides لـ Java؟
 للحصول على المساعدة الفنية ودعم المجتمع، قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
