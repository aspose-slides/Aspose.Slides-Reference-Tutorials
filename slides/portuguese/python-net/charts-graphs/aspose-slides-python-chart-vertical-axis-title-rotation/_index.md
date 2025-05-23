---
"date": "2025-04-23"
"description": "Aprenda a ajustar o ângulo de rotação dos títulos dos gráficos em apresentações usando o Aspose.Slides para Python, melhorando a legibilidade e a estética."
"title": "Como definir a rotação do título do eixo vertical de um gráfico no Aspose.Slides para Python"
"url": "/pt/python-net/charts-graphs/aspose-slides-python-chart-vertical-axis-title-rotation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como definir a rotação do título do eixo vertical de um gráfico no Aspose.Slides para Python

## Introdução

Em apresentações de dados, melhorar a legibilidade dos gráficos é crucial. Ajustar o ângulo de rotação do título do eixo vertical do seu gráfico usando o Aspose.Slides para Python pode fazer com que os títulos se encaixem perfeitamente ou se destaquem nos seus slides. Este tutorial orienta você na configuração desse ângulo de rotação para aprimorar a funcionalidade e o apelo visual.

**O que você aprenderá:**
- Como instalar e configurar o Aspose.Slides para Python.
- Etapas para adicionar e personalizar gráficos em seus slides.
- Técnicas para definir o ângulo de rotação dos títulos dos gráficos.
- Aplicações reais para esses recursos na visualização de dados.

Vamos começar abordando os pré-requisitos antes de nos aprofundarmos na implementação.

## Pré-requisitos

Antes de começar, certifique-se de ter:
- **Ambiente Python**: Instale o Python 3.x a partir de [python.org](https://www.python.org/).
- **Biblioteca Aspose.Slides**: Instale via pip para manipular apresentações de forma eficaz.
- **Conhecimento básico de programação Python**: A familiaridade com a sintaxe do Python e as operações de arquivo ajudará você a acompanhar.

## Configurando Aspose.Slides para Python

Para usar o Aspose.Slides, instale-o usando o pip. Abra seu terminal ou prompt de comando e execute:

```bash
pip install aspose.slides
```

### Etapas de aquisição de licença

A Aspose oferece diferentes opções de licença:
- **Teste grátis**: Baixe uma versão de teste em [Página de lançamento da Aspose](https://releases.aspose.com/slides/python-net/).
- **Licença Temporária**: Obtenha uma licença temporária para recursos estendidos por meio do [portal de compras](https://purchase.aspose.com/temporary-license/).
- **Comprar**: Considere comprar se achar a ferramenta indispensável, disponível no [Página de compra Aspose](https://purchase.aspose.com/buy).

#### Inicialização e configuração básicas

Veja como inicializar Aspose.Slides no seu script Python:

```python
import aspose.slides as slides

# Criar um objeto de apresentação
def main():
    with slides.Presentation() as pres:
        # Seu código irá aqui
        pass

if __name__ == "__main__":
    main()
```

## Guia de Implementação

### Adicionando e personalizando gráficos

#### Visão geral

Nesta seção, adicionaremos um gráfico de colunas agrupadas ao seu slide e o personalizaremos definindo o ângulo de rotação do título do eixo vertical.

#### Passos:

##### Etapa 1: adicionar um gráfico de colunas agrupadas

Comece adicionando um gráfico em coordenadas específicas com dimensões definidas:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        # Adicione um gráfico de colunas agrupadas ao slide 1
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
```

##### Etapa 2: Configurar o título do eixo vertical

Habilite e defina o ângulo de rotação para o título do eixo vertical:

```python
def configure_chart(chart):
    # Habilitar o título do eixo vertical
    chart.axes.vertical_axis.has_title = True
    
    # Defina o ângulo de rotação para 90 graus
    chart.axes.vertical_axis.title.text_format.text_block_format.rotation_angle = 90
```

##### Etapa 3: Salve sua apresentação

Por fim, salve sua apresentação com as alterações:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
        configure_chart(chart)
        
        # Salvar a apresentação
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_setting_rotation_angle_out.pptx

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}