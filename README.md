<div align="center">

# 📰 Reportajes Interactivos

### Periodismo inmersivo, libre y sin código

*Crea reportajes con scroll animado, gráficos, audio, video y portadas a pantalla completa directamente desde el navegador.*

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

Una aplicación web de una sola página que funciona como un **CMS de periodismo interactivo**. Pensada para estudiantes y docentes que necesitan publicar reportajes inmersivos **sin pagar nada** y **sin saber programar**. Cada autor inicia sesión con su cuenta de Google, arma su reportaje con bloques arrastrables y lo comparte con un enlace público.

> Construida como herramienta docente para cursos de Periodismo, sobre infraestructura 100% gratuita (GitHub Pages + Firebase Spark + ImgBB).

---

## 🧩 Bloques disponibles

| | Bloque | Qué hace |
|---|---|---|
| 🎬 | **Portada** | Pantalla completa con imagen o video de fondo y título animado |
| 🌄 | **Imagen full** | Imagen a pantalla completa con texto superpuesto |
| 📊 | **Gráfico** | Barras, líneas o torta — se animan al entrar en pantalla |
| 🎞️ | **Secuencia** | Las imágenes cambian a medida que avanzas (scrollytelling) |
| 🌠 | **Galería animada** | Fotos que entran desde la izquierda, el centro y la derecha |
| 🔍 | **Antes / Después** | Comparación de dos imágenes con control deslizante |
| 🔢 | **Cifra** | Un gran número que cuenta solo |
| 🕓 | **Línea de tiempo** | Cronología de hitos |
| 🎧 | **Audio** | 3 reproductores: Tecnológico, Retro (Winamp) y Spotify |
| 🎥 | **Video** | Embebido desde YouTube o Vimeo |
| 🌐 | **HTML / Embed** | Inserta Flourish, Genially, Datawrapper, Knight Lab… |

Más: título, subtítulo, párrafo, cita, imagen y separador.

---

## 🎨 Características

- 🔐 **Login con Google** — cada autor ve solo sus propios reportajes
- 🎭 **3 estilos visuales** — Editorial, Revista y Cine
- ✨ **Glassmorphism** opcional y **revelado palabra por palabra**
- 🌗 **Modo claro / oscuro** para la edición
- 🖼️ **Subida de imágenes** integrada (ImgBB)
- 📜 **Efectos de scroll** — parallax, zoom, reveal y scrollytelling
- 📑 **Índice lateral** y **tiempo de lectura** automáticos
- 🔗 **Publicación con URL pública**, compatible con móviles
- 💾 **Autoguardado** en la nube

---

## 👤 Autor

<div align="center">

### **Rolando Araos Millar**
**Docente de Periodismo**
Universidad Autónoma de Chile

</div>

---

## 🚀 ¿Quieres tu propia copia?

Esta herramienta es libre. Cualquiera puede duplicarla y usarla con sus estudiantes. Necesitas tu **propio** Firebase (gratis) porque ahí se guardan los reportajes de tus usuarios.

<details>
<summary><b>📦 Pasos para montar tu copia (haz clic para desplegar)</b></summary>

<br>

1. **Duplica el repositorio** con el botón verde **"Use this template"** (o haz *fork*).
2. **Crea un proyecto en [Firebase](https://console.firebase.google.com)** (plan Spark, gratis).
   - Activa **Authentication → Google**.
   - Crea **Firestore Database** (modo producción) y pega las reglas de seguridad (más abajo).
3. **Copia tu configuración** de Firebase y reemplázala en `index.html` (el bloque `firebaseConfig`).
4. **Autoriza tu dominio** en Authentication → Configuración → Dominios autorizados → `tu-usuario.github.io`.
5. **Crea una API key gratuita en [ImgBB](https://api.imgbb.com)** y reemplázala en `index.html` (`IMGBB_KEY`).
6. **Activa GitHub Pages** en Settings → Pages → rama `main`.
7. La primera vez, Firestore te pedirá **crear un índice** con un clic (aparece un enlace en la consola del navegador, F12).

### Reglas de seguridad de Firestore

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /reportajes/{id} {
      allow read: if resource.data.publicado == true
                  || (request.auth != null && request.auth.uid == resource.data.ownerUid);
      allow create: if request.auth != null
                    && request.auth.uid == request.resource.data.ownerUid;
      allow update, delete: if request.auth != null
                            && request.auth.uid == resource.data.ownerUid;
    }
  }
}
```

</details>

---

## 🛠️ Stack

`HTML + CSS + JavaScript` (sin frameworks) · `Firebase Auth + Firestore` · `Chart.js` · `ImgBB` · `GitHub Pages`

---

<div align="center">

Un desarrollo de **Rolando Araos Millar** · Docente de Periodismo, Universidad Autónoma de Chile

<sub>Licencia MIT — libre para usar, modificar y compartir.</sub>

</div>
