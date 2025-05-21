---
"description": "تعرّف على كيفية ضبط تنسيق التعبئة لعُقد أشكال SmartArt في جافا باستخدام Aspose.Slides. حسّن عروضك التقديمية بألوان زاهية ومرئيات آسرة."
"linktitle": "تعيين تنسيق التعبئة لعقدة شكل SmartArt في Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تعيين تنسيق التعبئة لعقدة شكل SmartArt في Java"
"url": "/ar/java/java-powerpoint-smartart-manipulation/set-fill-format-smartart-shape-node-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تعيين تنسيق التعبئة لعقدة شكل SmartArt في Java

## مقدمة
في ظلّ التطور السريع لإنشاء المحتوى الرقمي، يبرز Aspose.Slides for Java كأداة فعّالة لإنشاء عروض تقديمية مبهرة بصريًا بسهولة وفعالية. سواء كنت مطورًا محترفًا أو مبتدئًا، فإنّ إتقان فنّ التعامل مع الأشكال داخل الشرائح أمرٌ بالغ الأهمية لإنشاء عروض تقديمية آسرة تترك انطباعًا دائمًا لدى جمهورك.
## المتطلبات الأساسية
قبل الخوض في عالم إعداد تنسيق التعبئة لعقد أشكال SmartArt في Java باستخدام Aspose.Slides، تأكد من توفر المتطلبات الأساسية التالية:
1. مجموعة تطوير جافا (JDK): تأكد من تثبيت جافا على نظامك. يمكنك تنزيل أحدث إصدار من JDK وتثبيته من Oracle. [موقع إلكتروني](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. مكتبة Aspose.Slides لجافا: احصل على مكتبة Aspose.Slides لجافا من موقع Aspose الإلكتروني. يمكنك تنزيلها من الرابط المُرفق في البرنامج التعليمي. [رابط التحميل](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): اختر بيئة التطوير المتكاملة المُفضّلة لديك لتطوير جافا. من الخيارات الشائعة IntelliJ IDEA وEclipse وNetBeans.

## استيراد الحزم
في هذا البرنامج التعليمي، سنستخدم عدة حزم من مكتبة Aspose.Slides للتعامل مع أشكال SmartArt وعُقدها. قبل البدء، لنستورد هذه الحزم إلى مشروع Java الخاص بنا:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## الخطوة 1: إنشاء كائن عرض تقديمي
قم بتهيئة كائن العرض التقديمي لبدء العمل مع الشرائح:
```java
Presentation presentation = new Presentation();
```
## الخطوة 2: الوصول إلى الشريحة
استرداد الشريحة حيث تريد إضافة شكل SmartArt:
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## الخطوة 3: إضافة أشكال SmartArt والعقد
أضف شكل SmartArt إلى الشريحة وأدرج العقد فيه:
```java
ISmartArt chevron = slide.getShapes().addSmartArt(10, 10, 800, 60, SmartArtLayoutType.ClosedChevronProcess);
ISmartArtNode node = chevron.getAllNodes().addNode();
node.getTextFrame().setText("Some text");
```
## الخطوة 4: تعيين لون تعبئة العقدة
تعيين لون التعبئة لكل شكل داخل عقدة SmartArt:
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
إتقان فن ضبط تنسيق التعبئة لعقد أشكال SmartArt في جافا باستخدام Aspose.Slides يُمكّنك من إنشاء عروض تقديمية جذابة بصريًا تلقى صدى لدى جمهورك. باتباع هذا الدليل المفصل والاستفادة من الميزات القوية لـ Aspose.Slides، يمكنك فتح آفاق لا حصر لها لتصميم عروض تقديمية جذابة.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Slides لـ Java مع مكتبات Java الأخرى؟
نعم، يمكن دمج Aspose.Slides for Java بسلاسة مع مكتبات Java الأخرى لتحسين عملية إنشاء العرض التقديمي الخاص بك.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لنظام Java؟
نعم، يمكنك الاستفادة من نسخة تجريبية مجانية من Aspose.Slides for Java من الرابط المقدم في البرنامج التعليمي.
### أين يمكنني العثور على الدعم لـ Aspose.Slides لـ Java؟
يمكنك العثور على موارد دعم شاملة، بما في ذلك المنتديات والوثائق، على موقع Aspose.
### هل يمكنني تخصيص مظهر أشكال SmartArt بشكل أكبر؟
بالتأكيد! يوفر Aspose.Slides لـ Java مجموعة واسعة من خيارات التخصيص لتخصيص مظهر أشكال SmartArt وفقًا لتفضيلاتك.
### هل Aspose.Slides for Java مناسب للمبتدئين والمطورين ذوي الخبرة؟
نعم، يخدم Aspose.Slides for Java المطورين من جميع مستويات المهارة، ويوفر واجهات برمجة تطبيقات بديهية ووثائق شاملة لتسهيل التكامل والاستخدام بسهولة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}