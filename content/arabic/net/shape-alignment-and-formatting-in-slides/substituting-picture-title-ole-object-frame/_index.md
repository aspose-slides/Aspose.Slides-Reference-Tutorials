---
title: استبدال عنوان الصورة لإطار كائن OLE في شرائح العرض التقديمي
linktitle: استبدال عنوان الصورة لإطار كائن OLE في شرائح العرض التقديمي
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية استبدال عناوين الصور لإطارات كائنات OLE في شرائح العرض التقديمي باستخدام Aspose.Slides لـ .NET. دليل خطوة بخطوة مع كود المصدر الكامل.
type: docs
weight: 15
url: /ar/net/shape-alignment-and-formatting-in-slides/substituting-picture-title-ole-object-frame/
---

## مقدمة إلى Aspose.Slides لـ .NET

Aspose.Slides for .NET عبارة عن واجهة برمجة تطبيقات قوية تسمح للمطورين بإنشاء عروض PowerPoint التقديمية وتعديلها ومعالجتها دون الحاجة إلى تثبيت Microsoft Office أو PowerPoint. فهو يوفر نطاقًا واسعًا من الميزات للعمل مع عناصر مختلفة من العروض التقديمية، بما في ذلك الشرائح والأشكال والنصوص والصور وإطارات كائنات OLE.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Visual Studio أو أي بيئة تطوير .NET متوافقة.
-  Aspose.Slides لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/net/).

## تحميل عرض تقديمي

لنبدأ بتحميل عرض PowerPoint تقديمي موجود باستخدام Aspose.Slides لـ .NET. إذا لم يكن لديك عرض تقديمي للاختبار، فيمكنك إنشاء عرض تقديمي جديد أو تنزيل نموذج عرض تقديمي.

```csharp
using Aspose.Slides;

// قم بتحميل العرض التقديمي
using var presentation = new Presentation("sample.pptx");
```

## الوصول إلى إطارات كائنات OLE

 تسمح لك إطارات كائنات OLE (ربط الكائنات وتضمينها) بتضمين كائنات مثل الصور أو المستندات أو الملفات الأخرى داخل شريحة PowerPoint. للوصول إلى إطارات كائنات OLE في الشريحة، يمكنك التكرار عبر الأشكال والتحقق من وجود مثيلات لها`OleObjectFrameEx`.

```csharp
// التكرار من خلال الشرائح
foreach (var slide in presentation.Slides)
{
    // التكرار من خلال الأشكال الموجودة في الشريحة
    foreach (var shape in slide.Shapes)
    {
        if (shape is OleObjectFrameEx oleObject)
        {
            //الوصول إلى خصائص كائن OLE
            var title = oleObject.Title;
            var data = oleObject.ObjectData;
            
            // تنفيذ المزيد من الإجراءات
        }
    }
}
```

## استبدال عنوان الصورة

 لاستبدال عنوان الصورة لإطار كائن OLE، يمكنك ببساطة تحديث ملف`Title` ملكية`OleObjectFrameEx` مثال.

```csharp
foreach (var slide in presentation.Slides)
{
    foreach (var shape in slide.Shapes)
    {
        if (shape is OleObjectFrameEx oleObject)
        {
            // قم بتحديث العنوان
            oleObject.Title = "New Picture Title";
        }
    }
}
```

## حفظ العرض التقديمي المعدل

بعد إجراء التغييرات اللازمة، تحتاج إلى حفظ العرض التقديمي المعدل. يمكنك حفظه بتنسيقات مختلفة مثل PPTX أو PDF أو الصور.

```csharp
// احفظ العرض التقديمي
presentation.Save("modified.pptx", SaveFormat.Pptx);
```

## خاتمة

يعمل Aspose.Slides for .NET على تبسيط عملية العمل مع عروض PowerPoint التقديمية برمجيًا. في هذا الدليل، قمنا بتغطية خطوات استبدال عنوان الصورة لإطار كائن OLE في شرائح العرض التقديمي. باتباع هذه الخطوات، يمكنك التعامل مع العروض التقديمية بكفاءة وفقًا لمتطلباتك.

## الأسئلة الشائعة

### كيف يمكنني الحصول على Aspose.Slides لمكتبة .NET؟

 يمكنك تنزيل مكتبة Aspose.Slides for .NET من[هذا الرابط](https://releases.aspose.com/slides/net/).

### هل يمكنني استخدام Aspose.Slides لـ .NET دون تثبيت Microsoft Office؟

نعم، يسمح لك Aspose.Slides for .NET بالعمل مع عروض PowerPoint التقديمية دون الحاجة إلى تثبيت Microsoft Office.

### هل هناك عمليات أخرى يمكنني تنفيذها على إطارات كائنات OLE؟

قطعاً! يمكنك تنفيذ إجراءات متنوعة على إطارات كائنات OLE، مثل استبدال بيانات الكائن، أو تغيير حجمها، أو إعادة وضعها داخل الشرائح.

### هل يتوافق Aspose.Slides for .NET مع تنسيقات PowerPoint المختلفة؟

نعم، يدعم Aspose.Slides for .NET نطاقًا واسعًا من تنسيقات PowerPoint، بما في ذلك PPT وPPTX وPPS والمزيد.

### هل يمكنني أتمتة إنشاء عروض PowerPoint التقديمية باستخدام Aspose.Slides؟

بالتأكيد! يمكّنك Aspose.Slides for .NET من إنشاء عروض PowerPoint التقديمية ديناميكيًا من البداية، ودمج عناصر مختلفة مثل النص والصور والمخططات والمزيد.