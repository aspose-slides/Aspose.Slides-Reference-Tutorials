---
"date": "2025-04-23"
"description": "เรียนรู้วิธีปรับปรุงการนำเสนอ PowerPoint ของคุณด้วยแผนภูมิแบบไดนามิกโดยใช้ Aspose.Slides สำหรับ Python ปฏิบัติตามคำแนะนำทีละขั้นตอนนี้เพื่อสร้าง จัดการ และจัดรูปแบบแผนภูมิคอลัมน์แบบคลัสเตอร์อย่างมีประสิทธิภาพ"
"title": "สร้างและจัดรูปแบบแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Python"
"url": "/th/python-net/charts-graphs/create-charts-presentation-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# สร้างและจัดรูปแบบแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Python

## การแนะนำ

ในโลกปัจจุบันที่ข้อมูลเป็นปัจจัยสำคัญในการสื่อสารอย่างมีประสิทธิภาพ ไม่ว่าคุณจะเป็นนักวิเคราะห์ข้อมูล ผู้จัดการโครงการ หรือมืออาชีพทางธุรกิจ แผนภูมิแบบไดนามิกสามารถส่งเสริมข้อความของคุณได้อย่างมาก บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับการสร้างและจัดรูปแบบแผนภูมิคอลัมน์แบบคลัสเตอร์โดยใช้ Aspose.Slides สำหรับ Python ช่วยให้คุณยกระดับสไลด์ PowerPoint ของคุณได้อย่างง่ายดาย

**สิ่งที่คุณจะได้เรียนรู้:**
- วิธีการติดตั้งและตั้งค่า Aspose.Slides สำหรับ Python
- สร้างการนำเสนอใหม่และเพิ่มแผนภูมิคอลัมน์แบบคลัสเตอร์
- จัดการชุดข้อมูลและหมวดหมู่ภายในแผนภูมิ
- เติมและจัดรูปแบบข้อมูลชุดเพื่อให้มองเห็นได้ดีขึ้น

พร้อมที่จะปรับปรุงการนำเสนอของคุณหรือยัง มาสำรวจกันว่าคุณสามารถใช้ประโยชน์จาก Aspose.Slides เพื่อสร้างแผนภูมิที่น่าสนใจได้อย่างไร

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- **ติดตั้ง Python แล้ว:** ขอแนะนำเวอร์ชัน 3.6 ขึ้นไป
- **แพ็กเกจ Aspose.Slides สำหรับ Python:** ติดตั้งแพ็กเกจนี้โดยใช้ pip
- **ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Python:** ความคุ้นเคยกับรูปแบบภาษา Python และการจัดการไฟล์จะเป็นประโยชน์

## การตั้งค่า Aspose.Slides สำหรับ Python

ในการเริ่มต้น คุณจะต้องติดตั้งไลบรารี Aspose.Slides ซึ่งเป็นเครื่องมืออันทรงพลังที่ช่วยลดความยุ่งยากในการสร้างและจัดการงานนำเสนอ PowerPoint ใน Python

### การติดตั้ง

รันคำสั่งต่อไปนี้เพื่อติดตั้งแพ็กเกจ:

```bash
pip install aspose.slides
```

### การขอใบอนุญาต

Aspose นำเสนอใบอนุญาตทดลองใช้งานฟรีที่ให้คุณสำรวจความสามารถทั้งหมดได้โดยไม่มีข้อจำกัด ทำตามขั้นตอนเหล่านี้เพื่อรับใบอนุญาต:

1. เยี่ยม [ทดลองใช้ Aspose ฟรี](https://releases.aspose.com/slides/python-net/) เพื่อดาวน์โหลดแพ็คเกจทดลองใช้งาน
2. อีกวิธีหนึ่งคือขอใบอนุญาตชั่วคราวผ่านทาง [หน้าใบอนุญาตชั่วคราว](https://purchase-aspose.com/temporary-license/).

เมื่อคุณมีไฟล์ใบอนุญาตแล้ว ให้เริ่มต้นใช้งานในสคริปต์ Python ของคุณ:

```python
from aspose.slides import License

# ตั้งค่าใบอนุญาต Aspose.Slides
license = License()
license.set_license("path/to/your/license/file.lic")
```

## คู่มือการใช้งาน

เราจะแบ่งกระบวนการออกเป็นสามคุณลักษณะหลัก: การสร้างแผนภูมิ การจัดการชุดข้อมูลและหมวดหมู่ และการเติมและจัดรูปแบบข้อมูลชุด

### คุณลักษณะที่ 1: การสร้างและการเพิ่มแผนภูมิลงในงานนำเสนอ

#### ภาพรวม

คุณลักษณะนี้มุ่งเน้นที่การเพิ่มแผนภูมิคอลัมน์แบบคลัสเตอร์ลงในการนำเสนอของคุณโดยใช้ Aspose.Slides สำหรับ Python

#### การดำเนินการแบบทีละขั้นตอน

```python
import aspose.slides as slides

def create_and_add_chart():
    with slides.Presentation() as pres:
        # เพิ่มแผนภูมิคอลัมน์แบบคลัสเตอร์ที่ตำแหน่ง (100, 100) โดยมีความกว้าง 400 และความสูง 300
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 400, 300
        )
        
        # บันทึกการนำเสนอไปยังไฟล์ในไดเร็กทอรีเอาต์พุตของคุณ
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_creation_out.pptx", slides.export.SaveFormat.PPTX)

create_and_add_chart()
```

**คำอธิบาย:**
- **ตำแหน่งและขนาดของแผนภูมิ:** การ `add_chart` วิธีนี้ใช้กับพารามิเตอร์ที่ระบุประเภทแผนภูมิ ตำแหน่ง (x, y), ความกว้าง และความสูง
- **การบันทึกการนำเสนอ:** การนำเสนอจะถูกบันทึกไว้ในไดเร็กทอรีที่ระบุ

### คุณสมบัติ 2: การจัดการชุดข้อมูลและหมวดหมู่ของแผนภูมิ

#### ภาพรวม

หัวข้อนี้สาธิตวิธีการจัดการชุดข้อมูลและหมวดหมู่ภายในแผนภูมิของคุณอย่างมีประสิทธิภาพ

#### การดำเนินการแบบทีละขั้นตอน

```python
import aspose.slides as slides

def manage_chart_data_series_and_categories():
    with slides.Presentation() as pres:
        # เพิ่มแผนภูมิคอลัมน์แบบคลัสเตอร์ที่ตำแหน่ง (100, 100) โดยมีความกว้าง 400 และความสูง 300
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 400, 300
        )
        
        workbook = chart.chart_data.chart_data_workbook
        
        # ล้างซีรีย์และหมวดหมู่ที่มีอยู่ก่อนเพิ่มซีรีย์และหมวดหมู่ใหม่
        chart.chart_data.series.clear()
        chart.chart_data.categories.clear()
        
        # การเพิ่มซีรีส์ใหม่ชื่อ "ซีรีส์ 1" ลงในแผนภูมิ
        chart.chart_data.series.add(
            workbook.get_cell(0, 0, 1, "Series 1"), chart.type
        )
        
        # การเพิ่มสามหมวดหมู่ลงในข้อมูลแผนภูมิ
        chart.chart_data.categories.add(workbook.get_cell(0, 1, 0, "Category 1"))
        chart.chart_data.categories.add(workbook.get_cell(0, 2, 0, "Category 2"))
        chart.chart_data.categories.add(workbook.get_cell(0, 3, 0, "Category 3"))
        
        # บันทึกการนำเสนอไปยังไฟล์ในไดเร็กทอรีเอาต์พุตของคุณ
        pres.save("YOUR_OUTPUT_DIRECTORY/chart_series_categories_out.pptx", slides.export.SaveFormat.PPTX)

manage_chart_data_series_and_categories()
```

**คำอธิบาย:**
- **การล้างข้อมูลที่มีอยู่:** ก่อนที่จะเพิ่มซีรีย์หรือหมวดหมู่ใหม่ รายการและหมวดหมู่ที่มีอยู่จะถูกล้างเพื่อป้องกันข้อมูลซ้ำซ้อน
- **การเพิ่มซีรี่ส์และหมวดหมู่:** เพิ่มซีรีย์และหมวดหมู่ใหม่โดยใช้ `chart_data_workbook` วัตถุ.

### คุณลักษณะที่ 3: การเติมข้อมูลชุดข้อมูลและการจัดรูปแบบแผนภูมิ

#### ภาพรวม

ในฟีเจอร์นี้ เราจะเพิ่มจุดข้อมูลลงในแผนภูมิของคุณและจัดรูปแบบเพื่อเพิ่มความน่าสนใจให้กับแผนภูมิ

#### การดำเนินการแบบทีละขั้นตอน

```python
import aspose.slides as slides
import aspose.pydrawing as drawing

def populate_and_format_series_data():
    with slides.Presentation() as pres:
        # เพิ่มแผนภูมิคอลัมน์แบบคลัสเตอร์ที่ตำแหน่ง (100, 100) โดยมีความกว้าง 400 และความสูง 300
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 400, 300
        )
        
        workbook = chart.chart_data.chart_data_workbook
        
        # ล้างซีรีย์และหมวดหมู่ที่มีอยู่ก่อนเพิ่มซีรีย์และหมวดหมู่ใหม่
        chart.chart_data.series.clear()
        chart.chart_data.categories.clear()
        
        # การเพิ่มซีรีส์ใหม่ชื่อ "ซีรีส์ 1" ลงในแผนภูมิ
        chart.chart_data.series.add(
            workbook.get_cell(0, 0, 1, "Series 1"), chart.type
        )
        
        # การเพิ่มสามหมวดหมู่ลงในข้อมูลแผนภูมิ
        chart.chart_data.categories.add(workbook.get_cell(0, 1, 0, "Category 1"))
        chart.chart_data.categories.add(workbook.get_cell(0, 2, 0, "Category 2"))
        chart.chart_data.categories.add(workbook.get_cell(0, 3, 0, "Category 3"))
        
        # นำชุดแผนภูมิแรกมาเติมด้วยจุดข้อมูล
        series = chart.chart_data.series[0]
        series.data_points.add_data_point_for_bar_series(
            workbook.get_cell(0, 1, 1, -20)
        )
        series.data_points.add_data_point_for_bar_series(
            workbook.get_cell(0, 2, 1, 50)
        )
        series.data_points.add_data_point_for_bar_series(
            workbook.get_cell(0, 3, 1, -30)
        )
        
        # ตั้งค่าสีสำหรับค่าลบในซีรีส์
        invert_color = drawing.Color.red
        series.invert_if_negative = True
        series.format.fill.fill_type = slides.FillType.SOLID
        series.format.fill.solid_fill_color.color = series.get_automatic_series_color()
        series.inverted_solid_fill_color.color = invert_color
        
        # บันทึกการนำเสนอไปยังไฟล์ในไดเร็กทอรีเอาต์พุตของคุณ
        pres.save("YOUR_OUTPUT_DIRECTORY/populate_format_series_out.pptx", slides.export.SaveFormat.PPTX)

populate_and_format_series_data()
```

**คำอธิบาย:**
- **การเพิ่มจุดข้อมูล:** จุดข้อมูลจะถูกเพิ่มโดยใช้ `add_data_point_for_bar_series`-
- **การจัดรูปแบบค่าลบ:** ตัวเลือกการจัดรูปแบบแผนภูมิ เช่น การกลับสีสำหรับค่าลบ จะช่วยเพิ่มความสามารถในการอ่านข้อมูล

## การประยุกต์ใช้งานจริง

การใช้ Aspose.Slides เพื่อเพิ่มและจัดรูปแบบแผนภูมิในงานนำเสนอมีการใช้งานมากมาย:

1. **รายงานทางธุรกิจ:** ปรับปรุงรายงานรายไตรมาสด้วยภาพไดนามิกที่แสดงข้อมูลสำคัญได้อย่างชัดเจน
2. **สื่อการเรียนรู้:** สร้างเนื้อหาทางการศึกษาที่น่าสนใจด้วยการนำเสนอข้อมูลที่ซับซ้อนในรูปแบบภาพ
3. **การนำเสนอโครงการ:** ใช้แผนภูมิเพื่อแสดงความคืบหน้าและผลลัพธ์ของโครงการอย่างมีประสิทธิภาพ

หากทำตามแนวทางนี้ คุณจะสามารถใช้ Aspose.Slides สำหรับ Python เพื่อสร้างงานนำเสนอที่ทรงพลังและโดดเด่นได้

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}