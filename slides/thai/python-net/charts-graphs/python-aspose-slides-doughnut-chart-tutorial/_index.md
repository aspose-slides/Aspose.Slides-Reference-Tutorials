---
"date": "2025-04-22"
"description": "เรียนรู้วิธีสร้างแผนภูมิโดนัทด้วย Python และ Aspose.Slides คำแนะนำทีละขั้นตอนนี้ครอบคลุมถึงการตั้งค่า การปรับแต่ง และแนวทางปฏิบัติที่ดีที่สุดเพื่อปรับปรุงการนำเสนอของคุณ"
"title": "วิธีการสร้างแผนภูมิโดนัทใน Python โดยใช้ Aspose.Slides พร้อมคำแนะนำทีละขั้นตอน"
"url": "/th/python-net/charts-graphs/python-aspose-slides-doughnut-chart-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีการสร้างแผนภูมิโดนัทใน Python โดยใช้ Aspose.Slides: คำแนะนำทีละขั้นตอน

ในแวดวงของการแสดงภาพข้อมูล การนำเสนอข้อมูลอย่างมีประสิทธิภาพสามารถส่งผลต่อความเข้าใจและการตัดสินใจได้อย่างมาก ไม่ว่าคุณจะกำลังสร้างงานนำเสนอทางธุรกิจหรือวิเคราะห์ชุดข้อมูลที่ซับซ้อน แผนภูมิเป็นเครื่องมือที่สำคัญ ในบรรดาแผนภูมิประเภทต่างๆ แผนภูมิโดนัทถือเป็นวิธีที่น่าสนใจในการแสดงข้อมูลตามสัดส่วนพร้อมรูตรงกลางที่ใช้งานง่าย คำแนะนำทีละขั้นตอนนี้จะแนะนำคุณเกี่ยวกับการสร้างแผนภูมิโดนัทใน Python โดยใช้ Aspose.Slides ซึ่งเป็นไลบรารีอันทรงพลังสำหรับการจัดการงานนำเสนอ

## สิ่งที่คุณจะได้เรียนรู้
- วิธีตั้งค่าและใช้งาน Aspose.Slides สำหรับ Python
- กระบวนการเพิ่มแผนภูมิโดนัทลงในสไลด์การนำเสนอของคุณ
- การปรับแต่งซีรีส์และหมวดหมู่ภายในแผนภูมิ
- การปรับแต่งองค์ประกอบภาพ เช่น ป้ายกำกับ สี และเอฟเฟกต์การระเบิด
- แนวทางปฏิบัติที่ดีที่สุดสำหรับการเพิ่มประสิทธิภาพการทำงานด้วย Aspose.Slides

## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มต้น ให้แน่ใจว่าคุณมี:
- **สภาพแวดล้อม Python**:Python 3.x ติดตั้งอยู่บนเครื่องของคุณแล้ว
- **Aspose.Slides สำหรับ Python**: ติดตั้งไลบรารีนี้โดยใช้ pip
- **ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Python**:ความคุ้นเคยกับลูปและการเขียนโปรแกรมเชิงวัตถุจะเป็นประโยชน์

## การตั้งค่า Aspose.Slides สำหรับ Python
ในการเริ่มต้น ให้ติดตั้งไลบรารี Aspose.Slides ผ่าน pip:

```bash
pip install aspose.slides
```

### การขอใบอนุญาต
Aspose เสนอการทดลองใช้ฟรีเพื่อทดสอบฟีเจอร์ต่างๆ โดยไม่มีข้อจำกัดเป็นเวลาจำกัด หากต้องการรับสิ่งนี้:
1. เยี่ยมชม [ทดลองใช้งานฟรี](https://releases.aspose.com/slides/python-net/) หน้าหนังสือ.
2. ปฏิบัติตามคำแนะนำเพื่อดาวน์โหลดและสมัครใบอนุญาตชั่วคราวของคุณ

หากต้องการใช้ต่อ โปรดพิจารณาซื้อการสมัครสมาชิกจาก [หน้าการสั่งซื้อ](https://purchase-aspose.com/buy).

### การเริ่มต้นขั้นพื้นฐาน
หลังจากตั้งค่า Aspose.Slides แล้ว ให้เริ่มต้นระบบดังต่อไปนี้:

```python
import aspose.slides as slides

# สร้างอินสแตนซ์ของคลาสการนำเสนอ
with slides.Presentation() as pres:
    # โค้ดของคุณสำหรับจัดการการนำเสนออยู่ที่นี่

# บันทึกการนำเสนอหลังจากทำการเปลี่ยนแปลง
pres.save("output.pptx", slides.export.SaveFormat.PPTX)
```

## คู่มือการใช้งาน
เมื่อตั้งค่า Aspose.Slides เรียบร้อยแล้ว ให้ทำตามขั้นตอนเหล่านี้เพื่อเพิ่มแผนภูมิโดนัทลงในสไลด์การนำเสนอของคุณ

### การสร้างงานนำเสนอใหม่และการเพิ่มสไลด์
เริ่มต้นด้วยการสร้างอินสแตนซ์ของ `Presentation` ระดับ:

```python
import aspose.slides as slides

with slides.Presentation() as pres:
    # เข้าถึงหรือสร้างสไลด์ภายในบริบทนี้
```

### การเพิ่มแผนภูมิโดนัทลงในสไลด์แรก
เข้าถึงสไลด์แรกและใช้ `add_chart` วิธีการ ระบุชนิดแผนภูมิเป็น `DOUGHNUT`พร้อมตำแหน่งและขนาด:

```python
slide = pres.slides[0]
chart = slide.shapes.add_chart(slides.charts.ChartType.DOUGHNUT, 10, 10, 500, 500, False)
```

### การกำหนดค่าข้อมูลแผนภูมิ
ล้างข้อมูลที่มีอยู่และกำหนดค่าการตั้งค่าเช่นซ่อนคำอธิบาย:

```python
workbook = chart.chart_data.chart_data_workbook
chart.chart_data.series.clear()
chart.chart_data.categories.clear()
chart.has_legend = False
```

### การเพิ่มซีรี่ส์และหมวดหมู่
เพิ่มซีรีส์และหมวดหมู่ต่างๆ ลงในแผนภูมิโดนัท ต่อไปนี้เป็นวิธีการสร้างซีรีส์ 15 ชุดที่มีคุณสมบัติเฉพาะ:

```python
series_index = 0
while series_index < 15:
    series = chart.chart_data.series.add(
        workbook.get_cell(0, 0, series_index + 1, f"SERIES {series_index}"),
        chart.type
    )
    series.explosion = 0
    series.parent_series_group.doughnut_hole_size = 20
    series.parent_series_group.first_slice_angle = 351
    series_index += 1
```

เพิ่มหมวดหมู่ในลักษณะเดียวกัน:

```python
category_index = 0
while category_index < 15:
    chart.chart_data.categories.add(
        workbook.get_cell(0, category_index + 1, 0, f"CATEGORY {category_index}")
    )
    # เพิ่มจุดข้อมูลสำหรับแต่ละชุด
    i = 0
    while i < len(chart.chart_data.series):
        i_cs = chart.chart_data.series[i]
        data_point = i_cs.data_points.add_data_point_for_doughnut_series(
            workbook.get_cell(0, category_index + 1, i + 1, 1)
        )
        
        # ปรับแต่งลักษณะที่ปรากฏของจุดข้อมูลแต่ละจุด
        data_point.format.fill.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.solid_fill_color.color = drawing.Color.white
        data_point.format.line.width = 1
        
        # กำหนดค่าการตั้งค่าฉลากสำหรับซีรีย์สุดท้าย
        if i == len(chart.chart_data.series) - 1:
            lbl = data_point.label
            lbl.text_format.text_block_format.autofit_type = slides.TextAutofitType.SHAPE
            lbl.data_label_format.text_format.portion_format.font_bold = slides.NullableBool.TRUE
            lbl.data_label_format.text_format.portion_format.latin_font = slides.FontData("DINPro-Bold")
            lbl.data_label_format.text_format.portion_format.font_height = 12
            lbl.data_label_format.show_value = False
            lbl.data_label_format.show_category_name = True
        
        i += 1
    category_index += 1
```

### การบันทึกการนำเสนอ
สุดท้าย ให้บันทึกการนำเสนอของคุณไปยังไดเร็กทอรีที่ระบุ:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/chart_add_doughnut_callout_out.pptx", slides.export.SaveFormat.PPTX)
```

## การประยุกต์ใช้งานจริง
แผนภูมิโดนัทมีความหลากหลายและสามารถใช้ในสถานการณ์ต่างๆ เช่น:
1. **การจัดสรรงบประมาณ**:แสดงให้เห็นว่าแผนกต่างๆ ใช้เงินที่จัดสรรไว้อย่างไร
2. **การวิเคราะห์ส่วนแบ่งการตลาด**:การเปรียบเทียบส่วนแบ่งทางการตลาดของผลิตภัณฑ์หรือบริษัทคู่แข่ง
3. **ผลการสำรวจ**:การแสดงภาพคำตอบต่อคำถามแบบสำรวจเกี่ยวกับการตั้งค่าหรือระดับความพึงพอใจ

## การพิจารณาประสิทธิภาพ
เพื่อให้แน่ใจว่าได้ประสิทธิภาพสูงสุดเมื่อใช้ Aspose.Slides:
- ลดการใช้หน่วยความจำโดยกำจัดวัตถุอย่างถูกต้องหลังใช้งาน
- โหลดการนำเสนอลงในหน่วยความจำเฉพาะเมื่อจำเป็นเท่านั้น และปิดโดยเร็วที่สุด
- พิจารณาใช้สไลด์ประมวลผลแบบแบตช์หากคุณต้องทำงานกับแผนภูมิจำนวนมาก

## บทสรุป
หากทำตามคำแนะนำนี้ คุณจะได้เรียนรู้วิธีสร้างแผนภูมิโดนัทแบบไดนามิกโดยใช้ Aspose.Slides สำหรับ Python การแสดงภาพเหล่านี้จะช่วยปรับปรุงการนำเสนอของคุณโดยทำให้ข้อมูลเข้าใจง่ายและน่าสนใจยิ่งขึ้น สำรวจคุณลักษณะต่างๆ ของไลบรารีต่อไปเพื่อปรับแต่งและเพิ่มประสิทธิภาพแผนภูมิของคุณให้มากขึ้น

## ส่วนคำถามที่พบบ่อย
1. **ฉันสามารถใช้ Aspose.Slides ได้โดยไม่ต้องซื้อใบอนุญาตหรือไม่**
   - ใช่ คุณสามารถเริ่มต้นด้วยใบอนุญาตทดลองใช้งานฟรีเพื่อวัตถุประสงค์ในการประเมินผล
2. **ฉันจะเปลี่ยนสีแผนภูมิใน Aspose.Slides ได้อย่างไร**
   - ใช้ `fill_format` คุณสมบัติในการกำหนดสีที่ต้องการให้กับองค์ประกอบแผนภูมิของคุณ
3. **สามารถส่งออกแผนภูมิเป็นรูปภาพได้หรือไม่**
   - ใช่ คุณสามารถเรนเดอร์สไลด์ที่มีแผนภูมิเป็นรูปแบบภาพได้โดยใช้ความสามารถในการเรนเดอร์ของไลบรารี
4. **ปัญหาทั่วไปที่มักเกิดขึ้นเมื่อเพิ่มแผนภูมิคืออะไร?**
   - ตรวจสอบให้แน่ใจว่าได้เพิ่มจุดข้อมูลและหมวดหมู่ทั้งหมดอย่างถูกต้องก่อนพยายามบันทึกหรือแสดงแผนภูมิของคุณ
5. **ฉันสามารถรวม Aspose.Slides เข้ากับไลบรารี Python อื่นๆ ได้หรือไม่**
   - แน่นอน! คุณสามารถใช้ร่วมกับไลบรารี เช่น Pandas เพื่อเพิ่มประสิทธิภาพการจัดการข้อมูล

## ทรัพยากร
- [เอกสารประกอบ Aspose.Slides](https://reference.aspose.com/slides/python-net/)
- [ดาวน์โหลด Aspose.Slides](https://releases.aspose.com/slides/python-net/)
- [ซื้อใบอนุญาต](https://purchase.aspose.com/buy)
- [ทดลองใช้งานฟรีและใบอนุญาตชั่วคราว](https://releases.aspose.com/slides/python-net/)
- [ฟอรั่มชุมชน Aspose](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}