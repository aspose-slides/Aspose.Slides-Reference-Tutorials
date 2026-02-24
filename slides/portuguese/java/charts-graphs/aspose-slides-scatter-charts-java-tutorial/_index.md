---
date: '2026-02-24'
description: Aprenda a personalizar gráficos de dispersão usando Aspose.Slides para
  Java. Este guia orienta você na criação, estilização e salvamento de gráficos de
  dispersão dinâmicos em suas apresentações.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Personalizar Gráfico de Dispersão Aspose em Java
url: /pt/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

 and spaces.

Translate each bullet.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Personalizar Gráfico de Dispersão Aspose em Java

Neste tutorial você aprenderá a **customize scatter chart aspose** usando a poderosa biblioteca Aspose.Slides for Java. Vamos percorrer a configuração do seu projeto, a criação de um gráfico de dispersão, o ajuste dos tipos de séries e marcadores e, por fim, a gravação da apresentação. Ao final, você será capaz de gerar programaticamente gráficos de dispersão com aparência profissional e adaptar cada detalhe visual para corresponder à sua marca ou necessidades de relatório.

## Respostas Rápidas
- **Qual biblioteca eu preciso?** Aspose.Slides for Java (v25.4+).  
- **Qual versão do Java é suportada?** JDK 8 ou superior.  
- **Posso mudar as formas dos marcadores?** Sim – use `MarkerStyleType` para escolher estrelas, círculos, etc.  
- **Como salvo o arquivo?** Chame `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **É necessária licença?** Um teste gratuito funciona para desenvolvimento; uma licença comercial é necessária para produção.

## O que é “customize scatter chart aspose”?
Personalizar um gráfico de dispersão com Aspose significa definir programaticamente os dados, a aparência e o comportamento do gráfico — tudo, desde as coordenadas dos pontos até os símbolos dos marcadores — sem abrir o PowerPoint manualmente. Essa abordagem é ideal para relatórios automatizados, apresentações orientadas a dados ou qualquer cenário em que você precise de visualizações repetíveis e de alta qualidade.

## Por que personalizar gráficos de dispersão com Aspose.Slides?
- **Controle total** – modifique tipos de séries, estilos de marcadores, cores e muito mais via código Java.  
- **Automação** – gere dezenas de gráficos sob demanda para dashboards ou relatórios em lote.  
- **Multiplataforma** – funciona em qualquer SO que suporte Java, sem necessidade de instalação do Office.  
- **Desempenho** – API leve que lida eficientemente com grandes volumes de dados.

## Pré‑requisitos

Para acompanhar, certifique‑se de que você tem:

- **Aspose.Slides for Java** (v25.4 ou posterior).  
- **Java Development Kit (JDK)** 8 + instalado.  
- Maven ou Gradle para gerenciamento de dependências (ou você pode baixar o JAR manualmente).  
- Conhecimento básico de Java e familiaridade com sua ferramenta de build preferida.

## Configurando Aspose.Slides for Java

Integre a biblioteca ao seu projeto usando um dos métodos abaixo.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Ou obtenha a versão mais recente em [Aspose Releases](https://releases.aspose.com/slides/java/).

#### Aquisição de Licença
- **Teste Gratuito** – avaliação de 30 dias.  
- **Licença Temporária** – período de teste estendido.  
- **Licença Completa** – uso em produção com suporte premium.

## Guia Passo a Passo para Personalizar Gráfico de Dispersão Aspose

### 1️⃣ Prepare uma pasta para seus arquivos de apresentação
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```
*Por que isso importa:* Garantir que a pasta de saída exista evita `FileNotFoundException` quando você salvar o PPTX posteriormente.

### 2️⃣ Crie uma nova apresentação e obtenha o primeiro slide
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
Um `Presentation` novo fornece uma tela limpa; o primeiro slide é onde colocaremos o gráfico.

### 3️⃣ Adicione um gráfico de dispersão com linhas suaves
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
`ChartType.ScatterWithSmoothLines` cria um gráfico de dispersão com linhas suaves, perfeito para visualização de tendências.

### 4️⃣ Remova quaisquer séries padrão e adicione a sua própria
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
Eliminar as séries padrão lhe dá controle total sobre os dados que serão exibidos.

### 5️⃣ Preencha a primeira série com pontos de dados
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
`addDataPointForScatterSeries` recebe uma célula de valor X e uma célula de valor Y, construindo o ponto do scatter plot ponto a ponto.

### 6️⃣ Personalize o tipo de série e a aparência dos marcadores
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
Aqui nós **customize the scatter chart aspose** trocando para linhas retas, ampliando os marcadores e escolhendo símbolos distintos (estrela vs. círculo) para maior clareza visual.

### 7️⃣ Salve a apresentação
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
Salvar como `Pptx` preserva todas as personalizações do gráfico e deixa o arquivo pronto para compartilhamento ou edição adicional.

## Casos de Uso Comuns para Gráficos de Dispersão Personalizados
- **Painéis financeiros** – plotar preço da ação vs. volume.  
- **Pesquisa científica** – exibir medições experimentais com marcadores de erro.  
- **Gerenciamento de projetos** – comparar esforço planejado vs. real em tarefas.  

## Dicas de Desempenho
- Libere o objeto `Presentation` (`pres.dispose()`) após salvar para liberar recursos nativos.  
- Para conjuntos de dados grandes, preencha a planilha primeiro e depois vincule a série para evitar atualizações repetidas da UI.  
- Reutilize uma única instância de `IChartDataWorkbook` ao adicionar muitas séries.

## Perguntas Frequentes

### Como altero a cor dos marcadores?
Use `series.getMarker().getFillFormat().setFillColor(Color)` onde `Color` é uma instância de `java.awt.Color` (por exemplo, `Color.RED`).

### Posso adicionar mais de duas séries a um gráfico de dispersão?
Com certeza. Repita a chamada `chart.getChartData().getSeries().add(...)` para cada série adicional e preencha seus pontos de dados conforme necessário.

### É possível definir uma legenda personalizada para cada série?
Sim. Após criar uma série, chame `series.getLegend().setText("Your Legend Text")` para sobrescrever o nome padrão.

### Como exportar o gráfico como imagem em vez de PPTX?
Chame `chart.getImage().save("chart.png", ImageFormat.Png)` após configurar o gráfico. Isso gera um arquivo PNG independente.

### E se eu precisar animar os pontos de dispersão?
Aspose.Slides suporta efeitos de animação. Use `chart.getTimeline().getMainSequence().addEffect(...)` para adicionar animações de entrada ou ênfase ao gráfico ou a séries individuais.

---

**Última atualização:** 2026-02-24  
**Testado com:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}