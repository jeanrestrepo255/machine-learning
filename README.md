# Predicción de Cancelaciones de Reservas Hoteleras

**Trabajo Final — Machine Learning**

**Por:**
- **Jean Pierre Restrepo Casafús**
- **Juan Camilo Restrepo Henao**

Institución Universitaria Pascual Bravo · 2025

---

## Descripción del proyecto

Este proyecto aplica la metodología **CRISP-DM** para predecir si una reserva de hotel será cancelada antes de la llegada del huésped, usando el dataset [Hotel Booking Demand](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand) (Antonio, Almeida & Nunes, 2019) con 119,390 reservas de dos hoteles en Portugal.

**Pregunta de negocio:** ¿Es posible predecir si una reserva será cancelada antes de que ocurra, y qué factores la explican mejor?

---

## Estructura del repositorio

```
├── notebook.ipynb          # Análisis completo: EDA, modelamiento y prescriptivo
├── notebook.html           # Versión impresa del cuaderno con todos los resultados
├── model.joblib            # Random Forest sintonizado + umbral óptimo
├── preprocessor.joblib     # Pipeline de preprocesamiento serializado
├── requirements.txt        # Dependencias del entorno
└── README.md
```

---

## Modelos implementados

| Modelo | Tipo | Objetivo |
|--------|------|----------|
| Random Forest | Predictivo (clasificación) | Predecir si una reserva será cancelada |
| K-Means | Descriptivo (clustering) | Segmentar clientes por perfil de riesgo |
| Reglas de umbral | Prescriptivo | Traducir probabilidades en acciones concretas |

---

## Resultados principales

- **ROC-AUC:** 0.898
- **Recall (cancelaciones):** ~94% — supera el criterio de negocio (≥ 75%)
- **3 clusters** con tasas de cancelación de 26.2%, 42.8% y 99.3%
- Variables más importantes: `lead_time`, `deposit_type`, `total_of_special_requests`, `had_prev_cancellation`

---

## Cómo ejecutar

```bash
pip install -r requirements.txt
jupyter notebook notebook.ipynb
```

El cuaderno se ejecuta de principio a fin sin intervención manual. Todas las semillas aleatorias están fijadas (`random_state=42`).

---

## Tecnologías

`Python` · `scikit-learn` · `pandas` · `numpy` · `imbalanced-learn` · `matplotlib` · `seaborn` · `joblib`
