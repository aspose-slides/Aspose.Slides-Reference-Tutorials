---
"date": "2025-04-22"
"description": "تعرّف على كيفية تخصيص خطوط المخططات في عروض PowerPoint التقديمية باستخدام Aspose.Slides مع Python. اتبع هذا الدليل للاطلاع على الخطوات التفصيلية والتطبيقات العملية."
"title": "كيفية تخصيص خطوط المخططات في PowerPoint باستخدام Aspose.Slides لـ Python"
"url": "/ar/python-net/charts-graphs/customize-chart-fonts-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية تخصيص خطوط المخططات في PowerPoint باستخدام Aspose.Slides لـ Python

## مقدمة
هل ترغب في تحسين المظهر المرئي لرسوماتك البيانية في عروض PowerPoint التقديمية باستخدام بايثون؟ لست وحدك! يواجه العديد من المطورين تحديات عند محاولة تخصيص خطوط الرسوم البيانية برمجيًا. سيرشدك هذا الدليل إلى كيفية ضبط خصائص الخطوط للرسوم البيانية في PowerPoint باستخدام **Aspose.Slides لـ Python**من خلال إتقان هذه التقنيات، يمكنك إنشاء شرائح جذابة بصريًا وذات مظهر احترافي دون عناء.

في هذا البرنامج التعليمي، سنغطي:
- إعداد Aspose.Slides لـ Python
- تخصيص خطوط الرسم البياني بسهولة
- تطبيقات عملية لمشاريعك

لنبدأ بالتأكد من أن كل شيء جاهز!

### المتطلبات الأساسية
قبل الغوص في الأمر، تأكد من أنك قد غطيت المتطلبات الأساسية التالية:
1. **بيئة بايثون**:تأكد من تثبيت Python (الإصدار 3.6 أو أعلى).
2. **Aspose.Slides لـ Python**:ستحتاج إلى هذه المكتبة للتعامل مع ملفات PowerPoint.
3. **المعرفة الأساسية**:ستكون المعرفة ببرمجة Python والفهم الأساسي للعمل مع المكتبات مفيدة.

## إعداد Aspose.Slides لـ Python
للبدء، ستحتاج إلى تثبيت `aspose.slides` المكتبة باستخدام pip:

```bash
pip install aspose.slides
```

### خطوات الحصول على الترخيص
- **نسخة تجريبية مجانية**:قم بتنزيل نسخة تجريبية مجانية من [الموقع الرسمي لـ Aspose](https://releases.aspose.com/slides/python-net/).
- **رخصة مؤقتة**: لإجراء اختبارات أكثر شمولاً، احصل على ترخيص مؤقت من خلالهم [صفحة الشراء](https://purchase.aspose.com/temporary-license/).
- **شراء**:إذا وجدت أن الأداة لا تقدر بثمن بالنسبة لاحتياجاتك، ففكر في شراء ترخيص كامل من [موقع شراء Aspose](https://purchase.aspose.com/buy).

بمجرد التثبيت والترخيص، قم بتشغيل Aspose.Slides في Python:

```python
import aspose.slides as slides

# قم بتهيئة كائن العرض التقديمي باستخدام slides.Presentation() كـ pres:
    # الكود الخاص بك يذهب هنا
```

## دليل التنفيذ
في هذا القسم، سوف نستكشف كيفية تعيين خصائص خط الرسم البياني خطوة بخطوة.

### إضافة مخطط عمودي مجمع
أولاً، دعنا نضيف مخططًا عموديًا مجمعًا إلى عرضنا التقديمي:

```python
# أضف مخططًا عموديًا مجمعًا في الموضع والحجم المحددين.
chart = pres.slides[0].shapes.add_chart(
    slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 500, 400
)
```
**توضيح**:تضيف هذه القطعة مخططًا جديدًا إلى الشريحة الأولى من عرضك التقديمي. `add_chart` تتطلب هذه الطريقة تحديد نوع الرسم البياني وموضعه وحجمه على الشريحة.

### ضبط خصائص الخط
بعد ذلك، دعنا نحدد ارتفاع الخط للنص داخل الرسم البياني الخاص بنا:

```python
# تعيين ارتفاع الخط للنص في الرسم البياني.
chart.text_format.portion_format.font_height = 20
```
**توضيح**:يضبط هذا السطر حجم الخط لجميع أجزاء النص في مخططك. `font_height` يتم تحديد الخاصية بالنقاط، ويمكنك تعديل هذه القيمة لتناسب احتياجات التصميم الخاصة بك.

### عرض تسميات البيانات
لتحسين قابلية القراءة، سنعرض القيم على تسميات البيانات:

```python
# عرض القيم على تسميات البيانات للسلسلة الأولى.
chart.chart_data.series[0].labels.default_data_label_format.show_value = True
```
**توضيح**يضمن هذا الإعداد إظهار كل نقطة بيانات في السلسلة الأولى لقيمتها. يُعد هذا مفيدًا بشكل خاص لعرض معلومات دقيقة في لمحة.

### حفظ العرض التقديمي الخاص بك
وأخيرًا، احفظ العرض التقديمي في الموقع المطلوب:

```python
# احفظ العرض التقديمي في دليل الإخراج المحدد.
pres.save(
    "YOUR_OUTPUT_DIRECTORY/charts_font_properties_for_chart_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}