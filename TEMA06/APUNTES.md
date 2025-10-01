# Tema 6: Tipos de instalación de Odoo

---

## 1. Introducción
En este tema veremos los diferentes **tipos de instalación de Odoo** y qué opciones tenemos en función de los recursos técnicos y económicos de la empresa.  

Odoo se puede instalar de distintas formas:  
- **Versión Online (SaaS)**  
- **Instalador (Windows, Debian, RPM)**  
- **Código fuente (GitHub o ZIP)**  
- **Docker**  

Además, Odoo existe en **dos ediciones**:  
- **Community** → gratuita, de código abierto, licencia LGPLv3.  
- **Enterprise** → de pago, con módulos avanzados y soporte oficial.  

---

## 2. Tipos de instalación de Odoo

### 2.1. Versión Online (SaaS)
- Disponible en la web oficial de Odoo como **Odoo Online**.  
- No requiere instalación en el PC, solo un **navegador web**.  
- Incluye una **demo gratuita** (por horas) para probar módulos.  
- Plan gratuito inicial → pocos módulos, usuarios ilimitados.  
- Para más módulos o funcionalidades → suscripción mensual (Enterprise).  
- ✔️ Ventajas: sin preocupaciones de hardware, mantenimiento ni backups.  
- ❌ Desventajas: dependencia total del proveedor.  

---

### 2.2. Instalación con instalador
- Disponible para **Community** y **Enterprise**.  
- Sistemas soportados:  
  - **Windows** (ejecutable fácil para usuarios finales).  
  - **Debian/Ubuntu** (paquetes `.deb`).  
  - **CentOS/Fedora/RHEL** (paquetes `.rpm`).  

Ejemplo en Debian/Ubuntu:  
```bash
# Añadir clave y repositorio
sudo apt install postgresql -y
wget -O - https://nightly.odoo.com/odoo.key | apt-key add -
echo "deb http://nightly.odoo.com/13.0/nightly/deb/ ./" >> /etc/apt/sources.list.d/odoo.list
apt-get update && apt-get install odoo
```

Ejemplo en CentOS/Fedora:  
```bash
sudo dnf config-manager --add-repo=https://nightly.odoo.com/13.0/nightly/rpm/odoo.repo
sudo dnf install -y odoo
```

✔️ Ventajas: rápido, sencillo, todo se instala como servicio.  
❌ Desventaja: menos práctico para modificar código fuente.  

---

### 2.3. Instalación desde código fuente
- Descarga directa desde **GitHub** o en archivo `.zip`.  
- Requiere instalar manualmente dependencias:  
  - **Python 3.6+**  
  - **PostgreSQL**  
  - Librerías Python (`pip install -r requirements.txt`)  
- Ejecución con:  
```bash
python odoo-bin -r usuario -w contraseña --addons-path=addons -d basedatos
```

✔️ Ventajas: ideal para **desarrolladores**, se puede modificar el código y crear módulos personalizados.  
❌ Desventajas: mayor complejidad técnica.  

---

### 2.4. Instalación con Docker
- Odoo dispone de **imagen oficial en Docker Hub**.  
- Se levanta en un contenedor con un simple comando:  
```bash
docker run -p 8069:8069 --name odoo --link db:db -t odoo:16
```

✔️ Ventajas: despliegue rápido, reproducible y portable.  
❌ Desventajas: requiere conocimientos de Docker.  

---

## 3. Caso práctico: “Eligiendo la instalación correcta”
**Planteamiento**:  
- Usuario con **Windows**.  
- Solo quiere usar Odoo como usuario final, sin conocimientos de programación, Git o bases de datos.  

**Solución**:  
- Descargar e instalar el **ejecutable de Windows**.  
- Este incluye todo lo necesario (PostgreSQL, dependencias).  
- Se puede usar tanto con **Community** como con **Enterprise**.  

---

## 4. Resumen
- Odoo puede instalarse en distintas modalidades según necesidades: SaaS, instalador, código fuente y Docker.  
- **Community** → gratis, abierta, con lo esencial.  
- **Enterprise** → de pago, con módulos avanzados y soporte oficial.  
- Para un **usuario final sin conocimientos técnicos** → instalador de Windows.  
- Para **desarrolladores** → instalación desde código fuente o Docker.  
- Para **empresas que buscan simplicidad y escalabilidad** → Odoo Online (SaaS).  

---

## 5. Recursos y Webgrafía

📺 [Vídeo: Odoo versión SaaS](https://bit.ly/3fuUqkE)  
📺 [Vídeo: Odoo versión con instalador](https://bit.ly/2AXh4Dt)  
📺 [Vídeo: Odoo con código fuente](https://bit.ly/38RmAnC)  

- [Odoo](https://www.odoo.com/es_ES/)  
- [Repositorio Odoo en GitHub](https://github.com/odoo/)  

