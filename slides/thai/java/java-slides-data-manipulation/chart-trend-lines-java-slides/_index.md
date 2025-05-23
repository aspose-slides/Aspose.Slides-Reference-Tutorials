---
"description": "เรียนรู้วิธีเพิ่มเส้นแนวโน้มต่างๆ ลงใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ดสำหรับการแสดงภาพข้อมูลอย่างมีประสิทธิภาพ"
"linktitle": "แผนภูมิเส้นแนวโน้มใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "แผนภูมิเส้นแนวโน้มใน Java Slides"
"url": "/th/java/data-manipulation/chart-trend-lines-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แผนภูมิเส้นแนวโน้มใน Java Slides


## การแนะนำเส้นแนวโน้มของแผนภูมิในสไลด์ Java: คำแนะนำทีละขั้นตอน

ในคู่มือฉบับสมบูรณ์นี้ เราจะมาสำรวจวิธีการสร้างเส้นแนวโน้มของแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java เส้นแนวโน้มของแผนภูมิสามารถเป็นส่วนเสริมที่มีค่าสำหรับการนำเสนอของคุณ ช่วยให้แสดงภาพและวิเคราะห์แนวโน้มข้อมูลได้อย่างมีประสิทธิภาพ เราจะพาคุณผ่านขั้นตอนต่างๆ ด้วยคำอธิบายที่ชัดเจนและตัวอย่างโค้ด

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเริ่มสร้างเส้นแนวโน้มแผนภูมิ โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- สภาพแวดล้อมการพัฒนา Java
- Aspose.Slides สำหรับไลบรารี Java
- โปรแกรมแก้ไขโค้ดที่คุณเลือก

## ขั้นตอนที่ 1: เริ่มต้นใช้งาน

เริ่มต้นด้วยการกำหนดสภาพแวดล้อมที่จำเป็นและสร้างการนำเสนอใหม่:

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากยังไม่มีอยู่
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// การสร้างการนำเสนอแบบว่างเปล่า
Presentation pres = new Presentation();
```

เราได้เริ่มต้นการนำเสนอของเราแล้ว และตอนนี้เราก็พร้อมที่จะเพิ่มแผนภูมิคอลัมน์แบบคลัสเตอร์แล้ว:

```java
// การสร้างแผนภูมิคอลัมน์แบบคลัสเตอร์
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## ขั้นตอนที่ 2: การเพิ่มเส้นแนวโน้มเลขชี้กำลัง

เริ่มต้นด้วยการเพิ่มเส้นแนวโน้มเลขชี้กำลังลงในชุดแผนภูมิของเรา:

```java
// การเพิ่มเส้นแนวโน้มเลขชี้กำลังให้กับชุดแผนภูมิที่ 1
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## ขั้นตอนที่ 3: การเพิ่มเส้นแนวโน้มเชิงเส้น

ถัดไปเราจะเพิ่มเส้นแนวโน้มเชิงเส้นลงในชุดแผนภูมิของเรา:

```java
// การเพิ่มเส้นแนวโน้มเชิงเส้นให้กับชุดแผนภูมิที่ 1
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## ขั้นตอนที่ 4: การเพิ่มเส้นแนวโน้มลอการิทึม

ตอนนี้ มาเพิ่มเส้นแนวโน้มลอการิทึมลงในชุดแผนภูมิอื่นกัน:

```java
// การเพิ่มเส้นแนวโน้มลอการิทึมสำหรับแผนภูมิชุดที่ 2
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## ขั้นตอนที่ 5: การเพิ่มเส้นแนวโน้มค่าเฉลี่ยเคลื่อนที่

นอกจากนี้เรายังสามารถเพิ่มเส้นแนวโน้มค่าเฉลี่ยเคลื่อนที่ได้:

```java
// การเพิ่มเส้นแนวโน้มค่าเฉลี่ยเคลื่อนที่สำหรับชุดแผนภูมิที่ 2
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## ขั้นตอนที่ 6: การเพิ่มเส้นแนวโน้มพหุนาม

การเพิ่มเส้นแนวโน้มพหุนาม:

```java
// การเพิ่มเส้นแนวโน้มพหุนามสำหรับชุดแผนภูมิที่ 3
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## ขั้นตอนที่ 7: เพิ่มเส้นแนวโน้มพลัง

สุดท้ายนี้ ขอเพิ่มเส้นแนวโน้มพลัง:

```java
// การเพิ่มเส้นแนวโน้มพลังให้กับแผนภูมิชุดที่ 3
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## ขั้นตอนที่ 8: บันทึกการนำเสนอ

ตอนนี้เราได้เพิ่มเส้นแนวโน้มต่างๆ ลงในแผนภูมิแล้ว มาบันทึกการนำเสนอกัน:

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

ขอแสดงความยินดี! คุณได้สร้างงานนำเสนอที่มีเส้นแนวโน้มประเภทต่างๆ ใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว

## โค้ดต้นฉบับสมบูรณ์สำหรับเส้นแนวโน้มแผนภูมิในสไลด์ Java

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากยังไม่มีอยู่
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// การสร้างการนำเสนอแบบว่างเปล่า
Presentation pres = new Presentation();
// การสร้างแผนภูมิคอลัมน์แบบคลัสเตอร์
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
// การเพิ่มเส้นแนวโน้มเชิงสถิติสำหรับชุดแผนภูมิที่ 1
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
// การเพิ่มเส้นแนวโน้มเชิงเส้นให้กับชุดแผนภูมิที่ 1
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
// การเพิ่มเส้นแนวโน้มลอการิทึมสำหรับแผนภูมิชุดที่ 2
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
// การเพิ่มเส้นแนวโน้มค่าเฉลี่ยเคลื่อนที่สำหรับชุดแผนภูมิที่ 2
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
// การเพิ่มเส้นแนวโน้มพหุนามสำหรับชุดแผนภูมิที่ 3
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
// การเพิ่มเส้นแนวโน้มพลังให้กับแผนภูมิชุดที่ 3
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
// บันทึกการนำเสนอ
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการเพิ่มเส้นแนวโน้มประเภทต่างๆ ลงในแผนภูมิใน Java Slides โดยใช้ไลบรารี Aspose.Slides สำหรับ Java ไม่ว่าคุณจะทำงานเกี่ยวกับการวิเคราะห์ข้อมูลหรือสร้างงานนำเสนอที่ให้ข้อมูล ความสามารถในการแสดงแนวโน้มสามารถเป็นเครื่องมือที่มีประสิทธิภาพได้

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนสีของเส้นแนวโน้มใน Aspose.Slides สำหรับ Java ได้อย่างไร

หากต้องการเปลี่ยนสีของเส้นแนวโน้ม คุณสามารถใช้ `getSolidFillColor().setColor(Color)` วิธีการดังที่แสดงไว้ในตัวอย่างการเพิ่มเส้นแนวโน้มเชิงเส้น

### ฉันสามารถเพิ่มเส้นแนวโน้มหลายเส้นลงในชุดแผนภูมิเดียวได้หรือไม่

ใช่ คุณสามารถเพิ่มเส้นแนวโน้มหลายเส้นลงในชุดแผนภูมิเดียวได้ เพียงโทร `getTrendLines().add()` วิธีการสำหรับแต่ละเส้นแนวโน้มที่คุณต้องการเพิ่ม

### ฉันจะลบเส้นแนวโน้มออกจากแผนภูมิใน Aspose.Slides สำหรับ Java ได้อย่างไร

หากต้องการลบเส้นแนวโน้มออกจากแผนภูมิ คุณสามารถใช้ `removeAt(int index)` วิธีการโดยระบุดัชนีของเส้นแนวโน้มที่คุณต้องการลบ

### สามารถปรับแต่งการแสดงสมการเส้นแนวโน้มได้หรือไม่

ใช่ คุณสามารถปรับแต่งการแสดงสมการเส้นแนวโน้มได้โดยใช้ `setDisplayEquation(boolean)` วิธีการดังที่แสดงในตัวอย่าง

### ฉันจะเข้าถึงทรัพยากรและตัวอย่างเพิ่มเติมสำหรับ Aspose.Slides สำหรับ Java ได้อย่างไร

คุณสามารถเข้าถึงทรัพยากร เอกสารประกอบ และตัวอย่างเพิ่มเติมสำหรับ Aspose.Slides สำหรับ Java ได้ที่ [เว็บไซต์อาโพส](https://reference-aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}