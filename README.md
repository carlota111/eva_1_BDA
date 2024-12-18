# Proyecto RAG (Retrieval-Augmented Generation)

Este repositorio contiene varias implementaciones de RAG (Generación Aumentada por Recuperación) que aprovechan diferentes fuentes de datos y métodos para crear un vector store y realizar consultas. El sistema está diseñado para extraer información de diferentes fuentes (páginas web, archivos PDF) y realizar búsquedas utilizando un modelo basado en Recuperación con capacidades Generativas.

---
## Estructura proyecto
```bash
eva_1_BDA/
├── .gradio/
├── .vscode/                   
├── MongoAtlas/
|   ├── Castellano_RAG_Mongo.ipynb            
│   └── Ingles_RAG_Mongo.ipynb                
├── PDF/                    
|   ├── PIMENTON_MAYO.pdf            
│   └── recetas.pdf                         
├── Castellano_RAG_Mongo.ipynb                              
├── Ingles_RAG_Mongo.ipynb                
└── README.md    
````

---
## Tabla de Contenidos

- [Visión General](#visión-general)
- [RAG en Inglés - Vector Store basado en Páginas Web](#rag-en-inglés---vector-store-basado-en-páginas-web)
- [RAG en Castellano - Vector Store basado en PDF](#rag-en-castellano---vector-store-basado-en-pdf)
- [Uso](#uso)
- [Dependencias](#dependencias)

---

## Visión General

El objetivo de este proyecto es proporcionar un marco para construir sistemas RAG, donde los datos de texto se indexan en un vector store y se utilizan consultas en lenguaje natural para recuperar información relevante.

Este proyecto consta de:

1. **RAG en Inglés (Basado en Páginas Web)**: Crea un vector store a partir del contenido de una página web y permite realizar consultas sobre él.
2. **RAG en Castellano (Basado en PDF)**: Crea un vector store a partir de uno o varios archivos PDF y permite realizar consultas sobre él.

Ambas implementaciones utilizan **Chroma** para el almacenamiento de vectores, **LangChain** para la orquestación del flujo de trabajo y **HuggingFaceEmbeddings** para la generación de embeddings de texto.

---

## RAG en Inglés - Vector Store basado en Páginas Web

### Descripción

Este RAG permite crear un vector store a partir del contenido de una página web. El proceso consiste en:

1. Extraer el contenido de texto de una página web utilizando **BeautifulSoup**.
2. Dividir el contenido en fragmentos más pequeños para la indexación.
3. Almacenar los datos de texto en un **vector store Chroma** utilizando **HuggingFaceEmbeddings**.
4. Crear GUI para interactuar con el, utilizando **Gradio**.

## RAG en Castellano - Vector Store basado en PDF

### Descripción

Esta implementación permite crear un vector store a partir de uno o varios archivos PDF. El proceso consiste en:

1. Extraer el texto de los PDFs utilizando **PyPDF2**.
2. Dividir el texto en fragmentos.
3. Almacenar los datos extraídos en un **vector store Chroma** utilizando **HuggingFaceEmbeddings**.

## Uso

Una vez creado el vector store, puedes realizar consultas sobre él utilizando el **RetrievalQA** de **LangChain**.
## Dependencias

Asegúrate de tener instaladas las siguientes dependencias para ejecutar el proyecto:

- **LangChain**: Para orquestar el flujo de trabajo y gestionar los pasos de recuperación y generación.
- **Chroma**: Para almacenar e indexar los datos en vectores.
- **Hugging Face Embeddings**: Para generar embeddings de texto utilizando modelos pre-entrenados.
- **Gradio**: Para crear la interfaz de usuario (GUI).
- **BeautifulSoup**: Para extraer contenido de páginas web.
- **PyPDF2**: Para extraer texto de archivos PDF.

Primero asegurarnos de que están instaladas todas las herramientas básicas de compilación:
```bash
sudo apt update
sudo apt install build-essential
````

Ahora instala las dependencias, puedes ejecutar los siguientes comandos dentro de nuestro enviroment:
```bash
conda create --name rag python=3.13.1
conda activate rag
conda install pip
pip install langchain langchain_ollama
pip install pymongo
pip install chromadb sentence-transformers langchain_huggingface langchain_chroma langchain PyPDF2 requests BeautifulSoup4
pip install gradio
````
