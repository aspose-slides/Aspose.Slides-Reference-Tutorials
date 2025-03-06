---
title: แผนภูมิวงกลมใน Java Slides
linktitle: แผนภูมิวงกลมใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้างแผนภูมิวงกลมที่น่าทึ่งในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดสำหรับนักพัฒนา Java
weight: 23
url: /th/java/chart-data-manipulation/pie-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## ข้อมูลเบื้องต้นเกี่ยวกับการสร้างแผนภูมิวงกลมใน Java Slides โดยใช้ Aspose.Slides

ในบทช่วยสอนนี้ เราจะสาธิตวิธีการสร้างแผนภูมิวงกลมในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เราจะให้คำแนะนำทีละขั้นตอนและซอร์สโค้ด Java เพื่อช่วยคุณในการเริ่มต้น คู่มือนี้ถือว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณด้วย Aspose.Slides สำหรับ Java แล้ว

## ข้อกำหนดเบื้องต้น

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและกำหนดค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

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

// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงถึงไฟล์ PPTX
Presentation presentation = new Presentation();
```

 สร้างวัตถุการนำเสนอใหม่เพื่อแสดงไฟล์ PowerPoint ของคุณ แทนที่`"Your Document Directory"` พร้อมเส้นทางจริงที่คุณต้องการบันทึกการนำเสนอ

## ขั้นตอนที่ 3: เพิ่มสไลด์

```java
// เข้าถึงสไลด์แรก
ISlide slide = presentation.getSlides().get_Item(0);
```

รับสไลด์แรกของงานนำเสนอที่คุณต้องการเพิ่มแผนภูมิวงกลม

## ขั้นตอนที่ 4: เพิ่มแผนภูมิวงกลม

```java
// เพิ่มแผนภูมิวงกลมด้วยข้อมูลเริ่มต้น
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

เพิ่มแผนภูมิวงกลมลงในสไลด์ตามตำแหน่งและขนาดที่ระบุ

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
//ตั้งค่าชุดแรกเพื่อแสดงค่า
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
int defaultWorksheetIndex = 0;

// รับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// ลบซีรี่ส์และหมวดหมู่ที่สร้างโดยค่าเริ่มต้น
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// การเพิ่มหมวดหมู่ใหม่
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// กำลังเพิ่มซีรีส์ใหม่
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// กำลังเติมข้อมูลซีรีส์
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

ปรับแต่งข้อมูลแผนภูมิโดยเพิ่มหมวดหมู่และซีรีส์ และตั้งค่า ในตัวอย่างนี้ เรามีสามหมวดหมู่และหนึ่งชุดที่มีจุดข้อมูลที่สอดคล้องกัน

## ขั้นตอนที่ 7: ปรับแต่งส่วนแผนภูมิวงกลม

```java
// ตั้งค่าสีของเซกเตอร์
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// ปรับแต่งรูปลักษณ์ของแต่ละภาค
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// ปรับแต่งเส้นขอบเซกเตอร์
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// ปรับแต่งภาคอื่นๆ ในลักษณะเดียวกัน
```

ปรับแต่งลักษณะที่ปรากฏของแต่ละส่วนในแผนภูมิวงกลม คุณสามารถเปลี่ยนสี ลักษณะเส้นขอบ และคุณสมบัติการมองเห็นอื่นๆ ได้

## ขั้นตอนที่ 8: ปรับแต่งป้ายกำกับข้อมูล

```java
// ปรับแต่งป้ายกำกับข้อมูล
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// ปรับแต่งป้ายกำกับข้อมูลสำหรับจุดข้อมูลอื่นๆ ในลักษณะเดียวกัน
```

ปรับแต่งป้ายข้อมูลสำหรับแต่ละจุดข้อมูลในแผนภูมิวงกลม คุณสามารถควบคุมได้ว่าค่าใดจะแสดงบนแผนภูมิ

## ขั้นตอนที่ 9: แสดงเส้นผู้นำ

```java
// แสดงเส้นตัวนำสำหรับแผนภูมิ
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

เปิดใช้งานเส้นผู้นำเพื่อเชื่อมต่อป้ายกำกับข้อมูลกับเซกเตอร์ที่เกี่ยวข้อง

## ขั้นตอนที่ 10: ตั้งค่ามุมการหมุนของแผนภูมิวงกลม

```java
// ตั้งค่ามุมการหมุนสำหรับส่วนแผนภูมิวงกลม
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

ตั้งค่ามุมการหมุนสำหรับส่วนแผนภูมิวงกลม ในตัวอย่างนี้ เราตั้งค่าไว้ที่ 180 องศา

## ขั้นตอนที่ 11: บันทึกการนำเสนอ

```java
// บันทึกงานนำเสนอด้วยแผนภูมิวงกลม
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

บันทึกงานนำเสนอด้วยแผนภูมิวงกลมไปยังไดเร็กทอรีที่ระบุ

## กรอกซอร์สโค้ดสำหรับแผนภูมิวงกลมใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงถึงไฟล์ PPTX
Presentation presentation = new Presentation();
// เข้าถึงสไลด์แรก
ISlide slides = presentation.getSlides().get_Item(0);
// เพิ่มแผนภูมิด้วยข้อมูลเริ่มต้น
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// การตั้งชื่อแผนภูมิ
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// ตั้งค่าชุดแรกเพื่อแสดงค่า
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
int defaultWorksheetIndex = 0;
// รับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// ลบซีรี่ส์และหมวดหมู่ที่สร้างโดยค่าเริ่มต้น
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// การเพิ่มหมวดหมู่ใหม่
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// กำลังเพิ่มซีรีส์ใหม่
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// กำลังเติมข้อมูลซีรีส์
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// ไม่ได้ทำงานในเวอร์ชันใหม่
// การเพิ่มจุดใหม่และการตั้งค่าสีเซกเตอร์
// series.IsColorVaried = จริง;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// การตั้งค่าขอบเขตเซกเตอร์
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// การตั้งค่าขอบเขตเซกเตอร์
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// การตั้งค่าขอบเขตเซกเตอร์
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// สร้างป้ายกำกับที่กำหนดเองสำหรับแต่ละหมวดหมู่สำหรับซีรี่ส์ใหม่
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
// การตั้งค่ามุมการหมุนสำหรับส่วนแผนภูมิวงกลม
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// บันทึกการนำเสนอด้วยแผนภูมิ
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## บทสรุป

คุณสร้างแผนภูมิวงกลมในงานนำเสนอ PowerPoint ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งลักษณะที่ปรากฏของแผนภูมิและป้ายกำกับข้อมูลได้ตามความต้องการเฉพาะของคุณ บทช่วยสอนนี้เป็นตัวอย่างพื้นฐาน และคุณสามารถปรับปรุงและปรับแต่งแผนภูมิของคุณเพิ่มเติมได้ตามต้องการ

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนสีของแต่ละส่วนในแผนภูมิวงกลมได้อย่างไร

 หากต้องการเปลี่ยนสีของแต่ละส่วนในแผนภูมิวงกลม คุณสามารถปรับแต่งสีเติมสำหรับแต่ละจุดข้อมูลได้ ในตัวอย่างโค้ดที่ให้มา เราได้สาธิตวิธีการตั้งค่าสีเติมสำหรับแต่ละเซกเตอร์โดยใช้`getSolidFillColor().setColor()` วิธี. คุณสามารถแก้ไขค่าสีเพื่อให้ได้ลักษณะที่ต้องการได้

### ฉันสามารถเพิ่มหมวดหมู่และชุดข้อมูลเพิ่มเติมลงในแผนภูมิวงกลมได้หรือไม่

 ได้ คุณสามารถเพิ่มหมวดหมู่และชุดข้อมูลเพิ่มเติมลงในแผนภูมิวงกลมได้ เมื่อต้องการทำเช่นนี้ คุณสามารถใช้`getChartData().getCategories().add()` และ`getChartData().getSeries().add()` วิธีการดังแสดงในตัวอย่าง เพียงให้ข้อมูลและป้ายกำกับที่เหมาะสมสำหรับหมวดหมู่และซีรีส์ใหม่เพื่อขยายแผนภูมิของคุณ

### ฉันจะปรับแต่งลักษณะที่ปรากฏของป้ายกำกับข้อมูลได้อย่างไร

 คุณสามารถปรับแต่งลักษณะที่ปรากฏของป้ายกำกับข้อมูลได้โดยใช้`getDataLabelFormat()` วิธีการบนฉลากของแต่ละจุดข้อมูล ในตัวอย่าง เราได้สาธิตวิธีการแสดงค่าบนป้ายกำกับข้อมูลโดยใช้`getDataLabelFormat().setShowValue(true)`- คุณสามารถปรับแต่งป้ายกำกับข้อมูลเพิ่มเติมได้โดยการควบคุมค่าที่จะแสดง แสดงคีย์คำอธิบาย และปรับตัวเลือกการจัดรูปแบบอื่นๆ

### ฉันสามารถเปลี่ยนชื่อของแผนภูมิวงกลมได้หรือไม่

 ได้ คุณสามารถเปลี่ยนชื่อของแผนภูมิวงกลมได้ ในโค้ดที่ให้มา เราตั้งชื่อแผนภูมิโดยใช้`chart.getChartTitle().addTextFrameForOverriding("Sample Title")` - คุณสามารถแทนที่ได้`"Sample Title"` พร้อมข้อความหัวเรื่องที่คุณต้องการ

### ฉันจะบันทึกงานนำเสนอที่สร้างขึ้นด้วยแผนภูมิวงกลมได้อย่างไร

 หากต้องการบันทึกงานนำเสนอด้วยแผนภูมิวงกลม ให้ใช้`presentation.save()` วิธี. ระบุเส้นทางและชื่อไฟล์ที่ต้องการพร้อมกับรูปแบบที่คุณต้องการบันทึกงานนำเสนอ ตัวอย่างเช่น:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางและรูปแบบไฟล์ที่ถูกต้อง

### ฉันสามารถสร้างแผนภูมิประเภทอื่นโดยใช้ Aspose.Slides สำหรับ Java ได้หรือไม่

ใช่ Aspose.Slides สำหรับ Java รองรับแผนภูมิหลายประเภท รวมถึงแผนภูมิแท่ง แผนภูมิเส้น และอื่นๆ คุณสามารถสร้างแผนภูมิประเภทต่างๆ ได้โดยการเปลี่ยน`ChartType` เมื่อเพิ่มแผนภูมิ โปรดดูเอกสารประกอบของ Aspose.Slides สำหรับรายละเอียดเพิ่มเติมเกี่ยวกับการสร้างแผนภูมิประเภทต่างๆ

### ฉันจะค้นหาข้อมูลเพิ่มเติมและตัวอย่างการทำงานกับ Aspose.Slides สำหรับ Java ได้อย่างไร

 สำหรับข้อมูลเพิ่มเติม เอกสารโดยละเอียด และตัวอย่างเพิ่มเติม คุณสามารถไปที่[Aspose.Slides สำหรับเอกสาร Java](https://reference.aspose.com/slides/java/)- มีทรัพยากรที่ครอบคลุมเพื่อช่วยให้คุณใช้ห้องสมุดได้อย่างมีประสิทธิภาพ
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
