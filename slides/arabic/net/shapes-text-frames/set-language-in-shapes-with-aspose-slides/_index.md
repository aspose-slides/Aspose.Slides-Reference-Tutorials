---
"date": "2025-04-16"
"description": "تعرّف على كيفية تعيين سمات اللغة للنصوص داخل الأشكال باستخدام Aspose.Slides لـ .NET. يتناول هذا الدليل إضافة الأشكال تلقائيًا، وتعيين مُعرِّفات اللغة، وحفظ العروض التقديمية."
"title": "كيفية ضبط اللغة في أشكال PowerPoint باستخدام Aspose.Slides لـ .NET"
"url": "/ar/net/shapes-text-frames/set-language-in-shapes-with-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية ضبط اللغة في أشكال PowerPoint باستخدام Aspose.Slides لـ .NET

في عالم العروض التقديمية الرقمية، قد يكون ضمان سهولة الوصول إلى المحتوى وتنسيقه بشكل صحيح عبر مختلف اللغات أمرًا صعبًا. مع Aspose.Slides لـ .NET، يمكنك بسهولة ضبط سمات اللغة للنصوص داخل الأشكال في شرائح PowerPoint. تُعد هذه الميزة مفيدة بشكل خاص عند إعداد مستندات متعددة اللغات أو ضمان الاتساق في الاتصالات العالمية.

**ما سوف تتعلمه:**
- إضافة الأشكال التلقائية وإدراج النص فيها.
- تعيين معرف اللغة لأجزاء النص باستخدام Aspose.Slides.
- حفظ العروض التقديمية باستخدام تكوينات مخصصة.

دعونا نتعرف على كيفية تنفيذ هذه الميزة بسلاسة.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

- **المكتبات والتبعيات**يجب تثبيت Aspose.Slides لـ .NET. هذه المكتبة ضرورية للتعامل مع عروض PowerPoint التقديمية بلغة C#.
  
- **إعداد البيئة**:يجب أن يكون لديك بيئة تطوير مع .NET Core أو .NET Framework.

- **متطلبات المعرفة**:ستكون المعرفة بمفاهيم برمجة C# الأساسية وفهم مبادئ البرمجة الموجهة للكائنات مفيدة.

## إعداد Aspose.Slides لـ .NET

للبدء، عليك تثبيت مكتبة Aspose.Slides. يمكنك القيام بذلك بإحدى الطرق التالية:

**.NET CLI**
```shell
dotnet add package Aspose.Slides
```

**مدير الحزم**
```powershell
Install-Package Aspose.Slides
```

**واجهة مستخدم مدير الحزم NuGet**
ابحث عن "Aspose.Slides" وقم بتثبيت الإصدار الأحدث.

### الحصول على الترخيص

يمكنك البدء بفترة تجريبية مجانية عن طريق تنزيل ترخيص مؤقت من [هنا](https://purchase.aspose.com/temporary-license/)للاستخدام المستمر، فكر في شراء ترخيص من خلال [هذا الرابط](https://purchase.aspose.com/buy).

بمجرد أن يكون الإعداد جاهزًا، قم بتشغيل Aspose.Slides في مشروعك:

```csharp
using Aspose.Slides;
```

## دليل التنفيذ

الآن بعد أن قمنا بالإعداد، فلنقم بتنفيذ الميزة لتعيين اللغة لنص الشكل.

### نظرة عامة على الميزة: ضبط لغة النص والشكل

تتيح لك هذه الميزة تحديد لغة النص داخل شكل PowerPoint. بتحديد مُعرِّف اللغة، تضمن تطبيق التدقيق الإملائي والميزات الأخرى الخاصة باللغة بشكل صحيح.

#### الخطوة 1: تهيئة العرض التقديمي

ابدأ بإنشاء مثيل لـ `Presentation` فصل.

```csharp
using (Presentation pres = new Presentation())
{
    // الكود الخاص بك هنا
}
```

سيؤدي هذا إلى تهيئة كائن عرض تقديمي جديد في PowerPoint والذي سنقوم بمعالجته.

#### الخطوة 2: إضافة الشكل التلقائي وإطار النص

أضف شكل مستطيل إلى الشريحة الخاصة بك وأدرج نصًا فيه:

```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
shape.AddTextFrame("Text to apply spellcheck language");
```

هنا، `AddAutoShape` يُضيف مستطيلاً إلى الشريحة الأولى. تُحدد المعلمات موضعه وحجمه.

#### الخطوة 3: تعيين معرف اللغة

تعيين اللغة لجزء النص داخل الشكل:

```csharp
shape.TextFrame.Paragraphs[0].Portions[0].PortionFormat.LanguageId = "en-EN";
```

يؤدي هذا إلى تعيين اللغة الإنجليزية (المملكة المتحدة) كلغة للتحقق من التهجئة.

#### الخطوة 4: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي الخاص بك في المسار المحدد:

```csharp
pres.Save("YOUR_OUTPUT_DIRECTORY\	est1.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}