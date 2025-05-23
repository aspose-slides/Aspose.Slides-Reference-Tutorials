---
"date": "2025-04-17"
"description": "Aprenda a criar gráficos de dispersão dinâmicos usando o Aspose.Slides para Java. Aprimore suas apresentações com recursos de gráficos personalizáveis."
"title": "Crie e personalize gráficos de dispersão em Java com Aspose.Slides"
"url": "/pt/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crie e personalize gráficos de dispersão em Java com Aspose.Slides

Aprimore suas apresentações adicionando gráficos de dispersão dinâmicos usando Java com o Aspose.Slides. Este tutorial abrangente guiará você pela configuração de diretórios, inicialização de apresentações, criação de gráficos de dispersão, gerenciamento de dados de gráficos, personalização de tipos de séries e marcadores e salvamento do seu trabalho — tudo com facilidade.

**O que você aprenderá:**
- Configurando um diretório para armazenar arquivos de apresentação
- Inicializando e manipulando apresentações usando Aspose.Slides
- Criando gráficos de dispersão em slides
- Gerenciando e adicionando dados a séries de gráficos
- Personalizando tipos de séries de gráficos e marcadores
- Salvando sua apresentação com modificações

Vamos começar garantindo que você tenha os pré-requisitos necessários.

## Pré-requisitos

Para seguir este tutorial, certifique-se de ter:
- **Aspose.Slides para Java**: É necessária a versão 25.4 ou posterior.
- **Kit de Desenvolvimento Java (JDK)**: É necessário JDK 8 ou superior.
- Conhecimento básico de programação Java e familiaridade com ferramentas de construção Maven ou Gradle.

## Configurando o Aspose.Slides para Java

Antes de começar a codificar, integre o Aspose.Slides ao seu projeto usando um dos seguintes métodos:

### Especialista
Inclua esta dependência em seu `pom.xml` arquivo:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Adicione esta linha ao seu `build.gradle` arquivo:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativamente, baixe o Aspose.Slides mais recente para Java em [Lançamentos Aspose](https://releases.aspose.com/slides/java/).

#### Aquisição de Licença
- **Teste grátis**: Comece com um teste gratuito de 30 dias para explorar os recursos.
- **Licença Temporária**: Obtenha uma licença temporária para testes estendidos.
- **Comprar**: Compre uma licença para acesso e suporte completos.

Agora, inicialize o Aspose.Slides no seu aplicativo Java adicionando as importações necessárias, conforme mostrado abaixo.

## Guia de Implementação

### Configuração de diretório
Primeiro, certifique-se de que nosso diretório exista para armazenar os arquivos de apresentação. Essa etapa evita erros ao salvar o arquivo.

#### Crie o diretório se ele não existir
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Crie o diretório
    new File(dataDir).mkdirs();
}
```
Este trecho verifica se há um diretório especificado e o cria se ele não existir. Ele usa `File.exists()` para verificar a presença e `File.mkdirs()` para criar diretórios.

### Inicialização da apresentação

Em seguida, inicialize seu objeto de apresentação onde você adicionará o gráfico de dispersão.

#### Inicialize sua apresentação
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
Aqui, `new Presentation()` cria uma apresentação em branco. Acessamos o primeiro slide para trabalhar diretamente com ele.

### Criação de gráficos
O próximo passo é criar um gráfico de dispersão em nosso slide inicializado.

#### Adicionar gráfico de dispersão ao slide
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Este trecho de código adiciona um gráfico de dispersão com linhas suaves ao primeiro slide. Os parâmetros definem a posição e o tamanho do gráfico.

### Gerenciamento de dados gráficos
Agora vamos gerenciar os dados do nosso gráfico limpando todas as séries existentes e adicionando novas.

#### Gerenciar séries de gráficos
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adicionando novas séries ao gráfico
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
Esta seção limpa os dados existentes e adiciona duas novas séries ao nosso gráfico de dispersão.

### Adição de Pontos de Dados para Séries de Dispersão
Para visualizar nossos dados, adicionamos pontos a cada série no gráfico de dispersão.

#### Adicionar pontos de dados
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
Nós usamos `addDataPointForScatterSeries()` para anexar pontos de dados à nossa primeira série. Os parâmetros definem os valores de X e Y.

### Modificação de tipo de série e marcador
Personalize a aparência do seu gráfico alterando o tipo e o estilo dos marcadores em cada série.

#### Personalizar série
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modificando a segunda série
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
Essas alterações ajustam o tipo de série para usar linhas retas e marcadores. Também definimos o tamanho do marcador e o símbolo para distinção visual.

### Apresentação Salvando
Por fim, salve sua apresentação com todas as modificações feitas.

#### Salve sua apresentação
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
Usar `SaveFormat.Pptx` para especificar o formato do PowerPoint para salvar seu arquivo. Esta etapa é crucial para preservar todas as alterações.

## Aplicações práticas
Aqui estão alguns casos de uso do mundo real:
1. **Análise Financeira**: Use gráficos de dispersão para exibir tendências de ações ao longo do tempo.
2. **Pesquisa científica**: Representa pontos de dados experimentais para análise.
3. **Gerenciamento de projetos**: Visualize a alocação de recursos e as métricas de progresso.

Integrar o Aspose.Slides ao seu sistema permite automatizar a geração de relatórios, aumentando a produtividade e a precisão.

## Considerações de desempenho
Para um desempenho ideal:
- Gerencie o uso de memória descartando as apresentações após salvá-las.
- Use estruturas de dados eficientes para grandes conjuntos de dados.
- Minimize operações que exigem muitos recursos dentro de loops.

As melhores práticas garantem uma execução tranquila, mesmo com manipulações complexas de gráficos.

## Conclusão
Neste tutorial, você aprendeu a configurar diretórios, inicializar apresentações do Aspose.Slides, criar e personalizar gráficos de dispersão, gerenciar dados de séries, modificar marcadores e salvar seu trabalho. Para explorar melhor os recursos do Aspose.Slides, considere explorar recursos mais avançados, como animação e transições de slides.

**Próximos passos**: Experimente diferentes tipos de gráficos ou integre essas técnicas em um projeto Java maior.

## Perguntas frequentes

### Como altero a cor dos marcadores?
Para alterar a cor do marcador, use `series.getMarker().getFillFormat().setFillColor(ColorObject)`, onde `ColorObject` é a cor desejada.

### Posso adicionar mais de duas séries a um gráfico de dispersão?
Sim, você pode adicionar quantas séries forem necessárias repetindo o processo de adição de novas séries e pontos de dados.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}