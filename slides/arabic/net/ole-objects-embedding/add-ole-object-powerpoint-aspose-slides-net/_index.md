---
"date": "2025-04-16"
"description": "تعرّف على كيفية تضمين كائنات OLE في شرائح PowerPoint باستخدام Aspose.Slides لـ .NET. يغطي هذا الدليل التكامل، وحفظ التنسيقات، والتطبيقات العملية."
"title": "كيفية تضمين كائنات OLE في PowerPoint باستخدام Aspose.Slides .NET - دليل المطور"
"url": "/ar/net/ole-objects-embedding/add-ole-object-powerpoint-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية تضمين كائنات OLE في PowerPoint باستخدام Aspose.Slides .NET: دليل المطور

## مقدمة

حسّن عروض PowerPoint التقديمية بتضمين عناصر OLE (ربط الكائنات وتضمينها) بسلاسة، مثل جداول البيانات والمستندات والملفات الأخرى. سيرشدك هذا الدليل إلى كيفية استخدام Aspose.Slides لـ .NET لإضافة عناصر OLE إلى شرائح PowerPoint بكفاءة.

**ما سوف تتعلمه:**
- كيفية دمج كائنات OLE في شرائح PowerPoint
- خطوات لحفظ العرض التقديمي الخاص بك بتنسيقات مختلفة
- الميزات والفوائد الرئيسية لاستخدام Aspose.Slides لـ .NET

قبل أن نتعمق في التنفيذ، دعونا نراجع المتطلبات الأساسية!

## المتطلبات الأساسية

لمتابعة هذا البرنامج التعليمي بشكل فعال:

### المكتبات والإصدارات والتبعيات المطلوبة:
- **Aspose.Slides لـ .NET** مكتبة للعمل مع ملفات PowerPoint.
- الإصدارات المتوافقة من إطار عمل .NET أو .NET Core في بيئة التطوير الخاصة بك.

### متطلبات إعداد البيئة:
- محرر أكواد مثل Visual Studio أو VS Code.
- فهم أساسي لبرمجة C# ومفاهيم إطار عمل .NET.

## إعداد Aspose.Slides لـ .NET

لبدء استخدام Aspose.Slides، قم بتثبيت المكتبة عبر مدير الحزم المفضل لديك:

**.NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**وحدة تحكم مدير الحزمة:**
```bash
Install-Package Aspose.Slides
```

**واجهة مستخدم مدير حزمة NuGet:**
- ابحث عن "Aspose.Slides" وقم بتثبيت الإصدار الأحدث.

### خطوات الحصول على الترخيص:
1. **نسخة تجريبية مجانية:** ابدأ بإصدار تجريبي مجاني لاستكشاف الميزات.
2. **رخصة مؤقتة:** قم بتقديم طلب للحصول على ترخيص مؤقت إذا كنت بحاجة إلى أكثر مما تقدمه التجربة.
3. **شراء:** فكر في شراء ترخيص للاستخدام المستمر لـ Aspose.Slides دون قيود.

**التهيئة والإعداد الأساسي:**
بمجرد التثبيت، قم بتهيئة مشروعك باستخدام `using` عبارة لتضمين مساحات الأسماء الضرورية مثل `Aspose.Slides` و `System.IO`.

## دليل التنفيذ

### الميزة 1: تضمين كائن OLE في العرض التقديمي

#### ملخص
ترشدك هذه الميزة خلال عملية تضمين ملف مضمن ككائن OLE داخل شريحة PowerPoint باستخدام Aspose.Slides لـ .NET.

#### خطوات:

**الخطوة 1: تهيئة العرض التقديمي**
```csharp
using (Presentation pres = new Presentation())
{
    // الكود الخاص بك هنا...
}
```
- **توضيح:** نبدأ بإنشاء مثيل لـ `Presentation` للتلاعب بالشرائح.

**الخطوة 2: تحديد دليل المستندات وقراءة بايتات الملف**
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
byte[] fileBytes = File.ReadAllBytes(dataDir + "test.zip");
```
- **حدود:** `dataDir` هو المسار الذي سيتم تخزين ملفاتك فيه.
- **قيمة الإرجاع:** `fileBytes` يحتوي على المحتوى الثنائي لملفك، وهو أمر ضروري للتضمين.

**الخطوة 3: إنشاء كائن OleEmbeddedDataInfo**
```csharp
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(fileBytes, "zip");
```
- **غاية:** يقوم هذا الكائن بتغليف البيانات المضمنة وتحديد نوع الملف (على سبيل المثال، zip).

**الخطوة 4: إضافة إطار كائن OLE إلى الشريحة**
```csharp
IOleObjectFrame oleFrame = pres.Slides[0].Shapes.AddOleObjectFrame(150, 20, 50, 50, dataInfo);
oleFrame.IsObjectIcon = true;
```
- **توضيح:** تمت إضافة كائن OLE إلى الشريحة الأولى. هنا، `IsObjectIcon` تم ضبطه على true لعرض رمز بدلاً من الكائن بالكامل.

**نصائح استكشاف الأخطاء وإصلاحها:**
- تأكد من أن مسارات الملفات صحيحة ويمكن الوصول إليها.
- تأكد من أن نوع الملف المحدد في `OleEmbeddedDataInfo` يتوافق مع تنسيق الملف الفعلي الخاص بك.

### الميزة 2: حفظ العرض التقديمي

#### ملخص
تعرف على كيفية حفظ العرض التقديمي المعدّل بالتنسيق المطلوب باستخدام Aspose.Slides لـ .NET.

#### خطوات:

**الخطوة 1: تحديد دليل الإخراج وحفظه**
```csharp
string outputDir = \@"YOUR_OUTPUT_DIRECTORY";
pres.Save(outputDir + "SetFileTypeForAnEmbeddingObject.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}