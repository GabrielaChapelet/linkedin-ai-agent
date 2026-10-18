# 🚀 Automatización de Publicaciones: Trello + Make.com + IA + LinkedIn

Sistema integral de gestión editorial, enriquecimiento visual y publicación automatizada hacia LinkedIn, orquestado mediante **Trello**, **Make.com** e **Inteligencia Artificial**.

---

## 📌 Flujo de Trabajo (Workflow)
[ Trello: Ideas / Borradores ]
│
▼
[ Trello: Borradores Aprobados ]
│
│ (Disparador Butler: Mar y Jue @ 10:30)
▼
[ Trello: Aprobados ] ──(Webhook)──► [ Make.com: Router Condicional ]
│
┌──────────────────────────────────────┼──────────────────────────────────────┐
▼                                      ▼                                      ▼
[ Rama 1: Texto + Imagen ]            [ Rama 2: Solo Texto ]                [ Rama 3: Generación IA ]

Descarga adjunto de Trello          * Extrae texto de la tarjeta          * Genera imagen vía API

Sube multimedia a LinkedIn          * Publica post directo en LinkedIn    * Sube multimedia generada

Publica post con imagen                                                   * Publica post en LinkedIn
│                                      │                                      │
└──────────────────────────────────────┴──────────────────────────────────────┘
│
▼
[ Trello: Publicados ]


---

## ⚙️ Componentes del Sistema

### 1. Tablero Kanban (Trello)
* **`Ideas / Borradores`:** Espacio de redacción y preparación inicial de temas.
* **`Borradores Aprobados`:** Cola de contenido revisado listo para entrar al calendario.
* **`Aprobados`:** Lista detonante. Al recibir una tarjeta, activa el Webhook de Make.
* **`Publicados`:** Historial de publicaciones enviadas con éxito.

### 2. Programador Automático (Trello Butler)
* **Frecuencia:** Martes y Jueves a las 10:30 (Europe/Madrid).
* **Acción:** Mueve 1 tarjeta aleatoria desde `Borradores Aprobados` a `Aprobados`.
* **Regla Butler:**

* every 1 weeks on tuesday, thursday at 10:30 am, move 1 randomly-selected cards from list "Borradores Aprobados" to list "Aprobados"
* *(Si no hay tarjetas en la lista de borradores, la comprobación finaliza en vacío sin errores ni consumo de operaciones).*

### 3. Orquestación y Enrutamiento (Make.com)
* **Trigger:** Webhook instantáneo conectado a Trello.
* **Router inteligente:**
* **Ruta Multimedia:** Si la tarjeta tiene imagen adjunta, la procesa y publica en LinkedIn como post con imagen.
* **Ruta de Texto plano:** Si no contiene imagen, formatea y publica el post en formato texto respetando saltos de línea.
* **Ruta IA (Pollinations):** Si requiere recurso visual dinámico, genera la imagen automáticamente y la adjunta.
* **Cierre de estado:** Mueve la tarjeta en Trello a `Publicados` tras la confirmación de la API de LinkedIn.

---

## 🛠️ Tecnologías Utilizadas

* **Trello:** Gestión de contenido y automatizaciones nativas Butler.
* **Make.com:** Orquestación de webhooks, lógica condicional y llamadas API REST.
* **LinkedIn API:** Publicación automatizada de estados y assets multimedia.
* **Pollinations / IA:** Generación dinámica de recursos visuales.

---

## 📦 Instrucciones para Replicar el Proyecto

1. Clona o descarga los archivos `.json` incluidos en este repositorio.
2. En **Make.com**, crea un escenario nuevo y selecciona **Import Blueprint** desde el menú inferior (`...`).
3. Conecta tus credenciales personales en los módulos correspondientes:
 * Conexión de Trello (seleccionando tu Tablero y Listas).
 * Conexión de LinkedIn (autorizando permisos de publicación).
4. Configura en Trello la regla periódica de Butler con tus días y horarios preferidos.
