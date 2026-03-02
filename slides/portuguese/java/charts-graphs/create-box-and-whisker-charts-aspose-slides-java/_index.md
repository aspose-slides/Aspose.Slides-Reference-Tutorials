---
date: '2026-03-02'
description: Aprenda como criar box plot em Java, adicionar gráfico ao slide e gerar
  gráfico de caixa e bigodes no PowerPoint usando Aspose.Slides para Java.
keywords:
- Aspose.Slides for Java
- Box-and-Whisker Charts
- PowerPoint Java
title: Criar box plot em Java usando Aspose.Slides para PowerPoint
url: /pt/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como Criar Gráficos de Caixa e Bigodes no PowerPoint Usando Aspose.Slides para Java

Neste guia você **criará box plot java** com Aspose.Slides e, em seguida, incorporará o gráfico diretamente em um slide do PowerPoint. Criar apresentações de dados visualmente atraentes é crucial no mundo orientado a dados de hoje, e os gráficos são ferramentas essenciais para esse propósito. Se você deseja gerar gráficos de caixa e bigodes dentro do PowerPoint usando Java, a biblioteca Aspose.Slides oferece uma solução robusta. Este tutorial o conduzirá pela criação e configuração desses gráficos de forma fluida com Aspose.Slides para Java.

## O que você aprenderá

- Configurar seu ambiente para Aspose.Slides para Java
- Etapas para **adicionar gráfico ao slide** e gerar um gráfico de caixa‑bigodes no PowerPoint usando Java
- Melhores práticas para otimizar o desempenho ao trabalhar com Aspose.Slides
- Aplicações reais de gráficos de caixa‑e‑bigodes

## Respostas Rápidas
- **Qual biblioteca cria um box plot em Java?** Aspose.Slides para Java.  
- **Qual tipo de gráfico é usado?** `ChartType.BoxAndWhisker`.  
- **Preciso de licença?** Um teste gratuito funciona para avaliação; uma licença comercial é necessária para produção.  
- **Posso adicionar múltiplas séries?** Sim – repita o bloco de criação de série para cada conjunto de dados.  
- **Qual é o formato do arquivo final?** PowerPoint PPTX (`SaveFormat.Pptx`).

## Pré‑requisitos

Para seguir este tutorial, certifique‑se de que você tem:

- **Java Development Kit (JDK)**: JDK 8 ou superior deve estar instalado.  
- **Aspose.Slides para Java Library**: Essencial para manipular apresentações PowerPoint em Java.  
- **IDE**: Um Ambiente de Desenvolvimento Integrado como IntelliJ IDEA ou Eclipse para escrever e executar seu código.

## Configurando Aspose.Slides para Java

Para usar Aspose.Slides, adicione‑o como dependência. Você pode gerenciar isso via Maven, Gradle ou download direto.

### Maven

Adicione a seguinte dependência no seu `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

No seu `build.gradle`, inclua:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download Direto

Alternativamente, faça o download da versão mais recente em [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Aquisição de Licença

- **Teste Gratuito**: Comece com um teste gratuito para explorar os recursos.  
- **Licença Temporária**: Obtenha uma licença temporária para fins de avaliação.  
- **Compra**: Para funcionalidade completa, considere adquirir uma licença.

Para inicializar Aspose.Slides, certifique‑se de que a biblioteca está no seu classpath e configure quaisquer requisitos de licenciamento conforme necessário.

## Guia de Implementação

Agora vamos mergulhar no código passo a passo. Cada bloco é explicado antes do snippet para que você saiba exatamente o que ele faz.

### O que é um box plot e por que usá‑lo em Java?

Um gráfico de caixa‑e‑bigodes (frequentemente chamado de *box plot*) visualiza a distribuição dos dados — mediana, quartis e outliers — de forma compacta. Em Java, gerar esse gráfico programaticamente permite incorporar insights estatísticos diretamente em decks PowerPoint, eliminando a criação manual de gráficos.

### Por que adicionar gráfico ao slide com Aspose.Slides?

Aspose.Slides abstrai os detalhes de baixo nível do OpenXML, oferecendo uma API fluente para criar, estilizar e exportar gráficos. Isso significa que você pode automatizar a geração de relatórios, produzir branding consistente e integrar gráficos em fluxos de trabalho Java maiores.

### Etapa 1: Criar ou Abrir uma Apresentação

Primeiro, abra um PPTX existente ou inicie um novo:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **Dica:** Se o arquivo não existir, Aspose.Slides criará uma nova apresentação em branco para você.

### Etapa 2: Adicionar um Gráfico de Caixa‑e‑Bigodes ao Slide

Posicione o gráfico onde precisar, especificando a posição e o tamanho (em pontos):

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### Etapa 3: Limpar Dados Existentes

Antes de inserir novos dados, apague quaisquer categorias ou séries de espaço reservado:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### Etapa 4: Configurar Categorias

Adicione as categorias (rótulos do eixo X) que aparecerão sob cada caixa:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **Observação:** Ajuste o texto do rótulo para corresponder ao domínio dos seus dados (por exemplo, “Q1”, “Produto A”).

### Etapa 5: Criar e Personalizar a Série

Agora crie uma série, defina opções visuais e alimente os pontos numéricos:

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
series.setQuartileMethod(QuartileMethodType.Exclusive); // Set quartile method to Exclusive
series.setShowMeanLine(true); // Display mean line
series.setShowMeanMarkers(true); // Show markers for mean values
series.setShowInnerPoints(true); // Display inner points on the chart
series.setShowOutlierPoints(true); // Show outlier points on the chart

int[] data = {15, 41, 16, 10, 23, 16}; // Sample data points
for (int i = 0; i < data.length; i++) {
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(
        wb.getCell(0, "B" + (i + 1), data[i]));
}
```

Você pode substituir o array `int[] data` por valores lidos de um banco de dados, arquivo CSV ou qualquer outra fonte.

### Etapa 6: Salvar a Apresentação

Persista as alterações em um novo arquivo PPTX:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### Etapa 7: Liberar Recursos

Sempre descarte o objeto `Presentation` para liberar recursos nativos:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## Aplicações Práticas

Gráficos de caixa‑e‑bigodes são indispensáveis em análise estatística e apresentação de dados. Aqui estão alguns cenários onde eles se destacam:

1. **Análise Financeira** – Visualizar a distribuição de receitas por regiões.  
2. **Controle de Qualidade** – Identificar outliers em medições de fabricação.  
3. **Pesquisa Acadêmica** – Mostrar a variabilidade de resultados experimentais.  
4. **Pesquisa de Mercado** – Comparar desempenho de produtos entre demografias.

Integrar esses gráficos em apresentações PowerPoint permite que as partes interessadas compreendam dados complexos de forma rápida.

## Considerações de Desempenho

Ao trabalhar com Aspose.Slides em Java, tenha em mente estas dicas:

- **Gerenciamento de Memória** – Descarte objetos `Presentation` prontamente.  
- **Manipulação de Dados** – Carregue apenas os dados necessários; evite inserir conjuntos de dados massivos diretamente na planilha do gráfico.  
- **Carregamento Preguiçoso** – Se gerar muitas slides, considere criar gráficos apenas para aqueles que serão exibidos.

## Problemas Comuns e Soluções

| Problema | Causa | Solução |
|----------|-------|----------|
| **Gráfico aparece em branco** | Células de dados não preenchidas corretamente | Verifique se `wb.getCell` referencia a linha/coluna corretas e se o valor não é `null`. |
| **Outliers não são exibidos** | `setShowOutlierPoints` definido como `false` | Certifique‑se de chamar `series.setShowOutlierPoints(true)`. |
| **Vazamento de memória** | Apresentação não descartada | Sempre envolva o uso em try/finally e chame `dispose()`. |
| **Quartis incorretos** | Uso do método padrão `Inclusive` | Troque para `Exclusive` via `setQuartileMethod(QuartileMethodType.Exclusive)`. |

## Perguntas Frequentes

**Q1: O que é um gráfico de caixa‑e‑bigodes?**  
Um gráfico de caixa‑e‑bigodes, também conhecido como box plot, exibe a distribuição dos dados com base em cinco estatísticas resumidas: mínimo, primeiro quartil, mediana, terceiro quartil e máximo, além de quaisquer outliers.

**Q2: Posso personalizar a aparência do gráfico de caixa‑e‑bigodes?**  
Sim. Aspose.Slides permite alterar cores, estilos de linha, formas de marcadores e até adicionar rótulos de dados através da API de formatação do gráfico.

**Q3: É possível lidar com múltiplas séries em um único gráfico?**  
Absolutamente. Repita o bloco de criação de série para cada conjunto de dados que desejar visualizar.

**Q4: Como resolvo problemas de dados que não são exibidos corretamente?**  
Garanta que os dados estejam escritos corretamente nas células da planilha e que propriedades de visibilidade como `setShowMeanLine` estejam habilitadas.

**Q5: Onde posso obter suporte se encontrar problemas?**  
Visite o [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) para ajuda da comunidade ou consulte a documentação oficial.

**Q6: O Aspose.Slides suporta outros tipos de gráfico?**  
Sim, ele suporta linha, barra, pizza, dispersão, radar e muitos outros tipos de gráfico.

**Q7: Posso gerar gráficos em um ambiente de servidor sem interface gráfica?**  
A biblioteca funciona totalmente em cenários server‑side; nenhuma UI é necessária.

## Recursos

- **Documentação**: Explore referências detalhadas da API em [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Download**: Acesse as versões do Aspose.Slides [aqui](https://releases.aspose.com/slides/java/)  
- **Compra**: Adquira uma licença para desbloquear todos os recursos em [Aspose Purchase](https://purchase.aspose.com/buy)  
- **Teste Gratuito & Licença Temporária**: Comece com um teste gratuito ou solicite uma licença temporária [aqui](https://releases.aspose.com/slides/java/)

Seguindo este guia, você está pronto para gerar programaticamente gráficos de caixa‑e‑bigodes perspicazes em suas aplicações Java e incorporá‑los diretamente em apresentações PowerPoint. Boa codificação!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última atualização:** 2026-03-02  
**Testado com:** Aspose.Slides 25.4 (classificador JDK 16)  
**Autor:** Aspose