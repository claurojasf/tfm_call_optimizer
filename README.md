# tfm_call_optimizer
Ponganle wendy!

**test_embeddingsV4-2.ipynb:**
Almacena las transcripciones en BBDD vectorial haciendo que cada call tenga un ID y estas las separa por chunks de la forma:
call_001_chunk_001
call_001_chunk_002
call_001_chunk_003
call_002_chunk_001
call_002_chunk_002
...etc.

**test_rag_pipelineV6-2.ipynb:**
Pruebas de chatbot con transcripciones almacenadas según se hizo en el notebook "test_embeddingsV4-2.ipynb". Es una buena aproximación, pero no da información precisa en todos los casos y en otros casos da información errónea, ya que el código del retriever trae toda la información del RAG.

**test_rag_pipelineV7.ipynb:**
Utiliza el codigo del notebook "test_rag_pipelineV6-2.ipynb", pero tiene ajustes en el retriever, según lo que hablamos con Fernando, en donde en este se especifica la call, lo cual hace que las respuestas del chabot sean muy precisas.

**test_rag_pipelineV8_utils.ipynb:**
Utiliza funciones importadas desde el fichero "utils.py".

**utils.py:**
- Script que guarda funciones para código de notebook "test_rag_pipelineV8.ipynb".
- Streamlit usa este script para lanzar la app.

**test_rag_pipelineV9.ipynb:**
Utiliza el codigo del notebook "test_rag_pipelineV7.ipynb", pero tiene ajustes en el retriever, para obtener contexto de PDF de soluciones generales. En este código se puede elegir la llamada, pero el contexto del PDF siempre esta activo lo que puede causar respuestas incoherentes a veces. Para arreglar este problema se aplica la solución en código de script "app4.py".

**app4.py**:
- Se basa en código de "test_rag_pipelineV9.ipynb", pero hace que se elija entre que las respuestas sean específicas de la llamada, del PDF o ambos contextos al mismo tiempo.