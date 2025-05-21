---
"date": "2025-04-15"
"description": "تعرف على كيفية ضمان عرض الخطوط بشكل متسق عند تحويل العروض التقديمية إلى HTML باستخدام Aspose.Slides لـ .NET عن طريق تضمين الخطوط بشكل مباشر."
"title": "كيفية ربط الخطوط في HTML باستخدام Aspose.Slides لـ .NET - دليل خطوة بخطوة"
"url": "/ar/net/formatting-styles/font-linking-html-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية ربط الخطوط في HTML باستخدام Aspose.Slides لـ .NET

## مقدمة

قد يكون تحويل العروض التقديمية إلى HTML مع الحفاظ على عرض الخط المتسق عبر الأنظمة الأساسية أمرًا صعبًا. **Aspose.Slides لـ .NET** يقدم حلاً سلسًا من خلال السماح لك بربط جميع الخطوط المستخدمة في العرض التقديمي مباشرةً داخل إخراج HTML من خلال ملفات الخطوط المضمنة.

في هذا البرنامج التعليمي، سنستكشف كيفية تنفيذ ربط الخطوط باستخدام Aspose.Slides لـ .NET وضمان اتساق التصميم عبر منصات مختلفة. 

**ما سوف تتعلمه:**
- إعداد بيئتك باستخدام Aspose.Slides لـ .NET
- ربط الخطوط في تحويل HTML
- كتابة وحدات تحكم مخصصة لتضمين الخطوط
- التطبيقات العملية واعتبارات الأداء

دعونا نتعمق في الخطوات المطلوبة لتحقيق ذلك.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

### المكتبات والتبعيات المطلوبة
- **Aspose.Slides لـ .NET** المكتبة: المكون الأساسي لتنفيذنا.

### متطلبات إعداد البيئة
- بيئة تطوير مع تثبيت .NET Framework أو .NET Core.

### متطلبات المعرفة
- فهم أساسي لبرمجة C#.
- المعرفة بلغة HTML وCSS، وخاصةً `@font-face` قاعدة.

## إعداد Aspose.Slides لـ .NET

لاستخدام Aspose.Slides في مشروع .NET الخاص بك، عليك تثبيت المكتبة. إليك عدة طرق:

### استخدام .NET CLI
```bash
dotnet add package Aspose.Slides
```

### استخدام وحدة تحكم إدارة الحزم
```powershell
Install-Package Aspose.Slides
```

### عبر واجهة مستخدم مدير الحزم NuGet
- افتح مشروعك في Visual Studio.
- انتقل إلى "مدير حزمة NuGet".
- ابحث عن "Aspose.Slides" وقم بتثبيت الإصدار الأحدث.

### خطوات الحصول على الترخيص
يمكنك الحصول على ترخيص تجريبي مجاني لاختبار كافة الميزات دون قيود باتباع الخطوات التالية:
1. **نسخة تجريبية مجانية**:تنزيل ترخيص مؤقت [هنا](https://releases.aspose.com/slides/net/).
2. **رخصة مؤقتة**:تقدم بطلب للحصول على وصول موسع [هنا](https://purchase.aspose.com/temporary-license/).
3. **شراء**:للحصول على الوظائف الكاملة، قم بشراء ترخيص [هنا](https://purchase.aspose.com/buy).

### التهيئة والإعداد الأساسي
```csharp
// إنشاء مثيل لفئة الترخيص
easpose.slides.License license = new aspose.slides.License();

// قم بتطبيق الترخيص من مسار الملف
license.SetLicense("Aspose.Slides.lic");
```

## دليل التنفيذ

الآن، دعنا ننفذ ربط الخطوط في تحويل HTML باستخدام **Aspose.Slides لـ .NET**.

### نظرة عامة على الميزة: ربط الخطوط في تحويل HTML
تضمن هذه الميزة ربط جميع الخطوط المستخدمة في العرض التقديمي مباشرةً بملف HTML الناتج عن طريق تضمين ملفات الخطوط. توفر هذه الطريقة حلاً فعالاً للحفاظ على اتساق التصميم عبر مختلف المتصفحات والمنصات.

#### الخطوة 1: إنشاء وحدة التحكم المخصصة
إنشاء فئة وحدة تحكم مخصصة `LinkAllFontsHtmlController` الذي يرث من `EmbedAllFontsHtmlController`:
```csharp
using Aspose.Slides.Export;
using System.IO;

public class LinkAllFontsHtmlController : EmbedAllFontsHtmlController
{
    private readonly string m_basePath;

    public LinkAllFontsHtmlController(string[] fontNameExcludeList, string basePath)
        : base(fontNameExcludeList)
    {
        m_basePath = basePath; // تعيين الدليل الذي سيتم تخزين ملفات الخطوط فيه
    }
}
```
#### الخطوة 2: تنفيذ طريقة كتابة الخط
ال `WriteFont` تكتب الطريقة بيانات الخط إلى ملف وتولد كود HTML المقابل للتضمين:
```csharp
public override void WriteFont(
    IHtmlGenerator generator,
    IFontData originalFont,
    IFontData substitutedFont,
    string fontStyle,
    string fontWeight,
    byte[] fontData)
{
    // حدد اسم الخط الذي تريد استخدامه، مع تفضيل الخطوط البديلة إذا كانت متوفرة.
    string fontName = substitutedFont == null ? originalFont.FontName : substitutedFont.FontName;

    // إنشاء مسار ملف لملف الخط .woff.
    string path = Path.Combine(m_basePath, $"{fontName}.woff`);
    
    // اكتب بيانات الخط إلى مسار الملف المحدد.
    File.WriteAllBytes(path, fontData);

    // إنشاء كتلة نمط HTML تتضمن الخط باستخدام قاعدة @font-face.
    generator.AddHtml("<style>");
    generator.AddHtml("@font-face { ");
    generator.AddHtml($"font-family: '{fontName}'; ");
    generator.AddHtml($"src: url('{path}');");
    generator.AddHtml(\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}