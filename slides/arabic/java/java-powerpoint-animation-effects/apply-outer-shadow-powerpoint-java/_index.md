---
"description": "تعلّم كيفية تطبيق تأثير الظل الخارجي في PowerPoint باستخدام جافا مع Aspose.Slides. حسّن عروضك التقديمية بعمق وجاذبية بصرية."
"linktitle": "تطبيق الظل الخارجي في PowerPoint باستخدام Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تطبيق الظل الخارجي في PowerPoint باستخدام Java"
"url": "/ar/java/java-powerpoint-animation-effects/apply-outer-shadow-powerpoint-java/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تطبيق الظل الخارجي في PowerPoint باستخدام Java

## مقدمة
غالبًا ما يتطلب إنشاء عروض PowerPoint جذابة بصريًا إضافة تأثيرات متنوعة للأشكال والنصوص. أحد هذه التأثيرات هو الظل الخارجي، الذي يُبرز العناصر ويضيف عمقًا إلى شرائحك. في هذا البرنامج التعليمي، ستتعلم كيفية تطبيق تأثير الظل الخارجي على شكل في PowerPoint باستخدام Java مع Aspose.Slides.
## المتطلبات الأساسية

قبل أن تبدأ هذا البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:

1. مجموعة تطوير جافا (JDK): تأكد من تثبيت جافا على نظامك. يمكنك تنزيل أحدث إصدار من JDK وتثبيته من موقع Oracle الإلكتروني.

2. Aspose.Slides لـ Java: قم بتنزيل Aspose.Slides لـ Java وتثبيته من [صفحة التحميل](https://releases.aspose.com/slides/java/).

3. بيئة التطوير المتكاملة (IDE): اختر بيئة التطوير المتكاملة Java المفضلة لديك مثل Eclipse أو IntelliJ IDEA أو NetBeans للترميز وتشغيل تطبيقات Java.

4. المعرفة الأساسية بلغة جافا: ستكون المعرفة بأساسيات لغة برمجة جافا والمفاهيم الموجهة للكائنات مفيدة لفهم أمثلة التعليمات البرمجية.

## استيراد الحزم

أولاً، قم باستيراد الحزم اللازمة للعمل مع Aspose.Slides والوظائف ذات الصلة في مشروع Java الخاص بك:

```java
import com.aspose.slides.*;
```

الآن دعنا نقسم كود المثال إلى خطوات متعددة لتطبيق تأثير الظل الخارجي على شكل في PowerPoint باستخدام Java مع Aspose.Slides:

## الخطوة 1: إعداد بيئة مشروعك

قم بإنشاء مشروع Java جديد في بيئة التطوير المتكاملة المفضلة لديك وأضف مكتبة Aspose.Slides for Java إلى مسار بناء مشروعك.

## الخطوة 2: تهيئة كائن العرض التقديمي

إنشاء مثيل لـ `Presentation` الفئة، التي تمثل ملف عرض تقديمي PowerPoint.

```java
Presentation presentation = new Presentation();
```

## الخطوة 3: إضافة شريحة وشكل

احصل على مرجع للشريحة التي تريد إضافة الشكل إليها، ثم أضف شكلًا تلقائيًا (على سبيل المثال، مستطيل) إلى الشريحة.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 400, 300);
```

## الخطوة 4: تخصيص الشكل

قم بتعيين نوع التعبئة للشكل إلى "NoFill" وأضف نصًا إلى الشكل.

```java
shape.getFillFormat().setFillType(FillType.NoFill);
shape.addTextFrame("Aspose TextBox");
```

## الخطوة 5: تخصيص النص

الوصول إلى خصائص النص الخاصة بالشكل وتخصيص حجم الخط.

```java
IPortion portion = shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0);
IPortionFormat portionFormat = portion.getPortionFormat();
portionFormat.setFontHeight(50);
```

## الخطوة 6: تمكين تأثير الظل الخارجي

تمكين تأثير الظل الخارجي لجزء النص.

```java
IEffectFormat effectFormat = portionFormat.getEffectFormat();
effectFormat.enableOuterShadowEffect();
```

## الخطوة 7: تعيين معلمات الظل

قم بتحديد المعلمات الخاصة بتأثير الظل الخارجي، مثل نصف قطر التمويه، والاتجاه، والمسافة، ولون الظل.

```java
effectFormat.getOuterShadowEffect().setBlurRadius(8.0);
effectFormat.getOuterShadowEffect().setDirection(90.0F);
effectFormat.getOuterShadowEffect().setDistance(6.0);
effectFormat.getOuterShadowEffect().getShadowColor().setB((byte) 189);
effectFormat.getOuterShadowEffect().getShadowColor().setColorType(ColorType.Scheme);
effectFormat.getOuterShadowEffect().getShadowColor().setSchemeColor(SchemeColor.Accent1);
```

## الخطوة 8: حفظ العرض التقديمي

احفظ العرض التقديمي المعدّل مع تطبيق تأثير الظل الخارجي على الشكل.

```java
presentation.save("output.pptx", SaveFormat.Pptx);
```

## خاتمة

تهانينا! لقد نجحت في تطبيق تأثير الظل الخارجي على شكل في PowerPoint باستخدام جافا مع Aspose.Slides. جرّب معلمات مختلفة لتحقيق التأثيرات المرئية المطلوبة في عروضك التقديمية.

## الأسئلة الشائعة

### هل يمكنني تطبيق تأثير الظل الخارجي على أشكال أخرى غير المستطيلات؟
نعم، يمكنك تطبيق تأثير الظل الخارجي على الأشكال المختلفة التي يدعمها Aspose.Slides، مثل الدوائر والمثلثات والأشكال المخصصة.

### هل من الممكن تخصيص لون الظل وكثافته؟
بالتأكيد! لديك تحكم كامل في إعدادات الظل، بما في ذلك اللون، ونصف قطر التمويه، والاتجاه، والمسافة.

### هل يمكنني تطبيق تأثيرات متعددة على نفس الشكل؟
نعم، يمكنك الجمع بين تأثيرات متعددة مثل الظل الخارجي، والظل الداخلي، والتوهج، والانعكاس لتعزيز الجاذبية البصرية للأشكال والنصوص في عروضك التقديمية.

### هل يدعم Aspose.Slides تطبيق التأثيرات على عناصر النص؟
نعم، يمكنك تطبيق التأثيرات ليس فقط على الأشكال ولكن أيضًا على أجزاء النص الفردية داخل الأشكال، مما يمنحك مرونة كبيرة في تصميم الشرائح الخاصة بك.

### أين يمكنني العثور على المزيد من الموارد والدعم لـ Aspose.Slides؟
يمكنك الرجوع إلى [التوثيق](https://reference.aspose.com/slides/java/) للحصول على مراجع API التفصيلية واستكشاف [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع والمناقشات.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}