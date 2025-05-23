---
"date": "2025-04-22"
"description": "เรียนรู้วิธีสร้างแผนภูมิกล่องและแผนภูมิหนวดด้วย Aspose.Slides สำหรับ Python เพิ่มประสิทธิภาพการแสดงภาพข้อมูลในงานนำเสนอของคุณ"
"title": "สร้างแผนภูมิ Box และ Whisker ใน Python โดยใช้ Aspose.Slides"
"url": "/th/python-net/charts-graphs/create-box-whisker-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# สร้างแผนภูมิ Box และ Whisker ใน Python โดยใช้ Aspose.Slides

## วิธีการสร้างแผนภูมิกล่องและหนวดโดยใช้ Aspose.Slides สำหรับ Python

พัฒนาทักษะการสร้างภาพข้อมูลของคุณด้วยการเรียนรู้วิธีสร้างแผนภูมิกล่องและแผนภูมิหนวดโดยใช้ไลบรารี Aspose.Slides ที่มีประสิทธิภาพ แผนภูมิเหล่านี้เหมาะอย่างยิ่งสำหรับการแสดงการแจกแจงทางสถิติ ทำให้สามารถตีความข้อมูลที่ซับซ้อนได้อย่างง่ายดายในครั้งเดียว

**สิ่งที่คุณจะได้เรียนรู้:**
- การตั้งค่าสภาพแวดล้อมของคุณด้วย Aspose.Slides สำหรับ Python
- การสร้างและปรับแต่งแผนภูมิกล่องและหนวด
- การประยุกต์ใช้งานจริงและโอกาสในการบูรณาการ
- เคล็ดลับการเพิ่มประสิทธิภาพเพื่อประสิทธิภาพที่ดีขึ้น

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- **Aspose.Slides สำหรับ Python:** ไลบรารีที่จำเป็นสำหรับการสร้างและจัดการการนำเสนอ PowerPoint
- **สภาพแวดล้อม Python:** คุณจะต้องติดตั้ง Python ที่ใช้งานได้ (ควรใช้ Python 3.x)
- **ความรู้พื้นฐานเกี่ยวกับ Python:** ความคุ้นเคยกับการเขียนโปรแกรม Python จะช่วยให้คุณทำตามได้ง่ายขึ้น

## การตั้งค่า Aspose.Slides สำหรับ Python

### ข้อมูลการติดตั้ง

ในการเริ่มต้น ให้ติดตั้งไลบรารี Aspose.Slides โดยใช้ pip:

```bash
pip install aspose.slides
```

### ขั้นตอนการรับใบอนุญาต

Aspose นำเสนอตัวเลือกการออกใบอนุญาตที่แตกต่างกัน:
- **ทดลองใช้งานฟรี:** ดาวน์โหลดใบอนุญาตชั่วคราวเพื่อสำรวจคุณสมบัติเต็มรูปแบบโดยไม่มีข้อจำกัดในการประเมิน
- **ใบอนุญาตชั่วคราว:** เหมาะสำหรับโครงการระยะสั้นหรือการทดสอบ
- **ซื้อ:** รับใบอนุญาตถาวรหากคุณต้องการการเข้าถึงอย่างต่อเนื่อง

คุณสามารถรับใบอนุญาตเหล่านี้ได้ผ่านทาง [หน้าการซื้อ](https://purchase.aspose.com/buy) หรือขอทดลองใช้งานฟรีได้ที่ [หน้าใบอนุญาตชั่วคราว](https://purchase-aspose.com/temporary-license/).

### การเริ่มต้นและการตั้งค่าเบื้องต้น

หลังจากติดตั้งแล้ว ให้เริ่มต้น Aspose.Slides สำหรับ Python เพื่อเริ่มใช้งานการนำเสนอ นี่คือวิธีตั้งค่าสภาพแวดล้อมของคุณ:

```python
import aspose.slides as slides

# เริ่มต้นการนำเสนอ
def setup_presentation():
    with slides.Presentation() as pres:
        # ดำเนินการเช่นการเพิ่มแผนภูมิที่นี่
        pass
```

## คู่มือการใช้งาน

ในส่วนนี้ เราจะแนะนำคุณเกี่ยวกับการสร้างแผนภูมิกล่องและหนวด

### การเพิ่มแผนภูมิกล่องและหนวดลงในงานนำเสนอของคุณ

#### ภาพรวม

หากต้องการแสดงข้อมูลในงานนำเสนอของคุณอย่างมีประสิทธิภาพ ให้สร้างแผนภูมิกล่องและหนวดโดยใช้ Aspose.Slides สำหรับ Python แผนภูมิประเภทนี้เหมาะอย่างยิ่งสำหรับการแสดงการแจกแจงและระบุค่าผิดปกติ

#### การดำเนินการแบบทีละขั้นตอน

1. **สร้างงานนำเสนอใหม่:**
   
   เริ่มต้นโดยการสร้างอินสแตนซ์การนำเสนอใหม่:
   
   ```python
   import aspose.slides as slides
   
   def create_box_and_whisker_chart():
       # สร้างอินสแตนซ์การนำเสนอใหม่
       with slides.Presentation() as pres:
           # เพิ่มแผนภูมิในขั้นตอนต่อไป
           pass
   ```

2. **เพิ่มแผนภูมิลงในสไลด์ของคุณ:**
   
   ใส่กล่องและแผนภูมิหนวดที่ตำแหน่งที่คุณต้องการ:
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           # เพิ่มแผนภูมิ Box and Whisker บนสไลด์แรกที่ตำแหน่ง (50, 50) พร้อมขนาด (500, 400)
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
   ```

3. **ล้างข้อมูลที่มีอยู่:**
   
   ตรวจสอบให้แน่ใจว่าแผนภูมิว่างเปล่าก่อนที่จะเพิ่มข้อมูลใหม่:
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
           
           # ล้างข้อมูลหมวดหมู่และชุดที่มีอยู่ทั้งหมด
           chart.chart_data.categories.clear()
           chart.chart_data.series.clear()

           wb = chart.chart_data.chart_data_workbook
           wb.clear(0)  # ล้างสมุดงานสำหรับการป้อนข้อมูลใหม่
   ```

4. **เพิ่มหมวดหมู่ลงในแผนภูมิของคุณ:**
   
   เติมแผนภูมิของคุณด้วยหมวดหมู่:
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
           chart.chart_data.categories.clear()
           chart.chart_data.series.clear()

           wb = chart.chart_data.chart_data_workbook
           wb.clear(0)

           # กำหนดหมวดหมู่สำหรับข้อมูลแผนภูมิ
           for i in range(1, 7):
               category_name = f"Category {i}"
               chart.chart_data.categories.add(wb.get_cell(0, f"A{i}", category_name))
   ```

5. **กำหนดค่าซีรีย์:**
   
   ตั้งค่าซีรีย์ของคุณด้วยคุณสมบัติที่ต้องการ:
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
           chart.chart_data.categories.clear()
           chart.chart_data.series.clear()

           wb = chart.chart_data.chart_data_workbook
           wb.clear(0)

           for i in range(1, 7):
               category_name = f"Category {i}"
               chart.chart_data.categories.add(wb.get_cell(0, f"A{i}", category_name))

           # เพิ่มซีรีส์ใหม่และกำหนดค่าคุณสมบัติของซีรีส์นั้น
           series = chart.chart_data.series.add(slides.charts.ChartType.BOX_AND_WHISKER)
           series.quartile_method = slides.charts.QuartileMethodType.EXCLUSIVE
           series.show_mean_line = True
           series.show_mean_markers = True
           series.show_inner_points = True
           series.show_outlier_points = True

           # กำหนดจุดข้อมูลสำหรับชุดข้อมูล
           values = [15, 41, 16, 10, 23, 16]
           for i, value in enumerate(values, start=1):
               series.data_points.add_data_point_for_box_and_whisker_series(wb.get_cell(0, f"B{i}", value))
   ```

6. **บันทึกการนำเสนอ:**
   
   บันทึกงานของคุณด้วยแผนภูมิที่เพิ่มใหม่:
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
           chart.chart_data.categories.clear()
           chart.chart_data.series.clear()

           wb = chart.chart_data.chart_data_workbook
           wb.clear(0)

           for i in range(1, 7):
               category_name = f"Category {i}"
               chart.chart_data.categories.add(wb.get_cell(0, f"A{i}", category_name))

           series = chart.chart_data.series.add(slides.charts.ChartType.BOX_AND_WHISKER)
           series.quartile_method = slides.charts.QuartileMethodType.EXCLUSIVE
           series.show_mean_line = True
           series.show_mean_markers = True
           series.show_inner_points = True
           series.show_outlier_points = True

           values = [15, 41, 16, 10, 23, 16]
           for i, value in enumerate(values, start=1):
               series.data_points.add_data_point_for_box_and_whisker_series(wb.get_cell(0, f"B{i}", value))

           # บันทึกการนำเสนอ
           pres.save("YOUR_OUTPUT_DIRECTORY/charts_box_chart_out.pptx", slides.export.SaveFormat.PPTX)

   create_box_and_whisker_chart()
   ```

### เคล็ดลับการแก้ไขปัญหา

- **ตรวจสอบการติดตั้งห้องสมุด:** ทำให้มั่นใจ `aspose.slides` ได้รับการติดตั้งอย่างถูกต้องแล้ว.
- **ตรวจสอบการตั้งค่าใบอนุญาต:** หากคุณพบข้อจำกัด โปรดตรวจสอบให้แน่ใจว่าไฟล์ใบอนุญาตของคุณได้รับการตั้งค่าอย่างถูกต้อง
- **ข้อผิดพลาดทางไวยากรณ์:** ตรวจสอบซ้ำอีกครั้งเพื่อดูว่ามีการพิมพ์ผิดหรือข้อผิดพลาดใด ๆ ในรูปแบบโค้ดหรือไม่

## การประยุกต์ใช้งานจริงและโอกาสในการบูรณาการ

แผนภูมิกล่องและแผนภูมิหนวดเคราใช้กันอย่างแพร่หลายในการวิเคราะห์ธุรกิจเพื่อนำเสนอข้อมูลทางสถิติอย่างกระชับ แผนภูมิเหล่านี้ช่วยระบุแนวโน้ม ค่าผิดปกติ และรูปแบบต่างๆ ภายในชุดข้อมูล ทำให้แผนภูมิเหล่านี้เหมาะสำหรับการนำเสนอ รายงาน และแดชบอร์ด

การบูรณาการ Aspose.Slides เข้ากับ Python ช่วยให้สร้างการนำเสนอ PowerPoint แบบโต้ตอบที่สมบูรณ์และราบรื่นผ่านโปรแกรมได้ ทำให้วิธีการสื่อสารข้อมูลเชิงลึกที่ขับเคลื่อนด้วยข้อมูลดีขึ้น

## เคล็ดลับการเพิ่มประสิทธิภาพเพื่อประสิทธิภาพที่ดีขึ้น

- **ปรับปรุงการป้อนข้อมูล:** ตรวจสอบให้แน่ใจว่าชุดข้อมูลของคุณสะอาดและมีโครงสร้างที่ดีก่อนที่จะสร้างแผนภูมิเพื่อหลีกเลี่ยงข้อผิดพลาดในระหว่างการแสดงภาพ
- **ปรับแต่งแผนภูมิให้เหมาะสม:** ใช้ตัวเลือกการปรับแต่งของ Aspose.Slides อย่างชาญฉลาดเพื่อปรับปรุงการอ่านแผนภูมิโดยไม่ทำให้การนำเสนอมีองค์ประกอบมากเกินไป
- **ทำให้งานซ้ำๆ เป็นแบบอัตโนมัติ:** ใช้ประโยชน์จากสคริปต์ Python เพื่อทำให้การทำงานซ้ำๆ เช่น การจัดรูปแบบข้อมูลและการสร้างแผนภูมิเป็นแบบอัตโนมัติ ช่วยประหยัดเวลาและลดข้อผิดพลาด

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}