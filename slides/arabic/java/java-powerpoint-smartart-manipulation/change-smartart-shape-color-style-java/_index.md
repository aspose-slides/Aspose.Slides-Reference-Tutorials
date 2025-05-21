---
"description": "تعلم كيفية تغيير ألوان أشكال SmartArt ديناميكيًا في PowerPoint باستخدام Java وAspose.Slides. حسّن مظهرك بسهولة."
"linktitle": "تغيير نمط لون شكل SmartArt باستخدام Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تغيير نمط لون شكل SmartArt باستخدام Java"
"url": "/ar/java/java-powerpoint-smartart-manipulation/change-smartart-shape-color-style-java/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تغيير نمط لون شكل SmartArt باستخدام Java

## مقدمة
في هذا البرنامج التعليمي، سنشرح عملية تغيير أنماط ألوان أشكال SmartArt باستخدام جافا مع Aspose.Slides. تُعد SmartArt ميزة فعّالة في عروض PowerPoint التقديمية، حيث تتيح إنشاء رسومات جذابة بصريًا. بتغيير أنماط ألوان أشكال SmartArt، يمكنك تحسين التصميم العام والتأثير البصري لعروضك التقديمية. سنُقسّم العملية إلى خطوات سهلة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. بيئة تطوير Java: تأكد من تثبيت Java Development Kit (JDK) على نظامك.
2. Aspose.Slides لـ Java: قم بتنزيل Aspose.Slides لـ Java وتثبيته من [موقع إلكتروني](https://releases.aspose.com/slides/java/).
3. المعرفة الأساسية بلغة جافا: ستكون المعرفة بمفاهيم لغة برمجة جافا مفيدة.
## استيراد الحزم
قبل الغوص في الكود، دعنا نستورد الحزم الضرورية:
```java
import com.aspose.slides.*;
```
الآن، دعنا نقسم مثال الكود إلى تعليمات خطوة بخطوة:
## الخطوة 1: تحميل العرض التقديمي
أولاً، نحتاج إلى تحميل عرض PowerPoint الذي يحتوي على شكل SmartArt:
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "AccessSmartArtShape.pptx");
```
## الخطوة 2: التنقل عبر الأشكال
بعد ذلك، سننتقل عبر كل شكل داخل الشريحة الأولى لتحديد أشكال SmartArt:
```java
for (IShape shape : presentation.getSlides().get_Item(0).getShapes())
```
## الخطوة 3: التحقق من نوع SmartArt
بالنسبة لكل شكل، سوف نتحقق مما إذا كان شكل SmartArt:
```java
if (shape instanceof ISmartArt)
```
## الخطوة 4: تغيير نمط اللون
إذا كان الشكل عبارة عن شكل SmartArt، فسنقوم بتغيير نمط لونه:
```java
ISmartArt smart = (ISmartArt) shape;
if (smart.getColorStyle() == SmartArtColorType.ColoredFillAccent1)
{
    smart.setColorStyle(SmartArtColorType.ColorfulAccentColors);
}
```
## الخطوة 5: حفظ العرض التقديمي
وأخيرًا، سنقوم بحفظ العرض التقديمي المعدّل:
```java
presentation.save(dataDir + "ChangeSmartArtColorStyle_out.pptx", SaveFormat.Pptx);
```
## خاتمة
باتباع هذه الخطوات، يمكنك بسهولة تغيير أنماط ألوان أشكال SmartArt في عروض PowerPoint التقديمية باستخدام Java مع Aspose.Slides. جرّب أنماط ألوان مختلفة لتحسين المظهر المرئي لعروضك التقديمية.
## الأسئلة الشائعة
### هل يمكنني تغيير نمط اللون لأشكال SmartArt المحددة فقط؟
نعم، يمكنك تعديل الكود لاستهداف أشكال SmartArt محددة استنادًا إلى متطلباتك.
### هل يدعم Aspose.Slides خيارات معالجة أخرى لـ SmartArt؟
نعم، يوفر Aspose.Slides واجهات برمجة تطبيقات مختلفة للتعامل مع أشكال SmartArt، بما في ذلك تغيير الحجم وإعادة التموضع وإضافة نص.
### هل يمكنني أتمتة هذه العملية لعروض تقديمية متعددة؟
بالتأكيد، يمكنك دمج هذا الكود في نصوص المعالجة الدفعية للتعامل مع العروض التقديمية المتعددة بكفاءة.
### هل Aspose.Slides متوافق مع الإصدارات المختلفة من PowerPoint؟
نعم، يدعم Aspose.Slides مجموعة واسعة من إصدارات PowerPoint، مما يضمن التوافق مع معظم ملفات العرض التقديمي.
### أين يمكنني الحصول على الدعم للاستعلامات المتعلقة بـ Aspose.Slides؟
يمكنك زيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للحصول على المساعدة من المجتمع وموظفي دعم Aspose.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}