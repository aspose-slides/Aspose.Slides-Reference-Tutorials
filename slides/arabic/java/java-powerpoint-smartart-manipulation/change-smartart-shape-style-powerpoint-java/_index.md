---
"description": "تعلّم كيفية تغيير أنماط SmartArt في عروض PowerPoint التقديمية باستخدام Java مع Aspose.Slides for Java. حسّن عروضك التقديمية."
"linktitle": "تغيير نمط شكل SmartArt في PowerPoint باستخدام Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تغيير نمط شكل SmartArt في PowerPoint باستخدام Java"
"url": "/ar/java/java-powerpoint-smartart-manipulation/change-smartart-shape-style-powerpoint-java/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تغيير نمط شكل SmartArt في PowerPoint باستخدام Java

## مقدمة
في عالم تطوير جافا، يُعدّ إنشاء عروض تقديمية فعّالة أمرًا ضروريًا. سواءً كان ذلك لعروض تقديمية تجارية، أو لأغراض تعليمية، أو حتى لمشاركة المعلومات، تُعدّ عروض PowerPoint التقديمية وسيلة شائعة. مع ذلك، قد لا تُلبّي الأنماط والتنسيقات الافتراضية التي يُقدّمها PowerPoint احتياجاتنا بالكامل في بعض الأحيان. وهنا يأتي دور Aspose.Slides for Java.
Aspose.Slides لجافا هي مكتبة قوية تُمكّن مطوري جافا من العمل مع عروض PowerPoint التقديمية برمجيًا. تُوفر مجموعة واسعة من الميزات، بما في ذلك إمكانية التحكم في الأشكال والأنماط والرسوم المتحركة، وغيرها الكثير. في هذا البرنامج التعليمي، سنركز على مهمة محددة: تغيير نمط شكل SmartArt في عروض PowerPoint التقديمية باستخدام جافا.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، هناك بعض المتطلبات الأساسية التي يجب أن تكون موجودة:
1. مجموعة تطوير جافا (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيل أحدث إصدار وتثبيته من موقع Oracle الإلكتروني.
2. مكتبة Aspose.Slides لجافا: ستحتاج إلى تنزيل مكتبة Aspose.Slides لجافا وتضمينها في مشروعك. يمكنك العثور على رابط التنزيل. [هنا](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): اختر بيئة التطوير المتكاملة المُفضّلة لديك لتطوير Java. IntelliJ IDEA، أو Eclipse، أو NetBeans خيارات شائعة.

## استيراد الحزم
قبل البدء بالبرمجة، لنستورد الحزم اللازمة إلى مشروع جافا. ستمكننا هذه الحزم من العمل مع وظائف Aspose.Slides بسلاسة.
```java
import com.aspose.slides.*;
```
## الخطوة 1: تحميل العرض التقديمي
أولاً، نحتاج إلى تحميل عرض PowerPoint الذي نريد تعديله.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "AccessSmartArtShape.pptx");
```
## الخطوة 2: التنقل عبر الأشكال
بعد ذلك، سوف ننتقل عبر كل الأشكال الموجودة داخل الشريحة الأولى من العرض التقديمي.
```java
for (IShape shape : presentation.getSlides().get_Item(0).getShapes())
```
## الخطوة 3: التحقق من نوع SmartArt
بالنسبة لكل شكل، سوف نتحقق مما إذا كان شكل SmartArt.
```java
if (shape instanceof ISmartArt)
```
## الخطوة 4: الإرسال إلى SmartArt
إذا كان الشكل عبارة عن SmartArt، فسوف نقوم بإرساله إلى `ISmartArt` واجهة.
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
وأخيرًا، سنقوم بحفظ العرض التقديمي المعدّل في ملف جديد.
```java
presentation.save(dataDir + "ChangeSmartArtStyle_out.pptx", SaveFormat.Pptx);
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تغيير نمط أشكال SmartArt في عروض PowerPoint التقديمية باستخدام Java ومكتبة Aspose.Slides لـ Java. باتباع هذا الدليل التفصيلي، يمكنك بسهولة تخصيص مظهر أشكال SmartArt لتناسب احتياجات عرضك التقديمي بشكل أفضل.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Slides لـ Java مع مكتبات Java الأخرى؟
نعم، يمكن دمج Aspose.Slides for Java مع مكتبات Java الأخرى بسلاسة لتحسين وظائف تطبيقاتك.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لنظام Java؟
نعم، يمكنك الاستفادة من النسخة التجريبية المجانية من Aspose.Slides لـ Java من [هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على الدعم لـ Aspose.Slides لـ Java؟
يمكنك الحصول على الدعم لـ Aspose.Slides لـ Java من خلال زيارة [المنتدى](https://forum.aspose.com/c/slides/11).
### هل يمكنني شراء ترخيص مؤقت لـ Aspose.Slides لـ Java؟
نعم، يمكنك شراء ترخيص مؤقت لـ Aspose.Slides لـ Java من [هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على وثائق مفصلة لـ Aspose.Slides لـ Java؟
يمكنك العثور على وثائق مفصلة لـ Aspose.Slides لـ Java [هنا](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}