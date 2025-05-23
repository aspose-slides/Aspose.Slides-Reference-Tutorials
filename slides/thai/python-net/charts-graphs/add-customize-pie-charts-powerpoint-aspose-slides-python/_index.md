---
"date": "2025-04-22"
"description": "เรียนรู้วิธีการเพิ่มและปรับแต่งแผนภูมิวงกลมในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Python ประหยัดเวลาและรับรองความสอดคล้องกันด้วยคู่มือทีละขั้นตอนนี้"
"title": "วิธีการเพิ่มและปรับแต่งแผนภูมิวงกลมใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Python"
"url": "/th/python-net/charts-graphs/add-customize-pie-charts-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีการเพิ่มและปรับแต่งแผนภูมิวงกลมใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Python

## การแนะนำ
การสร้างงานนำเสนอที่ดึงดูดสายตาถือเป็นสิ่งสำคัญ โดยเฉพาะอย่างยิ่งเมื่อคุณต้องนำเสนอข้อมูลที่ซับซ้อนอย่างกระชับ ไม่ว่าจะเป็นรายงานทางการเงินหรือตัวชี้วัดประสิทธิภาพ แผนภูมิวงกลมสามารถเป็นเครื่องมือที่มีประสิทธิภาพในการแสดงสัดส่วนในครั้งเดียว อย่างไรก็ตาม การเพิ่มแผนภูมิเหล่านี้ลงในสไลด์ด้วยตนเองอาจใช้เวลานานและมีแนวโน้มว่าจะเกิดความไม่สอดคล้องกัน

ไลบรารี Aspose.Slides Python ช่วยให้กระบวนการอัตโนมัตินี้ราบรื่นยิ่งขึ้น บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับการใช้ Aspose.Slides สำหรับ Python เพื่อเพิ่มและปรับแต่งแผนภูมิวงกลมในงานนำเสนอ PowerPoint ได้อย่างง่ายดาย หากทำตามนี้ คุณจะไม่เพียงประหยัดเวลา แต่ยังมั่นใจได้ว่าสไลด์ของคุณจะมีความสม่ำเสมอ

**สิ่งที่คุณจะได้เรียนรู้:**
- วิธีการเพิ่มแผนภูมิวงกลมลงในสไลด์
- การกำหนดชื่อเรื่องและจัดข้อความให้ตรงกลางแผนภูมิวงกลม
- การกำหนดค่าชุดข้อมูลและหมวดหมู่สำหรับข้อมูลเชิงลึกโดยละเอียด
- การเปิดใช้งานการเปลี่ยนแปลงสีอัตโนมัติสำหรับชิ้นส่วนที่แตกต่างกัน

มาดูกันว่าคุณจะนำคุณลักษณะเหล่านี้ไปใช้อย่างมีประสิทธิภาพได้อย่างไร ก่อนเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าสภาพแวดล้อมของคุณได้รับการตั้งค่าอย่างถูกต้อง

## ข้อกำหนดเบื้องต้น
หากต้องการทำตามบทช่วยสอนนี้ คุณจะต้องมี:
- ติดตั้ง Python บนเครื่องของคุณแล้ว (แนะนำเวอร์ชัน 3.x)
- ไลบรารี Aspose.Slides สำหรับ Python
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Python และการนำเสนอ PowerPoint

ตรวจสอบให้แน่ใจว่าคุณมีการตั้งค่าที่จำเป็นสำหรับการเรียกใช้สคริปต์ Python หากไม่เป็นเช่นนั้น ให้พิจารณาติดตั้ง Python จาก [python.org](https://www-python.org/downloads/).

## การตั้งค่า Aspose.Slides สำหรับ Python
หากต้องการเริ่มใช้ Aspose.Slides ในโปรเจ็กต์ของคุณ ให้ติดตั้งผ่าน pip:

```bash
pip install aspose.slides
```

### ขั้นตอนการรับใบอนุญาต
Aspose เสนอให้ทดลองใช้ไลบรารีของตนได้ฟรี คุณสามารถดาวน์โหลดใบอนุญาตชั่วคราวเพื่อสำรวจความสามารถทั้งหมดได้โดยไม่มีข้อจำกัด ในการเริ่มต้น:
- เยี่ยม [หน้าการซื้อของ Aspose](https://purchase.aspose.com/buy) สำหรับตัวเลือกการซื้อ
- การขอใบอนุญาตชั่วคราวผ่านทาง [หน้าใบอนุญาตชั่วคราว](https://purchase-aspose.com/temporary-license/).

### การเริ่มต้นขั้นพื้นฐาน
คุณสามารถเริ่มต้น Aspose.Slides ในสคริปต์ Python ได้ดังนี้:

```python
import aspose.slides as slides

# เริ่มต้นคลาสการนำเสนอเพื่อสร้างหรือเปิดไฟล์การนำเสนอ
with slides.Presentation() as presentation:
    # รหัสของคุณอยู่ที่นี่
    pass
```

เมื่อตั้งค่านี้แล้ว คุณก็พร้อมที่จะเริ่มต้นเพิ่มแผนภูมิวงกลมลงในการนำเสนอของคุณได้

## คู่มือการใช้งาน

### การเพิ่มแผนภูมิวงกลมลงในสไลด์
#### ภาพรวม
การเพิ่มแผนภูมิวงกลมพื้นฐานเกี่ยวข้องกับการสร้างรูปร่างประเภทใหม่ `Chart` บนสไลด์ของคุณ หัวข้อนี้จะแนะนำคุณเกี่ยวกับขั้นตอนในการเพิ่มแผนภูมิวงกลมเริ่มต้น

#### ขั้นตอน
1. **เข้าถึงสไลด์แรก**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **เพิ่มรูปร่างแผนภูมิวงกลม**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   ```

   - พารามิเตอร์: `ChartType.PIE` ระบุชนิดของแผนภูมิ
   - พิกัดและมิติจะกำหนดตำแหน่งและขนาดของแผนภูมิวงกลม

3. **บันทึกการนำเสนอ**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_add_pie_chart_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### การกำหนดชื่อแผนภูมิวงกลมและข้อความตรงกลาง
#### ภาพรวม
การปรับแต่งแผนภูมิวงกลมของคุณด้วยชื่อเรื่องจะช่วยให้แผนภูมิอ่านง่ายขึ้นและให้ข้อมูลบริบทแก่ผู้ดู

#### ขั้นตอน
1. **เข้าถึงสไลด์แรก**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **เพิ่มแผนภูมิและตั้งชื่อ**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   
   # การตั้งชื่อเรื่อง
   chart.chart_title.add_text_frame_for_overriding("Sample Title")
   chart.chart_title.text_frame_for_overriding.text_frame_format.center_text = slides.NullableBool.TRUE
   chart.chart_title.height = 20
   chart.has_title = True
   ```

3. **บันทึกการนำเสนอ**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_set_pie_chart_title_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### การกำหนดค่าชุดข้อมูลและหมวดหมู่ของแผนภูมิวงกลม
#### ภาพรวม
หากต้องการให้แผนภูมิวงกลมของคุณมีข้อมูล คุณต้องป้อนข้อมูลจริงลงไป

#### ขั้นตอน
1. **เข้าถึงสไลด์แรก**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **กำหนดค่าข้อมูล**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   
   fact = chart.chart_data.chart_data_workbook
   
   # ล้างข้อมูลที่มีอยู่
   chart.chart_data.series.clear()
   chart.chart_data.categories.clear()
   
   # เพิ่มหมวดหมู่และซีรีส์ด้วยจุดข้อมูล
   chart.chart_data.categories.add(fact.get_cell(0, 1, 0, "First Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 2, 0, "2nd Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 3, 0, "3rd Qtr"))

   series = chart.chart_data.series.add(fact.get_cell(0, 0, 1, "Series 1"), chart.type)
   
   # เพิ่มจุดข้อมูล
   series.data_points.add_data_point_for_pie_series(fact.get_cell(0, 1, 1, 20))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(0, 2, 1, 50))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(0, 3, 1, 30))
   ```

3. **บันทึกการนำเสนอ**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_configure_pie_chart_data_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### การเปิดใช้งานสีชิ้นส่วนของแผนภูมิวงกลมอัตโนมัติ
#### ภาพรวม
การเพิ่มความน่าสนใจทางภาพโดยการเปลี่ยนสีส่วนต่างๆ โดยอัตโนมัติสามารถทำให้แผนภูมิของคุณน่าสนใจยิ่งขึ้น

#### ขั้นตอน
1. **เข้าถึงสไลด์แรก**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **เปิดใช้งานการเปลี่ยนแปลงสี**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   
   series = chart.chart_data.series[0]
   series.parent_series_group.is_color_varied = True
   ```

3. **บันทึกการนำเสนอ**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_enable_automatic_pie_slice_colors_out.pptx", slides.export.SaveFormat.PPTX)
   ```

## การประยุกต์ใช้งานจริง
1. **รายงานทางธุรกิจ**:ใช้แผนภูมิวงกลมเพื่อแสดงการกระจายส่วนแบ่งการตลาดในกลุ่มคู่แข่ง
2. **สื่อการเรียนรู้**:แสดงเปอร์เซ็นต์หัวข้อต่าง ๆ ที่ครอบคลุมในหลักสูตร
3. **การวิเคราะห์ทางการเงิน**:แสดงหมวดหมู่ค่าใช้จ่ายเป็นสัดส่วนของงบประมาณทั้งหมด
4. **ข้อมูลเชิงลึกด้านการตลาด**:สร้างภาพการแบ่งกลุ่มลูกค้าตามข้อมูลประชากรหรือความชอบ

การบูรณาการกับเครื่องมือวิเคราะห์ข้อมูล เช่น Pandas สามารถทำให้กระบวนการเป็นแบบอัตโนมัติมากขึ้น ทำให้สามารถอัปเดตแบบเรียลไทม์ภายในการนำเสนอได้

## การพิจารณาประสิทธิภาพ
เมื่อทำงานกับ Aspose.Slides และ Python:
- เพิ่มประสิทธิภาพโค้ดของคุณเพื่อจัดการหน่วยความจำอย่างมีประสิทธิภาพ โดยเฉพาะอย่างยิ่งเมื่อจัดการกับชุดข้อมูลขนาดใหญ่
- หลีกเลี่ยงการดำเนินการซ้ำซ้อนกับวัตถุการนำเสนอ
- ใช้ `with` คำชี้แจงสำหรับการจัดการบริบทเพื่อให้แน่ใจว่าทรัพยากรได้รับการปลดปล่อยอย่างเหมาะสมหลังการใช้งาน

## บทสรุป
ตอนนี้คุณมีความเข้าใจที่ครอบคลุมเกี่ยวกับวิธีการสร้างและปรับแต่งแผนภูมิวงกลมใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Python แล้ว การทำให้การทำงานเหล่านี้เป็นอัตโนมัติจะช่วยเพิ่มผลงานได้อย่างมาก พร้อมทั้งยังรับประกันความสอดคล้องกันในงานนำเสนอของคุณอีกด้วย 

เพื่อดำเนินการต่อไป ให้สำรวจการบูรณาการแหล่งข้อมูลแบบไดนามิกหรือการทำให้การสร้างสไลด์ทั้งหมดเป็นแบบอัตโนมัติ

## คำแนะนำคีย์เวิร์ด
- "Aspose.Slides สำหรับ Python"
- "แผนภูมิวงกลม PowerPoint"
- "สร้างแผนภูมิ PowerPoint อัตโนมัติด้วย Python"

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}