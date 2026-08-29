# Guía rápida: trabajar el repo desde VS Code

Ya no hace falta subir archivos uno por uno desde la web de GitHub.
Ahora el proyecto está en esta computadora y se trabaja desde VS Code.

**Carpeta del proyecto:** `C:\Users\diegg\Documents\GitHub\capstone-2026-siu-hub`

---

## Primera vez (solo una vez por persona)

### 1. Iniciar sesión en GitHub

Abre VS Code en la carpeta del proyecto y luego una terminal
(menú **Terminal → Nueva terminal**). Escribe:

```
gh auth login
```

Responde así:

| Pregunta | Respuesta |
|---|---|
| What account do you want to log into? | **GitHub.com** |
| What is your preferred protocol...? | **HTTPS** |
| Authenticate Git with your GitHub credentials? | **Yes** |
| How would you like to authenticate? | **Login with a web browser** |

Aparecerá un código de 8 caracteres (ej. `A1B2-C3D4`). Cópialo, presiona
Enter, se abre el navegador, pegas el código y autorizas. Listo.

### 2. Decir quién eres (para que los commits queden a tu nombre)

En la misma terminal, cambiando los datos por los tuyos:

```
git config --local user.name "Amanda Apellido"
git config --local user.email "correo-de-tu-cuenta-github@ejemplo.com"
```

> Usa el **mismo correo de tu cuenta de GitHub**, así los commits aparecen
> con tu foto y perfil.

Como esto es `--local`, queda guardado solo para este proyecto. Si después
se sienta otra persona en el mismo equipo, vuelve a correr estos dos
comandos con sus datos.

---

## El día a día (el ciclo de siempre)

Son cuatro pasos y todos se hacen desde el ícono de **Source Control** en la
barra lateral izquierda de VS Code (el de las ramitas, o `Ctrl+Shift+G`).

### 1. ANTES de empezar: traer lo último

Botón **⟳ Sync Changes** (o menú `...` → **Pull**).

> ⚠️ **Esto es lo más importante.** Hazlo siempre antes de tocar nada. Si dos
> personas editan sin hacer pull primero, aparecen conflictos.

### 2. Trabajar normal

Crea, edita, borra o arrastra archivos a la carpeta. Puedes arrastrar
**muchos archivos de una vez** — esa es toda la gracia de dejar de usar la web.

### 3. Guardar los cambios (commit)

En el panel de Source Control verás la lista de lo que cambió:

1. Escribe arriba un mensaje que diga **qué hiciste**
   (ej. `Agrega evidencias sesión 3` — mejor que `Update S01.md`)
2. Presiona el botón **✓ Commit**
3. Si pregunta por hacer "Stage" de todo, di que sí

### 4. Subir a GitHub (push)

Botón **Sync Changes** de nuevo. Eso sube tu commit y baja lo de los demás
al mismo tiempo.

---

## Resumen del ciclo

```
Sync (traer)  →  editar  →  escribir mensaje + Commit  →  Sync (subir)
```

---

## Preguntas comunes

**¿Qué pasa si alguien más subió algo mientras yo editaba?**
Al hacer Sync, Git une los cambios solo. Si dos personas tocaron *la misma
línea del mismo archivo*, VS Code muestra el conflicto en colores y te deja
elegir qué versión queda. No se pierde nada.

**¿Puedo subir archivos pesados (fotos, videos)?**
Fotos normales sí. Evita archivos de más de 100 MB: GitHub los rechaza.

**Me equivoqué y aún no hice commit.**
En Source Control, botón derecho sobre el archivo → **Discard Changes**.

**Ya hice commit pero no Sync.**
Menú `...` → **Commit** → **Undo Last Commit**. Los cambios vuelven a quedar
pendientes.

**No me deja subir / pide contraseña.**
Vuelve a correr `gh auth login`.
