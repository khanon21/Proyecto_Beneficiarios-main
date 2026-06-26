<img width="180" height="120" alt="0" src="https://github.com/user-attachments/assets/2b0c846c-de3e-42fe-b90d-a91ca492362c" />
<img width="1600" height="503" alt="0" src="https://github.com/user-attachments/assets/5d39acc1-abc3-4c4d-9b44-38e7f1e12510" />
<img width="1600" height="495" alt="0" src="https://github.com/user-attachments/assets/3e0f93f8-e977-495d-abf0-983efff47580" />
<img width="1515" height="773" alt="0" src="https://github.com/user-attachments/assets/ad6d8beb-e5a3-497f-9b43-ca79978d68a2" />
<img width="1600" height="519" alt="0" src="https://github.com/user-attachments/assets/f842ce7f-a55b-4be1-9819-d1e01e52c135" />
<img width="1516" height="773" alt="0" src="https://github.com/user-attachments/assets/4de1f179-33d4-41f5-83e4-49d2593b2c0e" />
Introducción

La transformación digital ha impulsado el desarrollo de sistemas de información que permiten automatizar procesos administrativos, mejorar la gestión de datos y optimizar la prestación de servicios en diferentes organizaciones. Dentro de este contexto surge el Proyecto Beneficiarios, una aplicación web diseñada para administrar de manera eficiente la información relacionada con los beneficiarios de un programa o institución.

El propósito principal del sistema es proporcionar una plataforma que facilite el almacenamiento, consulta, actualización y eliminación de información mediante una interfaz intuitiva, garantizando rapidez, seguridad e integridad de los datos. Para lograr este objetivo se implementó una arquitectura basada en el patrón Modelo-Vista-Controlador (MVC), la cual permite separar las responsabilidades de la aplicación, favoreciendo un desarrollo organizado, escalable y de fácil mantenimiento.

La solución fue desarrollada utilizando Next.js como framework principal para la construcción de la aplicación web, React para la creación de interfaces dinámicas e interactivas y MySQL como sistema gestor de bases de datos, garantizando un manejo eficiente de la información y una comunicación adecuada entre la capa de presentación y la base de datos mediante servicios API.

El sistema incorpora módulos especializados para la administración de localidades, discapacidades, hechos, sexo y zonas de colegio, implementando operaciones CRUD completas que permiten gestionar cada uno de estos registros de forma sencilla y segura.

Además de satisfacer los requerimientos funcionales planteados, el proyecto aplica buenas prácticas de desarrollo de software, organización modular del código y una arquitectura que facilita futuras ampliaciones, convirtiéndose en una base sólida para el desarrollo de aplicaciones empresariales orientadas a la gestión de información.

En conjunto, este proyecto representa una solución tecnológica que contribuye a la modernización de los procesos administrativos, mejora la calidad de la información y fortalece la eficiencia operativa mediante el uso de herramientas de desarrollo web actuales.
# Proyecto Beneficiarios

Sistema de gestión de beneficiarios, patrón **MVC**, hecho con **Next.js (App Router) + MySQL**.

## Módulos incluidos (todos con CRUD completo: consultar, crear, actualizar, eliminar)

| Módulo | Ruta | Tabla en BD |
|---|---|---|
| Localidades | /localidades | Localidad |
| Discapacidad | /discapacidad | Discapacidad |
| Hechos | /hechos | Hechos |
| Sexo | /sexo | Sexo |
| Zona Colegio | /zona | Zona_colegio |

## Estructura MVC

```
db/             -> conexión a MySQL (connection.js)
models/         -> lógica SQL de cada tabla
app/api/        -> controladores (rutas API REST)
app/<modulo>/   -> vistas (React) + su CSS exclusivo
app/Header.js   -> menú de navegación global
```

## Instalación y puesta en marcha (XAMPP)

### 1. Base de datos
1. Inicia Apache y MySQL en XAMPP.
2. Ve a http://localhost/phpmyadmin
3. Crea una base de datos llamada `proyecto_beneficiario`.
4. Pestaña Importar -> selecciona `proyecto_beneficiario.sql` (incluido en este proyecto) -> Importar.

### 2. Variables de entorno
Renombra el archivo `env-ejemplo.txt` a `.env.local` (debe quedar en la raíz del proyecto) y ajusta tus credenciales si es necesario:

```
DATABASE_URL="mysql://root:@localhost:3306/proyecto_beneficiario"
```

### 3. Instalar dependencias
```
npm install
```

### 4. Ejecutar
```
npm run dev
```

Abre http://localhost:3000

## Notas
- El proyecto usa mysql2 con un pool de conexiones (ver db/connection.js).
- Cada módulo es independiente: modelo propio, controlador propio (GET/POST y PUT/DELETE por id) y vista propia con su CSS exclusivo (CSS Modules, sin Tailwind).
- Para agregar un nuevo módulo, copia la estructura de "sexo" (la más simple, 1 columna) o de "localidades" (2 columnas) y ajusta nombres de tabla/columnas.
