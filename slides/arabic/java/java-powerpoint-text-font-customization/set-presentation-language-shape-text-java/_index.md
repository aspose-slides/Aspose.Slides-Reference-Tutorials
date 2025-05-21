---
"description": "تعلّم كيفية أتمتة عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. أنشئ الشرائح، وعدّلها، وحسّنها برمجيًا بسهولة."
"linktitle": "تعيين لغة العرض وشكل النص في Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تعيين لغة العرض وشكل النص في Java"
"url": "/ar/java/java-powerpoint-text-font-customization/set-presentation-language-shape-text-java/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تعيين لغة العرض وشكل النص في Java

## مقدمة
إنشاء عروض PowerPoint التقديمية ومعالجتها برمجيًا باستخدام جافا يُسهّل أتمتة سير العمل ويعزز الإنتاجية. يوفر Aspose.Slides لجافا مجموعة أدوات فعّالة لإنجاز هذه المهام بكفاءة. يرشدك هذا البرنامج التعليمي خلال الخطوات الأساسية لضبط لغة العرض التقديمي وتنسيق النص باستخدام Aspose.Slides لجافا.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك ما يلي:
- تم تثبيت Java Development Kit (JDK)
- Aspose.Slides لمكتبة Java، والتي يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/)
- بيئة التطوير المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse تم إعدادها على نظامك
- المعرفة الأساسية بلغة البرمجة جافا
## استيراد الحزم
للبدء، قم باستيراد حزم Aspose.Slides الضرورية في ملف Java الخاص بك:
```java
import com.aspose.slides.IAutoShape;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;
```
## الخطوة 1: إنشاء كائن عرض تقديمي
ابدأ بالتهيئة `Presentation` هدف:
```java
Presentation pres = new Presentation();
```
يؤدي هذا إلى إنشاء عرض تقديمي جديد في PowerPoint.
## الخطوة 2: إضافة شكل تلقائي وتكوينه
بعد ذلك، أضف شكلًا تلقائيًا إلى الشريحة الأولى وقم بتكوين خصائصه:
```java
ISlide slide = pres.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
```
هنا، نضيف مستطيل AutoShape عند الإحداثيات (50، 50) بأبعاد 200 × 50 بكسل.
## الخطوة 3: تعيين النص واللغة
تعيين محتوى النص وتحديد اللغة للتحقق من الإملاء:
```java
shape.addTextFrame("Text to apply spellcheck language");
shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setLanguageId("en-EN");
```
يستبدل `"Text to apply spellcheck language"` مع النص المطلوب. معرف اللغة `"en-EN"` يحدد اللغة الإنجليزية (الولايات المتحدة).
## الخطوة 4: حفظ العرض التقديمي
احفظ العرض التقديمي المعدّل في دليل الإخراج المحدد:
```java
pres.save("Your Output Directory" + "test1.pptx", SaveFormat.Pptx);
```
تأكد من الاستبدال `"Your Output Directory"` مع مسار الدليل الفعلي الذي تريد حفظ الملف فيه.
## الخطوة 5: التخلص من الموارد
التخلص منها بشكل صحيح `Presentation` هدف تحرير الموارد:
```java
pres.dispose();
```
تعتبر هذه الخطوة ضرورية لتجنب تسرب الذاكرة.

## خاتمة
في الختام، يُبسّط Aspose.Slides for Java عملية إنشاء عروض PowerPoint التقديمية وتعديلها برمجيًا. باتباع هذه الخطوات، يمكنك ضبط لغة العرض التقديمي وتكوين خصائص النص بكفاءة وفقًا لاحتياجاتك.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Slides لـ Java لإنشاء عروض تقديمية PowerPoint من الصفر؟
نعم، يوفر Aspose.Slides واجهات برمجة تطبيقات شاملة لإنشاء العروض التقديمية برمجيًا بالكامل.
### كيف يمكنني تطبيق خطوط مختلفة على النص في شرائح PowerPoint باستخدام Aspose.Slides لـ Java؟
يمكنك تعيين خصائص الخط من خلال `IPortionFormat` الكائنات المرتبطة بأجزاء النص.
### هل هناك نسخة تجريبية متاحة لـ Aspose.Slides لـ Java؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).
### أين يمكنني العثور على وثائق Aspose.Slides لـ Java؟
الوثائق التفصيلية متاحة [هنا](https://reference.aspose.com/slides/java/).
### ما خيارات الدعم المتوفرة لـ Aspose.Slides لـ Java؟
يمكنك زيارة منتدى Aspose.Slides [هنا](https://forum.aspose.com/c/slides/11) لدعم المجتمع.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}