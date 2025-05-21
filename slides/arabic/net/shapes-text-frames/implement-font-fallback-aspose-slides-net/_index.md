---
"date": "2025-04-16"
"description": "تعرف على كيفية تنفيذ قواعد الرجوع إلى الخطوط في Aspose.Slides لـ .NET لضمان عرض العروض التقديمية الخاصة بك للنص بشكل صحيح عبر اللغات والنصوص المختلفة."
"title": "كيفية تعيين قواعد الرجوع إلى الخطوط في Aspose.Slides لـ .NET - دليل شامل"
"url": "/ar/net/shapes-text-frames/implement-font-fallback-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية تعيين قواعد الرجوع إلى الخطوط في Aspose.Slides لـ .NET: دليل شامل

## مقدمة

يتطلب إنشاء العروض التقديمية باستخدام Aspose.Slides لـ .NET أحيانًا التعامل مع أحرف لا تدعمها خطوط معينة، مثل التاميلية أو اليابانية هيراغانا. يُعدّ ضبط قواعد الخطوط البديلة أمرًا أساسيًا لضمان عرض النص بشكل صحيح في عرضك التقديمي عبر مختلف اللغات والرموز.

في هذا البرنامج التعليمي، سنرشدك خلال عملية تطبيق قواعد الخطوط البديلة باستخدام Aspose.Slides لـ .NET. من التثبيت إلى التطبيقات العملية، يضمن هذا الدليل تناسقًا بصريًا لعروضك التقديمية بغض النظر عن محتواها.

**ما سوف تتعلمه:**
- تعريف نطاقات Unicode للبرامج النصية المختلفة.
- إعداد الخطوط الاحتياطية للأحرف غير المدعومة.
- تطبيق خط بديل في سيناريوهات العرض التقديمي في العالم الحقيقي.
- نصائح لتحسين الأداء والتكامل مع الأنظمة الأخرى.

دعونا نبدأ بمراجعة المتطلبات الأساسية.

## المتطلبات الأساسية

قبل البدء، تأكد من أن لديك:

- **Aspose.Slides لـ .NET** تم تثبيت المكتبة. ثبّتها باستخدام أيٍّ من الطرق التالية:
  - **.NET CLI**: يجري `dotnet add package Aspose.Slides`
  - **مدير الحزم**: ينفذ `Install-Package Aspose.Slides`
  - **واجهة مستخدم مدير الحزم NuGet**:البحث عن الإصدار الأحدث وتثبيته.
- بيئة تطوير تم إعدادها باستخدام .NET Core أو .NET Framework (الإصدار 4.5 أو أحدث).
- فهم أساسي لبرمجة C#.

## إعداد Aspose.Slides لـ .NET

للبدء في استخدام Aspose.Slides، احصل على ترخيص من [موقع Aspose](https://purchase.aspose.com/buy). إليك كيفية إعداده:

1. **تثبيت**:اتبع خطوات التثبيت المذكورة أعلاه.
2. **إعداد الترخيص**:
   - قم بتحميل ملف الترخيص الخاص بك إلى مشروعك باستخدام:
     ```csharp
     License license = new License();
     license.SetLicense("path_to_your_license_file.lic");
     ```

يتيح لك هذا الإعداد البدء في العمل مع Aspose.Slides لـ .NET.

## دليل التنفيذ

في هذا القسم، سوف نقوم بتوضيح عملية تعيين قواعد الرجوع إلى الخطوط في خطوات واضحة.

### 1. تحديد نطاقات Unicode والخطوط البديلة

تتطلب كل مجموعة نصوص أو رموز نطاقات Unicode محددة وخطوط احتياطية مقابلة لضمان العرض المناسب.

#### النص التاميلي

- **ملخص**:استخدم "Vijaya" للأحرف التاميلية عندما يفتقر الخط الأساسي إلى الدعم.

**خطوات التنفيذ:**

##### الخطوة 1: تحديد نطاق Unicode
```csharp
uint startUnicodeIndexTamil = 0x0B80; // بداية النطاق التاميلي
uint endUnicodeIndexTamil = 0x0BFF;   // نهاية النطاق التاميلي
```
تعرف هذه القطعة على نطاق Unicode للأحرف التاميلية.

##### الخطوة 2: إنشاء قاعدة احتياطية
```csharp
IFontFallBackRule tamilFallbackRule = new FontFallBackRule(startUnicodeIndexTamil, endUnicodeIndexTamil, "Vijaya");
```
هنا، نقوم بإنشاء قاعدة احتياطية باستخدام "Vijaya" كخط بديل.

#### هيراغانا اليابانية

- **ملخص**:استخدم "MS Mincho" أو "MS Gothic" للأحرف الهيراجانا غير المدعومة.

**خطوات التنفيذ:**

##### الخطوة 1: تحديد نطاق Unicode
```csharp
uint startUnicodeIndexHiragana = 0x3040; // بداية سلسلة هيراجانا
uint endUnicodeIndexHiragana = 0x309F;   // نهاية نطاق الهيراجانا
```
تحدد هذه القطعة حدود Unicode لـ Hiragana.

##### الخطوة 2: إنشاء قاعدة احتياطية
```csharp
IFontFallBackRule hiraganaFallbackRule = new FontFallBackRule(startUnicodeIndexHiragana, endUnicodeIndexHiragana, "MS Mincho, MS Gothic");
```
تحدد هذه القاعدة الخطوط الاحتياطية المتعددة لأحرف الهيراجانا.

#### شخصيات إيموجي

- **ملخص**:تأكد من عرض الرموز التعبيرية باستخدام الخطوط المناسبة مثل "Segoe UI Emoji".

**خطوات التنفيذ:**

##### الخطوة 1: تحديد نطاق Unicode
```csharp
uint startUnicodeIndexEmoji = 0x1F300; // بداية نطاق الرموز التعبيرية
uint endUnicodeIndexEmoji = 0x1F64F;   // نهاية نطاق الرموز التعبيرية
```
يحدد هذا نطاق Unicode للرموز التعبيرية.

##### الخطوة 2: إنشاء قاعدة احتياطية
```csharp
string[] fontNamesEmoji = { "Segoe UI Emoji, Segoe UI Symbol\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}