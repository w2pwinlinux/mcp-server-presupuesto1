# Servidor MCP para Gestión de Presupuesto en Excel

Este proyecto implementa un servidor MCP (Model Context Protocol) que monitorea y analiza un archivo Excel de presupuesto en tiempo real.

## Características

- Monitoreo en tiempo real de cambios en el archivo Excel
- Notificaciones de escritorio cuando se actualiza el archivo
- Análisis de presupuesto por departamento
- Detección de áreas que exceden el presupuesto
- Comparación entre presupuesto planificado y gastos actuales

## Requisitos

- Python 3.8 o superior
- Dependencias listadas en `requirements.txt`

## Instalación

1. Clonar el repositorio
2. Instalar las dependencias:
   ```bash
   pip install -r requirements.txt
   ```

## Estructura del Archivo Excel

El archivo `presupuesto.xlsx` debe contener las siguientes columnas:
- Departamento
- Presupuesto
- Gastos

## Uso

1. Asegúrate de tener un archivo Excel con el formato correcto
2. Ejecuta el servidor:
   ```bash
   python excel_mcp_server.py
   ```

## Funciones Disponibles

### get_budget_status
Obtiene el estado actual del presupuesto para un departamento específico o general.

### compare_budget
Compara los gastos actuales con el presupuesto planificado por departamento.

### check_overbudget
Identifica áreas que exceden su presupuesto según un umbral especificado.

## Notificaciones

El sistema enviará notificaciones de escritorio cuando:
- Se detecten actualizaciones en el archivo Excel
- Se identifiquen departamentos que excedan su presupuesto

## Integración con Claude Desktop

Puedes usar Claude Desktop para interactuar con el servidor MCP y realizar consultas sobre el presupuesto de forma natural.

Ejemplos de consultas:
- "¿Cuál es el estado actual del presupuesto del departamento de Marketing?"
- "Muestra una comparación de todos los departamentos"
- "Identifica departamentos que excedan el 90% de su presupuesto"

ARCHIVO JSON 
claude_desktop_config.json
{
  "mcpServers": {
    "ExcelBudgetServer": {
      "command": "C:/Users/Leved/miniconda3/python.exe",
      "args": ["d:/docker/trae/mcp1/excel_mcp_server.py"],
      "cwd": "d:/docker/trae/mcp1"
    }
  }
}
