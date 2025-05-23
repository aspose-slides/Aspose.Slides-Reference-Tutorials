---
"date": "2025-04-22"
"description": "เรียนรู้วิธีแสดงป้ายเปอร์เซ็นต์บนแผนภูมิในงานนำเสนอ PowerPoint ได้อย่างง่ายดายโดยใช้ Aspose.Slides สำหรับ Python เหมาะอย่างยิ่งสำหรับการปรับปรุงการแสดงภาพข้อมูล"
"title": "วิธีการแสดงป้ายเปอร์เซ็นต์บนแผนภูมิโดยใช้ Aspose.Slides สำหรับ Python - คู่มือฉบับสมบูรณ์"
"url": "/th/python-net/charts-graphs/display-percentage-labels-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีการแสดงป้ายเปอร์เซ็นต์บนแผนภูมิโดยใช้ Aspose.Slides สำหรับ Python

## การแนะนำ

การสร้างภาพข้อมูลอย่างมีประสิทธิผลเป็นสิ่งสำคัญในงานนำเสนอและรายงาน โดยเฉพาะอย่างยิ่งเมื่อคุณต้องการเน้นสัดส่วนหรือการแจกแจงอย่างชัดเจน แต่จะเกิดอะไรขึ้นหากคุณต้องการให้แสดงเปอร์เซ็นต์เหล่านั้นโดยตรงบนแผนภูมิของคุณ คู่มือที่ครอบคลุมนี้จะแนะนำคุณเกี่ยวกับการใช้ **Aspose.Slides สำหรับ Python** เพื่อแสดงค่าเปอร์เซ็นต์เป็นป้ายกำกับบนแผนภูมิได้อย่างง่ายดาย

### สิ่งที่คุณจะได้เรียนรู้:
- วิธีการสร้างและฝังแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Python
- การแสดงจุดข้อมูลเป็นป้ายเปอร์เซ็นต์บนแผนภูมิของคุณ
- บันทึกและจัดการการนำเสนอ PowerPoint อย่างมีประสิทธิภาพ

พร้อมที่จะเริ่มเพิ่มภาพเชิงลึกลงในข้อมูลของคุณหรือยัง มาดูสิ่งที่คุณต้องการก่อนจะลงลึกในโค้ดกันก่อน!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- **Aspose.Slides สำหรับ Python**:ไลบรารีนี้มีความจำเป็นสำหรับการสร้างและจัดการการนำเสนอ PowerPoint ด้วยโปรแกรม
- **สภาพแวดล้อม Python**:ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Python และการตั้งค่าสภาพแวดล้อม
- **ตัวจัดการแพ็กเกจ PIP**: ใช้เพื่อติดตั้ง Aspose.Slides

## การตั้งค่า Aspose.Slides สำหรับ Python

ในการเริ่มใช้ Aspose.Slides ก่อนอื่นคุณต้องติดตั้ง:

```bash
pip install aspose.slides
```

### ขั้นตอนการรับใบอนุญาต:
คุณสามารถเริ่มต้นด้วยการทดลองใช้ฟรีหรือรับใบอนุญาตชั่วคราวเพื่อสำรวจความสามารถทั้งหมดของ Aspose.Slides หากต้องการใช้งานแบบขยายเวลา โปรดพิจารณาซื้อการสมัครใช้งาน

#### การเริ่มต้นและการตั้งค่าเบื้องต้น

เมื่อติดตั้งแล้ว คุณจะเริ่มต้นสภาพแวดล้อมการนำเสนอของคุณดังนี้:

```python
import aspose.slides as slides

# เริ่มต้นวัตถุการนำเสนอ
def create_presentation():
    with slides.Presentation() as presentation:
        # รหัสของคุณที่นี่
```

## คู่มือการใช้งาน

ตอนนี้เราได้ตั้งค่าเสร็จแล้ว เรามาเริ่มแสดงเปอร์เซ็นต์บนแผนภูมิกัน

### การสร้างแผนภูมิและการเพิ่มข้อมูล

#### ภาพรวม
เราจะสร้างแผนภูมิคอลัมน์แบบเรียงซ้อนพร้อมป้ายเปอร์เซ็นต์สำหรับจุดข้อมูลแต่ละจุด ช่วยให้ผู้ดูเห็นสัดส่วนที่แน่นอนได้ในทันที

##### ขั้นตอนที่ 1: เพิ่มแผนภูมิลงในสไลด์ของคุณ

```python
# เข้าถึงสไลด์แรกในการนำเสนอของคุณ
def add_chart_to_slide(presentation):
    slide = presentation.slides[0]

    # เพิ่มแผนภูมิคอลัมน์แบบซ้อนกัน
    chart = slide.shapes.add_chart(slides.charts.ChartType.STACKED_COLUMN, 20, 20, 400, 400)
```

โค้ดสั้นๆ นี้จะเพิ่มแผนภูมิพื้นฐานลงในสไลด์แรก `add_chart` วิธีการระบุประเภทของแผนภูมิรวมทั้งตำแหน่งและขนาดของแผนภูมิ

##### ขั้นตอนที่ 2: คำนวณค่ารวมสำหรับหมวดหมู่

```python
def calculate_totals(chart):
    total_for_category = []
    # สรุปค่ารวมของทุกซีรี่ส์ในแต่ละหมวดหมู่
    for k in range(len(chart.chart_data.categories)):
        value = sum(
            chart.chart_data.series[i].data_points[k].value.data 
            for i in range(len(chart.chart_data.series))
        )
        total_for_category.append(value)
```

ลูปนี้จะคำนวณผลรวมของจุดข้อมูลทั้งหมดในชุด ซึ่งเป็นสิ่งสำคัญสำหรับการคำนวณเปอร์เซ็นต์

#### การตั้งค่าป้ายเปอร์เซ็นต์

##### ขั้นตอนที่ 3: กำหนดค่าจุดข้อมูลซีรีส์

```python
def set_percentage_labels(chart, totals):
    for series in chart.chart_data.series:
        # ตั้งค่าตัวเลือกป้ายกำกับเริ่มต้นเพื่อซ่อนข้อมูลที่ไม่จำเป็น
        series.labels.default_data_label_format.show_legend_key = False
        
        # คำนวณและตั้งค่าป้ายเปอร์เซ็นต์
        for j in range(len(series.data_points)):
            lbl = series.data_points[j].label
            data_point_percent = (series.data_points[j].value.data / totals[j]) * 100.0
            
            # สร้างส่วนข้อความที่มีค่าเปอร์เซ็นต์
            port = slides.Portion()
            port.text = "{0:4.2f} %".format(data_point_percent)
            port.portion_format.font_height = 8

            # ล้างฉลากที่มีอยู่และเพิ่มฉลากเปอร์เซ็นต์ใหม่
            lbl.text_frame_for_overriding.text = ""
            para = lbl.text_frame_for_overriding.paragraphs[0]
            para.portions.add(port)

            # ซ่อนองค์ประกอบป้ายข้อมูลอื่น ๆ
            lbl.data_label_format.show_series_name = False
            lbl.data_label_format.show_percentage = False
            lbl.data_label_format.show_legend_key = False
            lbl.data_label_format.show_category_name = False
            lbl.data_label_format.show_bubble_size = False
```

ส่วนนี้ประมวลผลจุดข้อมูลแต่ละจุดเพื่อคำนวณเปอร์เซ็นต์ของผลรวม และกำหนดให้เป็นป้ายกำกับ

### การบันทึกการนำเสนอของคุณ

```python
def save_presentation(presentation, output_directory):
    # บันทึกการนำเสนอของคุณด้วยการปรับเปลี่ยน
    presentation.save(f"{output_directory}/charts_display_percentage_as_labels_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}