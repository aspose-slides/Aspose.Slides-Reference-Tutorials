---
title: استخرج الصوت من الارتباطات التشعبية لبرنامج PowerPoint باستخدام Aspose.Slides
linktitle: استخراج الصوت من الارتباط التشعبي
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: استخرج الصوت من الارتباطات التشعبية في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ .NET. قم بتحسين مشاريع الوسائط المتعددة الخاصة بك دون عناء.
weight: 12
url: /ar/net/audio-and-video-extraction/extract-audio-from-hyperlink/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# استخرج الصوت من الارتباطات التشعبية لبرنامج PowerPoint باستخدام Aspose.Slides


في عالم عروض الوسائط المتعددة، يلعب الصوت دورًا حيويًا في تعزيز التأثير العام لشرائحك. هل سبق لك أن صادفت عرضًا تقديميًا لبرنامج PowerPoint يحتوي على ارتباطات تشعبية صوتية وتساءلت عن كيفية استخراج الصوت لاستخدامات أخرى؟ باستخدام Aspose.Slides for .NET، يمكنك تحقيق هذه المهمة دون عناء. في هذا الدليل التفصيلي، سنرشدك خلال عملية استخراج الصوت من رابط تشعبي في عرض PowerPoint التقديمي.

## المتطلبات الأساسية

قبل أن نتعمق في عملية الاستخراج، تأكد من توفر المتطلبات الأساسية التالية:

### 1. Aspose.Slides لمكتبة .NET

يجب أن يكون لديك مكتبة Aspose.Slides for .NET مثبتة في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك بالفعل، يمكنك تنزيله من موقع الويب على[Aspose.Slides لتوثيق .NET](https://reference.aspose.com/slides/net/).

### 2. عرض PowerPoint التقديمي مع الارتباطات التشعبية الصوتية

تأكد من أن لديك عرض تقديمي لـ PowerPoint (PPTX) يحتوي على ارتباطات تشعبية مع الصوت المرتبط. سيكون هذا هو المصدر الذي ستستخرج منه الصوت.

## استيراد مساحات الأسماء

أولاً، لنستورد مساحات الأسماء الضرورية في مشروع C# الخاص بك لاستخدام Aspose.Slides لـ .NET بشكل فعال. تعد مساحات الأسماء هذه ضرورية للعمل مع عروض PowerPoint التقديمية واستخراج الصوت من الارتباطات التشعبية.

```csharp
using System;
using System.IO;
using Aspose.Slides;
```

الآن بعد أن أصبح لدينا متطلباتنا الأساسية واستيراد مساحات الأسماء المطلوبة، فلنقسم عملية الاستخراج إلى خطوات متعددة.

## الخطوة 1: تحديد دليل المستندات

 ابدأ بتحديد الدليل الذي يوجد به عرض PowerPoint التقديمي الخاص بك. يمكنك استبدال`"Your Document Directory"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

```csharp
string dataDir = "Your Document Directory";
```

## الخطوة 2: قم بتحميل عرض PowerPoint التقديمي

 قم بتحميل عرض PowerPoint التقديمي (PPTX) الذي يحتوي على الارتباط التشعبي الصوتي باستخدام Aspose.Slides. يستبدل`"HyperlinkSound.pptx"`مع اسم الملف الفعلي للعرض التقديمي الخاص بك.

```csharp
string pptxFile = Path.Combine(dataDir, "HyperlinkSound.pptx");

using (Presentation pres = new Presentation(pptxFile))
{
    // انتقل إلى الخطوة التالية.
}
```

## الخطوة 3: احصل على صوت الارتباط التشعبي

احصل على الارتباط التشعبي للشكل الأول من شريحة PowerPoint. إذا كان الارتباط التشعبي يحتوي على صوت مرتبط، فسنشرع في استخراجه.

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
// يستخرج صوت الارتباط التشعبي في صفيف البايت
byte[] audioData = link.Sound.BinaryData;

// حدد المسار الذي تريد حفظ الصوت المستخرج فيه
string outMediaPath = Path.Combine(dataDir, "HyperlinkSound.mpg");

// احفظ الصوت المستخرج في ملف وسائط
File.WriteAllBytes(outMediaPath, audioData);
```

تهانينا! لقد نجحت في استخراج الصوت من ارتباط تشعبي في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides لـ .NET. يمكن الآن استخدام هذا الصوت المستخرج لأغراض أخرى في مشاريع الوسائط المتعددة الخاصة بك.

## خاتمة

يوفر Aspose.Slides for .NET حلاً قويًا وسهل الاستخدام لاستخراج الصوت من الارتباطات التشعبية في عروض PowerPoint التقديمية. باستخدام الخطوات الموضحة في هذا الدليل، يمكنك تحسين مشاريع الوسائط المتعددة الخاصة بك بسهولة عن طريق إعادة استخدام المحتوى الصوتي من العروض التقديمية الخاصة بك.

### الأسئلة المتداولة (الأسئلة الشائعة)

### هل يعتبر Aspose.Slides for .NET مكتبة مجانية؟
 لا، Aspose.Slides for .NET هي مكتبة تجارية، ولكن يمكنك استكشاف ميزاتها ووثائقها عن طريق تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).

### هل يمكنني استخراج الصوت من الارتباطات التشعبية بتنسيقات PowerPoint الأقدم مثل PPT؟
نعم، يدعم Aspose.Slides for .NET كلاً من تنسيقات PPTX وPPT لاستخراج الصوت من الارتباطات التشعبية.

### هل يوجد منتدى مجتمعي لدعم Aspose.Slides؟
 نعم، يمكنك الحصول على المساعدة ومشاركة تجاربك مع Aspose.Slides في[منتدى المجتمع Aspose.Slides](https://forum.aspose.com/).

### هل يمكنني شراء ترخيص مؤقت لـ Aspose.Slides لمشروع قصير المدى؟
نعم، يمكنك الحصول على ترخيص مؤقت لـ Aspose.Slides for .NET لتلبية احتياجات مشروعك على المدى القصير من خلال زيارة[هذا الرابط](https://purchase.aspose.com/temporary-license/).

### هل هناك تنسيقات صوتية أخرى مدعومة للاستخراج، بخلاف MPG؟
يسمح لك Aspose.Slides for .NET باستخراج الصوت بتنسيقات مختلفة، لا تقتصر على MPG. يمكنك تحويله إلى التنسيق المفضل لديك بعد الاستخراج.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
