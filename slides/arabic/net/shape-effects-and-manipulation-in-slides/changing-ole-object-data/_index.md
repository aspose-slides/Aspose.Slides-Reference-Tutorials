---
"description": "اكتشف قوة Aspose.Slides لـ .NET في تغيير بيانات كائنات OLE بسهولة. حسّن عروضك التقديمية بمحتوى ديناميكي."
"linktitle": "تغيير بيانات كائن OLE في العرض التقديمي باستخدام Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "تغيير بيانات كائن OLE في العرض التقديمي باستخدام Aspose.Slides"
"url": "/ar/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تغيير بيانات كائن OLE في العرض التقديمي باستخدام Aspose.Slides

## مقدمة
يُعد إنشاء عروض PowerPoint ديناميكية وتفاعلية مطلبًا شائعًا في عالمنا الرقمي اليوم. ومن الأدوات الفعّالة لتحقيق ذلك Aspose.Slides for .NET، وهي مكتبة قوية تُمكّن المطورين من معالجة عروض PowerPoint التقديمية وتحسينها برمجيًا. في هذا البرنامج التعليمي، سنتعمق في عملية تغيير بيانات كائنات OLE (ربط الكائنات وتضمينها) داخل شرائح العرض التقديمي باستخدام Aspose.Slides.
## المتطلبات الأساسية
قبل البدء في العمل مع Aspose.Slides لـ .NET، تأكد من توفر المتطلبات الأساسية التالية:
1. بيئة التطوير: قم بإعداد بيئة تطوير مع تثبيت .NET.
2. مكتبة Aspose.Slides: نزّل وثبّت مكتبة Aspose.Slides لـ .NET. يمكنك العثور على المكتبة [هنا](https://releases.aspose.com/slides/net/).
3. الفهم الأساسي: تعرف على المفاهيم الأساسية لبرمجة C# وعروض PowerPoint.
## استيراد مساحات الأسماء
في مشروع C# الخاص بك، قم باستيراد المساحات الأساسية اللازمة لاستخدام وظائف Aspose.Slides:
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## الخطوة 1: إعداد مشروعك
ابدأ بإنشاء مشروع C# جديد واستيراد مكتبة Aspose.Slides. تأكد من إعداد مشروعك بشكل صحيح، ومن توفر التبعيات المطلوبة.
## الخطوة 2: الوصول إلى العرض التقديمي والشريحة
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## الخطوة 3: تحديد موقع كائن OLE
انتقل عبر جميع الأشكال الموجودة في الشريحة للعثور على إطار كائن OLE:
```csharp
OleObjectFrame ole = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is OleObjectFrame)
    {
        ole = (OleObjectFrame)shape;
    }
}
```
## الخطوة 4: قراءة بيانات المصنف وتعديلها
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        // قراءة بيانات الكائن في المصنف
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            // تعديل بيانات المصنف
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            // تغيير بيانات كائن إطار Ole
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## الخطوة 5: حفظ العرض التقديمي
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## خاتمة
باتباع هذه الخطوات، يمكنك تغيير بيانات كائنات OLE بسلاسة داخل شرائح العرض التقديمي باستخدام Aspose.Slides لـ .NET. هذا يفتح آفاقًا واسعة لإنشاء عروض تقديمية ديناميكية ومخصصة، مصممة خصيصًا لتلبية احتياجاتك.
## الأسئلة الشائعة
### ما هو Aspose.Slides لـ .NET؟
Aspose.Slides for .NET هي مكتبة قوية تتيح للمطورين العمل مع عروض PowerPoint برمجيًا، مما يسمح بالتلاعب بها وتحسينها بسهولة.
### أين يمكنني العثور على وثائق Aspose.Slides؟
يمكن العثور على وثائق Aspose.Slides لـ .NET [هنا](https://reference.aspose.com/slides/net/).
### كيف يمكنني تنزيل Aspose.Slides لـ .NET؟
يمكنك تنزيل المكتبة من صفحة الإصدار [هنا](https://releases.aspose.com/slides/net/).
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides؟
نعم، يمكنك الوصول إلى النسخة التجريبية المجانية [هنا](https://releases.aspose.com/).
### أين يمكنني الحصول على الدعم لـ Aspose.Slides لـ .NET؟
للحصول على الدعم والمناقشات، قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}