# Follow View — Owlbear Rodeo

Extensión para que el **GM fije la vista de un jugador a un personaje**. La cámara de ese jugador se centra en la ficha y la sigue cuando se mueve.

## Instalar

1. Activá GitHub Pages en este repo (`Settings → Pages → Deploy from branch main / root`).
2. Manifest:
   `https://maxnannij.github.io/Owlbear-Follow-View/manifest.json`
3. En Owlbear: perfil → Add Extension → pegá esa URL → habilitala en la sala.

## Uso (GM)

1. Abrí el panel **Follow View**.
2. Elegí el **jugador**.
3. Elegí el **personaje** (o seleccionálo antes en el mapa).
4. **Fijar vista a este personaje**.
5. La cámara de ese jugador se centra y sigue el token.

Para soltar: **Quitar seguimiento** o **Quitar todos**.

## Cómo funciona

- El GM guarda asignaciones `jugador → itemId` en metadata de la sala.
- El script de fondo de cada cliente lee su asignación y llama a `OBR.viewport.setPosition` cuando se mueve el token.
- Solo afecta la vista del jugador asignado (el SDK no permite mover la cámara de otro desde el GM).

## Limitaciones

- El jugador puede seguir paneando manualmente; al moverse el token, la vista se recentra.
- Si el token se borra, el seguimiento queda huérfano hasta que el GM lo quite o reasigne.
