# AW Internet Sales - Modelo Tabular

## 📊 Descripción del Proyecto

Este proyecto contiene un modelo tabular de **Microsoft Analysis Services** basado en la base de datos **AdventureWorksDW2022**. El modelo está diseñado para analizar las ventas por internet de AdventureWorks, proporcionando una estructura de datos optimizada para Business Intelligence y análisis de datos.

## 🏗️ Arquitectura del Modelo

### Fuente de Datos
- **Base de datos**: AdventureWorksDW2022
- **Servidor**: localhost
- **Tipo de conexión**: SQL Server (TDS)
- **Modo de consulta**: InMemory

### Tablas del Modelo

#### 📅 Tablas de Dimensión
- **DimDate**: Dimensión temporal con jerarquías de calendario y fiscal
- **DimCustomer**: Información de clientes con datos demográficos
- **DimGeography**: Datos geográficos y territorios de ventas
- **DimProduct**: Catálogo de productos con categorías y subcategorías
- **DimProductCategory**: Categorías de productos
- **DimProductSubcategory**: Subcategorías de productos

#### 📈 Tabla de Hechos
- **FactInternetSales**: Transacciones de ventas por internet (2010-2014)

## 🔧 Características Técnicas

### Medidas Calculadas
El modelo incluye múltiples medidas DAX para análisis avanzado:

#### Medidas de Ventas
- `InternetTotalSales`: Total de ventas por internet
- `InternetTotalMargin`: Margen total de ventas
- `InternetTotalUnits`: Total de unidades vendidas
- `InternetTotalDiscountAmount`: Total de descuentos aplicados

#### Medidas de Rendimiento
- `InternetCurrentQuarterSalesPerformance`: KPI de rendimiento de ventas
- `InternetCurrentQuarterMarginPerformance`: KPI de rendimiento de margen
- `InternetPreviousQuarterSales`: Ventas del trimestre anterior
- `InternetCurrentQuarterSales`: Ventas del trimestre actual

#### Medidas de Tiempo
- `DaysCurrentQuarterToDate`: Días transcurridos en el trimestre actual
- `DaysInCurrentQuarter`: Total de días en el trimestre actual

### Jerarquías
- **Calendar**: Año → Semestre → Trimestre → Mes → Día
- **Fiscal**: Año Fiscal → Semestre Fiscal → Trimestre Fiscal → Mes → Día
- **ProductionCalendar**: Año → Semana → Día de la semana
- **Category**: Categoría → Subcategoría → Modelo → Producto

### Perspectivas
- **Internet Sales**: Perspectiva optimizada para análisis de ventas por internet

### Roles de Seguridad
- **Administrator**: Acceso completo al modelo
- **Sales Manager**: Acceso de lectura al modelo completo
- **Sales Analyst US**: Acceso restringido solo a datos de Estados Unidos

## 🚀 Configuración y Despliegue

### Requisitos Previos
- Microsoft Analysis Services (Tabular)
- SQL Server con AdventureWorksDW2022
- Visual Studio con Analysis Services Projects

### Configuración del Proyecto
```xml
DeploymentServerName: localhost
DeploymentServerDatabase: AW Internet Sales
DeploymentServerCubeName: Modelo
DeploymentOptionDirectQueryMode: InMemory
```

### Despliegue
1. Abrir el proyecto en Visual Studio
2. Configurar la cadena de conexión a AdventureWorksDW2022
3. Compilar el proyecto (Build)
4. Desplegar al servidor de Analysis Services

## 📊 Casos de Uso

Este modelo está optimizado para:
- **Análisis de ventas**: Tendencias, comparaciones trimestrales y anuales
- **Análisis de clientes**: Segmentación demográfica y geográfica
- **Análisis de productos**: Rendimiento por categorías y subcategorías
- **KPIs de rendimiento**: Seguimiento de objetivos de ventas y márgenes
- **Reportes ejecutivos**: Dashboards y análisis de alto nivel

## 🔍 Estructura de Archivos

```
AW Internet Sales/
├── Model.bim                    # Definición del modelo tabular
├── AW Internet Sales.smproj     # Archivo de proyecto
├── AW Internet Sales.sln        # Solución de Visual Studio
├── bin/                         # Archivos compilados y datos
│   └── Data/                    # Base de datos del modelo
└── obj/                         # Archivos temporales de compilación
```

## 📈 Datos de Ejemplo

El modelo incluye datos de ventas por internet de AdventureWorks desde 2010 hasta 2014, con información sobre:
- Más de 18,000 clientes únicos
- Productos de múltiples categorías (Bikes, Components, Clothing, Accessories)
- Transacciones distribuidas geográficamente
- Múltiples monedas y territorios de ventas

## 🛠️ Mantenimiento

### Actualización de Datos
El modelo está configurado para actualización incremental por particiones anuales. Para actualizar:
1. Ejecutar procesamiento de particiones específicas
2. Actualizar jerarquías y relaciones
3. Validar medidas calculadas

### Monitoreo
- Verificar rendimiento de consultas DAX
- Monitorear uso de memoria
- Revisar logs de procesamiento

## 📝 Notas de Desarrollo

- **Idioma**: El modelo está configurado en español (es-ES)
- **Formato de moneda**: Euros (€) con formato español
- **Particiones**: Datos organizados por año para optimizar rendimiento
- **Filtros**: Implementados filtros de seguridad por región geográfica

## 🤝 Contribución

Para contribuir al proyecto:
1. Crear una rama feature
2. Realizar cambios en el modelo
3. Probar en entorno de desarrollo
4. Crear pull request con descripción de cambios

## 📞 Soporte

Para soporte técnico o consultas sobre el modelo, contactar al equipo de Business Intelligence.

---

**Versión**: 1.0  
**Última actualización**: 2024  
**Compatibilidad**: Analysis Services 2019+