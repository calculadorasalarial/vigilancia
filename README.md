# 👮‍♂️ Calculadora de Nómina para Vigilantes - Colombia 2026

Herramienta web interactiva para la liquidación y simulación de nómina de personal de seguridad privada, ajustada estrictamente a la normativa laboral vigente en Colombia para la transición de jornada laboral 2025-2026.

## 📋 Características Principales

### 1. Cumplimiento Legal Automático
* **Ley 2101 de 2021 (Reducción Jornada):**
    * Detecta automáticamente la fecha seleccionada.
    * Aplica divisor **220 horas** (Jornada 44h) para fechas anteriores al 15 de julio de 2026.
    * Aplica divisor **210 horas** (Jornada 42h) a partir del 15 de julio de 2026.
* **Ley 2466 de 2025 (Reforma Laboral):**
    * Calcula los recargos nocturnos iniciando a las **7:00 p.m.** (anteriormente 9:00 p.m.).

### 2. Gestión de Turnos y Novedades
El sistema permite configurar patrones automáticos o editar manualmente día a día con los siguientes estados:
* ☀️ **Diurno:** Turno de 12 horas (6am - 6pm).
* 🌑 **Nocturno:** Turno de 12 horas (6pm - 6am).
* 🟢 **Descanso:** Día libre remunerado.
* 🟠 **Trabajo en Descanso (Extra):** Cálculo automático con recargo festivo (1.75x / 1.8x / 1.9x según vigencia).
* 🟣 **Permiso Remunerado:** Se liquida como básico ordinario.
* 🔴 **Ausencia:** Descuento del día (valor $0).

### 3. Precisión Financiera
* **Redondeo Contable:** El valor de la hora ordinaria se redondea al peso más cercano (ej. $7.959) antes de calcular extras, para coincidir con los software de nómina.
* **Deducciones de Ley:** Cálculo automático de Salud (4%) y Pensión (4%) sobre el IBC.
* **Auxilio de Transporte:** Sumado al final (no constitutivo de salario para prestaciones).

### 4. Reportes
* Generación de **PDF Detallado** en el navegador (Client-side) usando `jsPDF`.
* Incluye resumen financiero y desglose diario de horas y valores.

---

## 🚀 Cómo Usar

1.  Descarga el archivo `index.html` (o el nombre que le hayas dado a la calculadora).
2.  Ábrelo en cualquier navegador moderno (Google Chrome, Edge, Firefox).
3.  **Configuración Inicial:**
    * Ingresa el Salario Básico y Auxilio de Transporte.
    * Selecciona el Mes y Año a liquidar.
    * Elige un patrón de turnos (ej. 2x2x2) y la fecha de inicio del ciclo.
4.  **Ajuste Manual:**
    * Haz clic sobre cualquier día del calendario para rotar entre los estados (Diurno -> Nocturno -> Descanso -> Extra -> Permiso -> Ausencia).
5.  **Resultados:**
    * Verifica los totales en la parte inferior.
    * Haz clic en **"Descargar PDF"** para guardar el soporte.

---

## ⚖️ Tabla de Recargos (Referencia Técnica)

Los factores se aplican sobre el valor de la hora ordinaria (`Salario / Divisor Mensual`).

| Concepto | Factor Multiplicador | Descripción |
| :--- | :--- | :--- |
| **Hora Ordinaria** | 1.00 | Valor base. |
| **Recargo Nocturno** | 0.35 | Plus por trabajo entre 7pm y 6am. |
| **Extra Diurna** | 1.25 | Hora adicional diurna. |
| **Extra Nocturna** | 1.75 | Hora adicional nocturna. |
| **Recargo Dominical/Festivo** | 1.75 | Por trabajar en día de descanso obligatorio (ordinario). |
| **Extra Dom. Diurna** | 2.00 | Extra diurna en festivo. |
| **Extra Dom. Nocturna** | 2.50 | Extra nocturna en festivo. |

---

## 🛠️ Tecnologías Utilizadas

* **Frontend:** HTML5, CSS3, JavaScript (Vanilla).
* **Librerías:**
    * `jspdf`: Generación de documentos PDF.
    * `jspdf-autotable`: Creación de tablas dentro del PDF.

## 📄 Licencia

Este proyecto es de uso libre para fines educativos y administrativos. Se recomienda verificar los cálculos finales con el área contable.
