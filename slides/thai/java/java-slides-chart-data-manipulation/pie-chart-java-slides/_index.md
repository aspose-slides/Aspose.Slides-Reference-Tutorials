---
"description": "เรียนรู้วิธีการสร้างแผนภูมิวงกลมที่สวยงามในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับสำหรับนักพัฒนา Java"
"linktitle": "แผนภูมิวงกลมใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "แผนภูมิวงกลมใน Java Slides"
"url": "/th/java/chart-data-manipulation/pie-chart-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แผนภูมิวงกลมใน Java Slides


## บทนำสู่การสร้างแผนภูมิวงกลมใน Java Slides โดยใช้ Aspose.Slides

ในบทช่วยสอนนี้ เราจะสาธิตวิธีการสร้างแผนภูมิวงกลมในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เราจะให้คำแนะนำแบบทีละขั้นตอนและโค้ดต้นฉบับของ Java เพื่อช่วยคุณเริ่มต้นใช้งาน คู่มือนี้ถือว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาด้วย Aspose.Slides สำหรับ Java ไว้แล้ว

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและกำหนดค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

ตรวจสอบให้แน่ใจว่าได้นำเข้าคลาสที่จำเป็นจากไลบรารี Aspose.Slides

## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";

// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงไฟล์ PPTX
Presentation presentation = new Presentation();
```

สร้างวัตถุการนำเสนอใหม่เพื่อแสดงไฟล์ PowerPoint ของคุณ แทนที่ `"Your Document Directory"` ด้วยเส้นทางจริงที่คุณต้องการบันทึกการนำเสนอ

## ขั้นตอนที่ 3: เพิ่มสไลด์

```java
// เข้าถึงสไลด์แรก
ISlide slide = presentation.getSlides().get_Item(0);
```

รับสไลด์แรกของการนำเสนอที่คุณต้องการเพิ่มแผนภูมิวงกลม

## ขั้นตอนที่ 4: เพิ่มแผนภูมิวงกลม

```java
// เพิ่มแผนภูมิวงกลมด้วยข้อมูลเริ่มต้น
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

เพิ่มแผนภูมิวงกลมลงในสไลด์ในตำแหน่งและขนาดที่ระบุ

## ขั้นตอนที่ 5: ตั้งชื่อแผนภูมิ

```java
// ตั้งชื่อแผนภูมิ
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

ตั้งชื่อให้กับแผนภูมิวงกลม คุณสามารถปรับแต่งชื่อได้ตามต้องการ

## ขั้นตอนที่ 6: ปรับแต่งข้อมูลแผนภูมิ

```java
// ตั้งค่าชุดแรกที่จะแสดงค่า
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
int defaultWorksheetIndex = 0;

// การรับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// ลบซีรีย์และหมวดหมู่ที่สร้างตามค่าเริ่มต้น
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// การเพิ่มหมวดหมู่ใหม่
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// เพิ่มซีรีย์ใหม่
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// การเติมข้อมูลชุด
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

ปรับแต่งข้อมูลแผนภูมิโดยการเพิ่มหมวดหมู่และชุดข้อมูล และตั้งค่าของหมวดหมู่และชุดข้อมูลเหล่านั้น ในตัวอย่างนี้ เรามีหมวดหมู่ 3 หมวดหมู่และชุดข้อมูล 1 ชุดพร้อมจุดข้อมูลที่สอดคล้องกัน

## ขั้นตอนที่ 7: ปรับแต่งส่วนแผนภูมิวงกลม

```java
// ตั้งค่าสีภาคส่วน
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// ปรับแต่งรูปลักษณ์ของแต่ละภาคส่วนได้
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// ปรับแต่งขอบเขตภาคส่วน
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// ปรับแต่งภาคส่วนอื่นๆ ในลักษณะเดียวกัน
```

ปรับแต่งรูปลักษณ์ของแต่ละภาคส่วนในแผนภูมิวงกลม คุณสามารถเปลี่ยนสี สไตล์เส้นขอบ และคุณสมบัติภาพอื่นๆ ได้

## ขั้นตอนที่ 8: ปรับแต่งป้ายข้อมูล

```java
// ปรับแต่งป้ายข้อมูล
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// ปรับแต่งป้ายข้อมูลสำหรับจุดข้อมูลอื่น ๆ ในลักษณะเดียวกัน
```

ปรับแต่งป้ายข้อมูลสำหรับแต่ละจุดข้อมูลในแผนภูมิวงกลม คุณสามารถควบคุมค่าที่จะแสดงบนแผนภูมิได้

## ขั้นตอนที่ 9: แสดงเส้นผู้นำ

```java
// แสดงเส้นผู้นำสำหรับแผนภูมิ
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

เปิดใช้งานเส้นผู้นำเพื่อเชื่อมต่อป้ายข้อมูลกับภาคส่วนที่สอดคล้องกัน

## ขั้นตอนที่ 10: ตั้งค่ามุมการหมุนของแผนภูมิวงกลม

```java
// ตั้งค่ามุมการหมุนสำหรับภาคส่วนของแผนภูมิวงกลม
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

กำหนดมุมการหมุนสำหรับภาคส่วนของแผนภูมิวงกลม ในตัวอย่างนี้ เราตั้งไว้ที่ 180 องศา

## ขั้นตอนที่ 11: บันทึกการนำเสนอ

```java
// บันทึกการนำเสนอด้วยแผนภูมิวงกลม
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

บันทึกการนำเสนอด้วยแผนภูมิวงกลมไปยังไดเร็กทอรีที่ระบุ

## โค้ดต้นฉบับสมบูรณ์สำหรับแผนภูมิวงกลมใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงไฟล์ PPTX
Presentation presentation = new Presentation();
// เข้าถึงสไลด์แรก
ISlide slides = presentation.getSlides().get_Item(0);
// เพิ่มแผนภูมิด้วยข้อมูลเริ่มต้น
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// ตั้งค่าแผนภูมิชื่อ
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// ตั้งค่าซีรีส์แรกให้แสดงค่า
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
int defaultWorksheetIndex = 0;
// การรับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// ลบซีรีย์และหมวดหมู่ที่สร้างตามค่าเริ่มต้น
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// การเพิ่มหมวดหมู่ใหม่
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// เพิ่มซีรีย์ใหม่
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// ขณะนี้กำลังเพิ่มข้อมูลซีรีส์
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// ไม่ทำงานในเวอร์ชันใหม่
// การเพิ่มจุดใหม่และการตั้งค่าสีภาค
// ซีรีส์.IsColorVaried = true;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// การตั้งค่าขอบเขตภาค
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// การตั้งค่าขอบเขตภาค
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// การตั้งค่าขอบเขตภาค
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// สร้างป้ายกำกับที่กำหนดเองสำหรับแต่ละหมวดหมู่สำหรับซีรีย์ใหม่
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.setShowCategoryName(จริง);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// การแสดงเส้นผู้นำสำหรับแผนภูมิ
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// การตั้งค่ามุมการหมุนสำหรับภาคส่วนของแผนภูมิวงกลม
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// บันทึกการนำเสนอด้วยแผนภูมิ
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## บทสรุป

คุณได้สร้างแผนภูมิวงกลมในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว คุณสามารถปรับแต่งรูปลักษณ์ของแผนภูมิและป้ายข้อมูลตามความต้องการเฉพาะของคุณได้ บทช่วยสอนนี้ให้ตัวอย่างพื้นฐาน และคุณสามารถปรับปรุงและปรับแต่งแผนภูมิของคุณเพิ่มเติมตามต้องการได้

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนสีของแต่ละภาคส่วนในแผนภูมิวงกลมได้อย่างไร

หากต้องการเปลี่ยนสีของแต่ละภาคส่วนในแผนภูมิวงกลม คุณสามารถปรับแต่งสีเติมสำหรับแต่ละจุดข้อมูลได้ ในตัวอย่างโค้ดที่ให้มา เราได้สาธิตวิธีตั้งค่าสีเติมสำหรับแต่ละภาคส่วนโดยใช้ `getSolidFillColor().setColor()` วิธีการนี้ คุณสามารถปรับเปลี่ยนค่าสีเพื่อให้ได้รูปลักษณ์ที่ต้องการได้

### ฉันสามารถเพิ่มหมวดหมู่และชุดข้อมูลเพิ่มเติมลงในแผนภูมิวงกลมได้หรือไม่

ใช่ คุณสามารถเพิ่มหมวดหมู่และชุดข้อมูลเพิ่มเติมลงในแผนภูมิวงกลมได้ หากต้องการทำเช่นนี้ คุณสามารถใช้ `getChartData().getCategories().add()` และ `getChartData().getSeries().add()` วิธีการดังที่แสดงในตัวอย่าง เพียงให้ข้อมูลและป้ายกำกับที่เหมาะสมสำหรับหมวดหมู่และชุดข้อมูลใหม่เพื่อขยายแผนภูมิของคุณ

### ฉันจะปรับแต่งลักษณะที่ปรากฏของป้ายข้อมูลได้อย่างไร

คุณสามารถปรับแต่งลักษณะของป้ายข้อมูลได้โดยใช้ `getDataLabelFormat()` วิธีการบนป้ายชื่อจุดข้อมูลแต่ละจุด ในตัวอย่างนี้ เราได้สาธิตวิธีการแสดงค่าบนป้ายชื่อข้อมูลโดยใช้ `getDataLabelFormat().setShowValue(true)`คุณสามารถปรับแต่งป้ายข้อมูลเพิ่มเติมได้โดยการควบคุมค่าที่จะแสดง การแสดงคีย์คำอธิบาย และการปรับตัวเลือกการจัดรูปแบบอื่น

### ฉันสามารถเปลี่ยนชื่อของแผนภูมิวงกลมได้หรือไม่?

ใช่ คุณสามารถเปลี่ยนชื่อของแผนภูมิวงกลมได้ ในโค้ดที่ให้มา เราจะตั้งชื่อแผนภูมิโดยใช้ `chart.getChartTitle().addTextFrameForOverriding("Sample Title")`. คุณสามารถแทนที่ `"Sample Title"` พร้อมข้อความชื่อเรื่องตามต้องการ

### ฉันจะบันทึกการนำเสนอที่สร้างขึ้นด้วยแผนภูมิวงกลมได้อย่างไร

หากต้องการบันทึกการนำเสนอด้วยแผนภูมิวงกลม ให้ใช้ `presentation.save()` วิธีการ ระบุเส้นทางและชื่อไฟล์ที่ต้องการ พร้อมรูปแบบที่คุณต้องการบันทึกงานนำเสนอ ตัวอย่างเช่น:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

ตรวจสอบให้แน่ใจว่าคุณระบุเส้นทางและรูปแบบไฟล์ที่ถูกต้อง

### ฉันสามารถสร้างแผนภูมิประเภทอื่นโดยใช้ Aspose.Slides สำหรับ Java ได้หรือไม่

ใช่ Aspose.Slides สำหรับ Java รองรับแผนภูมิประเภทต่างๆ รวมถึงแผนภูมิแท่ง แผนภูมิเส้น และอื่นๆ คุณสามารถสร้างแผนภูมิประเภทต่างๆ ได้โดยการเปลี่ยนแปลง `ChartType` เมื่อเพิ่มแผนภูมิ โปรดดูเอกสาร Aspose.Slides เพื่อดูรายละเอียดเพิ่มเติมเกี่ยวกับการสร้างแผนภูมิประเภทต่างๆ

### ฉันจะค้นหาข้อมูลเพิ่มเติมและตัวอย่างการทำงานกับ Aspose.Slides สำหรับ Java ได้อย่างไร

สำหรับข้อมูลเพิ่มเติม เอกสารรายละเอียด และตัวอย่างเพิ่มเติม คุณสามารถไปที่ [เอกสาร Aspose.Slides สำหรับ Java](https://reference.aspose.com/slides/java/). มีทรัพยากรที่ครอบคลุมเพื่อช่วยให้คุณใช้ห้องสมุดได้อย่างมีประสิทธิภาพ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}