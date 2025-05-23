---
"date": "2025-04-17"
"description": "Aprenda a criar, personalizar e salvar gráficos com rótulos de porcentagem em apresentações Java usando o Aspose.Slides. Aprimore suas habilidades de apresentação hoje mesmo!"
"title": "Crie e personalize gráficos em apresentações Java usando Aspose.Slides"
"url": "/pt/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crie e personalize gráficos em apresentações Java usando Aspose.Slides

## Introdução
Criar apresentações atraentes geralmente envolve mais do que apenas texto; requer gráficos dinâmicos que transmitam informações de forma eficaz. Se você busca aprimorar suas apresentações em Java com recursos gráficos sofisticados usando o Aspose.Slides, este tutorial é para você. Guiaremos você na criação de uma apresentação, adicionando e configurando gráficos, calculando totais, exibindo rótulos de porcentagem e salvando seu trabalho — tudo em apenas algumas etapas fáceis.

**O que você aprenderá:**
- Como criar e personalizar apresentações com gráficos usando Aspose.Slides para Java
- Calculando totais de categorias em gráficos
- Exibindo dados como rótulos de porcentagem em gráficos
- Salvando apresentações com recursos de gráficos aprimorados

Vamos analisar os pré-requisitos necessários antes de começar.

## Pré-requisitos
Para seguir este tutorial, certifique-se de ter o seguinte:

- **Kit de Desenvolvimento Java (JDK)**: Versão 8 ou superior.
- **IDE**: Como IntelliJ IDEA, Eclipse ou qualquer IDE com suporte a Java.
- **Biblioteca Aspose.Slides para Java**: Isso é crucial para lidar com recursos de apresentação.

### Bibliotecas e versões necessárias
Você precisará do Aspose.Slides para Java. Veja como incluí-lo no seu projeto:

**Especialista:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativamente, você pode baixar a versão mais recente diretamente de [Lançamentos do Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

### Configuração do ambiente
Certifique-se de que seu ambiente de desenvolvimento esteja configurado para usar o JDK 8 ou posterior e que seu IDE esteja configurado para gerenciar dependências usando Maven ou Gradle.

**Aquisição de licença:**
- **Teste grátis**: Acesse recursos básicos para fins de teste.
- **Licença Temporária**: Teste recursos avançados sem limitações de avaliação.
- **Comprar**:Para uso comercial de longo prazo, considere comprar uma licença.

## Configurando o Aspose.Slides para Java
Comece configurando a biblioteca Aspose.Slides no seu projeto Java. Veja como inicializá-la e configurá-la:

1. Adicione a dependência via Maven ou Gradle, conforme mostrado acima.
2. Importe os pacotes Aspose.Slides necessários:
   ```java
   import com.aspose.slides.*;
   ```

3. Inicializar um novo `Presentation` exemplo:
   ```java
   Presentation presentation = new Presentation();
   ```

Esta configuração permitirá que você comece a criar apresentações programaticamente.

## Guia de Implementação

### Crie e personalize gráficos em sua apresentação

#### Visão geral
Criar um gráfico envolve inicializar sua apresentação, acessar slides e adicionar um gráfico com atributos específicos, como tipo, posição e tamanho.

**Passos:**
1. **Criar instância de apresentação**: Comece criando uma instância do `Presentation` aula.
2. **Slide de acesso**: Recupere o primeiro slide usando `get_Item(0)`.
3. **Adicionar gráfico**: Usar `addChart()` para adicionar um gráfico de colunas empilhadas em coordenadas especificadas com dimensões definidas.

```java
// Recurso: Criar uma apresentação com gráfico
import com.aspose.slides.*;

try {
    Presentation presentation = new Presentation();
    ISlide slide = presentation.getSlides().get_Item(0);
    
    IChart chart = slide.getShapes().addChart(
        ChartType.StackedColumn,
        20, 20, 400, 400
    );
} finally {
    if (presentation != null) presentation.dispose();
}
```

### Calcular totais para categorias

#### Visão geral
O cálculo dos totais das categorias envolve a iteração por cada série no gráfico para somar os valores por categoria.

**Passos:**
1. **Inicializar Array**: Crie uma matriz para armazenar valores totais.
2. **Iterar por categorias e séries**: Use loops aninhados para acumular totais para cada categoria de todas as séries.

```java
// Recurso: Calcular totais para categorias em um gráfico
import com.aspose.slides.*;

public void calculateCategoryTotals(IChart chart, double[] total_for_Cat) {
    for (int k = 0; k < chart.getChartData().getCategories().size(); k++) {
        IChartCategory cat = chart.getChartData().getCategories().get_Item(k);
        total_for_Cat[k] = 0;

        for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
            double value = (double) (
                chart.getChartData().getSeries().get_Item(i).
                    getDataPoints().get_Item(k).
                    getValue().getData());
            total_for_Cat[k] += value;
        }
    }
}
```

### Exibir dados como rótulos de porcentagem em um gráfico

#### Visão geral
Este recurso se concentra na configuração de rótulos de dados para exibir valores como porcentagens, proporcionando clareza na visualização.

**Passos:**
1. **Configurar rótulos de série**: Configure propriedades de rótulo, como tamanho da fonte e visibilidade das chaves de legenda.
2. **Calcular porcentagens**: Calcular porcentagem para cada ponto de dados com base no valor total da categoria.
3. **Definir texto do rótulo**: Formate rótulos para mostrar porcentagens com duas casas decimais.

```java
// Recurso: Exibir dados como rótulos de porcentagem em um gráfico
import com.aspose.slides.*;

public void displayPercentageLabels(IChart chart, double[] total_for_Cat) {
    for (int x = 0; x < chart.getChartData().getSeries().size(); x++) {
        IChartSeries series = chart.getChartData().getSeries().get_Item(x);
        
        series.getLabels().getDefaultDataLabelFormat().setShowLegendKey(false);

        for (int j = 0; j < series.getDataPoints().size(); j++) {
            IDataLabel lbl = series.getDataPoints().get_Item(j).getLabel();
            double dataPontPercent = (double) (
                series.getDataPoints().get_Item(j).
                    getValue().getData()) / total_for_Cat[j] * 100;

            IPortion port = new Portion();
            port.setText(String.format("{0:F2} %%", dataPontPercent));
            port.getPortionFormat().setFontHeight(8f);
            
            lbl.getTextFrameForOverriding().setText("");
            IParagraph para = lbl.getTextFrameForOverriding().getParagraphs().get_Item(0);
            para.getPortions().add(port);

            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowPercentage(false);
            lbl.getDataLabelFormat().setShowLegendKey(false);
            lbl.getDataLabelFormat().setShowCategoryName(false);
            lbl.getDataLabelFormat().setShowBubbleSize(false);
        }
    }
}
```

### Salvar apresentação com gráfico

#### Visão geral
Por fim, salve sua apresentação em um caminho especificado no formato PPTX.

**Passos:**
1. **Método de salvamento**:Use o `save()` método sobre o `Presentation` exemplo.
2. **Descartar recursos**: Garanta que os recursos sejam liberados após o salvamento.

```java
// Recurso: Salvar apresentação com gráfico
import com.aspose.slides.*;

public void savePresentation(Presentation presentation, String outputPath) {
    try {
        presentation.save(outputPath + "DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Aplicações práticas

1. **Relatórios financeiros**: Use gráficos para exibir porcentagens de crescimento de receita em todos os departamentos.
2. **Análise de dados de vendas**: Visualize dados de vendas por região com rótulos de porcentagem para obter insights mais claros.
3. **Apresentações Educacionais**: Aprimore apresentações acadêmicas com estatísticas visuais.
4. **Campanhas de Marketing**: Exiba métricas de desempenho da campanha como recursos visuais envolventes.
5. **Reuniões de Estratégia Empresarial**: Use gráficos para transmitir dados complexos em discussões de planejamento estratégico.

## Considerações de desempenho
- **Gerenciamento de memória**: Descarte de `Presentation` objetos prontamente para liberar recursos.
- **Otimizar o carregamento do gráfico**: Carregue somente elementos essenciais do gráfico na memória, se possível.
- **Processamento em lote**: Ao processar várias apresentações, considere processá-las em lotes para gerenciar o consumo de recursos de forma eficaz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}