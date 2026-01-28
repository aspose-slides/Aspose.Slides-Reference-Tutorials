---
date: '2026-01-17'
description: Aprenda a criar gráficos em Java usando Aspose.Slides, adicionar um gráfico
  de colunas agrupadas e salvar a apresentação como pptx. Guia passo a passo para
  desenvolvedores Java.
keywords:
- Aspose.Slides for Java
- chart manipulation in presentations
- Java presentation library
title: Como criar gráfico em Java com Aspose.Slides para Java
url: /pt/java/charts-graphs/aspose-slides-java-chart-manipulation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como criar gráfico em Java com Aspose.Slides para Java

## Introdução
Criar uma experiência de **create chart in java** que pareça profissional não precisa ser um problema. Com **Aspose.Slides for Java**, você pode adicionar, estilizar e salvar gráficos programaticamente — como um gráfico de colunas agrupadas — diretamente dentro de apresentações PowerPoint. Neste tutorial, percorreremos a configuração da biblioteca, a inicialização de uma apresentação, a inserção de um gráfico de colunas agrupadas, o ajuste da área de plotagem e, finalmente, a gravação do arquivo como PPTX. Ao final, você terá um trecho de código reutilizável que pode inserir em qualquer projeto Java.

**O que você aprenderá**
- Como configurar a dependência Aspose.Slides Maven ou Gradle  
- Como **create chart in java** e adicionar um gráfico de colunas agrupadas  
- Como configurar a área de plotagem (posição, tamanho, layout)  
- Como **save presentation as pptx** com o tratamento adequado de recursos  

Pronto para fazer seus dados falarem visualmente? Vamos começar!

## Respostas rápidas
- **Qual biblioteca eu preciso?** Aspose.Slides for Java (Maven/Gradle).  
- **Qual tipo de gráfico é demonstrado?** Gráfico de colunas agrupadas.  
- **Como salvo o arquivo?** Use `presentation.save(..., SaveFormat.Pptx)`.  
- **Preciso de licença?** Uma avaliação gratuita funciona para desenvolvimento; uma licença completa é necessária para produção.  
- **Posso alterar a área de plotagem?** Sim, você pode definir X, Y, largura, altura e o tipo de alvo de layout.

## O que é create chart in java?
Criar um gráfico em Java significa usar uma biblioteca para gerar objetos de gráfico, preenchê‑los com dados e incorporá‑los em um documento — aqui, um slide de PowerPoint. Aspose.Slides abstrai os detalhes de baixo nível do Office Open XML, permitindo que você se concentre no resultado visual.

## Por que adicionar gráfico de colunas agrupadas com Aspose.Slides?
Um gráfico de colunas agrupadas é perfeito para comparar várias séries de dados lado a lado. É amplamente usado em relatórios de negócios, painéis e apresentações. Aspose.Slides oferece controle total sobre cores, marcadores, eixos e layout sem abrir o PowerPoint manualmente.

## Pré-requisitos
- Biblioteca **Aspose.Slides for Java** (versão 25.4 ou mais recente).  
- **JDK 16** (ou superior) instalado.  
- Uma IDE como IntelliJ IDEA ou Eclipse.  
- Familiaridade básica com a sintaxe Java.

## Configurando Aspose.Slides para Java
### Maven
Add the dependency to your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Include the library in `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download direto
Alternatively, download the latest release from [Aspose's official site](https://releases.aspose.com/slides/java/).

#### Aquisição de licença
Use uma avaliação gratuita ou licença temporária para testes. Compre uma licença completa para implantações em produção.

### Inicialização e Configuração Básicas
Start a new Java class and import the core class:

```java
import com.aspose.slides.Presentation;
```

## Guia de Implementação
Percorreremos cada passo com explicações claras.

### Inicialização da Apresentação e Manipulação de Slides
#### Visão geral
First, create a fresh presentation and grab the first slide where the chart will live.

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
#### Visão geral
Fine‑tune the chart’s plot area to control where the data visualizes within the slide.

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
#### Visão geral
After customizing the chart, persist the presentation as a PPTX file.

**1. Salvar em Arquivo**

```java
presentation.save(YOUR_OUTPUT_DIRECTORY + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

> **Aviso:** Certifique‑se de que o diretório de saída exista e que a aplicação tenha permissão de gravação; caso contrário, a operação de salvamento falhará.

## Casos de Uso Comuns
- **Relatórios de Negócios:** Incorporar tendências de vendas e KPIs financeiros.  
- **Slides Educacionais:** Visualizar resultados de experimentos ou dados estatísticos.  
- **Propostas de Projeto:** Destacar marcos e alocação de recursos.  
- **Apresentações de Marketing:** Mostrar o desempenho de campanhas com gráficos vívidos.  
- **Planejamento de Eventos:** Exibir demografia dos participantes ou detalhamento da agenda.  

## Considerações de Desempenho
- Libere objetos `Presentation` prontamente para evitar vazamentos de memória.  
- Para conjuntos de dados grandes, preencha as séries do gráfico incrementalmente ao invés de carregar tudo de uma vez.  
- Use as ferramentas de profiling integradas ao Java para monitorar o uso de heap durante a geração do gráfico.  

## Perguntas Frequentes

**Q: Como adiciono outros tipos de gráfico?**  
A: Use o enum `ChartType` (por exemplo, `ChartType.Pie`, `ChartType.Line`) ao chamar `addChart`.

**Q: Posso personalizar as cores do gráfico?**  
A: Sim, modifique o formato de preenchimento da série ou a paleta do gráfico via API `IChart`.

**Q: Minha apresentação não salva — o que há de errado?**  
A: Verifique se `YOUR_OUTPUT_DIRECTORY` está correto, existe e tem permissão de escrita. Também verifique se há bloqueios de arquivo persistentes.

**Q: Como posso lidar com apresentações muito grandes de forma eficiente?**  
A: Processar slides em lotes, liberar cada `Presentation` após o uso e considerar aumentar o tamanho do heap da JVM, se necessário.

**Q: O Aspose.Slides é gratuito para projetos comerciais?**  
A: Uma avaliação gratuita está disponível para avaliação, mas uma licença comprada é necessária para implantação comercial.

## Recursos
- [Documentation](https://reference.aspose.com/slides/java/)
- [Download Aspose.Slides](https://releases.aspose.com/slides/java/)
- [Purchase License](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/slides/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/slides/11)

Comece a criar apresentações visualmente impressionantes com Aspose.Slides para Java hoje!

---

**Última atualização:** 2026-01-17  
**Testado com:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autor:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
