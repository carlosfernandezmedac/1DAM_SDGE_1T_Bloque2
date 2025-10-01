# Tema 5: Entorno de instalación de Odoo

---

## 1. Introducción
En este tema nos centraremos en el **entorno de instalación de Odoo**, un ERP de **código libre** muy extendido.  
Existen distintas formas de instalarlo (**Online, Instalador, Instalar el código fuente, Docker**) y dos ediciones principales que debemos conocer:  

- **Versión comunitaria**:  
  - Mantenida por la comunidad de software libre.  
  - Código disponible en GitHub: https://github.com/odoo/  
  - Totalmente gratuita.  

- **Versión empresarial (Enterprise)**:  
  - Mantenida por Odoo S.A. (Bélgica).  
  - Incluye más funcionalidades y soporte técnico oficial.  
  - Acceso restringido a clientes y socios.  

👉 Desde la versión comunitaria se puede **migrar** en cualquier momento a la versión empresarial.

---

## 2. Requisitos hardware de Odoo
Odoo no da unos requisitos fijos, sino **fórmulas de dimensionamiento** en función del número de usuarios concurrentes.  

### Regla de oro para calcular trabajadores
```
Número de trabajadores = (#CPU × 2) + 1
```
- Cada trabajador puede dar servicio a unos **6 usuarios concurrentes**.  
- Ejemplo: con 2 CPUs → (2 × 2) + 1 = 5 trabajadores → hasta 30 usuarios concurrentes.  

### Cálculo de la memoria RAM
Odoo considera que:  
- El **80%** de las solicitudes son **ligeras** (≈ 150 MB de RAM por trabajador).  
- El **20%** son **pesadas** (≈ 1 GB de RAM por trabajador).  

**Fórmula aproximada**:  
```
RAM = nº de trabajadores × (80% × 150 MB + 20% × 1024 MB)
```

### Ejemplo de estimación
| Trabajadores | CPUs recomendadas | RAM estimada |
|------------------------|-------------------|--------------|
| 5            | 2 CPUs            | 2 GB RAM     |
| 20            | 4 CPUs            | 8 GB RAM     |
| 100+           | 16 CPUs           | 32 GB RAM    |

**Conclusión**:  
Para dimensionar bien un servidor Odoo hay que calcular primero el número de trabajadores en función de CPUs y luego estimar la RAM con la fórmula anterior.

---

## 3. Requisitos software según tipo de instalación

Odoo se puede instalar de diferentes formas, cada una con sus propios requisitos:

### 3.1. Versión online (SaaS)
- No requiere instalación en local.  
- Basta con un **navegador web** moderno (Chrome, Firefox, Edge, Safari).  
- Ventaja: no se gestiona infraestructura.  
- Inconveniente: dependencia del proveedor y coste mensual.

### 3.2. Instalador
- Disponible tanto para **comunitaria** como **enterprise**.  
- Sistemas soportados: **Windows**, distribuciones **Debian/Ubuntu** y distribuciones basadas en **RPM** (Fedora, CentOS, RHEL).  
- Requisitos extra:  
  - **PostgreSQL** en el mismo host (gestor de base de datos usado por Odoo).  

### 3.3. Código fuente
- Ofrece máxima flexibilidad, ideal para desarrolladores.  
- Igual que instalador en cuanto a sistemas soportados.  
- Requisitos adicionales:  
  - Descarga del código (ZIP o repositorio Git).  
  - **Python 3.6 o superior** (módulos de Odoo están en Python).  
  - Compilador C++ (Visual Studio Build Tools en Windows).  
  - **Git** para control de versiones.  

### 3.4. Docker
- Uso de la **imagen oficial de Odoo** desde Docker Hub.  
- Requisitos: tener Docker instalado y conocimientos básicos de contenedores.  
- Permite un despliegue rápido y reproducible.

---

## 4. Caso práctico: La ampliación de personal
**Situación**:  
- Una empresa usa Odoo comunitario en servidor local (2 CPUs, 2 GB RAM).  
- Funciona bien con 5 empleados, pero planea crecer mucho y añadir muchos más usuarios.  

**Problema**:  
- En momentos punta habrá decenas de usuarios concurrentes.  
- Se necesita **escalabilidad y soporte**.  

**Opciones**:  
1. **Ampliar el servidor actual** (más CPUs y RAM).  
2. Migrar a **Odoo Online (Enterprise)**, con escalabilidad en la nube y soporte oficial.  

**Decisión**:  
- La empresa elige **Odoo Cloud (Enterprise)**, porque garantiza escalabilidad futura y servicio técnico especializado.  

---

## 5. Resumen
- Odoo puede instalarse de varias formas: online, instalador, código fuente o Docker.  
- Existen dos ediciones: **Comunitaria** (gratis, GitHub) y **Enterprise** (comercial, con soporte).  
- La **regla de oro** permite calcular trabajadores según CPUs y dimensionar la infraestructura.  
- La RAM necesaria depende del nº de usuarios concurrentes y del tipo de carga.  
- En entornos de crecimiento, es recomendable optar por soluciones escalables como Odoo Cloud.  

---

## 6. Recursos y Webgrafía

📺 [Vídeo: Ejemplo con los cálculos hardware](https://bit.ly/3fhcG0E)  

- [Odoo](https://www.odoo.com/es_ES/)  
- [Repositorio Odoo en GitHub](https://github.com/odoo/)  

