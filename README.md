# 🚀 Dashboard CRM Avanza Formación

Dashboard operativo para la gestión de candidatos del CRM de Avanza Formación. Sistema diseñado para optimizar el seguimiento de candidatos en las delegaciones de LABORA (Comunidad Valenciana) y SEFCARM (Región de Murcia).

## 🌐 Demo en Vivo

**URL de Producción**: [https://vinipurtan.github.io/crm-dashboard-avanza/](https://vinipurtan.github.io/crm-dashboard-avanza/)

![Dashboard Preview](https://img.shields.io/badge/Status-En%20Vivo-green?style=for-the-badge&logo=github-pages)

## 📋 Características Principales

### 🚨 Sistema de Alertas Críticas
- **Contactar Urgente**: Candidatos nuevos sin contactar >2 días
- **DARDE Caducado**: Documentos DARDE vencidos o próximos a vencer
- **Seguimiento Retrasado**: Candidatos contactados sin seguimiento >7 días
- **Documentación Atrasada**: Documentos pendientes >5 días

### 📊 Estadísticas en Tiempo Real
- **Total de Candidatos** activos en el sistema
- **Candidatos Sin Contactar** que requieren atención inmediata
- **Documentación Pendiente** por completar
- **Candidatos Inscritos** exitosamente

### 🔍 Filtros Inteligentes
- Todos los candidatos
- Alertas urgentes
- Sin contactar
- Documentación pendiente
- En seguimiento
- Inscritos

### 👥 Gestión Completa de Candidatos
- **Vista detallada** con información completa
- **Progreso de documentación** visual con barras de progreso
- **Estados del candidato** con códigos de color
- **Acciones rápidas**: Ver, Llamar, Gestionar Documentos

## 🏗️ Arquitectura Técnica

### Tecnologías Utilizadas
- **Frontend**: HTML5, CSS3, JavaScript (Vanilla)
- **Styling**: CSS Grid, Flexbox, Gradientes modernos
- **Icons**: Emojis nativos para máxima compatibilidad
- **Responsive**: Diseño adaptativo para móviles y desktop

### Integración con Notion CRM
- **API de Notion**: Conectado con base de datos ID `2331685debec80b6a9f1ce7ccaf0a88c`
- **Token configurado**: Para acceso directo al CRM de producción
- **Sincronización**: Datos actualizables desde el dashboard

### Estructura de Datos
```json
{
  "candidato": {
    "id": "string",
    "nombre": "string",
    "apellidos": "string", 
    "email": "string",
    "telefono": "string",
    "municipio": "string",
    "delegacion": "LABORA|SEFCARM",
    "estado": "SIN CONTACTAR|CONTACTADO|DOC PENDIENTE|INSCRITO|LISTA ESPERA",
    "documentos": {
      "dni": boolean,
      "darde": boolean,
      "estudios": boolean,
      "progreso": number
    },
    "prioridad": "Alta|Media|Baja"
  }
}
```

## 🎨 Diseño y UX

### Paleta de Colores
- **Primario**: `#667eea` → `#764ba2` (Gradiente principal)
- **Éxito**: `#48bb78` (Candidatos inscritos)
- **Advertencia**: `#ecc94b` (Documentación pendiente)
- **Error**: `#e53e3e` (Alertas críticas)
- **Info**: `#4299e1` (Estados neutros)

### Estados Visuales
- 🔴 **Sin Contactar**: Requiere acción inmediata
- 🟠 **Contactado**: En proceso de seguimiento
- 🟡 **Doc Pendiente**: Esperando documentación
- 🟢 **Inscrito**: Proceso completado exitosamente
- 🟣 **Lista Espera**: Candidato en espera

## 📱 Responsividad

El dashboard está completamente optimizado para:
- **Desktop**: Experiencia completa con todas las funcionalidades
- **Tablet**: Adaptación de layouts para pantallas medianas
- **Mobile**: Interface simplificada y táctil para smartphones

## ⚡ Funcionalidades Avanzadas

### Sistema de Alertas Automatizado
```javascript
function getAlerta(candidate) {
  // Detección automática de:
  // - DARDE caducados o próximos a vencer
  // - Candidatos sin contactar >2 días
  // - Seguimientos retrasados >7 días
  // - Documentación atrasada >5 días
}
```

### Actualización en Tiempo Real
- **Refresh automático**: Botón de actualización conectado a Notion API
- **Estados dinámicos**: Cambios reflejados instantáneamente
- **Contadores en vivo**: Estadísticas actualizadas automáticamente

### Progreso de Documentación
- **Barra visual**: Progreso de 0% a 100%
- **Indicadores específicos**: DNI, DARDE, Certificados de Estudios
- **Alertas de vencimiento**: Para documentos con fecha límite

## 🔧 Configuración y Despliegue

### Variables de Configuración
```javascript
const CONFIG = {
  NOTION_TOKEN: "ntn_r604595300474rKE1mbXBmb3t1I5tSgaY6mCnThfkZAbEL",
  DATABASE_ID: "2331685debec80b6a9f1ce7ccaf0a88c",
  API_VERSION: "2022-06-28"
};
```

### Despliegue en GitHub Pages
1. **Repositorio**: `vinipurtan/crm-dashboard-avanza`
2. **Branch**: `main`
3. **Build**: Automático con GitHub Actions
4. **URL**: https://vinipurtan.github.io/crm-dashboard-avanza/

## 🎯 Casos de Uso Operativos

### Para Secretaría (Usuario Principal)
- **Inicio del día**: Revisar alertas críticas
- **Gestión diaria**: Filtrar candidatos por estado
- **Seguimiento**: Actualizar progreso de documentación
- **Contacto**: Registrar llamadas y cambios de estado

### Para Coordinadores
- **Supervisión**: Estadísticas generales del proceso
- **Planificación**: Identificar cuellos de botella
- **Reportes**: Datos para informes semanales

### Para Dirección
- **KPIs**: Métricas de conversión y eficiencia
- **Alertas estratégicas**: Problemas que requieren intervención
- **Tendencias**: Análisis del flujo de candidatos

## 📊 Métricas y Analíticas

### KPIs Monitoreados
- **Tiempo medio de contacto**: Desde registro hasta primer contacto
- **Tasa de conversión**: De candidato a inscrito
- **Documentación completada**: Porcentaje de docs completos
- **Alertas críticas**: Número de situaciones urgentes

### Reportes Disponibles
- **Diario**: Alertas y acciones pendientes
- **Semanal**: Estadísticas de conversión
- **Mensual**: Análisis de tendencias

## 🔒 Seguridad y Privacidad

### Cumplimiento RGPD
- **Datos personales**: Tratamiento conforme a RGPD
- **Consentimientos**: Registro de aceptaciones
- **Acceso limitado**: Solo personal autorizado

### Seguridad Técnica
- **HTTPS**: Todas las comunicaciones cifradas
- **Token de API**: Acceso controlado a Notion
- **Validación**: Sanitización de datos de entrada

## 🚀 Roadmap y Mejoras Futuras

### Funcionalidades Planificadas
- [ ] **Notificaciones push** para alertas críticas
- [ ] **Exportación de reportes** en PDF/Excel
- [ ] **Integración con calendarios** para citas
- [ ] **Chat interno** para comunicación del equipo
- [ ] **App móvil nativa** para iOS/Android

### Optimizaciones Técnicas
- [ ] **Service Workers** para funcionamiento offline
- [ ] **PWA** (Progressive Web App)
- [ ] **Caching inteligente** de datos
- [ ] **Sincronización bidireccional** con Notion

## 👥 Equipo del Proyecto

### Desarrollo
- **Arquitecto Senior de Bases de Datos**: Diseño y implementación del CRM
- **Consultor de Sistemas**: Optimización y integración

### Negocio
- **Secretaría LABORA**: Usuario principal y testing
- **Coordinación Avanza**: Validación de procesos

## 📞 Soporte y Contacto

### Soporte Técnico
- **Issues**: Reportar problemas en GitHub Issues
- **Documentación**: Wiki del proyecto
- **Actualizaciones**: Changelog automático

### Contacto Comercial
- **Empresa**: Avanza Formación
- **Delegaciones**: LABORA (Comunidad Valenciana), SEFCARM (Región de Murcia)
- **Web**: [Avanza Formación](https://avanzaformacion.es)

## 📄 Licencia

**Proyecto propietario** - Avanza Formación

Copyright © 2025 Avanza Formación. Todos los derechos reservados.

Este proyecto ha sido desarrollado específicamente para las operaciones internas de Avanza Formación y está protegido por derechos de autor.

---

**🎯 Desarrollado para optimizar la gestión operativa del CRM Avanza Formación**

![Avanza](https://img.shields.io/badge/Avanza-Formación-blue?style=for-the-badge)
![LABORA](https://img.shields.io/badge/LABORA-Comunidad%20Valenciana-orange?style=for-the-badge)
![SEFCARM](https://img.shields.io/badge/SEFCARM-Región%20de%20Murcia-red?style=for-the-badge)
