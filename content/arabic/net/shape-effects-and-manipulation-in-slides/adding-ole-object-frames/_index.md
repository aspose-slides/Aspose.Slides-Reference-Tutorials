---
title: إضافة إطارات كائنات OLE إلى العرض التقديمي باستخدام Aspose.Slides
linktitle: إضافة إطارات كائنات OLE إلى العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تحسين عروض PowerPoint التقديمية بالمحتوى الديناميكي! اتبع دليلنا خطوة بخطوة باستخدام Aspose.Slides لـ .NET. تعزيز المشاركة الآن!
type: docs
weight: 15
url: /ar/net/shape-effects-and-manipulation-in-slides/adding-ole-object-frames/
---
## مقدمة
في هذا البرنامج التعليمي، سنتعمق في عملية إضافة إطارات كائنات OLE (ربط الكائنات وتضمينها) إلى شرائح العرض التقديمي باستخدام Aspose.Slides لـ .NET. Aspose.Slides هي مكتبة قوية تمكن المطورين من العمل مع ملفات PowerPoint برمجياً. اتبع هذا الدليل التفصيلي خطوة بخطوة لتضمين كائنات OLE بسلاسة في شرائح العرض التقديمي، مما يؤدي إلى تحسين ملفات PowerPoint الخاصة بك بمحتوى ديناميكي وتفاعلي.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1.  Aspose.Slides لـ .NET Library: تأكد من تثبيت مكتبة Aspose.Slides لـ .NET. يمكنك تنزيله من[Aspose.Slides لوثائق .NET](https://reference.aspose.com/slides/net/).
2. دليل المستندات: قم بإنشاء دليل على نظامك لتخزين الملفات الضرورية. يمكنك تعيين المسار إلى هذا الدليل في مقتطف الشفرة المقدم.
## استيراد مساحات الأسماء
للبدء، قم باستيراد مساحات الأسماء الضرورية إلى مشروعك:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using Aspose.Slides.Export;
```
## الخطوة 1: إعداد العرض التقديمي
```csharp
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
// قم بإنشاء الدليل إذا لم يكن موجودًا بالفعل.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// إنشاء فئة العرض التقديمي التي تمثل PPTX
using (Presentation pres = new Presentation())
{
    // الوصول إلى الشريحة الأولى
    ISlide sld = pres.Slides[0];
    
    // تابع إلى الخطوات التالية...
}
```
## الخطوة 2: تحميل كائن OLE (ملف Excel) للدفق
```csharp
// قم بتحميل ملف Excel للبث
MemoryStream mstream = new MemoryStream();
using (FileStream fs = new FileStream(dataDir + "book1.xlsx", FileMode.Open, FileAccess.Read))
{
    byte[] buf = new byte[4096];
    while (true)
    {
        int bytesRead = fs.Read(buf, 0, buf.Length);
        if (bytesRead <= 0)
            break;
        mstream.Write(buf, 0, bytesRead);
    }
}
```
## الخطوة 3: إنشاء كائن بيانات للتضمين
```csharp
// إنشاء كائن بيانات للتضمين
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(mstream.ToArray(), "xlsx");
```
## الخطوة 4: إضافة شكل إطار كائن OLE
```csharp
// إضافة شكل إطار كائن OLE
IOleObjectFrame oleObjectFrame = sld.Shapes.AddOleObjectFrame(0, 0, pres.SlideSize.Size.Width,
    pres.SlideSize.Size.Height, dataInfo);
```
## الخطوة 5: احفظ العرض التقديمي
```csharp
// اكتب PPTX على القرص
pres.Save(dataDir + "OleEmbed_out.pptx", SaveFormat.Pptx);
```
لقد نجحت الآن في إضافة إطار كائن OLE إلى شريحة العرض التقديمي باستخدام Aspose.Slides for .NET.
## خاتمة
في هذا البرنامج التعليمي، اكتشفنا التكامل السلس لإطارات كائنات OLE في شرائح PowerPoint باستخدام Aspose.Slides for .NET. تعمل هذه الوظيفة على تحسين العروض التقديمية الخاصة بك عن طريق السماح بالتضمين الديناميكي لكائنات مختلفة، مثل أوراق Excel، مما يوفر تجربة مستخدم أكثر تفاعلية.
## الأسئلة الشائعة
### س: هل يمكنني تضمين كائنات بخلاف أوراق Excel باستخدام Aspose.Slides لـ .NET؟
ج: نعم، يدعم Aspose.Slides تضمين كائنات OLE المتنوعة، بما في ذلك مستندات Word وملفات PDF.
### س: كيف يمكنني معالجة الأخطاء أثناء عملية تضمين كائن OLE؟
ج: تأكد من معالجة الاستثناءات المناسبة في التعليمات البرمجية الخاصة بك لمعالجة أي مشكلات قد تنشأ أثناء عملية التضمين.
### س: هل Aspose.Slides متوافق مع أحدث تنسيقات ملفات PowerPoint؟
ج: نعم، يدعم Aspose.Slides أحدث تنسيقات ملفات PowerPoint، بما في ذلك PPTX.
### س: هل يمكنني تخصيص مظهر إطار كائن OLE المضمن؟
ج: بالتأكيد، يمكنك ضبط الحجم والموضع والخصائص الأخرى لإطار كائن OLE وفقًا لتفضيلاتك.
### س: أين يمكنني طلب المساعدة إذا واجهت تحديات أثناء التنفيذ؟
 ج: قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع وتوجيهه.