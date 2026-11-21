# PTSCheck — Auditor de Procedimientos de Trabajo Seguro

**URL:** [www.ptscheck.com](https://www.ptscheck.com)  
**Versión web:** 0.5 · **Última actualización:** Noviembre 2026  
**Propietario:** Pucobre SpA — Minera El Espino

---

## ¿Qué es PTSCheck?

PTSCheck es una aplicación web que audita Procedimientos de Trabajo Seguro (PTS) de mantenimiento minero. Evalúa automáticamente un PTS subido por el usuario y entrega un puntaje, categoría y hallazgos con recomendaciones concretas.

La evaluación se basa en la **Pauta Única** de 9 dimensiones (A–I), con corpus normativo de referencia:

- D.S. 132/2002 — Reglamento de Seguridad Minera (SERNAGEOMIN)
- D.S. 44/2023 — Reglamento de Gestión Preventiva (vigente desde 01-FEB-2025)
- Ley 16.744 — Seguro social contra accidentes del trabajo
- D.S. 76/2006 — Régimen de subcontratación
- Res. 341/2023 ISP — Programa Preventivo MEHM
- Res. 668/2025 ISP — Identificación y evaluación de riesgos
- D.S. 594/1999 — Condiciones sanitarias y ambientales básicas
- Estándares de Control Operacional El Espino: ECO 2 y ECO 7

---

## Estructura del repositorio

```
/
├── index.html                        # Aplicación web principal (PTSCheck)
├── CNAME                             # Dominio: www.ptscheck.com
├── README.md                         # Este archivo
├── .gitignore
└── procedimientos/
    └── PETS-MNT-001/
        ├── PETS-MNT-001_Entrega_Devolucion_Equipos_v01.docx   # Procedimiento Word
        ├── PETS-MNT-001_Entrega_Devolucion_Equipos_v01.pdf    # Procedimiento PDF
        └── pts_mnt001.js                                        # Script generador (Node.js)
```

---

## Procedimientos elaborados

### PETS-MNT-001 Rev.01 — Entrega y Devolución de Equipos Móviles a Mantenimiento

| Campo | Detalle |
|---|---|
| **Código** | PETS-MNT-001 |
| **Revisión** | 01 |
| **Fecha** | Noviembre 2026 |
| **Flota** | Universal — toda la flota El Espino |
| **Páginas** | 14 |
| **Formato** | Carta vertical |
| **Riesgos fatales** | 4 (LOTO, atropello, explosión neumático, LOTO abandonado) |
| **Controles críticos** | Formato sí/no, respuesta en voz alta antes de exponerse al riesgo |
| **Fallas graves** | Verificadas: ninguna de las 8 está presente |

**Contenido:**
- Resumen de bolsillo (pág. 2)
- Objetivo, alcance y definiciones (pág. 3)
- Roles y responsabilidades
- EPP requerido
- Formulario de inspección (identificación del equipo + 8 secciones técnicas)
- Peligros y controles críticos — 4 riesgos fatales con pregunta sí/no (pág. 10)
- Controles críticos sí/no + verificaciones previas por rol
- Paso a paso: Etapa A (entrega a Mant.) y Etapa B (devolución a Ops.) — 15 pasos
- Protocolo de emergencia (pág. 14)
- Control de cambios

---

## Pauta de evaluación — 9 Dimensiones

| Dim. | Nombre | Puntos |
|------|--------|--------|
| A | Análisis de riesgo de la tarea | 15 |
| B | Controles críticos y jerarquía | 20 |
| C | Control de energías | 15 |
| D | Estructura y control documental | 10 |
| E | Redacción y facilidad de uso | 10 |
| F | Requisitos de mantenimiento | 10 |
| G | Implementación y legislación | 10 |
| H | Competencias, roles y contratistas | 5 |
| I | Emergencias | 5 |
| **Total** | | **100** |

**Categorías:** A (85–100) · B (70–84) · C (50–69) · D (<50 o con falla grave)

---

## Uso del script generador

El script `procedimientos/PETS-MNT-001/pts_mnt001.js` genera el DOCX del procedimiento usando la librería `docx` de Node.js.

```bash
# Instalar dependencia (solo primera vez)
npm install docx

# Generar el DOCX
node pts_mnt001.js
```

Requisitos: Node.js ≥ 16.

---

## Despliegue

El sitio se despliega automáticamente en GitHub Pages desde la rama `main`.  
El archivo `CNAME` apunta el dominio `www.ptscheck.com` a GitHub Pages.

---

*Documento elaborado con apoyo de herramientas de inteligencia artificial. La validación técnica y legal es responsabilidad de los profesionales competentes de la empresa.*
