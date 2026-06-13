---
date: '2026-03-07'
description: Aprenda a criar gráficos de linhas em Java usando Aspose.Slides, adicione
  título ao gráfico, adicione linhas de grade, formate os rótulos do gráfico e salve
  apresentações profissionais.
keywords:
- Aspose.Slides Java
- create charts in Java
- format PowerPoint charts
title: Como criar gráfico de linhas com Aspose.Slides em Java – Um guia completo
url: /pt/java/charts-graphs/create-format-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como criar um gráfico de linhas com Aspose.Slides em Java

## Como criar um gráfico de linhas em Java usando Aspose.Slides

### Introdução
Criar apresentações visualmente atraentes é fundamental para uma comunicação eficaz. Seja você um profissional de negócios ou um educador, muitas vezes precisa **criar gráficos de linhas** que sejam informativos e esteticamente agradáveis. Neste tutorial, percorreremos o uso do **Aspose.Slides for Java** para gerar um gráfico de linhas, adicionar título ao gráfico, inserir linhas de grade, formatar rótulos do gráfico e salvar o resultado como um arquivo PowerPoint.

#### Respostas rápidas
- **Qual biblioteca é a melhor para criar gráficos em Java?** Aspose.Slides for Java
- **Qual tipo de gráfico este guia aborda?** Gráfico de linhas com marcadores
- **Preciso de uma licença para executar o exemplo?** Uma licença temporária gratuita funciona para avaliação
- **Qual IDE posso usar?** Qualquer IDE Java, como IntelliJ IDEA, Eclipse ou NetBeans
- **Como os elementos do gráfico são formatados?** Usando chamadas de API fluente para títulos, eixos, linhas de grade, legendas e fundos

### O que é um gráfico de linhas e por que usar Aspose.Slides?
Um gráfico de linhas exibe pontos de dados conectados por linhas retas, tornando-o ideal para mostrar tendências ao longo do tempo. Aspose.Slides permite criar e personalizar totalmente esses gráficos programaticamente, eliminando a necessidade de edição manual no PowerPoint.

### Pré‑requisitos
- **Java Development Kit (JDK) 8+** instalado
- **IDE** (IntelliJ IDEA, Eclipse, NetBeans, etc.)
- **Aspose.Slides for Java** library (adicionada via Maven ou Gradle)

#### Bibliotecas e dependências necessárias
**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Como alternativa, faça o download do JAR mais recente em [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Aquisição de licença
- Obtenha uma [licença de avaliação gratuita](https://purchase.aspose.com/temporary-license/) para testes.
- Compre uma licença completa no [site oficial da Aspose](https://purchase.aspose.com/buy) para uso em produção.

### Configurando Aspose.Slides for Java
1. **Adicione a dependência** mostrada acima ao seu projeto.
2. **Aplique a licença** (se houver) antes de criar quaisquer objetos de apresentação.

```java
import com.aspose.slides.Presentation;
// Initialize the Presentation object
Presentation pres = new Presentation();
```

## Implementação passo a passo

### Etapa 1: Criar o diretório de saída (create directory java)
```java
import java.io.File;
// Define the target directory
String dataDir = "YOUR_DOCUMENT_DIRECTORY";

// Check if directory exists; create it if not
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs(); // Create directories recursively
}
```
*Por que isso importa:* Garantir que a pasta exista evita `FileNotFoundException` quando você salvar a apresentação posteriormente.

### Etapa 2: Adicionar um slide e inserir um gráfico de linhas
```java
import com.aspose.slides.*;
// Create a new presentation
Presentation pres = new Presentation();
try {
    // Access the first slide
    ISlide slide = pres.getSlides().get_Item(0);

    // Add a chart to the slide
    IChart chart = slide.getShapes().addChart(
        ChartType.LineWithMarkers, 50, 50, 500, 400);
```
*Explicação:* Isso cria um slide novo e coloca um **gráfico de linhas com marcadores** nas coordenadas especificadas.

### Etapa 3: Adicionar título ao gráfico (add chart title)
```java
// Enable and format the title
chart.setTitle(true);
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding()
    .getParagraphs().get_Item(0).getPortions().get_Item(0);

chartTitle.setText("Sample Line Chart");
chartTitle.getPortionFormat().setFontBold(NullableBool.True);
chartTitle.getPortionFormat().setFillType(FillType.Solid);
chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
chartTitle.getPortionFormat().setFontHeight(20);
```
*Dica:* Usar um título em negrito e cinza torna o gráfico instantaneamente reconhecível.

### Etapa 4: Formatizar eixos e inserir linhas de grade (add grid lines)
#### Formatação do eixo vertical
```java
IChartAxis verticalAxis = chart.getAxes().getVerticalAxis();

// Format major grid lines
verticalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.BLUE);
verticalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Configure axis properties
verticalAxis.setNumberFormat("0.0%");
verticalAxis.setMaxValue(15f);
verticalAxis.setMinValue(-2f);
```

#### Formatação do eixo horizontal
```java
IChartAxis horizontalAxis = chart.getAxes().getHorizontalAxis();

// Format major grid lines
horizontalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.GREEN);
horizontalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Set label positions and rotations
horizontalAxis.setTickLabelPosition(TickLabelPositionType.Low);
horizontalAxis.setTickLabelRotationAngle(45);
```
*Por que isso importa:* Linhas de grade claras e rótulos rotacionados melhoram a legibilidade, especialmente quando os pontos de dados são densos.

### Etapa 5: Personalizar a legenda (add chart title – already covered, but legend is part of overall formatting)
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Prevent overlap with the chart area
chart.getLegend().setOverlay(true);
```

### Etapa 6: Definir cores de fundo (format chart labels – part of overall visual styling)
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```

### Etapa 7: Salvar a apresentação
```java
// Save the presentation to disk
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Clean up resources
}
```
*Resultado:* Agora você tem um arquivo PowerPoint (`FormattedChart_out.pptx`) contendo um gráfico de linhas totalmente formatado.

## Aplicações práticas
- **Relatórios de negócios:** Exibir desempenho trimestral com linhas de tendência.
- **Slides educacionais:** Visualizar dados científicos em aulas.
- **Propostas de projetos:** Destacar marcos e previsões.
- **Análise de marketing:** Apresentar tendências de ROI de campanhas.
- **Integração com dashboards:** Exportar dados ao vivo para PowerPoint em reuniões com stakeholders.

## Considerações de desempenho
- **Gerenciamento de memória:** Sempre chame `dispose()` no objeto `Presentation` para liberar recursos nativos prontamente.

## Problemas comuns e soluções
| Problema | Solução |
|----------|---------|
| **Licença não aplicada** | Carregue a licença de avaliação/completa antes de criar quaisquer objetos `Presentation`. |
| **Gráfico aparece em branco** | Verifique se o slide realmente contém séries de dados; adicione séries se necessário. |
| **Arquivo não salvo** | Certifique‑se de que o diretório de saída exista (use a etapa “create directory java”). |
| **Cores não aplicadas** | Use constantes `Color` de `java.awt.Color` ou `PresetColor`. |

## Perguntas frequentes

**P: Posso criar outros tipos de gráfico além de gráficos de linhas?**  
R: Sim, Aspose.Slides suporta gráficos de barras, pizza, dispersão e muitos outros tipos.

**P: Como adiciono várias séries de dados ao gráfico de linhas?**  
R: Use `chart.getChartData().getSeries().add(...)` para inserir séries adicionais antes da formatação.

**P: É possível exportar o gráfico como imagem?**  
R: Absolutamente. Chame `chart.getChartData().getChartDataWorkbook().save(...)` ou renderize o slide para um formato de imagem.

**P: Preciso de uma licença paga para desenvolvimento?**  
R: Uma licença temporária gratuita funciona para avaliação; uma licença comercial é necessária para implantações em produção.

**P: Quais versões do Java são suportadas?**  
R: A biblioteca funciona com JDK 8 até JDK 22 (use o classificador apropriado, por exemplo, `jdk16`). 

---

**Última atualização:** 2026-03-07  
**Testado com:** Aspose.Slides for Java 25.4 (classificador jdk16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}