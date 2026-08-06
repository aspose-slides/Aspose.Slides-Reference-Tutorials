---
date: '2026-08-06'
description: Aprenda como alterar a cor da fonte da legenda e modificar o texto da
  legenda do gráfico usando o Aspose.Slides for Java. Siga instruções passo a passo
  para personalizar rapidamente as legendas dos gráficos.
keywords:
- customize chart legends in Aspose.Slides Java
- Aspose.Slides for Java legend customization
- Java presentation chart styling
lastmod: '2026-08-06'
og_description: Aprenda como alterar a cor da fonte da legenda e modificar o texto
  da legenda do gráfico com o Aspose.Slides for Java. Este guia mostra as etapas exatas
  e as melhores práticas.
og_image_alt: 'Developer guide: change legend font color in Aspose.Slides for Java'
og_title: Como alterar a cor da fonte da legenda no Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  headline: How to change legend font color in Aspose.Slides for Java
  type: TechArticle
- description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  name: How to change legend font color in Aspose.Slides for Java
  steps:
  - name: Initialize Aspose.Slides in your Java application.
    text: Initialize Aspose.Slides in your Java application.
  - name: Load an existing presentation or create a new one.
    text: Load an existing presentation or create a new one.
  - name: '**Load the presentation:**'
    text: '**Load the presentation:**'
  - name: '**Add a clustered column chart:**'
    text: '**Add a clustered column chart:**'
  - name: '**Access legend entry text format:**'
    text: '**Access legend entry text format:**'
  - name: '**Set bold and italic styles with a specific height:**'
    text: '**Set bold and italic styles with a specific height:**'
  - name: '**Change fill type to solid color for better visibility:**'
    text: '**Change fill type to solid color for better visibility:**'
  - name: '**Save your changes:**'
    text: '**Save your changes:**'
  - name: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
    text: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
  - name: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
    text: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
  type: HowTo
- questions:
  - answer: No, the color change is preserved in all export formats supported by Aspose.Slides,
      including PDF and PPTX.
    question: Does changing the legend font color affect exported PDF files?
  - answer: Yes – set `FillType.Gradient` and configure the gradient stops via `getGradientStyle()`.
    question: Can I use a gradient instead of a solid color?
  - answer: A chart can have up to 256 legend entries, limited only by the number
      of data series you add.
    question: How many legend entries can a chart have?
  type: FAQPage
tags:
- change legend font color
- Aspose.Slides
- Java chart customization
- presentation styling
title: Como alterar a cor da fonte da legenda no Aspose.Slides for Java
url: /pt/java/charts-graphs/customize-chart-legends-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como alterar a cor da fonte da legenda no Aspose.Slides para Java

## Introdução
Se você precisar **alterar a cor da fonte da legenda** em um gráfico, o Aspose.Slides para Java oferece controle total sobre cada entrada da legenda. Este tutorial orienta você na personalização dos estilos de texto da legenda, aplicação de fontes em negrito ou itálico e definição de cores sólidas para que seus gráficos tenham exatamente a aparência desejada. Ao final deste guia, você será capaz de modificar o texto da legenda do gráfico com confiança e integrar as alterações em qualquer apresentação existente.

**O que você aprenderá**
- Como **alterar a cor da fonte da legenda** programaticamente.
- Formas de **modificar o texto da legenda do gráfico** como negrito, itálico e tamanho.
- Dicas para aplicar as alterações em vários gráficos em uma única apresentação.
- Como integrar essas etapas em um fluxo de automação maior.

## Respostas rápidas
- **Posso alterar a cor de uma única entrada da legenda?** Sim – acesse a entrada pelo seu índice e defina o formato de preenchimento como cor sólida.  
- **Preciso de licença para usar essas APIs?** Uma licença temporária ou paga é necessária para produção; um teste gratuito funciona para avaliação.  
- **Qual versão do Java é suportada?** Aspose.Slides para Java 25.4+ funciona com JDK 16 e versões mais recentes.  
- **As alterações afetarão outros elementos do gráfico?** Não, a formatação da legenda é isolada da estilização das séries de dados.  
- **É possível processamento em lote?** Absolutamente – percorra slides e gráficos para aplicar as mesmas configurações de legenda em todo o deck.

## O que é alterar a cor da fonte da legenda?
`change legend font color` refere‑se à operação programática de definir a cor do texto das entradas da legenda de um gráfico usando a API Aspose.Slides. Essa operação atualiza a aparência visual da legenda sem alterar os dados subjacentes.

## Por que personalizar as legendas dos gráficos?
Aspose.Slides suporta **mais de 50 formatos de entrada e saída** e pode lidar com apresentações com **mais de 500 slides** mantendo o uso de memória abaixo de 200 MB. Personalizar as legendas melhora a legibilidade, reforça as cores da marca e garante que pontos de dados importantes se destaquem — especialmente em decks corporativos ou educacionais onde a clareza visual impulsiona a tomada de decisão.

## Pré‑requisitos
- Biblioteca **Aspose.Slides para Java** (Versão 25.4 ou posterior).  
- Java Development Kit (JDK) 16 ou superior.  
- Uma IDE como IntelliJ IDEA, Eclipse ou NetBeans.  
- Maven ou Gradle para gerenciamento de dependências.  
- Conhecimento básico de programação Java.

## Configurando o Aspose.Slides para Java
Para começar a personalizar as legendas dos seus gráficos, adicione a biblioteca ao seu projeto usando um dos métodos abaixo.

### Maven
Adicione a dependência a seguir ao seu arquivo `pom.xml`:
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
Você também pode obter o JAR mais recente em [Lançamentos do Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

#### Etapas para obtenção de licença
- **Teste gratuito:** Comece com um teste gratuito para explorar os recursos do Aspose.Slides.  
- **Licença temporária:** Solicite uma licença temporária para avaliação prolongada.  
- **Compra:** Para acesso total, considere adquirir uma licença em [Aspose Purchase](https://purchase.aspose.com/buy).

#### Inicialização básica e configuração
Após adicionar a biblioteca ao seu projeto:
1. Inicialize o Aspose.Slides em sua aplicação Java.  
2. Carregue uma apresentação existente ou crie uma nova.

## Como alterar a cor da fonte da legenda?
Para mudar a cor da fonte da legenda, carregue a apresentação, recupere o objeto do gráfico, obtenha sua legenda e então modifique o formato de texto de cada entrada da legenda definindo o tipo de preenchimento como sólido e especificando a cor desejada. Esta única operação atualiza a cor do texto da legenda instantaneamente sem precisar redesenhar todo o slide. Exemplo: `legendEntry.getTextFormat().getFillFormat().setFillType(FillType.Solid); legendEntry.getTextFormat().getFillFormat().setSolidFillColor(Color.RED);` Essa abordagem funciona para qualquer tipo de gráfico e não requer re‑renderização do slide inteiro.

### Acessando e modificando propriedades de texto da legenda

#### Definição de âncora
A interface `IChart` representa um objeto de gráfico em um slide, e seu método `getLegend()` retorna um objeto `ILegend` que contém uma coleção de itens `ILegendEntry`.

#### Adicionando um gráfico à sua apresentação
1. **Carregue a apresentação:**  
   ```java
   Presentation pres = new Presentation(dataDir + "/test.pptx");
   ```  

2. **Adicione um gráfico de colunas agrupadas:**  
   ```java
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 50, 50, 600, 400);
   ```  

#### Personalizando propriedades da fonte
3. **Acesse o formato de texto da entrada da legenda:**  
   Aqui, `legendEntry` é um objeto `ILegendEntry` que representa uma única entrada na legenda do gráfico.  
   ```java
   IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
   ```  

4. **Defina estilos em negrito e itálico com uma altura específica:**  
   ```java
   tf.getPortionFormat().setFontBold(NullableBool.True);
   tf.getPortionFormat().setFontHeight(20);
   tf.getPortionFormat().setFontItalic(NullableBool.True);
   ```  

5. **Altere o tipo de preenchimento para cor sólida para melhor visibilidade:**  
   ```java
   tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
   tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
   ```  

#### Salvando a apresentação
6. **Salve suas alterações:**  
   ```java
   pres.save(outputDir + "/output.pptx", SaveFormat.Pptx);
   ```  

### Armadilhas comuns e solução de problemas
- Verifique se o índice da entrada da legenda corresponde à ordem das séries no seu gráfico.  
- Certifique‑se de que está usando uma versão da biblioteca que suporta `setSolidFillColor` (disponível desde a versão 20.9).  

## Aplicações práticas
Personalizar o texto da legenda é útil em diversos cenários reais:

1. **Apresentações corporativas:** Alinhe as cores da legenda com a identidade visual da empresa para um aspecto profissional.  
2. **Materiais educacionais:** Destaque séries de dados importantes usando cores de legenda contrastantes.  
3. **Decks de marketing:** Realce métricas de desempenho com legendas em negrito e coloridas para captar a atenção dos stakeholders.  

Você também pode automatizar atualizações de legenda extraindo valores de cor de um banco de dados ou arquivo de configuração.

## Considerações de desempenho
Ao processar decks grandes, tenha em mente estas dicas:

- **Gerenciamento eficiente de memória:** Chame `presentation.dispose()` após salvar para liberar recursos nativos.  
- **Carregue apenas os slides necessários:** Use `Presentation.load(String path, LoadOptions options)` com `LoadOptions.setLoadOnlySlideIds()` se precisar de um subconjunto.  
- **Processamento em lote:** Agrupe atualizações de legenda por slide para reduzir o número de chamadas de API e melhorar o throughput.

## Conclusão
Agora você sabe como **alterar a cor da fonte da legenda** e **modificar o texto da legenda do gráfico** usando o Aspose.Slides para Java. Essas personalizações aumentam a clareza visual e ajudam a transmitir os dados de forma mais eficaz. Experimente diferentes fontes, tamanhos e cores para combinar com o guia de estilo da sua apresentação e explore outros recursos de estilização de gráficos para criar decks verdadeiramente profissionais.

**Próximos passos**
- Tente aplicar o mesmo estilo de legenda a gráficos de pizza e de linha.  
- Combine a personalização da legenda com a formatação de rótulos de dados para um gráfico totalmente alinhado à marca.  

Pronto para elevar suas apresentações? Implemente as etapas acima e veja a diferença instantaneamente!

## Seção de Perguntas Frequentes
1. **Como altero a cor do texto de uma entrada da legenda?**  
   Use `getFillFormat().setFillType(FillType.Solid)` e depois `setSolidFillColor(Color.SUA_COR)` no formato de texto da entrada da legenda.

2. **Posso aplicar essas alterações a todas as legendas de uma apresentação?**  
   Sim – itere por cada slide, localize cada gráfico e atualize suas entradas de legenda dentro de um loop.

3. **É possível ajustar dinamicamente o tamanho da fonte com base no comprimento do texto?**  
   Você pode calcular o tamanho necessário com `TextFrame.getTextFrameFormat().getFontHeight()` e defini‑lo via `setFontHeight(double)`.

4. **E se eu encontrar problemas com a indexação das entradas da legenda?**  
   Verifique se o índice usado corresponde à ordem das séries; lembre‑se de que os índices começam em zero.

5. **Onde encontro mais exemplos do Aspose.Slides?**  
   Explore a [Documentação da Aspose](https://reference.aspose.com/slides/java/) para guias abrangentes e referências de API.

**Perguntas e Respostas Adicionais**

**P: Alterar a cor da fonte da legenda afeta arquivos PDF exportados?**  
R: Não, a alteração de cor é preservada em todos os formatos de exportação suportados pelo Aspose.Slides, incluindo PDF e PPTX.

**P: Posso usar um gradiente em vez de uma cor sólida?**  
R: Sim – defina `FillType.Gradient` e configure as paradas do gradiente via `getGradientStyle()`.

**P: Quantas entradas de legenda um gráfico pode ter?**  
R: Um gráfico pode ter até 256 entradas de legenda, limitado apenas pelo número de séries de dados que você adicionar.

## Recursos
- **Documentação:** Guia completo sobre o uso dos recursos do Aspose.Slides ([Link](https://reference.aspose.com/slides/java/)).  
- **Download:** Acesse a versão mais recente do Aspose.Slides para Java ([Link](https://releases.aspose.com/slides/java/)).  
- **Compra:** Adquira uma licença para desbloquear todas as funcionalidades ([Link](https://purchase.aspose.com/buy)).  
- **Teste gratuito & licença temporária:** Comece com testes gratuitos e solicite licenças temporárias ([Link de Teste Gratuito](https://releases.aspose.com/slides/java/), [Link de Licença Temporária](https://purchase.aspose.com/temporary-license/)).  
- **Suporte:** Obtenha ajuda da comunidade no fórum de suporte da Aspose ([Link](https://forum.aspose.com/c/slides/11)).

---

**Última atualização:** 2026-08-06  
**Testado com:** Aspose.Slides para Java 25.4  
**Autor:** Aspose

## Tutoriais Relacionados

- [Aprimorando Gráficos do PowerPoint: Personalização de Fonte e Eixo com Aspose.Slides para Java](/slides/java/charts-graphs/enhance-powerpoint-charts-aspose-slides-java/)
- [Aspose.Slides para Java: Guia de Quadros de Texto Dinâmicos & Personalização de Fonte](/slides/java/shapes-text-frames/aspose-slides-java-dynamic-text-frames-fonts/)
- [Animando Gráficos no PowerPoint Usando Aspose.Slides para Java – Guia Passo a Passo](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}