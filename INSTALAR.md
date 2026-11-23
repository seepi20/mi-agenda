# Instalar Mi Agenda en tu iPhone (gratis, con SideStore)

SideStore renueva la app **desde el propio iPhone**, sin PC. El PC solo hace falta una vez, para instalar SideStore.

## Atajo rápido: añadir a la pantalla de inicio (sin SideStore)

Sube el proyecto a GitHub (comandos de la Parte 1, con el repositorio **público**). Luego en GitHub: **Settings → Pages → Source: GitHub Actions**. Cuando termine "Publicar web", tu dirección será `https://TU_USUARIO.github.io/mi-agenda/`. Ábrela en **Safari** en el iPhone → Compartir → **Añadir a pantalla de inicio**. No caduca, pero los avisos solo suenan con la app abierta; para avisos con la app cerrada usa la versión nativa de abajo.

## Parte 1 · Obtener el archivo de la app (.ipa)

1. Crea una cuenta gratuita en https://github.com y un repositorio nuevo (privado vale), por ejemplo `mi-agenda`.
2. Instala Git (https://git-scm.com) y, desde esta carpeta, en PowerShell:
   ```powershell
   git init -b main
   git add .
   git commit -m "Mi Agenda"
   git remote add origin https://github.com/TU_USUARIO/mi-agenda.git
   git push -u origin main
   ```
3. En GitHub: pestaña **Actions** → "Build iOS (IPA sin firmar)" → espera ~10 min.
4. Entra en esa ejecución, baja a **Artifacts** y descarga `Mi-Agenda-ipa`. Descomprime el zip: dentro está `Mi-Agenda.ipa`.
5. Pasa el `.ipa` al iPhone (iCloud Drive, AirDrop, correo a ti mismo…) y guárdalo en la app **Archivos**.

## Parte 2 · Instalar SideStore (una sola vez, con el PC)

Los pasos exactos cambian con el tiempo: sigue la guía oficial en https://sidestore.io y consulta https://github.com/nab138/iloader. Resumen:

1. En el iPhone instala **LocalDevVPN** desde la App Store.
2. En el PC instala **iTunes** (versión de la web de Apple) y **iloader** (https://github.com/nab138/iloader).
3. Conecta el iPhone por USB, pulsa "Confiar", abre iloader, inicia sesión con tu Apple ID y elige **instalar SideStore** (crea también el archivo de emparejamiento).
4. En el iPhone: Ajustes → General → VPN y gestión de dispositivos → confía en tu Apple ID. Activa el **Modo desarrollador** (Ajustes → Privacidad y seguridad) y reinicia.
5. Abre SideStore e importa el archivo de emparejamiento si te lo pide.

## Parte 3 · Instalar y renovar Mi Agenda (desde el móvil)

1. Abre **LocalDevVPN** y conéctalo.
2. Abre SideStore → **My Apps** → **+** → elige `Mi-Agenda.ipa`.
3. Abre Mi Agenda y **permite las notificaciones**.
4. **Renovar:** con LocalDevVPN conectado, abre SideStore → My Apps → pulsa los "X DAYS" junto a la app. Hazlo cada 3-4 días. SideStore también puede renovar solo en segundo plano si LocalDevVPN está conectado.

Si el archivo de emparejamiento se invalida (reset del iPhone o actualización de iOS), hay que volver a generarlo con el PC.

## Actualizar la app

`git add . ; git commit -m "cambios" ; git push`, baja el nuevo `.ipa` de Actions e instálalo con **+** en SideStore. Se instala encima y **conserva tus datos**.

## Notas

- Cuenta gratuita de Apple: la app caduca a los 7 días si no se renueva (los datos no se pierden). Máximo 3 apps.
- Haz copias de vez en cuando: Ajustes → Exportar datos.
- Para que **nunca** caduque haría falta la cuenta de pago de Apple (99 $/año).
