# N8N-RAG-Consulta

**Descripción**

Este proyecto tiene como objetivo centralizar y automatizar el acceso a procedimientos técnicos utilizados en laboratorios mediante un sistema inteligente basado en IA. La solución emplea un enfoque de RAG (Retrieval-Augmented Generation) que permite combinar el poder de modelos de lenguaje avanzados con una base de conocimiento personalizada construida a partir de documentos reales del laboratorio.

El sistema está compuesto por dos flujos principales:

Vectorización y carga de documentación técnica:
Los procedimientos de laboratorio (por ejemplo, en formato PDF) son cargados, procesados y divididos en fragmentos de texto relevantes. Estos fragmentos son transformados en vectores numéricos (embeddings) mediante modelos de OpenAI, y luego almacenados en una base vectorial como Pinecone, junto con metadatos como el nombre del documento, número de página, o versión del procedimiento.

Consulta inteligente vía agente de IA:
Los usuarios pueden realizar consultas en lenguaje natural (por ejemplo: “¿Cuál es el procedimiento para determinar cloruros?”). El sistema convierte la consulta en un embedding, recupera los fragmentos más relevantes desde Pinecone, y luego utiliza un modelo de lenguaje (OpenAI) para generar una respuesta precisa, citando el contenido específico del procedimiento.

Este enfoque permite:

- Consultas contextuales sobre los procedimientos sin necesidad de conocer el formato o estructura del documento original.

- Acceso rápido a documentos técnicos y normativas internas del laboratorio.

- Trazabilidad y precisión, al devolver respuestas basadas en contenido verificado y documentado.

- Actualización dinámica, permitiendo incorporar nuevas versiones de documentos sin modificar el flujo principal.

**Tecnologías usadas**

n8n, Pinecone,Google drive, Open AI.

**Funcionamiento**

En este caso se guardo un PDF en google drive

<img src="https://github.com/Robchem95/N8N-RAG-Consulta/blob/main/Fotos%20flujo%20consulta%20de%20procedimientos/PDF%20en%20Google%20drive.png" width="300"/>

Este se fragmenta (vectoriza) en (pine-cone), y se incrusta mediante Open AI dejo una foto del flujo:

<img src="https://github.com/Robchem95/N8N-RAG-Consulta/blob/main/Fotos%20flujo%20consulta%20de%20procedimientos/Flujo%20n8n.png" width="800"/>

Para este caso el chat de consulta se utilizo el nativo de n8n , pero es facilmente adaptable a whatsapp o Telegram.

Un ejemplo de una consulta lo pueden ver aca:

<img src="https://github.com/Robchem95/N8N-RAG-Consulta/blob/main/Fotos%20flujo%20consulta%20de%20procedimientos/Consulta%20en%20n8n.png" width="300"/>

<img src="https://github.com/Robchem95/N8N-RAG-Consulta/blob/main/Fotos%20flujo%20consulta%20de%20procedimientos/Texto%20en%20documento.png"/>

De esta forma ofrecemos una rapida forma de consultar documentos , y mas en contexto de laboratorio que requieren consulta constante de procedimientos. 



