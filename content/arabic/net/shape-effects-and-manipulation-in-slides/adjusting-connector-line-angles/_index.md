---
title: ضبط زوايا خط الموصل في شرائح العرض التقديمي باستخدام Aspose.Slides
linktitle: ضبط زوايا خط الموصل في شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تحسين شرائح العرض التقديمي الخاص بك عن طريق ضبط زوايا خط الموصل باستخدام Aspose.Slides for .NET. دليل خطوة بخطوة مع أمثلة التعليمات البرمجية.
type: docs
weight: 28
url: /ar/net/shape-effects-and-manipulation-in-slides/adjusting-connector-line-angles/
---

تلعب خطوط الموصل دورًا حاسمًا في إنشاء شرائح عرض تقديمي جيدة التنظيم وجذابة بصريًا. فهي تساعد في إنشاء علاقات بين العناصر المختلفة في الشريحة، مما يعزز وضوح المعلومات. توفر Aspose.Slides، وهي واجهة برمجة تطبيقات .NET قوية، ميزات متنوعة للتعامل مع خطوط الموصلات هذه، بما في ذلك ضبط زواياها. في هذا البرنامج التعليمي، سوف نستكشف كيفية ضبط زوايا خط الموصل في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET.

## مقدمة لخطوط الموصل

تعتبر خطوط الوصلات أدوات مساعدة بصرية أساسية في العروض التقديمية، وتستخدم لتوضيح العلاقات بين الأشياء أو المفاهيم. يتم استخدامها بشكل شائع لإنشاء المخططات الانسيابية والرسوم البيانية والرسوم التوضيحية للعملية. يمكن أن يؤثر ضبط زوايا خطوط الموصل بشكل كبير على الشكل العام للشريحة وإمكانية فهمها.

## الشروع في العمل مع Aspose.Slides لـ .NET

قبل أن نتعمق في ضبط زوايا خط الموصل، فلنقم بإعداد بيئة التطوير الخاصة بنا ودمج Aspose.Slides في مشروعنا. اتبع الخطوات التالية:

1. قم بتنزيل وتثبيت Aspose.Slides لـ .NET من[هنا](https://releases.aspose.com/slides/net/).
2. قم بإنشاء مشروع .NET جديد في بيئة التطوير المفضلة لديك.
3. أضف مرجعًا إلى مكتبة Aspose.Slides في مشروعك.

## إضافة خطوط الموصل إلى الشرائح

لضبط زوايا خط الموصل، نحتاج أولاً إلى إضافة خطوط موصل إلى شرائحنا. إليك كيفية القيام بذلك باستخدام Aspose.Slides:

```csharp
// إنشاء مثيل لكائن العرض التقديمي
using (Presentation presentation = new Presentation())
{
    // قم بالوصول إلى الشريحة التي تريد إضافة خطوط الرابط إليها
    ISlide slide = presentation.Slides[0];

    // تحديد نقاط البداية والنهاية لخط الموصل
    PointF startPoint = new PointF(100, 100);
    PointF endPoint = new PointF(300, 200);

    // أضف خط الموصل إلى الشريحة
    IAutoShape connectorLine = slide.Shapes.AddLine(startPoint.X, startPoint.Y, endPoint.X, endPoint.Y);

    // تخصيص مظهر خط الموصل
    connectorLine.LineFormat.Style = LineStyle.Single;
    connectorLine.LineFormat.Width = 2;
}
```

## الوصول إلى زوايا خط الموصل وتعديلها

الآن بعد أن أصبح لدينا خطوط الموصلات في شريحتنا، فلنستكشف كيفية الوصول إلى زواياها وتعديلها باستخدام Aspose.Slides:

```csharp
// قم بالوصول إلى خط الموصل الذي أضفناه سابقًا
IAutoShape connectorLine = slide.Shapes[0] as IAutoShape;

// الوصول إلى تنسيق خط الموصل
ILineFormat lineFormat = connectorLine.LineFormat;

// احصل على الزاوية الحالية لخط الموصل
double currentAngle = lineFormat.Alignment.Angle;

// تعديل زاوية خط الموصل
lineFormat.Alignment.Angle = 45; // اضبط الزاوية حسب الرغبة
```

## تطبيق تعديلات زاوية مخصصة

يمكّننا Aspose.Slides من تطبيق تعديلات زاوية مخصصة على خطوط الموصل، مما يسمح بمحاذاة العناصر وترتيبها بدقة. فيما يلي مثال لضبط زوايا خطوط الموصلات المتعددة لإنشاء رسم تخطيطي متدفق:

```csharp
foreach (IAutoShape shape in slide.Shapes)
{
    if (shape is IAutoShape && shape != connectorLine)
    {
        ILineFormat shapeLineFormat = shape.LineFormat;
        shapeLineFormat.Alignment.Angle = 30; // تطبيق زاوية متسقة على جميع الخطوط
    }
}
```

## الأسئلة الشائعة

### كيف يمكنني إزالة خط موصل من الشريحة؟

لإزالة خط موصل من شريحة، يمكنك استخدام مقتطف التعليمات البرمجية التالي:

```csharp
IAutoShape connectorLine = slide.Shapes[0] as IAutoShape;
slide.Shapes.Remove(connectorLine);
```

### هل يمكنني تغيير لون خطوط الموصل؟

 نعم، يمكنك تغيير لون خطوط الموصل باستخدام`LineFormat` ملكية. هنا مثال:

```csharp
lineFormat.FillFormat.SolidFillColor.Color = Color.Red;
```

### هل من الممكن إضافة رؤوس الأسهم إلى خطوط الموصل؟

 بالتأكيد! يمكنك إضافة رؤوس أسهم إلى خطوط الموصل عن طريق تعديل`LineFormat` ملكية:

```csharp
lineFormat.EndArrowheadLength = ArrowheadLength.Short;
lineFormat.EndArrowheadStyle = ArrowheadStyle.Triangle;
```

### كيف يمكنني ضبط التباعد بين العناصر المتصلة بالخطوط؟

لضبط التباعد بين العناصر المتصلة، يمكنك تعديل نقاط البداية والنهاية لخطوط الموصل. سيؤثر هذا على المحاذاة المرئية بين العناصر.

### أين يمكنني العثور على المزيد من الموارد على Aspose.Slides لـ .NET؟

يمكنك العثور على وثائق شاملة ومراجع واجهة برمجة التطبيقات (API) على Aspose.Slides لـ .NET[هنا](https://reference.aspose.com/slides/net/).

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا عملية ضبط زوايا خط الموصل في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET. لقد تعلمنا كيفية إضافة خطوط الموصلات، والوصول إلى زواياها وتعديلها، وتطبيق تعديلات مخصصة لإنشاء مخططات ورسوم توضيحية جذابة بصريًا. يعمل Aspose.Slides على تمكين المطورين من تحسين عروضهم التقديمية من خلال التحكم الدقيق في خطوط الموصل، مما يؤدي في النهاية إلى تحسين وضوح المحتوى وتأثيره.