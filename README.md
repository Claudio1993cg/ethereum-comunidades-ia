# Comunidades en Ethereum + interpretación con IA

Análisis de una red de transacciones de Ethereum con **Louvain**, **PageRank** y evaluación crítica de hipótesis generadas con **ChatGPT**.

> Objetivo: pasar de métricas de red a hipótesis interpretables, **sin confundir hipótesis con hechos**.

## Qué hace este proyecto

1. Limpia y valida un dataset de **5.000** transacciones (`from_address` → `to_address`).
2. Construye un grafo dirigido (**5.620** nodos, **4.601** aristas).
3. Calcula centralidades (grado, PageRank, betweenness).
4. Detecta comunidades con Louvain (**1.188** comunidades; la mayor tiene **467** nodos).
5. Selecciona el **top 10** de esa comunidad por PageRank.
6. Usa ChatGPT solo como apoyo interpretativo.
7. Verifica en Python una afirmación cuantitativa de la IA: el hub tiene PageRank **130,92×** el del segundo nodo.

## Stack

- Python 3.13
- pandas · NetworkX · matplotlib · NumPy
- Jupyter Notebook

```bash
pip install pandas==3.0.5 networkx==3.6.1 matplotlib numpy==2.5.2 ipykernel
```

## Cómo ejecutar

1. Clonar este repositorio.
2. Abrir `demo_final.ipynb` en VS Code o Jupyter.
3. Verificar que `transactions.csv` esté en la misma carpeta.
4. **Restart & Run All**.

## Archivos incluidos

| Archivo | Descripción |
|---------|-------------|
| `demo_final.ipynb` | Notebook con código, resultados y visualizaciones |
| `transactions.csv` | Dataset de transacciones |
| `Informe_IMRaD_Actividad3.pdf` | Informe académico |
| `Reflexion_Etica_Actividad3.pdf` | Uso responsable de IA |
| `Respuesta_Original_ChatGPT.pdf` | Evidencia de la interacción con IA |

## Resultados clave

- Transacciones usadas: **4.999** (se excluyó 1 registro sin destino).
- Semilla de reproducibilidad: **42**.
- SHA-256 de `transactions.csv`:  
  `712bb757578f5430f2d67b5f8d445a057041bf2c011c835a730df863599fc2ab`
- PageRank: `alpha=0.85`, `weight=None`.
- Louvain: grafo no dirigido, `resolution=1`, `seed=42`.

## Uso responsable de IA

ChatGPT se usó para formular hipótesis sobre el top 10, pidiendo separar hechos de conjeturas.  
La verificación cuantitativa (**130,92×**) se hizo en Python.  
**No** se afirmaron identidades ni propietarios de direcciones sin evidencia externa.

## Posibles mejoras

- Etiquetas públicas verificadas (p. ej. Etherscan) para el top 10.
- Sensibilidad de parámetros (PageRank con/sin pesos, otras resoluciones de Louvain).
- Historial más amplio y tipo de cuenta (contrato vs wallet).
