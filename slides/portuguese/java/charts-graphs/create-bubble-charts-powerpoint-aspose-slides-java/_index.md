---
date: '2026-09-17'
description: Aprenda como criar bubble chart powerpoint usando Aspose.Slides for Java.
  Este guia mostra como adicionar chart ao slide, configurar bubble size e salvar
  o PPTX de forma eficiente.
keywords:
- create bubble chart powerpoint
- add chart to slide
- Aspose.Slides for Java tutorial
- bubble chart PowerPoint
- Java presentation automation
lastmod: '2026-09-17'
og_description: Aprenda como criar bubble chart powerpoint usando Aspose.Slides for
  Java. Este tutorial explica como adicionar chart ao slide, ajustar bubble sizes
  e salvar a presentation de forma eficiente.
og_image_alt: 'Developer guide: create bubble chart powerpoint using Aspose.Slides
  for Java'
og_title: Criar bubble chart powerpoint com Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  headline: Create bubble chart powerpoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  name: Create bubble chart powerpoint with Aspose.Slides for Java
  steps:
  - name: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
    text: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
  - name: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
    text: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
  - name: '**Geographical data** – plot cities with population encoded in bubble size.'
    text: '**Geographical data** – plot cities with population encoded in bubble size.'
  - name: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
    text: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java is a standalone library that lets you create, edit,
      and convert PowerPoint files without needing Microsoft Office.
    question: What is Aspose.Slides for Java?
  - answer: Add the Maven or Gradle dependency shown earlier, or drop the JAR into
      your classpath, then import `com.aspose.slides.*`.
    question: How do I integrate Aspose.Slides with my existing Java project?
  - answer: Yes, the library efficiently handles presentations up to **2 GB** and
      supports streaming to avoid loading the whole file into memory.
    question: Can I use Aspose.Slides for large presentations?
  - answer: Over **50 chart types** are supported, including bar, line, pie, radar,
      and waterfall charts.
    question: What chart types are available besides bubble charts?
  - answer: Absolutely. You can customize colors, fonts, borders, and data labels
      via the chart’s `ChartSeries` and `ChartTitle` objects.
    question: Is there built‑in support for styling chart elements?
  type: FAQPage
tags:
- create bubble chart
- Aspose.Slides
- Java charting
- PowerPoint automation
- slide graphics
title: Criar bubble chart powerpoint com Aspose.Slides for Java
url: /pt/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar gráfico de bolhas no PowerPoint com Aspose.Slides para Java

## Introdução
Se você precisar **criar gráfico de bolhas no PowerPoint** apresentações programaticamente, o Aspose.Slides para Java oferece uma API limpa, do lado do servidor, que funciona sem o Microsoft Office. Neste tutorial você aprenderá como adicionar um gráfico a um slide, controlar o tamanho das bolhas e salvar o PPTX final enquanto gerencia recursos de forma eficiente. As etapas são divididas para que você possa copiar‑colar o código em qualquer projeto Java e ver os resultados instantaneamente.

## Respostas rápidas
- **Qual biblioteca eu preciso?** Aspose.Slides for Java
- **Qual versão do Java é necessária?** JDK 16 ou superior
- **Como adiciono um gráfico de bolhas?** Chame `addChart(ChartType.Bubble, …)` em um slide
- **Posso mudar o tamanho da bolha?** Sim, via `setBubbleSizeScale()`
- **Como salvo o arquivo?** Use `pres.save("Result.pptx", SaveFormat.Pptx)`

## O que é criar gráfico de bolhas no PowerPoint?
Criar um gráfico de bolhas no PowerPoint significa gerar programaticamente um gráfico onde cada ponto de dados é representado por uma bolha cuja posição X, posição Y e tamanho codificam três dimensões de dados. O Aspose.Slides para Java cuida da renderização, portanto você não precisa do PowerPoint instalado.

## Por que usar Aspose.Slides para Java?
O Aspose.Slides suporta **mais de 50 tipos de gráficos**, pode processar apresentações de até **2 GB** sem carregar o arquivo inteiro na memória e funciona em qualquer plataforma que suporte Java 16+. Essas capacidades quantificadas o tornam uma escolha confiável para relatórios de nível empresarial.

## Pré-requisitos
- **Java Development Kit** 16 ou mais recente instalado.
- **Aspose.Slides for Java** library (adicione via Maven, Gradle ou download direto do JAR).
- Familiaridade básica com a sintaxe Java e programação orientada a objetos.

## Configurando Aspose.Slides para Java
Para começar a usar o Aspose.Slides, inclua a biblioteca no seu sistema de build.

### Maven
Adicione a seguinte dependência ao seu `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Inclua isto no seu `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download direto
Você também pode obter o JAR mais recente em [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Aquisição de licença
- **Teste gratuito** – explore todos os recursos sem custo.  
- **Licença temporária** – avaliação estendida para projetos maiores.  
- **Licença completa** – necessária para implantações em produção.

### Inicialização e configuração básicas
A classe `Presentation` é o ponto de entrada para criar ou carregar arquivos PowerPoint.  
```java
// Initialize a new presentation
Presentation pres = new Presentation();
``` 
```java
import com.aspose.slides.Presentation;
```

## Guia de implementação
A seguir, um passo‑a‑passo para criar um gráfico de bolhas e gerenciar recursos.

## Como criar gráfico de bolhas no PowerPoint
Nesta seção você aprenderá a sequência exata de chamadas de API necessárias para gerar um gráfico de bolhas, configurar suas propriedades visuais e persistir o resultado como um arquivo PPTX. A abordagem funciona em qualquer projeto Java que inclua o Aspose.Slides e siga as melhores práticas de gerenciamento de recursos.

### Resposta direta
Crie um novo `Presentation`, chame `addChart(ChartType.Bubble, …)` no slide desejado, ajuste a escala de tamanho das bolhas com `setBubbleSizeScale(150)`, então salve usando `pres.save("Result.pptx", SaveFormat.Pptx)`. Essa sequência adiciona um gráfico de bolhas totalmente funcional em apenas algumas linhas de Java.

- **`ChartType.Bubble`** representa o tipo de gráfico de bolhas.  
- **`addChart`** insere um novo gráfico do tipo especificado em um slide.  
- **`setBubbleSizeScale`** ajusta o tamanho geral das bolhas no gráfico.  
- **`SaveFormat.Pptx`** especifica o formato de arquivo PPTX para salvamento.  

#### Implementação passo a passo
**1. Initialize presentation** – instantiate the `Presentation` object.  
```java
Presentation pres = new Presentation();
```

**2. Add bubble chart** – insert the chart at the chosen coordinates.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Bubble, 100, 100, 400, 300
);
```
- `ChartType.Bubble` indica ao Aspose.Slides que deve criar um gráfico de bolhas.  
- Os parâmetros numéricos definem a posição X/Y e a largura/altura em pontos.

**3. Configure bubble size scale** – enlarge bubbles for better visual impact.  
```java
chart.getChartData().getSeriesGroups().get_Item(0).setBubbleSizeScale(150);
```
- Definir a escala para **150 %** torna cada bolha 1,5 × maior que o padrão.

**4. Save presentation** – write the PPTX to disk.  
```java
pres.save("YOUR_OUTPUT_DIRECTORY/Result.pptx", SaveFormat.Pptx);
```

#### Dicas de solução de problemas
- Verifique as permissões de gravação para a pasta de saída.  
- Confirme que o JAR do Aspose.Slides corresponde à versão do JDK que você está usando.

## Como gerenciar recursos do PowerPoint de forma eficaz
O gerenciamento eficaz de recursos evita vazamentos de memória e mantém a pegada da JVM baixa, especialmente ao processar decks grandes ou ao executar em um ambiente de servidor. Siga o padrão abaixo para garantir que recursos nativos sejam liberados mesmo se ocorrer uma exceção.

### Resposta direta
Depois de terminar de trabalhar com um `Presentation`, sempre chame `pres.dispose()` dentro de um bloco `try‑finally`; isso libera recursos nativos e permite que a JVM recupere a memória prontamente.

- **`pres.dispose()`** libera recursos nativos usados pela apresentação.

**1. Create and modify** – work with the presentation as needed.  
```java
Presentation pres = new Presentation();
```

**2. Dispose resources** – free memory once processing is complete.  
```java
if (pres != null) pres.dispose();
```

## Aplicações práticas
Gráficos de bolhas se destacam em cenários onde três dimensões de dados precisam ser visualizadas simultaneamente:

1. **Análise de mercado** – o tamanho da bolha representa a receita enquanto os eixos X/Y mostram crescimento e participação de mercado.  
2. **Métricas de desempenho** – compare a produtividade dos funcionários (X), satisfação (Y) e impacto (tamanho).  
3. **Dados geográficos** – plote cidades com a população codificada no tamanho da bolha.  
4. **Gerenciamento de projetos** – visualize cronograma (X), custo (Y) e risco (tamanho) em um único slide.

## Considerações de desempenho
- **Uso de recursos** – libere as apresentações prontamente para manter o uso de heap baixo.  
- **Gerenciamento de memória Java** – envolva o trabalho com a apresentação em `try‑finally` para garantir a liberação mesmo em exceções.  
- **Mantenha-se atualizado** – atualize para a versão mais recente do Aspose.Slides para aproveitar otimizações de desempenho e correções de bugs.

## Perguntas frequentes

**Q: O que é Aspose.Slides para Java?**  
A: Aspose.Slides para Java é uma biblioteca autônoma que permite criar, editar e converter arquivos PowerPoint sem precisar do Microsoft Office.

**Q: Como integro o Aspose.Slides ao meu projeto Java existente?**  
A: Adicione a dependência Maven ou Gradle mostrada anteriormente, ou coloque o JAR no seu classpath, então importe `com.aspose.slides.*`.

**Q: Posso usar o Aspose.Slides para apresentações grandes?**  
A: Sim, a biblioteca manipula apresentações de até **2 GB** de forma eficiente e oferece streaming para evitar o carregamento do arquivo inteiro na memória.

**Q: Quais tipos de gráficos estão disponíveis além dos gráficos de bolhas?**  
A: Mais de **50 tipos de gráficos** são suportados, incluindo barras, linhas, pizza, radar e gráficos de cascata.

**Q: Existe suporte nativo para estilizar elementos do gráfico?**  
A: Absolutamente. Você pode personalizar cores, fontes, bordas e rótulos de dados via os objetos `ChartSeries` e `ChartTitle` do gráfico.

## Recursos
- **Documentação**: [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Download**: [Aspose.Slides Releases](https://releases.aspose.com/slides/java/)  
- **Compra**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Teste gratuito**: [Start with a Free Trial](https://releases.aspose.com/slides/java/)  
- **Licença temporária**: [Get a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Suporte**: [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

---

**Última atualização:** 2026-09-17  
**Testado com:** Aspose.Slides for Java 25.4 (jdk16)  
**Autor:** Aspose

## Tutoriais Relacionados

- [How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java create powerpoint chart using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [Create PowerPoint Chart Java – Save Presentations with Charts Using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}