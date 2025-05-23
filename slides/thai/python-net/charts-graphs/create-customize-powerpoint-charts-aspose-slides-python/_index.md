---
"date": "2025-04-23"
"description": "เรียนรู้วิธีการสร้างและปรับแต่งแผนภูมิใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Python เพิ่มประสิทธิภาพการนำเสนอของคุณด้วยภาพระดับมืออาชีพได้อย่างง่ายดาย"
"title": "สร้างแผนภูมิ PowerPoint อย่างเชี่ยวชาญด้วย Aspose.Slides สำหรับ Python และสร้างและปรับแต่งได้อย่างง่ายดาย"
"url": "/th/python-net/charts-graphs/create-customize-powerpoint-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# เรียนรู้การสร้างและปรับแต่งแผนภูมิใน PowerPoint ด้วย Aspose.Slides สำหรับ Python

## การแนะนำ
การสร้างงานนำเสนอที่ดึงดูดสายตาถือเป็นสิ่งสำคัญสำหรับการสื่อสารที่มีประสิทธิภาพ ไม่ว่าคุณจะนำเสนอต่อห้องประชุมหรือแบ่งปันข้อมูลเชิงลึกกับลูกค้า ความท้าทายมักอยู่ที่การผสานรวมแผนภูมิที่น่าสนใจซึ่งแสดงข้อมูลของคุณภายในสไลด์ PowerPoint ได้อย่างแม่นยำ **Aspose.Slides สำหรับ Python**งานนี้จะราบรื่นและมีประสิทธิภาพ

ในบทช่วยสอนที่ครอบคลุมนี้ เราจะมาเรียนรู้วิธีใช้ Aspose.Slides Python เพื่อสร้างและปรับแต่งแผนภูมิ PowerPoint ได้อย่างง่ายดาย ไลบรารีอันทรงพลังนี้มีคุณสมบัติที่แข็งแกร่งเพื่อเพิ่มประสิทธิภาพการนำเสนอของคุณด้วยภาพคุณภาพระดับมืออาชีพ

**สิ่งที่คุณจะได้เรียนรู้:**
- วิธีตั้งค่า Aspose.Slides สำหรับ Python
- การสร้างแผนภูมิเส้นภายในสไลด์
- การแก้ไขข้อมูลแผนภูมิที่มีอยู่
- การตั้งค่าเครื่องหมายที่กำหนดเองโดยใช้รูปภาพ
- การประยุกต์ใช้เทคนิคเหล่านี้ในโลกแห่งความเป็นจริง

พร้อมที่จะยกระดับแผนภูมิ PowerPoint ของคุณหรือยัง มาเจาะลึกข้อกำหนดเบื้องต้นและเริ่มต้นกันเลย!

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ให้แน่ใจว่าคุณมีเครื่องมือและความรู้ที่จำเป็นในการปฏิบัติตาม:

1. **การติดตั้ง Python**:ตรวจสอบให้แน่ใจว่าได้ติดตั้ง Python ไว้ในระบบของคุณแล้ว (แนะนำเวอร์ชัน 3.6 ขึ้นไป)
2. **Aspose.Slides สำหรับ Python**: ติดตั้งผ่าน pip:
   ```bash
   pip install aspose.slides
   ```
3. **สภาพแวดล้อมการพัฒนา**:ใช้ IDE เช่น VSCode หรือ PyCharm เพื่อการจัดการโค้ดที่ดีขึ้น
4. **ความรู้พื้นฐานเกี่ยวกับ Python**:ความคุ้นเคยกับโครงสร้างภาษา Python และแนวคิดการเขียนโปรแกรมเป็นสิ่งสำคัญ

## การตั้งค่า Aspose.Slides สำหรับ Python
ในการเริ่มต้น คุณต้องตั้งค่า Aspose.Slides สำหรับ Python ในสภาพแวดล้อมการพัฒนาของคุณ:

### การติดตั้ง
ติดตั้งไลบรารีโดยใช้ pip:
```bash
pip install aspose.slides
```

### การขอใบอนุญาต
Aspose.Slides นำเสนอตัวเลือกการออกใบอนุญาตที่แตกต่างกัน:
- **ทดลองใช้งานฟรี**:ทดสอบคุณสมบัติที่มีฟังก์ชั่นจำกัด
- **ใบอนุญาตชั่วคราว**:รับใบอนุญาตชั่วคราวฟรีเพื่อเข้าถึงคุณสมบัติเต็มรูปแบบระหว่างการทดสอบ
- **ซื้อ**:หากต้องการใช้อย่างต่อเนื่อง โปรดพิจารณาซื้อการสมัครสมาชิก

**การเริ่มต้นและการตั้งค่าเบื้องต้น:**
```python
import aspose.slides as slides

# การเริ่มต้นวัตถุการนำเสนอ
with slides.Presentation() as presentation:
    # เพิ่มโค้ดของคุณที่นี่เพื่อจัดการการนำเสนอ
    pass
```

## คู่มือการใช้งาน
ให้เราแบ่งการใช้งานออกเป็น 3 คุณสมบัติหลัก:

### สร้างและเพิ่มแผนภูมิ
#### ภาพรวม
คุณลักษณะนี้สาธิตการเพิ่มแผนภูมิเส้นพร้อมเครื่องหมายลงในสไลด์ PowerPoint

**ขั้นตอน:**
1. **การนำเสนอแบบเปิด**:เริ่มต้นด้วยการเปิดการนำเสนอใหม่หรือที่มีอยู่
2. **เลือกสไลด์**: เลือกสไลด์ที่คุณต้องการเพิ่มแผนภูมิ
3. **เพิ่มแผนภูมิเส้น**: ใช้ `add_chart` วิธีการแทรกแผนภูมิ
4. **บันทึกการนำเสนอ**:บันทึกการเปลี่ยนแปลงของคุณด้วยสไลด์ที่อัปเดต

**การใช้งานโค้ด:**
```python
import aspose.slides as slides

def add_chart_to_slide():
    # เปิดงานนำเสนอใหม่
    with slides.Presentation() as presentation:
        # เลือกสไลด์แรก
        slide = presentation.slides[0]
        
        # เพิ่มแผนภูมิเส้นพร้อมเครื่องหมายไปยังสไลด์ที่เลือกที่ตำแหน่ง (0, 0) และขนาด (400, 400)
        chart = slide.shapes.add_chart(
            slides.charts.ChartType.LINE_WITH_MARKERS, 0, 0, 400, 400
        )
        
        # บันทึกการนำเสนอพร้อมแผนภูมิที่เพิ่มลงในดิสก์
        presentation.save("YOUR_OUTPUT_DIRECTORY/charts_set_marker_options_out.pptx", slides.export.SaveFormat.PPTX)
```

### ปรับเปลี่ยนข้อมูลแผนภูมิ
#### ภาพรวม
เรียนรู้วิธีการล้างข้อมูลที่มีอยู่และเพิ่มชุดจุดใหม่ลงในแผนภูมิ

**ขั้นตอน:**
1. **แผนภูมิการเข้าถึง**:ดึงข้อมูลแผนภูมิจากสไลด์ของคุณ
2. **ล้างซีรีย์ที่มีอยู่**: ลบชุดข้อมูลที่มีอยู่ก่อนหน้านี้ออก
3. **เพิ่มจุดข้อมูลใหม่**:แทรกข้อมูลใหม่เข้าในชุดข้อมูล
4. **บันทึกการเปลี่ยนแปลง**: คงการเปลี่ยนแปลงไว้ในไฟล์นำเสนอ

**การใช้งานโค้ด:**
```python
import aspose.slides as slides

def modify_chart_data():
    with slides.Presentation() as presentation:
        slide = presentation.slides[0]
        chart = slide.shapes.add_chart(slides.charts.ChartType.LINE_WITH_MARKERS, 0, 0, 400, 400)
        
        # เข้าถึงดัชนีเวิร์กชีตเริ่มต้นสำหรับข้อมูลแผนภูมิ
        default_worksheet_index = 0
        fact = chart.chart_data.chart_data_workbook
        
        # ล้างชุดที่มีอยู่ทั้งหมดในแผนภูมิ
        chart.chart_data.series.clear()
        
        # เพิ่มซีรีส์ใหม่พร้อมระบุชื่อและประเภทลงในแผนภูมิ
        chart.chart_data.series.add(fact.get_cell(default_worksheet_index, 1, 1, "Series 1"), chart.type)
        
        # เข้าถึงชุดข้อมูลแรก (และชุดเดียว) ในแผนภูมิ
        series = chart.chart_data.series[0]
        
        # เพิ่มจุดข้อมูลลงในชุดข้อมูลและตั้งค่าค่าของจุดข้อมูลเหล่านี้
        point = series.data_points.add_data_point_for_line_series(fact.get_cell(default_worksheet_index, 1, 1, 4.5))
        point.value = 4.5
        
        point = series.data_points.add_data_point_for_line_series(fact.get_cell(default_worksheet_index, 2, 1, 2.5))
        point.value = 2.5
        
        point = series.data_points.add_data_point_for_line_series(fact.get_cell(default_worksheet_index, 3, 1, 3.5))
        point.value = 3.5
        
        point = series.data_points.add_data_point_for_line_series(fact.get_cell(default_worksheet_index, 4, 1, 4.5))
        point.value = 4.5
        
        # บันทึกการนำเสนอที่อัปเดตลงในดิสก์
        presentation.save("YOUR_OUTPUT_DIRECTORY/charts_set_marker_options_out.pptx", slides.export.SaveFormat.PPTX)
```

### ตั้งค่าเครื่องหมายแผนภูมิพร้อมรูปภาพ
#### ภาพรวม
ปรับปรุงแผนภูมิของคุณด้วยการตั้งค่าเครื่องหมายภาพแบบกำหนดเองสำหรับจุดข้อมูล

**ขั้นตอน:**
1. **เพิ่มแผนภูมิเส้น**:แทรกแผนภูมิเส้นเข้าไปในสไลด์
2. **โหลดรูปภาพ**:เพิ่มรูปภาพที่จะใช้เป็นเครื่องหมายจากไดเร็กทอรีเอกสารของคุณ
3. **ตั้งค่าเครื่องหมายภาพ**:นำภาพเหล่านี้ไปใช้กับจุดข้อมูลเฉพาะบนซีรีส์
4. **ปรับขนาดเครื่องหมาย**: ปรับขนาดเครื่องหมายภาพเพื่อให้มองเห็นได้ชัดเจนยิ่งขึ้น

**การใช้งานโค้ด:**
```python
import aspose.slides as slides

def set_chart_markers_with_images():
    # เปิดงานนำเสนอใหม่
    with slides.Presentation() as presentation:
        slide = presentation.slides[0]
        
        # เพิ่มแผนภูมิเส้นพร้อมเครื่องหมายไปยังสไลด์ที่เลือกที่ตำแหน่ง (0, 0) และขนาด (400, 400)
        chart = slide.shapes.add_chart(
            slides.charts.ChartType.LINE_WITH_MARKERS, 0, 0, 400, 400
        )
        
        # เข้าถึงดัชนีเวิร์กชีตเริ่มต้นสำหรับข้อมูลแผนภูมิ
        default_worksheet_index = 0
        fact = chart.chart_data.chart_data_workbook
        
        # ล้างชุดที่มีอยู่ทั้งหมดในแผนภูมิและเพิ่มชุดใหม่
        chart.chart_data.series.clear()
        chart.chart_data.series.add(fact.get_cell(default_worksheet_index, 1, 1, "Series 1"), chart.type)
        
        # เข้าถึงชุดข้อมูลแรก (และชุดเดียว) ในแผนภูมิ
        series = chart.chart_data.series[0]
        
        # โหลดรูปภาพและเพิ่มลงในคอลเลกชั่นรูปภาพของงานนำเสนอ
        image1 = slides.Images.from_file("YOUR_DOCUMENT_DIRECTORY/image1.jpg")
        imgx1 = presentation.images.add_image(image1)
        
        image2 = slides.Images.from_file("YOUR_DOCUMENT_DIRECTORY/image2.jpg")
        imgx2 = presentation.images.add_image(image2)
        
        # เพิ่มจุดข้อมูลและตั้งค่าภาพเครื่องหมายของพวกเขา
        point = series.data_points.add_data_point_for_line_series(fact.get_cell(default_worksheet_index, 1, 1, 4.5))
        point.marker.format.fill.fill_type = slides.FillType.PICTURE
        point.marker.format.fill.picture_fill_format.picture.image = imgx1
        
        point = series.data_points.add_data_point_for_line_series(fact.get_cell(default_worksheet_index, 2, 1, 2.5))
        point.marker.format.fill.fill_type = slides.FillType.PICTURE
        point.marker.format.fill.picture_fill_format.picture.image = imgx2
        
        # บันทึกการนำเสนอพร้อมเครื่องหมายที่กำหนดเองลงในดิสก์
        presentation.save("YOUR_OUTPUT_DIRECTORY/charts_with_image_markers_out.pptx", slides.export.SaveFormat.PPTX)
```

## บทสรุป
เมื่อทำตามบทช่วยสอนนี้แล้ว คุณจะมีพื้นฐานที่มั่นคงในการสร้างและปรับแต่งแผนภูมิใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Python ไม่ว่าจะเป็นการเพิ่มชุดข้อมูลใหม่หรือปรับปรุงการแสดงภาพด้วยเครื่องหมายภาพ เทคนิคเหล่านี้จะช่วยให้คุณสร้างการนำเสนอที่มีประสิทธิภาพมากขึ้นได้

## คำแนะนำคีย์เวิร์ด
- "Aspose.Slides สำหรับ Python"
- "การปรับแต่งแผนภูมิ PowerPoint"
- "สร้างแผนภูมิใน PowerPoint โดยใช้ Python"
- “การปรับปรุงการนำเสนอ Python”

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}