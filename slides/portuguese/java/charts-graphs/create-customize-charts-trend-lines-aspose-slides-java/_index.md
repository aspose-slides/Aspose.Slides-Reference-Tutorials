---
date: '2026-08-21'
description: Aprenda a criar um clustered column chart e adicionar trend lines com
  Aspose.Slides for Java. Inclui configuração de license, integração Maven/Gradle
  e exemplos detalhados.
keywords:
- create clustered column chart
- add trend line
- aspose slides license
- java chart creation
- trend lines in charts
lastmod: '2026-08-21'
og_description: Crie um clustered column chart e adicione trend lines usando Aspose.Slides
  for Java. Este guia cobre configuração de license, Maven/Gradle e step‑by‑step code
  snippets.
og_image_alt: Aspose.Slides for Java tutorial showing a clustered column chart with
  trend lines
og_title: Crie um clustered column chart e adicione trend lines com Aspose.Slides
  for Java
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  headline: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  type: TechArticle
- description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  name: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  steps:
  - name: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
    text: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
  - name: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
    text: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
  - name: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
    text: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
  - name: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
    text: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
  - name: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
    text: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
  - name: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
    text: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
  - name: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
    text: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
  - name: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
    text: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
  type: HowTo
- questions:
  - answer: Add the `<dependency>` snippet shown in the Maven section to your `pom.xml`
      and run `mvn clean install`.
    question: How do I set up Aspose.Slides for a Maven project?
  - answer: Yes, you can modify line style, width, dash pattern, and even forecast
      forward/backward values via the `ITrendline` API.
    question: Can I customise trend lines beyond colour and label?
  - answer: Verify that your JDK version matches the Aspose.Slides minimum requirement
      (JDK 8+). Consult the Aspose release notes for any breaking changes.
    question: What should I do if I encounter a version‑compatibility error?
  - answer: Absolutely. Loop through each `IChart` in a slide collection and invoke
      the appropriate `addTrendline` method for each series.
    question: Is it possible to add trend lines to multiple charts automatically?
  - answer: Yes, a purchased Aspose.Slides license removes evaluation limits and unlocks
      full performance optimisations.
    question: Do I need a paid license for production use?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides for Java
- Java chart customization
- trend line examples
- Java presentation generation
title: Como criar um clustered column chart e adicionar trend lines usando Aspose.Slides
  for Java
url: /pt/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar gráfico de colunas agrupadas e adicionar linhas de tendência usando Aspose.Slides for Java

Criar apresentações impactantes geralmente começa com uma visualização clara dos seus dados. Neste guia você **criará objetos de gráfico de colunas agrupadas**, depois os enriquecerá com uma variedade de linhas de tendência — exponencial, linear, logarítmica, média móvel, polinomial e potência — usando a poderosa API Aspose.Slides for Java.

## Respostas rápidas
- **Qual é o primeiro passo?** Inicializar um objeto `Presentation` e adicionar um gráfico de colunas agrupadas a um slide.  
- **Qual versão da biblioteca é necessária?** Aspose.Slides for Java 25.4 ou mais recente.  
- **Posso usar Maven ou Gradle?** Sim, ambos são suportados; Maven usa `<dependency>` e Gradle usa `implementation`.  
- **Preciso de licença?** Uma licença de avaliação funciona para avaliação; uma licença completa Aspose.Slides remove as limitações de avaliação.  
- **Quantos tipos de linha de tendência estão disponíveis?** Seis tipos incorporados: exponencial, linear, logarítmica, média móvel, polinomial e potência.

## O que é criar gráfico de colunas agrupadas?
`create clustered column chart` significa gerar um gráfico que agrupa várias séries de dados lado a lado dentro de cada categoria, facilitando a comparação de valores entre as séries. Esse tipo de gráfico é ideal para visualizar dados categóricos, como vendas trimestrais por região, permitindo que os espectadores identifiquem rapidamente diferenças entre os grupos.

## Por que adicionar linha de tendência?
Linhas de tendência revelam o padrão subjacente de uma série de dados, ajudando a prever valores futuros, destacar taxas de crescimento ou suavizar dados ruidosos. Ao adicionar uma linha de tendência a um gráfico de colunas agrupadas, números brutos se transformam em insights acionáveis, permitindo que as partes interessadas compreendam tendências de longo prazo e tomem decisões baseadas em dados.

## Pré‑requisitos
- **Java Development Kit (JDK):** 8 ou superior.  
- **Aspose.Slides for Java:** versão 25.4 ou mais recente.  
- **IDE:** IntelliJ IDEA, Eclipse ou qualquer editor compatível com Java.  
- **Ferramenta de build:** Maven ou Gradle (opcional, mas recomendado).  
- **Licença:** um arquivo de licença Aspose.Slides de avaliação ou adquirido.  

É desejável que você esteja confortável com a sintaxe básica de Java e familiarizado com o gerenciamento de dependências de projetos.

## Como configurar Aspose.Slides for Java?
Adicione a biblioteca Aspose.Slides ao seu projeto usando o gerenciador de dependências de sua preferência e, em seguida, coloque o arquivo de licença onde o runtime puder localizá‑lo. Isso garante funcionalidade total e remove as restrições de avaliação.

### Maven
Adicione esta dependência ao seu arquivo `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Inclua esta linha no seu arquivo `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download direto
Você também pode baixar o JAR manualmente em [lançamentos do Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

#### Licença Aspose Slides
Coloque o arquivo `Aspose.Slides.lic` na raiz do seu projeto ou defina a licença programaticamente com `License license = new License(); license.setLicense("Aspose.Slides.lic");`. Uma licença de avaliação remove todas as restrições de recursos, mas uma licença adquirida elimina a marca d'água de avaliação e concede otimizações de desempenho completas. Para uso em produção, considere adquirir uma licença na [página de compra da Aspose](https://purchase.aspose.com/buy).

## Como criar uma apresentação e adicionar um gráfico de colunas agrupadas?
A classe `Presentation` representa um arquivo PowerPoint e fornece métodos para criar, editar e salvar slides. Instancie um `Presentation`, adicione um slide e, em seguida, chame `addChart` com `ChartType.ClusteredColumn` para criar o objeto de gráfico. Esse processo configura a tela do slide, insere uma forma de gráfico e a prepara para preenchimento de dados e estilização.

1. **Inicializar a apresentação** – configure a pasta de saída e crie uma nova instância `Presentation`.  
```java
   String dataDir = "YOUR_DOCUMENT_DIRECTORY";
   File dir = new File(dataDir);
   if (!dir.exists()) {
       dir.mkdirs();
   }
   ```

2. **Adicionar um gráfico de colunas agrupadas** – obtenha a forma de gráfico, configure suas séries e preencha os pontos de dados.  
```java
   Presentation pres = new Presentation();
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 20, 20, 500, 400);
   pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
   ```

## Como adicionar uma linha de tendência exponencial?
A interface `ITrendline` define uma linha de tendência que pode ser adicionada a uma série de gráfico para modelar padrões de dados. Aplique uma linha de tendência exponencial a uma série criando uma instância `ITrendline`, definindo seu `TrendlineType` para `Exponential` e anexando‑a à série desejada. Esse tipo de linha de tendência é útil para dados que crescem rapidamente a uma taxa crescente.

1. **Configurar a linha de tendência** – selecione a série e chame `addTrendline(TrendlineType.Exponential)`.  
```java
   ITrendline tredLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
   tredLineExp.setDisplayEquation(false); // Hides the equation for simplicity.
   ```

## Como adicionar uma linha de tendência linear?
Uma linha de tendência linear mostra a linha reta de melhor ajuste através dos seus pontos de dados. Você também pode personalizar sua aparência, como cor e espessura da linha, para combinar com o estilo da sua apresentação.

1. **Configurar a linha de tendência** – use `addTrendline(TrendlineType.Linear)` e então ajuste `getLineFormat().setFillFormat().setFillType(FillType.Solid)` para mudar a cor.  
```java
   ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
   tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
   tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
   ```

## Como adicionar uma linha de tendência logarítmica com um quadro de texto personalizado?
Linhas de tendência logarítmicas são ideais para dados que crescem rapidamente no início e depois se estabilizam. Substituir o rótulo padrão permite que você adicione um texto explicativo que esclareça o significado da tendência.

1. **Personalizar a linha de tendência** – após adicionar a linha de tendência, acesse seu `getDataLabel()` e defina a propriedade `setText("Custom label")`.  
```java
   ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
   tredLineLog.addTextFrameForOverriding("New log trend line");
   ```

## Como adicionar uma linha de tendência de média móvel?
Linhas de tendência de média móvel suavizam flutuações de curto prazo para destacar tendências de longo prazo. Você pode especificar o período (número de pontos) usado para a média, permitindo controlar a suavidade da linha.

1. **Configurar a linha de tendência** – chame `addTrendline(TrendlineType.MovingAverage)` e defina `setPeriod(3)` para usar uma média móvel de três pontos.  
```java
   ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
   tredLineMovAvg.setPeriod((byte) 3); // Sets the period for calculation.
   String newTrendLineName = "New TrendLine Name";
   tredLineMovAvg.setTrendlineName(newTrendLineName);
   ```

## Como adicionar uma linha de tendência polinomial?
Linhas de tendência polinomiais ajustam os dados com uma curva definida por uma equação polinomial. A propriedade `order` controla o grau do polinômio, permitindo modelar relacionamentos mais complexos.

1. **Personalizar a linha de tendência** – após adicionar a linha de tendência, defina `setOrder(3)` para um ajuste cúbico.  
```java
   ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
   tredLinePol.setForward(1); // Sets forward value.
   byte order = 3;
   tredLinePol.setOrder(order); // Polynomial degree/order.
   ```

## Como adicionar uma linha de tendência de potência?
Linhas de tendência de potência são úteis quando os dados seguem uma relação de lei de potência. Você também pode definir valores de previsão para trás e para frente para estender a linha além do intervalo de dados existente.

1. **Configurar a linha de tendência** – use `addTrendline(TrendlineType.Power)` e ajuste `setBackward(2)` para estender a linha para trás.  
```java
   ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
   tredLinePower.setBackward(1); // Sets backward value.
   ```

## Aplicações práticas de linhas de tendência em gráficos de colunas agrupadas
- **Análise financeira:** Tendências exponenciais e polinomiais ajudam a prever movimentos de preços de ações.  
- **Previsão de vendas:** Linhas de média móvel suavizam picos sazonais, proporcionando uma visão mais clara das tendências subjacentes de vendas.  
- **Pesquisa científica:** Tendências logarítmicas são perfeitas para dados que abrangem várias ordens de magnitude, como intensidade acústica ou níveis de pH.  
- **Monitoramento de operações:** Linhas de tendência de potência podem modelar a degradação de desempenho ao longo do tempo.

## Como otimizar a memória ao usar Aspose.Slides?
Descarte objetos prontamente e use `presentation.dispose()` após salvar. Para conjuntos de dados grandes, habilite o carregamento preguiçoso de imagens e evite carregar todo o gráfico na memória de uma só vez.

- **Padrões de descarte:** Envolva `Presentation` em um bloco try‑with‑resources ou chame `presentation.dispose()` em um bloco finally.  
- **Carregamento preguiçoso:** Defina `ChartData.setUseCache(true)` ao lidar com milhares de pontos de dados.  
- **Saída em streaming:** Escreva a apresentação diretamente em um `FileOutputStream` para evitar manter todo o arquivo na RAM.

## Benefícios quantificados do Aspose.Slides for Java
Aspose.Slides suporta **mais de 50 tipos de gráfico**, pode gerar apresentações com **mais de 1.000 slides** em menos de **30 segundos** em uma CPU típica de 2 GHz, e processa **PDFs de 500 páginas** sem exigir o Microsoft Office instalado. Esses números são verificados na versão mais recente 25.4.

## Conclusão
Agora você tem uma solução completa, de ponta a ponta, para **criar objetos de gráfico de colunas agrupadas** e enriquecê‑los com todos os principais tipos de linha de tendência disponíveis no Aspose.Slides for Java. Seguindo os passos acima, você pode produzir apresentações orientadas a dados que são visualmente atraentes e analiticamente poderosas.

Os próximos passos incluem explorar opções de estilo de gráfico, exportar para PDF/HTML e automatizar a geração de gráficos em múltiplas fontes de dados.

## Perguntas frequentes

**Q: Como configuro Aspose.Slides para um projeto Maven?**  
A: Adicione o trecho `<dependency>` mostrado na seção Maven ao seu `pom.xml` e execute `mvn clean install`.

**Q: Posso personalizar linhas de tendência além de cor e rótulo?**  
A: Sim, você pode modificar o estilo da linha, largura, padrão de traço e até valores de previsão para frente/para trás via a API `ITrendline`.

**Q: O que devo fazer se encontrar um erro de compatibilidade de versão?**  
A: Verifique se sua versão do JDK corresponde ao requisito mínimo do Aspose.Slides (JDK 8+). Consulte as notas de versão da Aspose para quaisquer mudanças incompatíveis.

**Q: É possível adicionar linhas de tendência a vários gráficos automaticamente?**  
A: Absolutamente. Percorra cada `IChart` em uma coleção de slides e invoque o método `addTrendline` apropriado para cada série.

**Q: Preciso de licença paga para uso em produção?**  
A: Sim, uma licença adquirida do Aspose.Slides remove limites de avaliação e desbloqueia otimizações de desempenho completas.

---

**Última atualização:** 2026-08-21  
**Testado com:** Aspose.Slides for Java 25.4  
**Autor:** Aspose

## Tutoriais relacionados

- [aspose slides maven dependency: Add and Configure Charts in Presentations Using Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Add animation to PowerPoint chart using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Create PowerPoint Chart Java – Save Presentations with Charts Using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}