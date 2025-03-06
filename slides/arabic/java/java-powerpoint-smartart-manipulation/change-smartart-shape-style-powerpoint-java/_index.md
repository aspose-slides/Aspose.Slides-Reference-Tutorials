---
title: تغيير نمط شكل SmartArt في PowerPoint باستخدام Java
linktitle: تغيير نمط شكل SmartArt في PowerPoint باستخدام Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تغيير أنماط SmartArt في عروض PowerPoint التقديمية باستخدام Java مع Aspose.Slides لـ Java. تعزيز العروض التقديمية الخاصة بك.
weight: 23
url: /ar/java/java-powerpoint-smartart-manipulation/change-smartart-shape-style-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تغيير نمط شكل SmartArt في PowerPoint باستخدام Java

## مقدمة
في عالم تطوير Java، غالبًا ما يكون إنشاء عروض تقديمية قوية أمرًا ضروريًا. سواء أكان ذلك لأغراض تجارية، أو للأغراض التعليمية، أو ببساطة لمشاركة المعلومات، فإن عروض PowerPoint التقديمية هي وسيلة شائعة. ومع ذلك، في بعض الأحيان قد لا تلبي الأنماط والتنسيقات الافتراضية التي يوفرها PowerPoint احتياجاتنا بشكل كامل. هذا هو المكان الذي يلعب فيه Aspose.Slides for Java.
Aspose.Slides for Java هي مكتبة قوية تسمح لمطوري Java بالعمل مع عروض PowerPoint التقديمية برمجياً. فهو يوفر مجموعة واسعة من الميزات، بما في ذلك القدرة على التعامل مع الأشكال والأنماط والرسوم المتحركة، وأكثر من ذلك بكثير. في هذا البرنامج التعليمي، سوف نركز على مهمة واحدة محددة: تغيير نمط شكل SmartArt في عروض PowerPoint التقديمية باستخدام Java.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، هناك بعض المتطلبات الأساسية التي يجب أن تتوفر لديك:
1. Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيل أحدث إصدار وتثبيته من موقع Oracle الإلكتروني.
2. Aspose.Slides for Java Library: ستحتاج إلى تنزيل مكتبة Aspose.Slides for Java وتضمينها في مشروعك. يمكنك العثور على رابط التحميل[هنا](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): اختر IDE المفضل لديك لتطوير Java. تعد IntelliJ IDEA أو Eclipse أو NetBeans من الخيارات الشائعة.

## حزم الاستيراد
قبل أن نبدأ بالبرمجة، فلنستورد الحزم الضرورية لمشروع Java الخاص بنا. ستمكننا هذه الحزم من العمل مع وظائف Aspose.Slides بسلاسة.
```java
import com.aspose.slides.*;
```
## الخطوة 1: قم بتحميل العرض التقديمي
أولاً، نحتاج إلى تحميل عرض PowerPoint التقديمي الذي نريد تعديله.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "AccessSmartArtShape.pptx");
```
## الخطوة 2: اجتياز الأشكال
بعد ذلك، سنتنقل عبر كل شكل داخل الشريحة الأولى من العرض التقديمي.
```java
for (IShape shape : presentation.getSlides().get_Item(0).getShapes())
```
## الخطوة 3: التحقق من نوع SmartArt
بالنسبة لكل شكل، سوف نتحقق مما إذا كان شكل SmartArt.
```java
if (shape instanceof ISmartArt)
```
## الخطوة 4: الإرسال إلى SmartArt
 إذا كان الشكل عبارة عن SmartArt، فسنرسله إلى`ISmartArt` واجهه المستخدم.
```java
ISmartArt smart = (ISmartArt) shape;
```
## الخطوة 5: التحقق من النمط وتغييره
سنقوم بعد ذلك بالتحقق من النمط الحالي لـ SmartArt وتغييره إذا لزم الأمر.
```java
if (smart.getQuickStyle() == SmartArtQuickStyleType.SimpleFill)
{
    smart.setQuickStyle(SmartArtQuickStyleType.Cartoon);
}
```
## الخطوة 6: حفظ العرض التقديمي
وأخيرًا، سنقوم بحفظ العرض التقديمي المعدل في ملف جديد.
```java
presentation.save(dataDir + "ChangeSmartArtStyle_out.pptx", SaveFormat.Pptx);
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تغيير نمط شكل SmartArt في عروض PowerPoint التقديمية باستخدام Java وAspose.Slides لمكتبة Java. باتباع الدليل الموضح خطوة بخطوة، يمكنك بسهولة تخصيص مظهر أشكال SmartArt لتناسب احتياجات العرض التقديمي بشكل أفضل.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Slides لـ Java مع مكتبات Java الأخرى؟
نعم، يمكن دمج Aspose.Slides for Java مع مكتبات Java الأخرى بسلاسة لتحسين وظائف تطبيقاتك.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ Java؟
 نعم، يمكنك الاستفادة من النسخة التجريبية المجانية من Aspose.Slides لـ Java من[هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على الدعم لـ Aspose.Slides لـ Java؟
 يمكنك الحصول على الدعم لـ Aspose.Slides لـ Java من خلال زيارة الموقع[المنتدى](https://forum.aspose.com/c/slides/11).
### هل يمكنني شراء ترخيص مؤقت لـ Aspose.Slides لـ Java؟
 نعم، يمكنك شراء ترخيص مؤقت لـ Aspose.Slides for Java من[هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على وثائق مفصلة عن Aspose.Slides لـ Java؟
 يمكنك العثور على وثائق مفصلة عن Aspose.Slides لـ Java[هنا](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
