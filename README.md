<div align="center">

# 📰 Reportajes Interactivos

### Periodismo inmersivo, libre y sin código

*Crea reportajes con scroll animado, gráficos, audio, video y portadas a pantalla completa directamente desde el navegador — y ahora, en equipo y en tiempo real.*

<br>

![status](https://img.shields.io/badge/estado-en%20producción-2c7a45?style=for-the-badge)
![licencia](https://img.shields.io/badge/licencia-MIT-2D4ECC?style=for-the-badge)
![costo](https://img.shields.io/badge/costo-100%25%20gratis-E8A13A?style=for-the-badge)

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=flat-square&logo=firebase&logoColor=black)
![Chart.js](https://img.shields.io/badge/Chart.js-FF6384?style=flat-square&logo=chartdotjs&logoColor=white)

</div>

---

## ✨ ¿Qué es esto?

Una aplicación web de una sola página que funciona como un **CMS de periodismo interactivo**. Pensada para estudiantes y docentes que necesitan publicar reportajes inmersivos **sin pagar nada** y **sin saber programar**. Cada autor inicia sesión con su cuenta de Google, arma su reportaje con bloques y lo comparte con un enlace público — y puede **invitar a compañeros a editar el mismo reportaje a la vez**.

> Construida como herramienta docente para cursos de Periodismo, sobre infraestructura 100% gratuita (GitHub Pages + Firebase Spark + ImgBB).

---

## 🧩 Bloques disponibles

| | Bloque | Qué hace |
|---|---|---|
| 🎬 | **Portada** | Pantalla completa con imagen o video de fondo y título animado |
| 🌄 | **Imagen full** | Imagen a pantalla completa con texto superpuesto |
| 📊 | **Gráfico** | Barras, líneas o torta — se animan al entrar en pantalla |
| 🎞️ | **Secuencia** | Las imágenes cambian a medida que avanzas (scrollytelling) |
| 🌠 | **Galería animada** | Fotos que entran desde la izquierda, el centro y la derecha, con texto sobre degradado |
| 🔍 | **Antes / Después** | Comparación de dos imágenes con control deslizante |
| 🔢 | **Cifra** | Un gran número que cuenta solo |
| 🕓 | **Línea de tiempo** | Cronología de hitos |
| 🎧 | **Audio** | 3 reproductores: Tecnológico, Retro (Winamp) y Spotify |
| 🎥 | **Video** | Embebido desde YouTube o Vimeo |
| 🌐 | **HTML / Embed** | Inserta Flourish, Genially, Datawrapper, Knight Lab… |

M�s: título, subtítulo, párrafo, cita, imagen y separador.

---

## 🎨 Características

- 👥 **Edición colaborativa en tiempo real** — varios autores editan el mismo reportaje a la vez y ven los cambios en vivo
- 🔐 **Login con Google** — cada autor ve sus propios reportajes y los que le comparten
- 🎭 **3 estilos visuales** — Editorial, Revista y Cine
- ✨ **Glassmorphism** opcional y **revelado palabra por palabra**
- 🌗 **Modo claro / oscuro** para la edición
- 🖼️ **Subida de imágenes** integrada (ImgBB)
- 📜 **Efectos de scroll** — parallax, zoom, reveal y scrollytelling
- 📑 **Índice lateral** y **tiempo de lectura** automáticos
- 🔗 **Publicación con URL pública**, compatible con móviles
- 💾 **Autoguardado** en la nube

---

## 👥 Cómo funciona la colaboración

El autor de un reportaje pulsa **👥 Colaboradores**, agrega los correos Gmail de su equipo y listo: esas personas verán el reportaje en su panel marcado como **Compartido** y podrán editarlo. Los cambios de cada quien aparecen en vivo en la pantalla de los demás. Mientras alguien escribe en un bloque no se le interrumpe; al soltarlo, el resto se sincroniza. Solo el autor original puede gestionar la lista de colaboradores y eliminar el reportaje.

> **Nota:** si dos personas editan el **mismo bloque** en el mismo instante, gana el último que guarda. Repartiéndose secciones distintas, el trabajo en equipo fluye sin perder nada.

---

## 👤 Autor

<div align="center">

### **Rolando Araos Millar**
**Docente de Periodismo**
Universidad Autónoma de Chile

</div>

---

## 🚀 Crea tu propia copia (para otros docentes o equipos)

Esta herramienta es **libre**. Cualquier docente o equipo puede tener su propia versión, con sus propios reportajes y estudiantes. Cada copia necesita su **propio proyecto de Firebase** (gratis) porque ahí se guardan los datos de *tus* usuarios. No necesitas saber programar: es copiar, pegar dos claves y activar un par de cosas con clics.

<details>
<summary><b>📦 Guía paso a paso (haz clic para desplegar)</b></summary>

<br>

**1. Duplica el repositorio**
Pulsa el botón verde **"Use this template" → Create a new repository** (o haz *fork*).

**2. Crea tu proyecto en Firebase** (plan Spark, gratis) en [console.firebase.google.com](https://console.firebase.google.com)
- **Authentication → Sign-in method → Google:** actívalo.
- **Firestore Database → Crear base de datos** (modo producción).

**3. Conecta tu Firebase a la app**
En tu proyecto Firebase → ⚙️ *Configuración del proyecto* → *Tus apps* → ícono **</>** (web), registra una app y copia el bloque `firebaseConfig`. Pégalo en `index.html` reemplazando el que viene de ejemplo.

**4. Pega las reglas de seguridad**
En **Firestore → Reglas**, pega las reglas de más abajo y publica.

**5. Crea el índice de colaboración** (una sola vez, lo haces tú y queda para todos tus usuarios)
En **Firestore → Índices → Crear índice**:
- Colección: `reportajes`
- Campo 1: `editores` → **Arrays**
- Campo 2: `updatedAt` → **Descending**

**6. Autoriza tu dominio**
En **Authentication → Configuración → Dominios autorizados**, agrega `tu-usuario.github.io`.

**7. Pon tu propia clave de ImgBB**
Crea una clave gratuita en [api.imgbb.com](https://api.imgbb.com) y reemplaza el valor de `IMGBB_KEY` en `index.html` por la tuya. *(Importante: usa la tuya; si dejas la de otra persona, consumes su cuota de subida de imágenes.)*

**8. Publica con GitHub Pages**
En **Settings → Pages → Branch: `main`**. En 1-2 minutos tu app estará en línea.

</details>

### 🔐 Reglas de seguridad de Firestore

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /reportajes/{id} {
      allow read: if resource.data.publicado == true
                  || (request.auth != null && request.auth.uid == resource.data.ownerUid)
                  || (request.auth != null && request.auth.token.email in resource.data.get('editores', []));
      allow create: if request.auth != null
                    && request.auth.uid == request.resource.data.ownerUid;
      allow update: if request.auth != null && (
                      request.auth.uid == resource.data.ownerUid
                      || ( request.auth.token.email in resource.data.get('editores', [])
                           && request.resource.data.ownerUid == resource.data.ownerUid
                           && request.resource.data.get('editores', []) == resource.data.get('editores', []) )
                    );
      allow delete: if request.auth != null
                    && request.auth.uid == resource.data.ownerUid;
    }
  }
}
```

Estas reglas permiten leer los reportajes publicados, y editar solo al autor y a los colaboradores que él invite. Borrar queda reservado al autor, y un colaborador no puede cambiar al dueño ni alterar la lista de invitados.

---

## 🛠️ Stack

`HTML + CSS + JavaScript` (sin frameworks) · `Firebase Auth + Firestore (tiempo real)` · `Chart.js` · `ImgBB` · `GitHub Pages`

---

<div align="center">

Un desarrollo de **Rolando Araos Millar** · Docente de Periodismo, Universidad Autónoma de Chile

<sub>Licencia MIT — libre para usar, modificar y compartir.</sub>

</div>
