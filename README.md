# Dishonored MissionStats — Edición en español

> **Fork en español** de [Dishonored MissionStats](https://github.com/adm244/Dishonored-MissionStats),
> un **mod nativo** para *Dishonored* (Arkane Studios) que añade un botón de **estadísticas** al menú
> de pausa y avisa en pantalla de ciertos eventos de la misión.

**Nuestro objetivo con este fork** es **acercar el mod al público hispanohablante** y hacerlo **fácil
de usar y de personalizar**, sin necesidad de tocar código:

- 📖 **Documentación en español**: descripción, instalación y configuración explicadas paso a paso.
- 🗣️ **Textos traducidos al español** (botón, avisos y contador de monedas) listos para usar.
- 🎛️ **Configuración sencilla**: un solo archivo `.ini` editable con el Bloc de notas para activar o
  desactivar funciones y cambiar cualquier texto (ideal para traducir a otros idiomas).
- 🔎 **Guía de problemas frecuentes** y notas para que no tengas sorpresas al instalarlo.

> Si buscas el texto original en inglés, consérvalo en [`README.en.md`](README.en.md).

---

## Índice

1. [¿Qué hace este mod?](#1-qué-hace-este-mod)
2. [Características](#2-características)
3. [Sobre este fork](#3-sobre-este-fork)
4. [Requisitos](#4-requisitos)
5. [Instalación](#5-instalación)
6. [Configuración y personalización](#6-configuración-y-personalización)
7. [Solución de problemas](#7-solución-de-problemas)
8. [Compilación desde el código fuente](#8-compilación-desde-el-código-fuente)
9. [Compatibilidad](#9-compatibilidad)
10. [Créditos y licencia](#10-créditos-y-licencia)

---

## 1. ¿Qué hace este mod?

En *Dishonored*, las estadísticas de la misión (alarmas, cuerpos encontrados, detecciones, bajas,
monedas, etc.) solo se ven **al terminar** la misión. Este mod añade un botón **«Estadísticas»** al
**menú de pausa** para consultarlas **en mitad de la partida**, reutilizando la pantalla de resultados
original del juego.

![Botón Estadísticas en el menú de pausa](https://staticdelivery.nexusmods.com/mods/802/images/17/17-1575764585-1536986851.png)

Además, **vigila ciertos eventos** mientras juegas y muestra un aviso en el HUD la primera vez que
ocurren:

- 🚨 **Alarma activada** (solo una vez);
- 🕵️ **Cuerpo encontrado** (solo una vez);
- 👁️ **Te han detectado** (solo una vez);
- ⚔️ **Has matado a un hostil o a un civil** (solo una vez);
- 🪙 **Monedas recogidas** (contador continuo `recogidas / total`).

![Avisos en pantalla durante la partida](https://staticdelivery.nexusmods.com/mods/802/images/17/17-1575764636-1730046211.png)

**Todo es opcional y configurable**: puedes activar o desactivar cada aviso (y el propio botón) y
cambiar cualquier texto desde un archivo de configuración.

---

## 2. Características

| Característica | Descripción |
|---|---|
| **Estadísticas a mitad de misión** | Botón nuevo en el menú de pausa que abre la pantalla de resultados con los datos actuales. |
| **Cálculo de caos** | Muestra el nivel de caos (bajo/alto) de la misión en curso. |
| **Acciones especiales** | Refleja banderas como «Fantasma» o «Manos limpias» según tu progreso. |
| **Avisos configurables** | Alarma, cuerpo, detección, bajas y monedas, cada uno con su interruptor. |
| **Multi-idioma** | Los textos se cargan desde el `.ini` en **UTF-8**: puedes traducirlo a cualquier idioma. |
| **Sin tocar el juego** | Todo se ejecuta en memoria; no modifica archivos del juego. |
| **Compatible con DLC** | Soporta *The Knife of Dunwall* y *The Brigmore Witches* (no son obligatorios). |

---

## 3. Sobre este fork

Este repositorio es un **fork** del proyecto original de **Adam Worgen (adm244)**. El código del mod
se mantiene **sin cambios funcionales**; lo que aporta este fork es **toda la capa de usuario**, para
que instalar, entender y personalizar el mod sea mucho más fácil:

| Aspecto | Proyecto original | Este fork |
|---|---|---|
| Documentación | README breve en inglés | **README completo en español** + el original conservado en `README.en.md` |
| Textos del mod | En inglés | **Traducidos al español** en `data/missionstats.ini` (y original en `data/missionstats.en.ini`) |
| Guía de configuración | No detallada | **Tabla de todas las opciones y textos**, con notas y ejemplos |
| Instalación | 2 líneas | **Paso a paso**, con avisos y solución de problemas |
| Personalización | «Hay un archivo de config» | **Explícita**: activar/desactivar funciones y traducir a otros idiomas |

> **Filosofía del fork:** que puedas disfrutar del mod leyendo solo este README, **sin abrir código
> ni saber programar**. La idea es que *acercar el mod al español* sea el punto de partida, no la
> meta: también queremos documentar, facilitar el acceso y hacerlo personalizable.

**Atribución:** el mérito del mod es del autor original. Este fork solo añade documentación y
traducción, y respeta su licencia de dominio público.

---

## 4. Requisitos

| Requisito | Detalle |
|---|---|
| **Sistema** | Windows (32 bits o 64 bits; el juego es de 32 bits). |
| **Juego** | *Dishonored* (versión para PC, Steam o GOG) con el soporte de los DLC *The Knife of Dunwall* y *The Brigmore Witches* (los DLC **no** son obligatorios). |
| **Nada más** | **No** necesitas inyector de DLL ni programas externos: el mod se carga solo al arrancar el juego. |
| **Permisos** | Poder escribir en la carpeta de instalación del juego (si está en `C:\Program Files`, quizá necesites permisos de administrador). |
| **Opcional** | [DebugView](https://learn.microsoft.com/sysinternals/downloads/debugview) para ver mensajes de diagnóstico si algo no funciona. |

> ⚠️ **Importante:** este mod está pensado **solo** para la versión del juego que incluye el soporte
> de los DLC mencionados. En otras versiones o con modificaciones del `.exe` puede no funcionar o
> provocar errores.

---

## 5. Instalación

El mod consta de **dos archivos**: la **DLL** y su **archivo de configuración**. Solo hay que
copiarlos en la carpeta del juego con los nombres correctos.

### Paso 0 — Haz una copia de seguridad (recomendado)

Abre la carpeta `Dishonored\Binaries\Win32` y comprueba si ya existe un `dinput8.dll` (a veces lo
crean otros mods). Si lo hay, **guárdalo aparte** antes de continuar.

### Paso 1 — Consigue `dinput8.dll`

Elige **una** de estas opciones:

- **Opción A (recomendada):** descarga el binario desde la sección **Releases** de este repositorio
  (si está disponible).
- **Opción B:** compílalo tú mismo siguiendo la [sección 8](#8-compilación-desde-el-código-fuente).
  El resultado se llama `missionstats.dll` y luego lo renombras.

### Paso 2 — Coloca la DLL

1. Copia el binario dentro de `...\Dishonored\Binaries\Win32`.
2. **Renómbralo a `dinput8.dll`** (así es como el juego lo carga automáticamente; no se necesita
   inyector).

> 💡 Ruta típica en Steam: `C:\Program Files (x86)\Steam\steamapps\common\Dishonored\Binaries\Win32`
> Ruta típica en GOG: `C:\GOG Games\Dishonored\Binaries\Win32`

### Paso 3 — Coloca la configuración

1. Toma el archivo [`data/missionstats.ini`](data/missionstats.ini) de este repositorio (ya está **en
   español**).
2. **Renómbralo a `dinput8.ini`** y déjalo **en la misma carpeta** que la DLL.

> ⚠️ **Muy importante:** el mod busca el archivo de configuración con **el mismo nombre que la DLL**.
> Como la DLL se llama `dinput8.dll`, la configuración **debe** llamarse `dinput8.ini`. Si los nombres
> no coinciden, el mod se ejecuta con los valores por defecto y **no** cargará tu configuración.

### Paso 4 — Comprueba el resultado

Al terminar, la carpeta debe quedar así:

```
Dishonored\Binaries\Win32\
├── Dishonored.exe
├── dinput8.dll        <-- el mod (renombrado)
├── dinput8.ini        <-- tu configuración (en español)
└── ... (resto de archivos del juego)
```

Arranca el juego, pausa durante una misión y busca el botón **«ESTADÍSTICAS»** en el menú.

### Notas de instalación

* **Carpeta `NativeMods`:** el README original mencionaba copiar una carpeta `NativeMods`. Esa carpeta
  **no existe en este repositorio** y no es necesaria aquí: para este mod bastan la DLL y el `.ini`.
  Si tu distribución incluye una carpeta `NativeMods`, cópiala junto al ejecutable tal como indique su
  autor.
* **GOG:** si juegas en GOG, **no** inicies el juego a través del cliente **Galaxy** (es un problema
  conocido). Lánzalo directamente desde `Dishonored.exe`.
* **Desinstalar:** borra `dinput8.dll` y `dinput8.ini` (y restaura el `dinput8.dll` original si lo
  tenías). No queda nada más modificado.

---

## 6. Configuración y personalización

Toda la personalización se hace en el archivo **`dinput8.ini`** (el `data/missionstats.ini` de este
repositorio, renombrado). Se edita con cualquier editor de texto (**Bloc de notas**, Notepad++,
VS Code…).

> 🔄 **Se lee una sola vez, al arrancar el juego.** Después de cambiar el archivo, **cierra y vuelve a
> abrir el juego** para que se apliquen los cambios.
>
> 📝 **Guarda siempre en UTF-8.** Si usas el Bloc de notas, elige *UTF-8* en «Codificación» al guardar.
> Así los acentos y las eñes se muestran correctamente.

### 6.1. Estructura del archivo

El archivo tiene **dos secciones**:

```ini
[Strings]      ; los TEXTOS que se muestran en pantalla (aquí es donde "traduces")
[Options]      ; los INTERRUPTORES que activan o desactivan cada función
```

* Las líneas que empiezan por **`;`** son **comentarios** y no se tienen en cuenta.
* Los textos van **entre comillas y precedidos de `L`**: `L"como este ejemplo"`. Ese `L` es
  obligatorio (indica que el texto se lee como UTF-16 desde tu UTF-8).
* Los valores `true`/`false` activan o desactivan una opción.

### 6.2. Sección `[Options]` — activar y desactivar funciones

| Clave | Qué controla | `true` | `false` |
|---|---|---|---|
| `bAddStatsButton` | El **botón «Estadísticas»** en el menú de pausa. | Añade el botón | No añade el botón |
| `bShowAlarm` | Aviso **«Alarma activada»**. | Muestra el aviso | No lo muestra |
| `bShowBodyFound` | Aviso **«Cuerpo encontrado»**. | Muestra el aviso | No lo muestra |
| `bShowSpotted` | Aviso **«Te han detectado»**. | Muestra el aviso | No lo muestra |
| `bShowKilled` | Aviso **«Has matado a alguien»**. | Muestra el aviso | No lo muestra |
| `bShowCoinsCollected` | Contador de **monedas recogidas**. | Muestra el contador | No lo muestra |

Ejemplo: **solo quiero el botón, sin avisos**

```ini
[Options]
bAddStatsButton = true
bShowAlarm = false
bShowBodyFound = false
bShowSpotted = false
bShowKilled = false
bShowCoinsCollected = false
```

Ejemplo: **solo avisos importantes, sin el contador de monedas**

```ini
[Options]
bAddStatsButton = true
bShowAlarm = true
bShowBodyFound = true
bShowSpotted = true
bShowKilled = true
bShowCoinsCollected = false
```

> ℹ️ Si **dejas el archivo vacío o con una clave mal escrita**, el mod usa sus **valores por defecto**:
> botón **activado**; avisos de detección, bajas y monedas **activados**; avisos de **alarma y cuerpo
> desactivados**. Para no llevarte sorpresas, escribe siempre todas las claves.

### 6.3. Sección `[Strings]` — cambiar los textos

Aquí es donde **personalizas o traduces** todo lo que se muestra en pantalla.

| Clave | Cuándo se muestra | Texto en español (por defecto en este fork) |
|---|---|---|
| `btnStatsText` | Texto del **botón** del menú de pausa. | `L"ESTADÍSTICAS"` |
| `msgAlarm` | Al **activarse una alarma**. | `L"Alarma activada"` |
| `msgBodyFound` | Al **encontrar un cuerpo**. | `L"Cuerpo encontrado"` |
| `msgSpotted` | Al **ser detectado**. | `L"Te han detectado"` |
| `msgKilled` | Al **matar** a un hostil o civil. | `L"Has matado a alguien"` |
| `msgCoinsCollected` | Cada vez que **recoges monedas**. | `L"Recogidas %g de %d monedas"` |

### 6.4. Notas sobre el contador de monedas

`msgCoinsCollected` es el **único** texto con **comodines de formato**:

* **`%g`** → se sustituye por las **monedas recogidas** hasta el momento (número).
* **`%d`** → se sustituye por el **total de monedas** de la misión (número).

> ⚠️ Si borras `%g` o `%d`, o cambias su orden, el contador mostrará cifras incorrectas o textos
> raros. Mantenlos siempre que quieras que aparezcan los números. Ejemplo válido:
> `L"Monedas: %g/%d"`.

### 6.5. Cómo traducir el mod a **otro idioma**

Es muy sencillo: **no cambies las claves**, solo los textos entre comillas.

```ini
[Strings]
btnStatsText = L"STATS"
msgAlarm = L"Alarm triggered"
msgBodyFound = L"Body found"
msgSpotted = L"You were detected"
msgKilled = L"You killed someone"
msgCoinsCollected = L"Coins: %g of %d"
```

Pasos:

1. Abre el `.ini` con un editor de texto.
2. Traduce **solo** el contenido de las comillas.
3. Conserva **exactamente** los nombres de las claves (`btnStatsText`, `msgAlarm`, …) y el `L` antes
   de las comillas.
4. Guarda en **UTF-8** y reinicia el juego.

> Comparte tu traducción: puedes publicarla como un `.ini` alternativo. En este repositorio tienes
> `data/missionstats.ini` (**español**) y `data/missionstats.en.ini` (**inglés original**) como
> ejemplos de partida.

### 6.6. Archivo completo de ejemplo (español, todo activado)

```ini
; MissionStats mod config file
; Make sure all strings are encoded as UTF-8

; Version 1.1 - Español

[Strings]
btnStatsText = L"ESTADÍSTICAS"
msgAlarm = L"Alarma activada"
msgBodyFound = L"Cuerpo encontrado"
msgSpotted = L"Te han detectado"
msgKilled = L"Has matado a alguien"
msgCoinsCollected = L"Recogidas %g de %d monedas"

[Options]
bAddStatsButton = true
bShowAlarm = true
bShowBodyFound = true
bShowSpotted = true
bShowKilled = true
bShowCoinsCollected = true
```

---

## 7. Solución de problemas

| Síntoma | Causa probable y solución |
|---|---|
| **No aparece el botón «ESTADÍSTICAS»** | Comprueba que `bAddStatsButton = true`, que reiniciaste el juego y que el archivo se llama `dinput8.ini` y está en la **misma carpeta** que `dinput8.dll`. |
| **El botón aparece atenuado / no se puede pulsar** | Es el comportamiento normal: se bloquea si **no** estás en una misión o si aún no hay estadísticas. Cárgate una partida y prueba. |
| **No aparece ningún aviso en pantalla** | Revisa que el aviso correspondiente esté en `true` en `[Options]`. Recuerda que alarma y cuerpo están **desactivados** si no los pones explícitamente en `true`. |
| **El juego no arranca o se cierra al inicio** | Tu versión del juego probablemente **no coincide** con la soportada. Borra `dinput8.dll`/`dinput8.ini` y restaura el `dinput8.dll` original si lo había. |
| **Acentos o eñes salen como símbolos raros** | El archivo **no** está guardado en **UTF-8**. Vuelve a guardarlo indicando esa codificación. |
| **El contador de monedas muestra números o texto raros** | Al editar `msgCoinsCollected` has cambiado o eliminado `%g` / `%d`. Restáuralos. |
| **Con GOG no funciona** | No lo lances por **Galaxy**. Ejecuta `Dishonored.exe` directamente. |
| **Conflicto con otro mod** | Dos mods no pueden ocupar a la vez el nombre `dinput8.dll`. Desinstala el otro mod o busca una versión compatible. |
| **Sin pistas de qué falla** | Usa **DebugView** (arrancado como administrador) y busca mensajes del mod, como `InitPatches: …` o `ReadConfig: …`. |

Si nada de esto soluciona el problema, abre un *issue* en el repositorio indicando: versión del juego
(Steam/GOG), idioma, y qué archivos `.ini` usaste.

---

## 8. Compilación desde el código fuente

Si prefieres compilar el mod tú mismo (o no encuentras un binario ya compilado), necesitas **Visual
Studio** con las herramientas de C++ (MSVC). El mod se compila como **una sola unidad**.

### Opción rápida (línea de comandos)

Abre el **Símbolo del sistema para desarrolladores de VS x86** (*x86 Native Tools Command Prompt*) y,
desde la carpeta del repositorio, ejecuta:

```bat
cl /O2 /WX /nologo /LD /I code\common /Fe"missionstats" code\main.cpp /link kernel32.lib
```

Se genera **`missionstats.dll`** → renómbralo a **`dinput8.dll`** (ver [sección 5](#5-instalación)).

### Opción `build.bat`

El repositorio incluye `tools/build.bat`, pensado para el *toolchain* **cdev**. Requiere dos cosas:

* las variables de entorno de **cdev** (`%source%`, `%bin%`, `%tools%`, `%project%`);
* el **DirectX SDK (junio 2010)** instalado (`%DXSDK_DIR%`), porque el script enlaza `d3dx9.lib`.

> ℹ️ **Nota:** el mod **no** usa DirectX para nada en su versión funcional (el archivo `code/d3dhook.cpp`
> es un experimento que **no** se compila). Por eso la opción rápida funciona **sin** DirectX SDK.

---

## 9. Compatibilidad

El mod está desarrollado para una **versión concreta** del ejecutable del juego (la última que
incluye soporte para los DLC). Esto no es una limitación de este fork, sino de la técnica que usa el
mod (reescribe instrucciones de máquina del `.exe` en direcciones fijas).

| Versión del juego | Estado |
|---|---|
| Última versión con soporte de **The Knife of Dunwall** y **The Brigmore Witches** (Steam/GOG) | ✅ Compatible |
| DLC *The Knife of Dunwall* / *The Brigmore Witches* | ✅ Soportados (y **opcionales**) |
| Otras versiones / ejecutables modificados (p. ej. parches de terceros, «no-CD») | ❌ No garantizado; puede fallar o provocar errores |

> 🧩 Si el juego se actualiza o cambias de versión y el mod deja de funcionar, **desinstálalo** (borra
> los dos archivos) hasta que se adapte a la nueva versión.

---

## 10. Créditos y licencia

### 👏 Créditos

* **Mod original y código:** *Adam Worgen* (**adm244**) — [repositorio original](https://github.com/adm244/Dishonored-MissionStats).
  Todo el mérito de esta obra es suyo.
* **Este fork (documentación en español, traducción de textos y guía de personalización):** **zl0wly**.

### 📜 Licencia

Este software se publica en el **dominio público** (licencia *Unlicense*). Puedes copiarlo, modificarlo,
publicarlo, usarlo, compilarlo, venderlo o distribuirlo libremente, tanto con fines comerciales como
no comerciales.

El texto completo está en el archivo [`LICENSE`](LICENSE).

> Se distribuye **TAL CUAL**, sin garantía de ningún tipo. Úsalo bajo tu propia responsabilidad.

---

## 📎 Recursos del repositorio

| Documento | Para qué sirve |
|---|---|
| [`README.md`](README.md) | Este documento (español): uso, instalación y configuración. |
| [`README.en.md`](README.en.md) | README original en inglés (conservado). |
| [`data/missionstats.ini`](data/missionstats.ini) | Configuración **en español** (plantilla lista para usar). |
| [`data/missionstats.en.ini`](data/missionstats.en.ini) | Configuración **en inglés** original. |
| [`code/`](code) | Código fuente completo del mod. |
| [`tools/`](tools) | Scripts de compilación del *toolchain* cdev. |

---

*¿Te ha resultado útil? Deja una estrella ⭐ y, si mejoras algo, ¡envía tu aporte!*

