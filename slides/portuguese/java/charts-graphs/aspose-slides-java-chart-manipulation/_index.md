---
date: '2026-06-08'
description: Aprenda como criar um gráfico PowerPoint em Java com Aspose.Slides, configurar
  a dependência Maven, adicionar um gráfico de colunas agrupadas e salvar como PPTX.
keywords:
- java create powerpoint chart
- maven dependency aspose slides
- chart manipulation in presentations
- java presentation library
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to java create powerpoint chart with Aspose.Slides, set up
    the Maven dependency, add a clustered column chart, and save as PPTX.
  headline: Java create powerpoint chart using Aspose.Slides
  type: TechArticle
- questions:
  - answer: Use the `ChartType` enum (e.g., `ChartType.Pie`, `ChartType.Line`) when
      calling `addChart`.
    question: How do I add other chart types?
  - answer: Yes, modify the series’ fill format or the chart’s palette via the `IChart`
      API.
    question: Can I customize chart colors?
  - answer: Verify that the output directory path is correct, exists, and is writable.
      Also ensure no other process holds a lock on the file.
    question: My presentation won’t save—what’s wrong?
  - answer: Process slides in batches, dispose of each `Presentation` after use, and
      consider increasing the JVM heap size if needed.
    question: How can I handle very large presentations efficiently?
  - answer: A free trial is available for evaluation, but a purchased license is required
      for commercial deployment.
    question: Is Aspose.Slides free for commercial projects?
  type: FAQPage
title: Java cria gráfico PowerPoint usando Aspose.Slides
url: /pt/java/charts-graphs/aspose-slides-java-chart-manipulation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java criar gráfico PowerPoint usando Aspose.Slides

## Introdução
Neste guia você **java create powerpoint chart** de forma simples com Aspose.Slides para Java. Vamos percorrer a instalação do pacote Maven ou Gradle, a inicialização de um `Presentation`, a inserção de um gráfico de colunas agrupadas, o ajuste fino da área de plotagem e, finalmente, a gravação do resultado como um arquivo PPTX. Ao final, você terá um trecho pronto para uso que funciona em qualquer projeto Java, seja para criar um relatório empresarial ou um gerador automático de slides.

**O que você aprenderá**
- Como adicionar a dependência Maven para Aspose.Slides  
- Como **java create powerpoint chart** e inserir um gráfico de colunas agrupadas  
- Como ajustar a área de plotagem (posição, tamanho, alvo de layout)  
- Como **save presentation as pptx** com a limpeza adequada de recursos  

Pronto para transformar dados brutos em slides atraentes? Vamos começar!

## Respostas Rápidas
- **Qual biblioteca eu preciso?** Aspose.Slides para Java (disponível via Maven ou Gradle).  
- **Qual tipo de gráfico é demonstrado?** Gráfico de colunas agrupadas.  
- **Como salvo o arquivo?** Chame `presentation.save("output.pptx", SaveFormat.Pptx)`.  
- **Preciso de licença?** Um teste gratuito funciona para desenvolvimento; uma licença completa é necessária para produção.  
- **Posso mudar a área de plotagem?** Sim – defina X, Y, largura, altura e escolha um tipo de alvo de layout.

## O que é java create powerpoint chart?
`java create powerpoint chart` refere‑se à geração programática de um objeto de gráfico, preenchendo‑o com dados e incorporando‑o em um slide PowerPoint usando uma biblioteca Java. Aspose.Slides abstrai o formato Open XML para que você possa focar no design visual em vez dos detalhes internos do arquivo.

## Por que adicionar um gráfico de colunas agrupadas com Aspose.Slides?
Um gráfico de colunas agrupadas é perfeito para comparar várias séries de dados lado a lado. É amplamente usado em relatórios empresariais, painéis e apresentações. Aspose.Slides oferece controle total sobre cores, marcadores, eixos e layout sem abrir o PowerPoint manualmente. Ele permite destacar tendências entre categorias, tornando os insights de dados mais claros para as partes interessadas. Com Aspose.Slides você pode ajustar programaticamente a formatação das séries, a escala dos eixos e os rótulos de dados, garantindo que o gráfico siga a identidade visual e os padrões corporativos.

## Pré‑requisitos
- **Aspose.Slides para Java** (versão 25.4 ou mais recente).  
- **JDK 16** ou superior.  
- Uma IDE como IntelliJ IDEA ou Eclipse.  
- Conhecimentos básicos de Java.

## Configurando Aspose.Slides para Java
### Maven
Adicione a dependência ao seu `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
</dependency>
```

### Gradle
Inclua a biblioteca no `build.gradle`:

```gradle
implementation 'com.aspose:aspose-slides:25.4'
```

### Download Direto
Alternativamente, faça o download da versão mais recente em [Aspose's official site](https://releases.aspose.com/slides/java/).

#### Aquisição de Licença
Use um teste gratuito ou licença temporária para testes. Adquira uma licença completa para implantações em produção.

## Inicialização Básica e Configuração
A classe `Presentation` é o ponto de entrada para criar e manipular arquivos PowerPoint. Crie uma nova classe Java e importe a classe principal:

```java
import com.aspose.slides.Presentation;
```

## Guia de Implementação
Vamos percorrer cada passo com explicações claras.

### Inicialização da Apresentação e Manipulação de Slides
#### Definição de Âncora
`Presentation` é o objeto de nível superior do Aspose.Slides que representa um arquivo PowerPoint completo na memória.  

#### Visão Geral
Primeiro, crie uma nova apresentação e obtenha o primeiro slide onde o gráfico será inserido.

**1. Criar e Inicializar uma Apresentação**

```java
Presentation presentation = new Presentation();
```

**2. Acessar o Primeiro Slide**

```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Adicionar um Gráfico de Colunas Agrupadas**

```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

> **Dica profissional:** Sempre envolva o uso da apresentação em um bloco `try‑finally` e chame `presentation.dispose()` no `finally` para liberar recursos nativos.

### Configuração da Área de Plotagem
#### Visão Geral
Ajuste fino da área de plotagem do gráfico para controlar onde os dados são visualizados dentro do slide.

**1. Definir Posição e Tamanho**

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
```

**2. Definir Tipo de Alvo de Layout**

```java
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

### Salvando a Apresentação
#### Visão Geral
Após personalizar o gráfico, persista a apresentação como um arquivo PPTX.

**1. Salvar em Arquivo**

```java
presentation.save(YOUR_OUTPUT_DIRECTORY + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

> **Aviso:** Certifique‑se de que o diretório de saída exista e que a aplicação tenha permissão de gravação; caso contrário, a operação de salvamento falhará.

## Casos de Uso Comuns
- **Relatórios Empresariais:** Incorporar tendências de vendas e KPIs financeiros.  
- **Slides Educacionais:** Visualizar resultados de experimentos ou dados estatísticos.  
- **Propostas de Projeto:** Destacar marcos e alocação de recursos.  
- **Decks de Marketing:** Mostrar desempenho de campanhas com gráficos vívidos.  
- **Planejamento de Eventos:** Exibir demografia de participantes ou divisão de agenda.

## Considerações de Desempenho
- Libere objetos `Presentation` rapidamente para evitar vazamentos de memória.  
- Para conjuntos de dados grandes, preencha as séries do gráfico incrementalmente em vez de carregar tudo de uma vez.  
- Use as ferramentas de profiling nativas do Java para monitorar o uso de heap durante a geração do gráfico.

## Perguntas Frequentes

**P: Como adiciono outros tipos de gráfico?**  
R: Use o enum `ChartType` (por exemplo, `ChartType.Pie`, `ChartType.Line`) ao chamar `addChart`.

**P: Posso personalizar as cores do gráfico?**  
R: Sim, modifique o formato de preenchimento da série ou a paleta do gráfico via API `IChart`.

**P: Minha apresentação não salva – o que está errado?**  
R: Verifique se o caminho do diretório de saída está correto, existe e tem permissão de escrita. Também assegure que nenhum outro processo esteja bloqueando o arquivo.

**P: Como lidar com apresentações muito grandes de forma eficiente?**  
R: Processar os slides em lotes, liberar cada `Presentation` após o uso e considerar aumentar o tamanho do heap da JVM, se necessário.

**P: Aspose.Slides é gratuito para projetos comerciais?**  
R: Um teste gratuito está disponível para avaliação, mas uma licença comprada é necessária para implantação comercial.

## Recursos
- [Documentation](https://reference.aspose.com/slides/java/)
- [Download Aspose.Slides](https://releases.aspose.com/slides/java/)
- [Purchase License](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/slides/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/slides/11)

Comece a criar apresentações visualmente impressionantes com Aspose.Slides para Java hoje mesmo!

---

**Última atualização:** 2026-06-08  
**Testado com:** Aspose.Slides para Java 25.4 (JDK 16)  
**Autor:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

## Tutoriais Relacionados

- [How to create clustered column chart in Java with Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [How to Add and Configure Charts in Presentations Using Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Create Animated PowerPoint Java – Animate PowerPoint Charts with Aspose.Slides](/slides/java/animations-transitions/animate-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}