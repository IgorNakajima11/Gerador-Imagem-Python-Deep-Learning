# Geração de Imagens com Deep Learning: Moda Animal com TensorFlow e Keras

## Descrição

Este projeto explora o uso do Stable Diffusion, implementado com TensorFlow e Keras, para gerar imagens de animais vestindo roupas. O foco é criar conteúdo visual para campanhas de moda, detalhando prompts e ajustando parâmetros para obter resultados de alta qualidade e precisão. O objetivo final é utilizar essas imagens na criação de vídeos e outros materiais de marketing.

## Conteúdo do Curso

1.  **Usando o Stable Diffusion**
    *   Melhorando a Precisão
        *   Detalhamento dos Prompts
        *   Geração de Imagens
        *   Alterando a Precisão de Ponto Flutuante
2.  **Conclusão**

## Tecnologias Utilizadas

*   TensorFlow
*   Keras
*   KerasCV
*   Stable Diffusion

## Configuração do Ambiente

1.  **Instalação das Bibliotecas:**

    ```bash
    pip install tensorflow
    pip install keras
    pip install keras-cv
    ```
2.  **Configuração da Precisão de Ponto Flutuante:**

    Para acelerar a geração de imagens sem comprometer significativamente a qualidade, configure a precisão de ponto flutuante para `mixed_float16`:

    ```python
    import keras
    keras.mixed_precision.set_global_policy("mixed_float16")
    ```

## Como Usar

1.  **Importar as Bibliotecas Necessárias:**

    ```python
    import keras_cv
    import keras
    ```
2.  **Instanciar o Modelo Stable Diffusion:**

    ```python
    modelo = keras_cv.models.StableDiffusion(img_width=512, img_height=512)
    ```
3.  **Criar Prompts Detalhados para Gerar Imagens:**

    Utilize prompts detalhados para guiar o modelo na geração das imagens desejadas.

    ```python
    imagens = modelo.text_to_image(
        "Panda wearing a blue hat, dark fantasy art, "
        "high quality, highly detailed, elegant, sharp focus, "
        "concept art, character concepts, digital painting, mystery, adventure",
        batch_size=3,
    )
    ```
4.  **Visualizar as Imagens Geradas:**

    Utilize uma função para visualizar as imagens geradas. (A função `plot_images()` deve ser definida no seu código).

    ```python
    plot_images(imagens)
    ```

## Exemplos de Uso

### Gato Humanoide com Jeans Dourado

```python
imagens = modelo.text_to_image(
    "Humanoid cat wearing golden jeans, dark fantasy art, "
    "high quality, highly detailed, elegant, sharp focus, "
    "concept art, character concepts, digital painting, mystery, adventure",
    batch_size=3,
)
plot_images(imagens)

imagens = modelo.text_to_image(
    "Panda wearing a blue hat, dark fantasy art, "
    "high quality, highly detailed, elegant, sharp focus, "
    "concept art, character concepts, digital painting, mystery, adventure",
    batch_size=3,
)
plot_images(imagens)

