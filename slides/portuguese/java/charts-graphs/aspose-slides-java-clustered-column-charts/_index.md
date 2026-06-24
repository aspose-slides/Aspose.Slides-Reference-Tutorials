---
date: '2026-03-18'
description: Aprenda como criar um gráfico de colunas agrupadas em Java com Aspose.Slides,
  como adicionar o gráfico, definir cores e salvar a apresentação como PPTX. Guia
  passo a passo com exemplos de código.
keywords:
- create clustered column chart
- aspose slides java tutorial
- clustered column chart java
title: Como criar um gráfico de colunas agrupadas em Java com Aspose.Slides
url: /pt/java/charts-graphs/aspose-slides-java-clustered-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como criar gráfico de colunas agrupadas em Java com Aspose.Slides

## Introdução
Criar representações de dados visualmente atraentes é essencial para apresentações empresariais impactantes, e aprender **como criar clustered column chart** programaticamente pode economizar horas de trabalho manual. Neste tutorial você verá **como adicionar chart**, definir **cores** automaticamente e, finalmente, **salvar a apresentação como PPTX** usando **Aspose.Slides for Java**. Vamos percorrer tudo o que você precisa — desde a configuração da biblioteca até a adição do gráfico, personalização das cores de preenchimento das séries e persistência do arquivo.

### O que você vai alcançar
- Instalar e configurar Aspose.Slides for Java  
- **Create clustered column chart** em uma apresentação totalmente nova  
- Aplicar automaticamente cores de preenchimento das séries (**how to set colors**)  
- **Save presentation as PPTX** no disco (**how to save presentation**)  

Vamos tratar dos pré-requisitos antes de começarmos a criar o gráfico.

## Respostas Rápidas
- **What is the primary class?** `Presentation` from `com.aspose.slides`  
- **How do I add a chart?** Use `addChart(ChartType.ClusteredColumn, …)` on a slide’s shape collection (**how to add chart**)  
- **Can I set colors automatically?** Yes, call `setAutomaticSeriesColor(true)` on each series (**how to set colors**)  
- **Which format is used for saving?** `SaveFormat.Pptx` (PowerPoint) (**save presentation as pptx**)  
- **Do I need a license?** A trial works for testing; a full license is required for production  

## Pré-requisitos
Antes de começar, certifique‑se de que você tem as ferramentas e conhecimentos necessários:

### Bibliotecas e Dependências Necessárias
Você precisará da biblioteca Aspose.Slides for Java. Garanta que está usando a versão 25.4 com suporte ao JDK16.

### Requisitos de Configuração do Ambiente
Seu ambiente de desenvolvimento deve suportar Java (preferencialmente JDK16) e ser capaz de compilar projetos usando Maven ou Gradle.

### Pré-requisitos de Conhecimento
Familiaridade com programação Java básica, trabalho com bibliotecas via Maven/Gradle e compreensão de apresentações PowerPoint será benéfica.

## Configurando Aspose.Slides para Java
Para integrar Aspose.Slides ao seu projeto, siga as instruções de configuração abaixo:

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

**Download Direto**  
Para quem prefere downloads diretos, visite [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Etapas para Aquisição de Licença
- **Free Trial**: Comece com uma avaliação gratuita para explorar os recursos.  
- **Temporary License**: Obtenha uma licença temporária para testar sem limitações.  
- **Purchase**: Para uso contínuo, adquira uma licença completa.

**Inicialização e Configuração Básica**  
Inicialize Aspose.Slides da seguinte forma:
```java
import com.aspose.slides.Presentation;
// Initialize the Presentation class
Presentation presentation = new Presentation();
```

## Como Adicionar um Gráfico de Colunas Agrupadas
Adicionar um gráfico é o primeiro passo funcional. Esta seção explica **how to add chart** usando a API.

### Recurso 1: Criar um Gráfico de Colunas Agrupadas
Vamos criar um gráfico de colunas agrupadas usando Aspose.Slides for Java. Esse recurso permite que você adicione gráficos visualmente atraentes aos seus slides sem esforço.

#### Visão Geral
Nesta seção, inicializaremos uma nova apresentação e inseriremos um gráfico de colunas agrupadas no primeiro slide.

**Etapa 1: Inicializar Presentation**  
Crie um objeto `Presentation` para começar a trabalhar com arquivos PowerPoint:
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation presentation = new Presentation();
```

**Etapa 2: Adicionar Gráfico de Colunas Agrupadas**  
Adicione o gráfico nas coordenadas especificadas (100, 50) e dimensões (600 × 400):
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

**Etapa 3: Limpar Recursos**  
Sempre libere recursos para evitar vazamentos de memória:
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

## Como Definir Cores para o Gráfico
Aprimore a aparência visual aplicando automaticamente cores de preenchimento das séries (**how to set colors**).

### Recurso 2: Definir Cor de Preenchimento Automática das Séries
Defina a cor de cada série do gráfico automaticamente para um visual coeso.

#### Visão Geral
Defina a cor de cada série do gráfico automaticamente para um visual coeso.

**Etapa 1: Acessar o Gráfico e Iterar Séries**  
Após criar seu gráfico, acesse‑o e itere sobre suas séries:
```java
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(com.aspose.slides.ChartType.ClusteredColumn, 100, 50, 600, 400);

for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().get_Item(i).setAutomaticSeriesColor(true);
}
```

**Etapa 2: Gerenciamento de Recursos**  
Libere o objeto `Presentation` quando terminar:
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

## Como Salvar a Apresentação como PPTX
Depois que o gráfico estiver com boa aparência, você desejará persistir o arquivo (**how to save presentation**).

### Recurso 3: Salvar Apresentação no Disco
Por fim, salve seu trabalho com facilidade usando Aspose.Slides.

#### Visão Geral
Salve suas apresentações editadas no formato e local desejados.

**Etapa 1: Definir Caminho de Saída**  
Especifique onde deseja salvar o arquivo:
```java
import com.aspose.slides.SaveFormat;
String outputPath = "YOUR_OUTPUT_DIRECTORY/AutoFillSeries_out.pptx";
```

**Etapa 2: Salvar Apresentação**  
Use o método `save` do objeto `Presentation`:
```java
presentation.save(outputPath, SaveFormat.Pptx);
```

## Aplicações Práticas
- **Financial Reports**: Visualize earnings trimestrais com clareza.  
- **Marketing Data Analysis**: Apresente resultados de campanhas usando visuais impactantes.  
- **Project Management**: Acompanhe marcos e progresso visualmente em reuniões de equipe.

## Considerações de Desempenho
Ao trabalhar com Aspose.Slides, considere estas boas práticas:

- Gerencie a memória de forma eficaz descartando objetos `Presentation` prontamente.  
- Otimize o tamanho dos arquivos ao salvar apresentações para conservar espaço em disco.  
- Use estruturas de dados eficientes para as séries do gráfico a fim de melhorar o desempenho.

## Conclusão
Parabéns! Você aprendeu como **create clustered column chart**, definir **cores** automaticamente e **save the presentation as PPTX** usando Aspose.Slides for Java. Essa habilidade não só aprimora suas apresentações, mas também simplifica o processo de representação visual de dados.

**Próximos Passos:**  
Explore recursos adicionais, como personalizar elementos do gráfico, adicionar rótulos de dados ou integrar fontes de dados externas para expandir as capacidades do seu projeto.

## Seção de Perguntas Frequentes
1. **How do I install Aspose.Slides for a specific JDK version?**  
   - Use dependências Maven/Gradle especificando `classifier` conforme mostrado na seção de configuração.  
2. **What if my presentation doesn't save correctly?**  
   - Certifique‑se de que você tem permissões de gravação no diretório de saída e que o caminho do arquivo está correto.  
3. **Can I create other types of charts using Aspose.Slides for Java?**  
   - Absolutely! Explore opções de `ChartType` como Pie, Bar ou Line charts.  
4. **How do I handle large datasets in my chart?**  
   - Optimize estruturas de dados e considere pré‑processar seus dados antes de visualizá‑los.  
5. **Where can I find more examples of using Aspose.Slides for Java?**  
   - Visite a [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) para guias abrangentes e exemplos de código.

## Recursos
- **Documentation**: [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Download**: [Get Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Purchase**: [Buy a License](https://purchase.aspose.com/buy)  
- **Free Trial**: [Start a Free Trial](https://releases.aspose.com/slides/java/)  
- **Temporary License**: [Request Here](https://purchase.aspose.com/temporary-license/)  
- **Support**: [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-03-18  
**Tested With:** Aspose.Slides 25.4 (JDK16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}