---
title: เส้นแนวโน้มแผนภูมิใน Java Slides
linktitle: เส้นแนวโน้มแผนภูมิใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเพิ่มเส้นแนวโน้มต่างๆ ลงใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ดเพื่อการแสดงภาพข้อมูลที่มีประสิทธิภาพ
weight: 15
url: /th/java/data-manipulation/chart-trend-lines-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เส้นแนวโน้มแผนภูมิใน Java Slides


## ข้อมูลเบื้องต้นเกี่ยวกับเส้นแนวโน้มของแผนภูมิใน Java Slides: คำแนะนำทีละขั้นตอน

ในคู่มือที่ครอบคลุมนี้ เราจะสำรวจวิธีสร้างเส้นแนวโน้มแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java เส้นแนวโน้มของแผนภูมิสามารถเป็นส่วนเสริมที่มีคุณค่าในการนำเสนอของคุณ ช่วยให้เห็นภาพและวิเคราะห์แนวโน้มข้อมูลได้อย่างมีประสิทธิภาพ เราจะแนะนำคุณตลอดกระบวนการพร้อมคำอธิบายที่ชัดเจนและตัวอย่างโค้ด

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกในการสร้างเส้นแนวโน้มของแผนภูมิ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- สภาพแวดล้อมการพัฒนาจาวา
- Aspose.Slides สำหรับไลบรารี Java
- เครื่องมือแก้ไขโค้ดที่คุณเลือก

## ขั้นตอนที่ 1: เริ่มต้นใช้งาน

เริ่มต้นด้วยการตั้งค่าสภาพแวดล้อมที่จำเป็นและสร้างงานนำเสนอใหม่:

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากไม่มีอยู่
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// กำลังสร้างการนำเสนอที่ว่างเปล่า
Presentation pres = new Presentation();
```

เราได้เริ่มต้นการนำเสนอของเราแล้ว และตอนนี้เราพร้อมที่จะเพิ่มแผนภูมิคอลัมน์แบบกลุ่มแล้ว:

```java
// การสร้างแผนภูมิคอลัมน์แบบคลัสเตอร์
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## ขั้นตอนที่ 2: การเพิ่มเส้นแนวโน้มแบบเอ็กซ์โปเนนเชียล

เริ่มต้นด้วยการเพิ่มเส้นแนวโน้มแบบเอ็กซ์โพเนนเชียลให้กับชุดแผนภูมิของเรา:

```java
// การเพิ่มเส้นแนวโน้มเอ็กซ์โพเนนเชียลสำหรับแผนภูมิชุดที่ 1
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## ขั้นตอนที่ 3: การเพิ่มเส้นแนวโน้มเชิงเส้น

ต่อไป เราจะเพิ่มเส้นแนวโน้มเชิงเส้นลงในชุดแผนภูมิของเรา:

```java
// การเพิ่มเส้นแนวโน้มเชิงเส้นสำหรับแผนภูมิชุดที่ 1
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## ขั้นตอนที่ 4: การเพิ่มเส้นแนวโน้มลอการิทึม

ตอนนี้ เรามาเพิ่มเส้นแนวโน้มลอการิทึมให้กับชุดแผนภูมิอื่น:

```java
// การเพิ่มเส้นแนวโน้มลอการิทึมสำหรับแผนภูมิชุดที่ 2
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## ขั้นตอนที่ 5: การเพิ่มเส้นแนวโน้มค่าเฉลี่ยเคลื่อนที่

นอกจากนี้เรายังสามารถเพิ่มเส้นแนวโน้มค่าเฉลี่ยเคลื่อนที่ได้:

```java
// การเพิ่มเส้นแนวโน้มค่าเฉลี่ยเคลื่อนที่สำหรับแผนภูมิชุดที่ 2
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## ขั้นตอนที่ 6: การเพิ่มเส้นแนวโน้มพหุนาม

การเพิ่มเส้นแนวโน้มพหุนาม:

```java
// การเพิ่มเส้นแนวโน้มพหุนามสำหรับแผนภูมิชุดที่ 3
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## ขั้นตอนที่ 7: การเพิ่มเส้นแนวโน้มพลังงาน

สุดท้ายนี้ มาเพิ่มเส้นแนวโน้มกำลัง:

```java
// การเพิ่มเส้นแนวโน้มกำลังสำหรับแผนภูมิชุดที่ 3
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## ขั้นตอนที่ 8: บันทึกการนำเสนอ

ตอนนี้เราได้เพิ่มเส้นแนวโน้มต่างๆ ลงในแผนภูมิของเราแล้ว มาบันทึกการนำเสนอกันดีกว่า:

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

ยินดีด้วย! คุณสร้างงานนำเสนอด้วยเส้นแนวโน้มประเภทต่างๆ ใน Java Slides ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java

## กรอกซอร์สโค้ดสำหรับเส้นแนวโน้มแผนภูมิใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากไม่มีอยู่
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// กำลังสร้างการนำเสนอที่ว่างเปล่า
Presentation pres = new Presentation();
// การสร้างแผนภูมิคอลัมน์แบบคลัสเตอร์
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
// การเพิ่มเส้นแนวโน้มโพเนนเชียลสำหรับแผนภูมิชุดที่ 1
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
// การเพิ่มเส้นแนวโน้มเชิงเส้นสำหรับแผนภูมิชุดที่ 1
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
// การเพิ่มเส้นแนวโน้มลอการิทึมสำหรับแผนภูมิชุดที่ 2
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
// การเพิ่มเส้นแนวโน้ม MovingAverage สำหรับแผนภูมิชุดที่ 2
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
// การเพิ่มเส้นแนวโน้มพหุนามสำหรับแผนภูมิชุดที่ 3
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
// การเพิ่มเส้นแนวโน้มกำลังสำหรับแผนภูมิชุดที่ 3
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
// กำลังบันทึกการนำเสนอ
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีเพิ่มเส้นแนวโน้มประเภทต่างๆ ลงในแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับไลบรารี Java ไม่ว่าคุณจะทำงานเกี่ยวกับการวิเคราะห์ข้อมูลหรือสร้างการนำเสนอข้อมูล ความสามารถในการแสดงภาพแนวโน้มสามารถเป็นเครื่องมือที่มีประสิทธิภาพได้

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนสีของเส้นแนวโน้มใน Aspose.Slides สำหรับ Java ได้อย่างไร

 หากต้องการเปลี่ยนสีของเส้นแนวโน้ม คุณสามารถใช้`getSolidFillColor().setColor(Color)` ดังแสดงในตัวอย่างการเพิ่มเส้นแนวโน้มเชิงเส้น

### ฉันสามารถเพิ่มเส้นแนวโน้มหลายเส้นลงในชุดแผนภูมิเดียวได้หรือไม่

ได้ คุณสามารถเพิ่มเส้นแนวโน้มหลายเส้นลงในชุดแผนภูมิเดียวได้ เพียงโทรไปที่`getTrendLines().add()` วิธีการสำหรับแต่ละเส้นแนวโน้มที่คุณต้องการเพิ่ม

### ฉันจะลบเส้นแนวโน้มออกจากแผนภูมิใน Aspose.Slides สำหรับ Java ได้อย่างไร

 หากต้องการลบเส้นแนวโน้มออกจากแผนภูมิ คุณสามารถใช้`removeAt(int index)` วิธีระบุดัชนีของเส้นแนวโน้มที่คุณต้องการลบ

### เป็นไปได้ไหมที่จะปรับแต่งการแสดงสมการเส้นแนวโน้ม?

 ใช่ คุณสามารถปรับแต่งการแสดงสมการเส้นแนวโน้มได้โดยใช้`setDisplayEquation(boolean)` วิธีการดังแสดงในตัวอย่าง

### ฉันจะเข้าถึงทรัพยากรและตัวอย่างเพิ่มเติมสำหรับ Aspose.Slides สำหรับ Java ได้อย่างไร

 คุณสามารถเข้าถึงทรัพยากร เอกสาร และตัวอย่างเพิ่มเติมสำหรับ Aspose.Slides สำหรับ Java ได้บน[เว็บไซต์กำหนด](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
