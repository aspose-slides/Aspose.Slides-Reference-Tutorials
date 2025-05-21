---
"description": "تعلّم كيفية استخراج النص من عُقد SmartArt في عروض PowerPoint التقديمية بلغة Java باستخدام Aspose.Slides. دليل سهل وخطوة بخطوة للمطورين."
"linktitle": "الحصول على نص من عقدة SmartArt في Java PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "الحصول على نص من عقدة SmartArt في Java PowerPoint"
"url": "/ar/java/java-powerpoint-text-alignment-formatting/get-text-from-smartart-node-java-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# الحصول على نص من عقدة SmartArt في Java PowerPoint

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية استخراج النص من عقد SmartArt في عروض PowerPoint التقديمية بلغة Java باستخدام Aspose.Slides. Aspose.Slides هي مكتبة Java فعّالة تُمكّن المطورين من إنشاء عروض PowerPoint التقديمية وتعديلها وتحويلها برمجيًا. يُمكن أن يكون استخراج النص من عقد SmartArt مفيدًا لتطبيقات مُختلفة، مثل استخراج البيانات وتحليل المحتوى وغيرها. بنهاية هذا الدليل، ستُصبح لديك فهم واضح لكيفية استرداد النص من عقد SmartArt بكفاءة باستخدام Aspose.Slides في Java.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. مجموعة تطوير Java (JDK): يتطلب Aspose.Slides for Java إصدار JDK 8 أو أعلى.
2. Aspose.Slides لمكتبة Java: يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): استخدم IntelliJ IDEA، أو Eclipse، أو أي بيئة تطوير متكاملة من اختيارك مع دعم Java.
4. ملف العرض التقديمي: لديك ملف PowerPoint (.pptx) يحتوي على SmartArt وتريد استخراج النص منه.
## استيراد الحزم
للبدء، قم باستيراد فئات Aspose.Slides الضرورية في ملف Java الخاص بك:
```java
import com.aspose.slides.*;
```
## الخطوة 1: إعداد مشروعك
ابدأ بإعداد مشروع جافا الخاص بك وتضمين Aspose.Slides for Java في تبعيات مشروعك. تأكد من إضافة ملف Aspose.Slides JAR إلى مسار البناء أو تبعيات Maven/Gradle.
## الخطوة 2: تحميل العرض التقديمي
قم بتحميل ملف العرض التقديمي PowerPoint باستخدام Aspose.Slides.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Presentation.pptx");
```
## الخطوة 3: الوصول إلى SmartArt على الشريحة
استرداد الشريحة الأولى من العرض التقديمي والوصول إلى كائن SmartArt.
```java
ISlide slide = presentation.getSlides().get_Item(0);
ISmartArt smartArt = (ISmartArt) slide.getShapes().get_Item(0);
```
## الخطوة 4: استرداد عقد SmartArt
قم بالوصول إلى جميع العقد داخل SmartArt للتنقل عبر أشكال كل عقدة.
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
من الجيد التخلص من كائن العرض التقديمي بمجرد الانتهاء من استخدامه.
```java
finally {
    if (presentation != null) presentation.dispose();
}
```
## خاتمة
في هذا البرنامج التعليمي، تناولنا كيفية استخراج النص من عُقد SmartArt في عروض PowerPoint التقديمية باستخدام Aspose.Slides. باتباع هذه الخطوات، يمكنك استرداد محتوى النص من كائنات SmartArt برمجيًا بفعالية، مما يُسهّل مهام معالجة المستندات المختلفة في تطبيقات Java.

## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات قوية تتيح للمطورين إنشاء عروض PowerPoint ومعالجتها وتحويلها برمجيًا باستخدام Java.
### كيف يمكنني تنزيل Aspose.Slides لـ Java؟
يمكنك تنزيل Aspose.Slides لـ Java من [هنا](https://releases.aspose.com/slides/java/).
### هل Aspose.Slides for Java مناسب للاستخدام التجاري؟
نعم، يُمكن استخدام Aspose.Slides لجافا تجاريًا. يُمكنك شراء التراخيص. [هنا](https://purchase.aspose.com/buy).
### هل يوفر Aspose.Slides for Java نسخة تجريبية مجانية؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Slides لـ Java [هنا](https://releases.aspose.com/).
### أين يمكنني العثور على الدعم لـ Aspose.Slides لـ Java؟
للحصول على المساعدة الفنية ودعم المجتمع، قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}