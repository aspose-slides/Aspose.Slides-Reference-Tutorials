---
title: تطبيق الظل الخارجي في PowerPoint مع Java
linktitle: تطبيق الظل الخارجي في PowerPoint مع Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تطبيق تأثير الظل الخارجي في PowerPoint باستخدام Java باستخدام Aspose.Slides. قم بتحسين عروضك التقديمية بعمق وجاذبية بصرية.
weight: 13
url: /ar/java/java-powerpoint-animation-effects/apply-outer-shadow-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
غالبًا ما يتضمن إنشاء عروض PowerPoint التقديمية الجذابة إضافة تأثيرات متنوعة إلى الأشكال والنص. أحد هذه التأثيرات هو الظل الخارجي، الذي يمكن أن يجعل العناصر بارزة ويضيف عمقًا إلى شرائحك. في هذا البرنامج التعليمي، ستتعلم كيفية تطبيق تأثير الظل الخارجي على شكل في PowerPoint باستخدام Java مع Aspose.Slides.
## المتطلبات الأساسية

قبل أن تبدأ هذا البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:

1. Java Development Kit (JDK): تأكد من تثبيت Java على نظامك. يمكنك تنزيل أحدث إصدار من JDK وتثبيته من موقع Oracle الإلكتروني.

2.  Aspose.Slides لـ Java: قم بتنزيل Aspose.Slides لـ Java وتثبيته من[صفحة التحميل](https://releases.aspose.com/slides/java/).

3. بيئة التطوير المتكاملة (IDE): اختر Java IDE المفضل لديك مثل Eclipse أو IntelliJ IDEA أو NetBeans لتشفير تطبيقات Java وتشغيلها.

4. معرفة Java الأساسية: سيكون الإلمام بأساسيات لغة برمجة Java والمفاهيم الموجهة للكائنات مفيدًا لفهم أمثلة التعليمات البرمجية.

## حزم الاستيراد

أولاً، قم باستيراد الحزم اللازمة للعمل مع Aspose.Slides والوظائف ذات الصلة في مشروع Java الخاص بك:

```java
import com.aspose.slides.*;
```

لنقم الآن بتقسيم كود المثال إلى خطوات متعددة لتطبيق تأثير الظل الخارجي على شكل في PowerPoint باستخدام Java مع Aspose.Slides:

## الخطوة 1: قم بإعداد بيئة مشروعك

أنشئ مشروع Java جديدًا في بيئة التطوير المتكاملة (IDE) المفضلة لديك وأضف مكتبة Aspose.Slides for Java إلى مسار بناء مشروعك.

## الخطوة 2: تهيئة كائن العرض التقديمي

 إنشاء مثيل لـ`Presentation` فئة، والتي تمثل ملف عرض تقديمي ل PowerPoint.

```java
Presentation presentation = new Presentation();
```

## الخطوة 3: إضافة شريحة وشكل

احصل على مرجع للشريحة التي تريد إضافة الشكل إليها، ثم قم بإضافة شكل تلقائي (على سبيل المثال، مستطيل) إلى الشريحة.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 400, 300);
```

## الخطوة 4: تخصيص الشكل

اضبط نوع تعبئة الشكل على "NoFill" وأضف نصًا إلى الشكل.

```java
shape.getFillFormat().setFillType(FillType.NoFill);
shape.addTextFrame("Aspose TextBox");
```

## الخطوة 5: تخصيص النص

الوصول إلى خصائص النص للشكل وتخصيص حجم الخط.

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

حدد معلمات تأثير الظل الخارجي، مثل نصف قطر التمويه والاتجاه والمسافة ولون الظل.

```java
effectFormat.getOuterShadowEffect().setBlurRadius(8.0);
effectFormat.getOuterShadowEffect().setDirection(90.0F);
effectFormat.getOuterShadowEffect().setDistance(6.0);
effectFormat.getOuterShadowEffect().getShadowColor().setB((byte) 189);
effectFormat.getOuterShadowEffect().getShadowColor().setColorType(ColorType.Scheme);
effectFormat.getOuterShadowEffect().getShadowColor().setSchemeColor(SchemeColor.Accent1);
```

## الخطوة 8: احفظ العرض التقديمي

احفظ العرض التقديمي المعدل مع تطبيق تأثير الظل الخارجي على الشكل.

```java
presentation.save("output.pptx", SaveFormat.Pptx);
```

## خاتمة

تهانينا! لقد نجحت في تطبيق تأثير الظل الخارجي على شكل في PowerPoint باستخدام Java مع Aspose.Slides. قم بتجربة معلمات مختلفة لتحقيق التأثيرات المرئية المطلوبة في العروض التقديمية الخاصة بك.

## الأسئلة الشائعة

### هل يمكنني تطبيق تأثير الظل الخارجي على أشكال أخرى غير المستطيلات؟
نعم، يمكنك تطبيق تأثير الظل الخارجي على الأشكال المختلفة التي يدعمها Aspose.Slides، مثل الدوائر والمثلثات والأشكال المخصصة.

### هل من الممكن تخصيص لون الظل وكثافته؟
قطعاً! لديك سيطرة كاملة على معلمات الظل، بما في ذلك اللون ونصف قطر التمويه والاتجاه والمسافة.

### هل يمكنني تطبيق تأثيرات متعددة على نفس الشكل؟
نعم، يمكنك الجمع بين تأثيرات متعددة مثل الظل الخارجي والظل الداخلي والتوهج والانعكاس لتعزيز المظهر البصري للأشكال والنصوص في عروضك التقديمية.

### هل يدعم Aspose.Slides تطبيق التأثيرات على عناصر النص؟
نعم، يمكنك تطبيق التأثيرات ليس فقط على الأشكال ولكن أيضًا على أجزاء النص الفردية داخل الأشكال، مما يمنحك مرونة واسعة في تصميم الشرائح الخاصة بك.

### أين يمكنني العثور على المزيد من الموارد والدعم لـ Aspose.Slides؟
 يمكنك الرجوع إلى[توثيق](https://reference.aspose.com/slides/java/) للحصول على مراجع تفصيلية لواجهة برمجة التطبيقات (API) واستكشاف[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع والمناقشات.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
