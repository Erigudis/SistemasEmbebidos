# Mini-GPT: Sistemas Embebidos y Redes Neuronales

Modelo de lenguaje en miniatura basado en la arquitectura **Transformer**, implementado desde cero y entrenado con un corpus técnico sobre **sistemas embebidos** (~70 KB). El objetivo del laboratorio es comprender de forma práctica cómo funciona internamente un LLM: tokenización, embeddings, atención, entrenamiento y generación.

## 📌 Descripción del proyecto

Este proyecto implementa un **Mini-GPT** que aprende a predecir el siguiente carácter de un texto técnico. Aunque es un modelo pequeño (del orden de cientos de miles de parámetros), las operaciones internas son las mismas que utilizan los modelos de gran escala como GPT-3 o GPT-4.

El trabajo incluye:

- Tokenización a nivel de carácter.
- Embeddings de token + embeddings posicionales.
- Bloques Transformer con multi-head self-attention, conexiones residuales, LayerNorm y MLP.

- Cabeza de predicción lineal + softmax para obtener la distribución del siguiente token.

- Entrenamiento con cross-entropy y optimizador AdamW, en CPU.

## 🧠 Arquitectura

El modelo está compuesto por:

1. **Tokenización por carácter**: cada carácter distinto es un token.
2. **Embeddings**: se suman el embedding del token y el embedding posicional, obteniendo una matriz de forma \(T \times d\).
3. **Bloques Transformer**: multi-head self-attention con máscara causal, conexiones residuales, LayerNorm y MLP.

4. **Cabeza de predicción**: capa lineal seguida de softmax para obtener la probabilidad del siguiente token.



## 📊 Resultados

- **Evolución de la pérdida**: descenso claro durante el entrenamiento, sin signos evidentes de sobreajuste extremo.

- **Generación antes vs. después**: antes el modelo generaba caracteres aleatorios; después genera fragmentos coherentes relacionados con sistemas embebidos (microcontrolador, tiempo real, memoria, RTOS).
- **Efecto de la temperatura**:
  - Baja (0.3): texto predecible y repetitivo.

  - Media (0.8): mejor equilibrio entre coherencia y variedad.

  - Alta (1.4–1.5): texto creativo pero con más errores y pérdida de sentido.
.
- **Experimentos de escala**: al aumentar capas y dimensión de embeddings, la pérdida final disminuyó y la calidad mejoró, aunque con mayor tiempo de entrenamiento.



## 🚀 Cómo usarlo

1. Clona el repositorio:
   ```bash
   git clone https://github.com/tu-usuario/tu-repositorio.git
   cd tu-repositorio
   ```
2. Ejecuta el script principal para entrenar el modelo:
   ```bash
   python train.py
   ```
3. Para generar texto con el modelo entrenado:
   ```bash
   python generate.py --temperature 0.8
   ```


## 📁 Estructura del repositorio

```
├── train.py              # Entrenamiento del modelo
├── generate.py           # Generación de texto
├── model.py              # Definición de la arquitectura Mini-GPT
├── data/                # Corpus de sistemas embebidos
├── notebooks/           # Experimentos y visualizaciones
├── README.md            # Este archivo
└── requirements.txt     # Dependencias
```


## 📚 Preguntas conceptuales

El informe incluye respuestas a preguntas conceptuales sobre LLMs (tokenización, embeddings, self-attention, máscara causal, multi-head attention, descenso por gradiente, capacidades emergentes, entre otras). Consulta el documento del proyecto para más detalle.




## 🤖 Declaración de uso de IA

Se utilizó asistencia de inteligencia artificial como apoyo para la estructuración del informe y la redacción de algunas secciones. Todo el código, los experimentos, las capturas y el análisis de resultados fueron realizados y comprendidos por el autor, quien es capaz de explicar y defender cada parte del trabajo entregado.



## 📜 Licencia

Este proyecto fue creado con fines educativos, como parte del curso **Sistemas Embebidos y Redes Neuronales** (Cuarto Semestre, Escuela de Informática/Desarrollo de Software).
