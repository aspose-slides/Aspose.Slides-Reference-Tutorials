---
"date": "2025-04-22"
"description": "เรียนรู้วิธีการสร้างและปรับแต่งแผนภูมิวงกลมใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Python เพิ่มประสิทธิภาพการนำเสนอของคุณด้วยข้อมูลเชิงลึกที่ขับเคลื่อนด้วยข้อมูล"
"title": "สร้างแผนภูมิวงกลม PowerPoint ที่น่าสนใจด้วย Aspose.Slides สำหรับ Python | บทช่วยสอนเกี่ยวกับแผนภูมิและกราฟ"
"url": "/th/python-net/charts-graphs/aspose-slides-python-powerpoint-pie-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# สร้างแผนภูมิวงกลม PowerPoint ด้วย Aspose.Slides สำหรับ Python

**หมวดหมู่:** แผนภูมิและกราฟ

การสร้างงานนำเสนอที่น่าสนใจและให้ข้อมูลถือเป็นกุญแจสำคัญในการสื่อสารข้อมูลเชิงลึกที่ขับเคลื่อนด้วยข้อมูลอย่างมีประสิทธิภาพ หากคุณต้องการปรับปรุงสไลด์ PowerPoint ของคุณโดยใช้แผนภูมิวงกลมที่ดึงดูดสายตา **Aspose.Slides สำหรับ Python** ไลบรารีเป็นเครื่องมือที่ยอดเยี่ยมที่ช่วยลดความซับซ้อนของกระบวนการนี้ ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับการสร้างแผนภูมิวงกลมใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Python

## สิ่งที่คุณจะได้เรียนรู้:
- ติดตั้งและตั้งค่า Aspose.Slides สำหรับ Python
- สร้างแผนภูมิวงกลมพื้นฐานในสไลด์ PowerPoint
- ปรับแต่งแผนภูมิวงกลมของคุณด้วยจุดข้อมูล สี ขอบ ป้ายกำกับ เส้นนำ และการหมุน
- เพิ่มประสิทธิภาพการทำงานเมื่อทำงานกับแผนภูมิ

มาดูรายละเอียดขั้นตอนที่จำเป็นในการเริ่มต้นกันเลย

## ข้อกำหนดเบื้องต้น

ก่อนที่จะนำโค้ดไปใช้ โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:
- ติดตั้ง Python ในระบบของคุณแล้ว (แนะนำเวอร์ชัน 3.6 ขึ้นไป)
- `pip` ตัวจัดการแพ็คเกจสำหรับการติดตั้งไลบรารี
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Python และการนำเสนอ PowerPoint

## การตั้งค่า Aspose.Slides สำหรับ Python

ในการเริ่มทำงานกับ Aspose.Slides สำหรับ Python คุณจำเป็นต้องติดตั้งไลบรารีโดยใช้ pip:

```bash
pip install aspose.slides
```

**การได้มาซึ่งใบอนุญาต:**
คุณสามารถเริ่มต้นโดยดาวน์โหลดใบอนุญาตทดลองใช้งานฟรีจาก [หน้าดาวน์โหลดของ Aspose](https://releases.aspose.com/slides/python-net/)หากต้องการใช้อย่างครอบคลุมมากขึ้น โปรดพิจารณาซื้อใบอนุญาตเต็มรูปแบบหรือรับใบอนุญาตชั่วคราวเพื่อวัตถุประสงค์ในการประเมินผล

### การเริ่มต้นและการตั้งค่าเบื้องต้น

เมื่อคุณติดตั้ง Aspose.Slides แล้ว นำเข้าโมดูลที่จำเป็นลงในสคริปต์ Python ของคุณ:

```python
import aspose.slides as slides
import aspose.pydrawing as drawing
```

## คู่มือการใช้งาน

ในส่วนนี้เราจะแบ่งการสร้างแผนภูมิวงกลมออกเป็นขั้นตอนโดยละเอียด

### การสร้างและปรับแต่งแผนภูมิวงกลมของคุณ

#### ภาพรวม
การสร้างแผนภูมิวงกลมเกี่ยวข้องกับการเริ่มต้นวัตถุการนำเสนอ การเพิ่มสไลด์ และการแทรกแผนภูมิด้วยจุดข้อมูลที่กำหนดเองและองค์ประกอบภาพ

#### ขั้นตอนการสร้างแผนภูมิวงกลม

1. **คลาสการสร้างตัวอย่างการนำเสนอ**
   เริ่มต้นด้วยการสร้างอินสแตนซ์การนำเสนอ ซึ่งจะทำหน้าที่เป็นคอนเทนเนอร์สำหรับสไลด์และแผนภูมิของคุณ

   ```python
   with slides.Presentation() as presentation:
       # เข้าถึงสไลด์แรก
       slide = presentation.slides[0]
   ```

2. **เพิ่มแผนภูมิวงกลมลงในสไลด์**
   ใช้ `add_chart` วิธีการแทรกแผนภูมิวงกลมตามพิกัดที่กำหนดบนสไลด์

   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   ```

3. **ตั้งชื่อแผนภูมิ**
   ปรับแต่งแผนภูมิของคุณด้วยชื่อที่เหมาะสมและจัดรูปแบบให้ข้อความอยู่ตรงกลาง

   ```python
   chart.chart_title.add_text_frame_for_overriding("Sample Title")
   chart.chart_title.text_frame_for_overriding.text_frame_format.center_text = slides.NullableBool.TRUE
   chart.chart_title.height = 20
   chart.has_title = True
   ```

4. **สมุดงานข้อมูลแผนภูมิการเข้าถึง**
   ใช้ `chart_data_workbook` เพื่อจัดการและปรับแต่งหมวดหมู่และชุดข้อมูลของคุณ

   ```python
   fact = chart.chart_data.chart_data_workbook
   default_worksheet_index = 0

   # ล้างซีรีย์หรือหมวดหมู่ที่มีอยู่
   chart.chart_data.series.clear()
   chart.chart_data.categories.clear()

   # เพิ่มหมวดหมู่ใหม่ (ไตรมาส)
   chart.chart_data.categories.add(fact.get_cell(0, 1, 0, "First Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 2, 0, "2nd Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 3, 0, "3rd Qtr"))

   # เพิ่มซีรีย์ใหม่
   series = chart.chart_data.series.add(fact.get_cell(0, 0, 1, "Series 1"), chart.type)
   ```

5. **เติมข้อมูลลงในซีรีส์ด้วยจุดข้อมูล**
   แทรกจุดข้อมูลลงในชุดของคุณเพื่อแสดงส่วนต่างๆ ของวงกลม

   ```python
   series.data_points.add_data_point_for_pie_series(fact.get_cell(default_worksheet_index, 1, 1, 20))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(default_worksheet_index, 2, 1, 50))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(default_worksheet_index, 3, 1, 30))
   ```

6. **ใช้สีต่างๆ กับแผนภูมิ**
   ปรับแต่งชิ้นพายแต่ละชิ้นด้วยสีสันที่แตกต่างกัน

   ```python
   chart.chart_data.series_groups[0].is_color_varied = True

   # กำหนดฟังก์ชั่นสำหรับปรับแต่งลักษณะที่ปรากฏของจุด
   def customize_point(point, fill_color, line_color):
       point.format.fill.fill_type = slides.FillType.SOLID
       point.format.fill.solid_fill_color.color = drawing.Color(fill_color)
       
       point.format.line.fill_format.fill_type = slides.FillType.SOLID
       point.format.line.fill_format.solid_fill_color.color = drawing.Color(line_color)
       point.format.line.width = 3.0
       point.format.line.style = slides.LineStyle.THIN_THICK
       point.format.line.dash_style = slides.LineDashStyle.DASH_DOT
   
   # ปรับแต่งลักษณะที่ปรากฏของจุดข้อมูลแรก
   customize_point(series.data_points[0], "Cyan", "Gray")
   ```

7. **ปรับแต่งฉลากสำหรับจุดข้อมูล**
   ปรับการตั้งค่าฉลากเพื่อแสดงค่า เปอร์เซ็นต์ หรือชื่อชุด

   ```python
   def customize_label(point, show_value=True, show_legend_key=False,
                       show_percentage=False, show_series_name=False):
       lbl = point.label
       lbl.data_label_format.show_value = show_value
       lbl.data_label_format.show_legend_key = show_legend_key
       lbl.data_label_format.show_percentage = show_percentage
       lbl.data_label_format.show_series_name = show_series_name
   
   # ตั้งค่าคุณสมบัติฉลากสำหรับจุดข้อมูลแรก
   customize_label(series.data_points[0], True)
   ```

8. **เปิดใช้งานเส้นผู้นำและหมุนชิ้นส่วนของวงกลม**
   เพื่อการอ่านที่ง่ายขึ้น ให้เปิดใช้งานเส้นผู้นำและหมุนส่วนตามต้องการ

   ```python
   series.labels.default_data_label_format.show_leader_lines = True

   # หมุนชิ้นพายชิ้นแรก 180 องศา
   chart.chart_data.series_groups[0].first_slice_angle = 180
   ```

9. **บันทึกการนำเสนอ**
   สุดท้ายให้บันทึกการนำเสนอของคุณพร้อมการปรับแต่งทั้งหมดที่ใช้

   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_pie_chart_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### เคล็ดลับการแก้ไขปัญหา
- ตรวจสอบให้แน่ใจว่า Aspose.Slides ได้รับการติดตั้งและนำเข้าอย่างถูกต้อง
- ตรวจสอบการพิมพ์ผิดในชื่อวิธีการหรือพารามิเตอร์ เพราะอาจทำให้เกิดข้อผิดพลาดได้
- ตรวจสอบว่าเส้นทางไดเร็กทอรีมีอยู่ที่ที่คุณบันทึกไฟล์เอาต์พุตของคุณ

## การประยุกต์ใช้งานจริง

แผนภูมิวงกลมมีความหลากหลายและมีประโยชน์สำหรับโดเมนต่างๆ:
1. **การวิเคราะห์ทางธุรกิจ**:แสดงภาพการกระจายรายได้จากผลิตภัณฑ์และบริการที่แตกต่างกัน
2. **รายงานการตลาด**:แสดงส่วนแบ่งการตลาดของคู่แข่งในอุตสาหกรรมที่กำหนด
3. **การนำเสนอด้านการศึกษา**:สาธิตข้อมูลสถิติที่เกี่ยวข้องกับผลการเรียนของนักเรียนหรือข้อมูลประชากร

## การพิจารณาประสิทธิภาพ
- ลดการใช้ทรัพยากรให้เหลือน้อยที่สุดโดยเพิ่มประสิทธิภาพองค์ประกอบแผนภูมิและลดความซับซ้อนที่ไม่จำเป็น
- ใช้โครงสร้างข้อมูลที่มีประสิทธิภาพเมื่อจัดการชุดข้อมูลขนาดใหญ่สำหรับแผนภูมิ
- จัดการหน่วยความจำอย่างมีประสิทธิภาพด้วยการปล่อยทรัพยากรทันทีหลังการใช้งาน

## บทสรุป

หากทำตามคำแนะนำนี้ คุณจะได้เรียนรู้วิธีสร้างแผนภูมิวงกลมใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Python ตอนนี้คุณสามารถนำเทคนิคเหล่านี้ไปใช้กับการนำเสนอของคุณและสำรวจตัวเลือกการปรับแต่งเพิ่มเติมได้ ลองผสานรวมแผนภูมิประเภทอื่นหรือใช้คุณลักษณะ Aspose.Slides เพิ่มเติมเพื่อเสริมทักษะการแสดงภาพข้อมูลของคุณ

### ขั้นตอนต่อไป
- ทดลองปรับแต่งแผนภูมิที่แตกต่างกัน
- สำรวจการผสานรวมของแผนภูมิในรายงานแบบไดนามิก
- เจาะลึกเอกสาร Aspose.Slides เพื่อดูฟีเจอร์ขั้นสูงเพิ่มเติม

## ส่วนคำถามที่พบบ่อย

1. **Aspose.Slides คืออะไร?**
   - ไลบรารีอันทรงพลังที่ให้สามารถสร้างและจัดการการนำเสนอ PowerPoint ได้ตามโปรแกรม
2. **ฉันสามารถใช้ Aspose.Slides ได้ฟรีหรือไม่?**
   - ใช่ คุณสามารถเริ่มต้นด้วยใบอนุญาตทดลองใช้งานหรือประเมินความสามารถก่อนการซื้อได้
3. **ฉันสามารถสร้างแผนภูมิประเภทอื่นๆ อะไรได้บ้าง?**
   - นอกเหนือจากแผนภูมิวงกลมแล้ว คุณยังสามารถสร้างแผนภูมิแท่ง กราฟเส้น กราฟแบบกระจาย และอื่นๆ ได้โดยใช้ Aspose.Slides

## คำแนะนำคีย์เวิร์ด
- "Aspose.Slides สำหรับ Python"
- "แผนภูมิวงกลม PowerPoint"
- "แผนภูมิ PowerPoint Python"

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}