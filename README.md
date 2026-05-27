Apertura de Cuentas INVEX — Persona Física
App Streamlit que lee una Solicitud de Apertura de Cuentas en PDF, extrae los datos automáticamente y genera un ZIP con los 12 formatos llenos.

Estructura del proyecto
apertura_app/
├── app.py                  ← app Streamlit (todo en un archivo)
├── requirements.txt
├── templates/
│   └── pf/                 ← pon aquí tus 12 plantillas preparadas
│       ├── 1-Checklist Expediente.xlsx
│       ├── 2-kyc Visita Ocular (Firma) (3).xlsx
│       ├── 3-Clasificación de Matriz de Riesgo.docx
│       └── ...
└── README.md
Paso 1 — Preparar las plantillas (una sola vez)
Corre las cells 4 y 12 de tu notebook Apertura_Cuentas_PF.ipynb para generar la carpeta templates/pf/ con los marcadores Jinja.

Luego copia esa carpeta dentro de apertura_app/templates/pf/.

Paso 2 — Probar localmente
pip install -r requirements.txt
streamlit run app.py
Paso 3 — Subir a Streamlit Cloud
Crea un repositorio en GitHub (puede ser privado) y sube esta carpeta.
Ve a https://share.streamlit.io → "New app"
Selecciona tu repo → rama main → archivo app.py
Deploy
La app estará disponible en una URL pública del tipo: https://tu-usuario-apertura-invex.streamlit.app

Notas
La app NO necesita LibreOffice: entrega un ZIP con los formatos (docx + xlsx) listos para abrir en Word/Excel.
Si en el futuro quieres el expediente PDF unificado, se puede agregar conversión con LibreOffice en un servidor propio (Railway/Render).
Las plantillas NO se suben al repo de GitHub si las agregas a .gitignore. Sin embargo, para que Streamlit Cloud las encuentre SÍ deben estar en el repo.
