---
"description": "تعرّف على كيفية إضافة روابط تشعبية إلى شرائح PowerPoint باستخدام Aspose.Slides لـ .NET. عزّز عروضك التقديمية بعناصر تفاعلية."
"linktitle": "إضافة ارتباط تشعبي إلى الشريحة"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إضافة ارتباطات تشعبية إلى الشرائح في .NET باستخدام Aspose.Slides"
"url": "/ar/net/hyperlink-manipulation/add-hyperlink/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة ارتباطات تشعبية إلى الشرائح في .NET باستخدام Aspose.Slides


في عالم العروض التقديمية الرقمية، يُعد التفاعل أمرًا بالغ الأهمية. إضافة روابط تشعبية إلى شرائحك تجعل عرضك التقديمي أكثر جاذبية وإثراءً بالمعلومات. Aspose.Slides for .NET هي مكتبة فعّالة تتيح لك إنشاء عروض PowerPoint التقديمية وتعديلها ومعالجتها برمجيًا. في هذا البرنامج التعليمي، سنوضح لك كيفية إضافة روابط تشعبية إلى شرائحك باستخدام Aspose.Slides for .NET. 

## المتطلبات الأساسية

قبل أن نتعمق في إضافة الارتباطات التشعبية إلى الشرائح، تأكد من توفر المتطلبات الأساسية التالية:

1. Visual Studio: يجب أن يكون Visual Studio مثبتًا على جهاز الكمبيوتر الخاص بك لتتمكن من كتابة وتنفيذ كود .NET.

2. Aspose.Slides لـ .NET: يجب تثبيت مكتبة Aspose.Slides لـ .NET. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/net/).

3. المعرفة الأساسية بلغة C#: ستكون المعرفة ببرمجة C# مفيدة.

## استيراد مساحات الأسماء

للبدء، عليك استيراد مساحات الأسماء اللازمة في مشروع C#. في هذه الحالة، ستحتاج إلى مساحات الأسماء التالية من مكتبة Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

الآن، دعنا نقوم بتقسيم عملية إضافة الارتباطات التشعبية إلى الشرائح إلى خطوات متعددة.

## الخطوة 1: تهيئة العرض التقديمي

أولاً، أنشئ عرضًا تقديميًا جديدًا باستخدام Aspose.Slides. إليك الطريقة:

```csharp
using (Presentation presentation = new Presentation())
{
    // الكود الخاص بك يذهب هنا
}
```

يقوم هذا الكود بتشغيل عرض تقديمي جديد في PowerPoint.

## الخطوة 2: إضافة إطار نصي

الآن، لنُضِف إطارًا نصيًا إلى شريحتك. سيُصبح هذا الإطار النصي العنصر القابل للنقر في شريحتك. 

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

يقوم الكود أعلاه بإنشاء شكل مستطيل تلقائي ويضيف إطار نصي بالنص "Aspose: File Format APIs".

## الخطوة 3: إضافة ارتباط تشعبي

الآن، لنُضِف رابطًا تشعبيًا إلى إطار النص الذي أنشأته. هذا سيجعل النص قابلًا للنقر.

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

في هذه الخطوة، عيّننا عنوان URL للرابط التشعبي إلى "https://www.aspose.com/" وأضفنا تلميحًا للمعلومات الإضافية. يمكنك أيضًا تنسيق مظهر الرابط التشعبي، كما هو موضح أعلاه.

## الخطوة 4: حفظ العرض التقديمي

وأخيرًا، احفظ عرضك التقديمي باستخدام الرابط التشعبي المضاف.

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

يحفظ هذا الكود العرض التقديمي باسم "presentation-out.pptx".

الآن، قمت بنجاح بإضافة ارتباط تشعبي إلى شريحة باستخدام Aspose.Slides لـ .NET.

## خاتمة

في هذا البرنامج التعليمي، استكشفنا كيفية إضافة روابط تشعبية إلى الشرائح في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ .NET. باتباع هذه الخطوات، يمكنك جعل عروضك التقديمية أكثر تفاعلية وجاذبية، وتوفير روابط قيّمة لموارد أو معلومات إضافية.

لمزيد من المعلومات والوثائق التفصيلية، قم بزيارة [توثيق Aspose.Slides لـ .NET](https://reference.aspose.com/slides/net/).

## الأسئلة الشائعة

### 1. هل يمكنني إضافة ارتباطات تشعبية إلى أشكال أخرى بالإضافة إلى إطارات النص؟

نعم، يمكنك إضافة ارتباطات تشعبية إلى أشكال مختلفة مثل المستطيلات والصور والمزيد باستخدام Aspose.Slides لـ .NET.

### 2. كيف يمكنني إزالة ارتباط تشعبي من شكل في شريحة PowerPoint؟

يمكنك إزالة ارتباط تشعبي من شكل عن طريق ضبط `HyperlinkClick` الممتلكات إلى `null`.

### 3. هل يمكنني تغيير عنوان URL للرابط التشعبي بشكل ديناميكي في الكود الخاص بي؟

بالتأكيد! يمكنك تحديث عنوان URL للرابط التشعبي في أي نقطة من الكود الخاص بك عن طريق تعديل `Hyperlink` ملكية.

### 4. ما هي العناصر التفاعلية الأخرى التي يمكنني إضافتها إلى شرائح PowerPoint باستخدام Aspose.Slides؟

يوفر Aspose.Slides مجموعة واسعة من الميزات التفاعلية، بما في ذلك أزرار الإجراءات وعناصر الوسائط المتعددة والرسوم المتحركة.

### 5. هل Aspose.Slides متاح للغات برمجة أخرى؟

نعم، Aspose.Slides متاح للعديد من لغات البرمجة، بما في ذلك Java وPython.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}