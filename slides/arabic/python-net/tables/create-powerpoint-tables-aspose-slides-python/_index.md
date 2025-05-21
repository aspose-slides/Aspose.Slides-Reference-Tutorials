---
"date": "2025-04-24"
"description": "تعرّف على كيفية إنشاء جداول PowerPoint باستخدام Aspose.Slides للغة بايثون. يُبسّط هذا الدليل المُفصّل العملية، ويضمن اتساق عروضك التقديمية."
"title": "إنشاء جداول PowerPoint باستخدام Aspose.Slides وPython - دليل خطوة بخطوة"
"url": "/ar/python-net/tables/create-powerpoint-tables-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء جداول PowerPoint باستخدام Aspose.Slides وPython

إنشاء الجداول في عروض PowerPoint التقديمية برمجيًا يوفر عليك الوقت ويضمن اتساق المستندات. سواء كنت تُنشئ تقارير، أو تُنشئ مواد تدريبية، أو تُطوّر أدوات عروض تقديمية آلية، فإن استخدام Aspose.Slides لـ Python يُبسط هذه العملية من خلال السماح بدمج إنشاء الجداول بسلاسة في قاعدة بياناتك البرمجية. سيرشدك هذا الدليل التفصيلي خطوة بخطوة إلى خطوات إنشاء جدول PowerPoint في الشريحة الأولى باستخدام Aspose.Slides وPython.

## ما سوف تتعلمه:
- كيفية إعداد البيئة الخاصة بك لـ Aspose.Slides باستخدام Python
- تعليمات خطوة بخطوة لإنشاء الجداول في شرائح PowerPoint
- التطبيقات العملية لدمج الجداول في العروض التقديمية
- اعتبارات الأداء عند العمل مع Aspose.Slides

دعونا نتعمق في المتطلبات الأساسية ونبدأ!

### المتطلبات الأساسية

قبل البدء، تأكد من إعداد بيئتك بشكل صحيح. إليك ما ستحتاجه:
1. **بيئة بايثون**:تأكد من تثبيت Python 3.x على نظامك.
2. **Aspose.Slides لـ Python**ستكون هذه المكتبة بمثابة أداة أساسية لدينا للتعامل مع ملفات PowerPoint.
3. **بيئة تطوير متكاملة أو محرر نصوص**:مثل PyCharm أو VSCode أو أي محرر تفضله.

### إعداد Aspose.Slides لـ Python

لبدء استخدام Aspose.Slides لـ Python، اتبع الخطوات التالية:

**التثبيت عبر pip:**

```bash
pip install aspose.slides
```

**الحصول على الترخيص:** 
- **نسخة تجريبية مجانية**:قم بتنزيل النسخة التجريبية المجانية من [موقع Aspose](https://releases.aspose.com/slides/python-net/).
- **رخصة مؤقتة**:احصل على ترخيص مؤقت للاستخدام الموسع من خلال زيارة هذا [وصلة](https://purchase.aspose.com/temporary-license/).
- **شراء**:للحصول على الميزات الكاملة، فكر في شراء ترخيص من [صفحة الشراء](https://purchase.aspose.com/buy).

**التهيئة الأساسية:**

بعد التثبيت، يمكنك البدء باستخدام Aspose.Slides في نصوص بايثون. استورد المكتبة كما هو موضح أدناه:

```python
import aspose.slides as slides
```

### دليل التنفيذ

الآن بعد أن قمنا بإعداد بيئتنا، فلننتقل إلى إنشاء الجداول.

#### إنشاء جدول على شريحة

**ملخص**:سنقوم بإنشاء جدول بسيط وإضافته إلى الشريحة الأولى من عرض تقديمي على PowerPoint. 

##### الخطوة 1: إنشاء مثيل لفئة العرض التقديمي

ال `Presentation` تُمثل الفئة ملف PPT. هنا، سنفتح أو ننشئ عرضًا تقديميًا جديدًا:

```python
with slides.Presentation() as pres:
    # يتم استخدام مثيل العرض التقديمي داخل كتلة مدير السياق هذه.
```

##### الخطوة 2: الوصول إلى الشريحة الأولى

الوصول إلى الشريحة الأولى يسمح لنا بإضافة جدولنا هناك:

```python
slide = pres.slides[0]  # سيؤدي هذا إلى جلب الشريحة الأولى من العرض التقديمي.
```

##### الخطوة 3: تحديد أبعاد الجدول وإضافتها إلى الشريحة

قم بتحديد عرض الأعمدة وارتفاع الصفوف، ثم أضف جدولًا عند الإحداثيات المحددة (x=50، y=50):

```python
dbl_cols = [50, 50, 50]  # عرض الأعمدة
dbl_rows = [50, 30, 30, 30, 30]  # ارتفاعات الصفوف

table = slide.shapes.add_table(50, 50, dbl_cols, dbl_rows)  # إضافة جدول إلى الشريحة.
```

##### الخطوة 4: ملء خلايا الجدول بالنص

قم بالتكرار خلال كل خلية في الجدول وأضف النص:

```python
for row in table.rows:
    for cell in row:
        tf = cell.text_frame
        tf.text = "T" + str(cell.first_row_index) + str(cell.first_column_index)
        
        if tf.paragraphs:  # تأكد من وجود فقرات للتعديل.
            tf.paragraphs[0].portions[0].portion_format.font_height = 10
            tf.paragraphs[0].paragraph_format.bullet.type = slides.BulletType.NONE
```

##### الخطوة 5: حفظ العرض التقديمي

وأخيرًا، احفظ عرضك التقديمي في الموقع المحدد:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/tables_create_table_out.ppt\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}