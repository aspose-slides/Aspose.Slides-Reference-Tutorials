---
"description": "استخرج الصوت من الروابط التشعبية في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ .NET. حسّن مشاريع الوسائط المتعددة لديك بسهولة."
"linktitle": "استخراج الصوت من الرابط التشعبي"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "استخراج الصوت من الروابط التشعبية في PowerPoint باستخدام Aspose.Slides"
"url": "/ar/net/audio-and-video-extraction/extract-audio-from-hyperlink/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# استخراج الصوت من الروابط التشعبية في PowerPoint باستخدام Aspose.Slides


في عالم العروض التقديمية متعددة الوسائط، يلعب الصوت دورًا حيويًا في تعزيز التأثير العام لشرائحك. هل سبق لك أن صادفت عرضًا تقديميًا على PowerPoint يحتوي على روابط صوتية وتساءلت عن كيفية استخراج الصوت لاستخدامات أخرى؟ مع Aspose.Slides لـ .NET، يمكنك تحقيق هذه المهمة بسهولة. في هذا الدليل التفصيلي، سنشرح لك عملية استخراج الصوت من رابط في عرض تقديمي على PowerPoint.

## المتطلبات الأساسية

قبل أن نتعمق في عملية الاستخراج، تأكد من توفر المتطلبات الأساسية التالية:

### 1. مكتبة Aspose.Slides لـ .NET

يجب تثبيت مكتبة Aspose.Slides for .NET في بيئة التطوير لديك. إذا لم تكن مثبتة بالفعل، يمكنك تنزيلها من الموقع الإلكتروني على [توثيق Aspose.Slides لـ .NET](https://reference.aspose.com/slides/net/).

### 2. عرض تقديمي على PowerPoint مع روابط صوتية

تأكد من أن لديك عرضًا تقديميًا بصيغة PowerPoint (PPTX) يحتوي على روابط تشعبية مصحوبة بالصوت. سيكون هذا هو المصدر الذي ستستخرج منه الصوت.

## استيراد مساحات الأسماء

أولاً، لنستورد مساحات الأسماء اللازمة في مشروع C# الخاص بك لاستخدام Aspose.Slides لـ .NET بفعالية. هذه المساحات ضرورية للعمل مع عروض PowerPoint التقديمية واستخراج الصوت من الروابط التشعبية.

```csharp
using System;
using System.IO;
using Aspose.Slides;
```

الآن بعد أن وضعنا المتطلبات الأساسية في مكانها وقمنا باستيراد مساحات الأسماء المطلوبة، فلنبدأ بتقسيم عملية الاستخراج إلى خطوات متعددة.

## الخطوة 1: تحديد دليل المستندات

ابدأ بتحديد الدليل الذي يوجد فيه عرض PowerPoint التقديمي. يمكنك استبدال `"Your Document Directory"` مع المسار الفعلي إلى دليل المستند الخاص بك.

```csharp
string dataDir = "Your Document Directory";
```

## الخطوة 2: تحميل عرض PowerPoint

حمّل عرض PowerPoint التقديمي (PPTX) الذي يحتوي على رابط الصوت باستخدام Aspose.Slides. استبدل `"HyperlinkSound.pptx"` مع اسم الملف الفعلي للعرض التقديمي الخاص بك.

```csharp
string pptxFile = Path.Combine(dataDir, "HyperlinkSound.pptx");

using (Presentation pres = new Presentation(pptxFile))
{
    // انتقل إلى الخطوة التالية.
}
```

## الخطوة 3: الحصول على صوت الارتباط التشعبي

احصل على رابط الشكل الأول من شريحة PowerPoint. إذا كان للرابط صوت مرتبط، فسنقوم باستخراجه.

```csharp
IHyperlink link = pres.Slides[0].Shapes[0].HyperlinkClick;

if (link.Sound != null)
{
    // انتقل إلى الخطوة التالية.
}
```

## الخطوة 4: استخراج الصوت من الارتباط التشعبي

إذا كان الارتباط التشعبي يحتوي على صوت مرتبط، فيمكننا استخراجه كمصفوفة بايت وحفظه كملف وسائط.

```csharp
// استخراج صوت الارتباط التشعبي في مجموعة البايتات
byte[] audioData = link.Sound.BinaryData;

// حدد المسار الذي تريد حفظ الصوت المستخرج فيه
string outMediaPath = Path.Combine(dataDir, "HyperlinkSound.mpg");

// حفظ الصوت المستخرج في ملف وسائط
File.WriteAllBytes(outMediaPath, audioData);
```

تهانينا! لقد نجحت في استخراج الصوت من رابط تشعبي في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لـ .NET. يمكنك الآن استخدام هذا الصوت المستخرج لأغراض أخرى في مشاريع الوسائط المتعددة الخاصة بك.

## خاتمة

يوفر Aspose.Slides for .NET حلاً فعالاً وسهل الاستخدام لاستخراج الصوت من الروابط التشعبية في عروض PowerPoint التقديمية. باتباع الخطوات الموضحة في هذا الدليل، يمكنك تحسين مشاريع الوسائط المتعددة الخاصة بك بسهولة عن طريق إعادة استخدام المحتوى الصوتي من عروضك التقديمية.

### الأسئلة الشائعة

### هل Aspose.Slides لـ .NET مكتبة مجانية؟
لا، Aspose.Slides for .NET هي مكتبة تجارية، ولكن يمكنك استكشاف ميزاتها ووثائقها عن طريق تنزيل نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).

### هل يمكنني استخراج الصوت من الروابط التشعبية في تنسيقات PowerPoint القديمة مثل PPT؟
نعم، يدعم Aspose.Slides for .NET كل من تنسيقي PPTX وPPT لاستخراج الصوت من الارتباطات التشعبية.

### هل يوجد منتدى مجتمعي لدعم Aspose.Slides؟
نعم، يمكنك الحصول على المساعدة ومشاركة تجاربك مع Aspose.Slides في [منتدى مجتمع Aspose.Slides](https://forum.aspose.com/).

### هل يمكنني شراء ترخيص مؤقت لـ Aspose.Slides لمشروع قصير المدى؟
نعم، يمكنك الحصول على ترخيص مؤقت لـ Aspose.Slides لـ .NET لتلبية احتياجات مشروعك قصير المدى من خلال زيارة [هذا الرابط](https://purchase.aspose.com/temporary-license/).

### هل هناك تنسيقات صوتية أخرى مدعومة للاستخراج، إلى جانب MPG؟
يتيح لك Aspose.Slides for .NET استخراج الصوت بتنسيقات متعددة، بما في ذلك MPG. يمكنك تحويله إلى التنسيق الذي تفضله بعد الاستخراج.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}