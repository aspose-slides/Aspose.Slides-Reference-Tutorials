---
title: الوصول إلى العقد التابعة في SmartArt باستخدام Java
linktitle: الوصول إلى العقد التابعة في SmartArt باستخدام Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية الوصول إلى العقد الفرعية ومعالجتها في SmartArt باستخدام Aspose.Slides لـ Java باستخدام هذا الدليل التفصيلي خطوة بخطوة.
weight: 10
url: /ar/java/java-powerpoint-smartart-manipulation/access-child-nodes-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# الوصول إلى العقد التابعة في SmartArt باستخدام Java

## مقدمة
هل تساءلت يومًا كيف يمكنك التعامل مع رسومات SmartArt في عروضك التقديمية برمجيًا؟ Aspose.Slides for Java هي مكتبتك المفضلة لإدارة عروض PowerPoint التقديمية وتحريرها. تسمح هذه الأداة القوية للمطورين بالوصول إلى العناصر المختلفة ومعالجتها داخل العرض التقديمي، بما في ذلك رسومات SmartArt. في هذا البرنامج التعليمي، سنرشدك خلال الوصول إلى العقد الفرعية في SmartArt باستخدام Java، مما يجعل عروضك التقديمية أكثر ديناميكية وتفاعلية. بحلول نهاية هذا الدليل، ستكون مجهزًا بالمعرفة اللازمة لاجتياز عقد SmartArt ومعالجتها بسهولة.
## المتطلبات الأساسية
قبل الغوص في الكود، تأكد من توفر المتطلبات الأساسية التالية:
-  Java Development Kit (JDK): تأكد من تثبيت JDK على جهازك. يمكنك تنزيله من[موقع جافا](https://www.oracle.com/java/technologies/javase-downloads.html).
-  Aspose.Slides for Java: قم بتنزيل مكتبة Aspose.Slides وتضمينها في مشروعك. يمكنك الحصول عليه من[هنا](https://releases.aspose.com/slides/java/).
- بيئة التطوير المتكاملة (IDE): استخدم IDE مثل IntelliJ IDEA أو Eclipse للحصول على تجربة ترميز أفضل.
- ملف العرض التقديمي: احصل على ملف PowerPoint يحتوي على رسومات SmartArt جاهز للمعالجة.
## حزم الاستيراد
أولاً، ستحتاج إلى استيراد الحزم الضرورية من Aspose.Slides. تعتبر هذه الواردات ضرورية للوصول إلى عناصر العرض التقديمي ومعالجتها.
```java
import com.aspose.slides.*;
```
دعونا نقسم عملية الوصول إلى العقد الفرعية في SmartArt إلى خطوات بسيطة يمكن التحكم فيها.
## الخطوة 1: إعداد بيئتك
قبل أن تتمكن من التعامل مع العرض التقديمي، تحتاج إلى إعداد بيئة التطوير الخاصة بك عن طريق تضمين مكتبة Aspose.Slides في مشروعك.
1.  تنزيل Aspose.Slides: احصل على المكتبة من[رابط التحميل](https://releases.aspose.com/slides/java/).
2. تضمين المكتبة: أضف ملف JAR الذي تم تنزيله إلى مسار إنشاء مشروعك.
## الخطوة 2: قم بتحميل العرض التقديمي
قم بتحميل عرض PowerPoint التقديمي الذي يحتوي على رسم SmartArt الذي تريد معالجته.
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "AccessChildNodes.pptx");
```
## الخطوة 3: الوصول إلى شكل SmartArt
قم بالتنقل عبر الأشكال الموجودة في الشريحة الأولى للعثور على شكل SmartArt.
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes()) {
    if (shape instanceof SmartArt) {
        ISmartArt smart = (ISmartArt) shape;
        // سيتم اتباع خطوات أخرى هنا
    }
}
```
## الخطوة 4: اجتياز عقد SmartArt
بمجرد أن تتمكن من الوصول إلى شكل SmartArt، قم بالتنقل عبر كافة العقد الخاصة به.
```java
for (int i = 0; i < smart.getAllNodes().size(); i++) {
    ISmartArtNode node0 = (ISmartArtNode) smart.getAllNodes().get_Item(i);
    // سيتم اتباع خطوات أخرى هنا
}
```
## الخطوة 5: الوصول إلى العقد الفرعية
داخل كل عقدة SmartArt، قم بالوصول إلى العقد الفرعية الخاصة بها.
```java
for (int j = 0; j < node0.getChildNodes().size(); j++) {
    ISmartArtNode node = (ISmartArtNode) node0.getChildNodes().get_Item(j);
    // سيتم اتباع خطوات أخرى هنا
}
```
## الخطوة 6: طباعة تفاصيل العقدة
اطبع تفاصيل كل عقدة فرعية، مثل النص والمستوى والموضع.
```java
String outString = String.format("j = %d, Text = %s, Level = %d, Position = %d", j, node.getTextFrame().getText(), node.getLevel(), node.getPosition());
System.out.println(outString);
```
## الخطوة 7: تنظيف الموارد
وأخيرًا، تأكد من التخلص من كائن العرض التقديمي لتحرير الموارد.
```java
if (pres != null) pres.dispose();
```
## خاتمة
باتباع هذه الخطوات، يمكنك الوصول بكفاءة إلى العقد الفرعية ومعالجتها في SmartArt باستخدام Aspose.Slides for Java. تعمل هذه المكتبة القوية على تبسيط عملية التعامل مع عروض PowerPoint التقديمية برمجياً، مما يتيح لك إنشاء محتوى ديناميكي وتفاعلي. سواء كنت تقوم بأتمتة إنشاء التقارير أو تحسين العروض التقديمية، فإن Aspose.Slides يوفر الأدوات التي تحتاجها.
## الأسئلة الشائعة
### هل يمكنني التعامل مع العناصر الأخرى في العرض التقديمي باستخدام Aspose.Slides لـ Java؟
نعم، يتيح لك Aspose.Slides for Java التعامل مع العناصر المختلفة مثل النص والأشكال والصور والمخططات داخل العرض التقديمي.
### هل Aspose.Slides لـ Java مجاني للاستخدام؟
 يقدم Aspose.Slides for Java نسخة تجريبية مجانية. لمواصلة الاستخدام، يمكنك شراء ترخيص من[موقع إلكتروني](https://purchase.aspose.com/buy).
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ Java؟
 يمكنك الحصول على ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ Java؟
 الوثائق متاحة[هنا](https://reference.aspose.com/slides/java/).
### ما هو أفضل بيئة تطوير متكاملة (IDE) للتطوير باستخدام Aspose.Slides لـ Java؟
IntelliJ IDEA وEclipse هما بيئات تطوير متكاملة شائعة تعمل بشكل جيد مع Aspose.Slides لـ Java.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
