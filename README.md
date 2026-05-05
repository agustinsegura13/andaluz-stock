# GroceryStock Pro

App web para gestión de productos de retail — escaneo de códigos de barra, edición de nombres y exportación a Excel.

## Funciones

- Importar catálogo desde Excel (.xlsx) o CSV
- Escanear códigos de barra con la cámara del celular
- Buscar productos por SKU o nombre
- Editar nombre y precio de cada producto
- Seleccionar productos para exportar
- Exportar a Excel (.xlsx) listo para cargar en el POS
- Funciona como PWA (se instala en el celular)

---

## Cómo subir a Vercel (gratis, 5 minutos)

### Opción A — Sin instalar nada (recomendado)

1. Entrá a [github.com](https://github.com) y creá una cuenta gratuita si no tenés.
2. Creá un repositorio nuevo (botón verde "New"), nombre: `grocerystock`, dejalo público.
3. Subí todos estos archivos arrastrándolos al repositorio.
4. Entrá a [vercel.com](https://vercel.com) → "Sign up" → conectá con tu cuenta de GitHub.
5. Hacé clic en "Add New Project" → seleccioná el repositorio `grocerystock`.
6. Sin cambiar nada, hacé clic en **Deploy**.
7. En 1 minuto te da una URL tipo `grocerystock.vercel.app`. ¡Listo!

### Opción B — Con Git (para quien ya sabe)

```bash
npm install -g vercel
cd grocerystock
vercel
```

---

## Estructura del proyecto

```
grocerystock/
├── index.html          ← Toda la app (un solo archivo)
├── vercel.json         ← Configuración de Vercel
├── README.md           ← Este archivo
└── public/
    └── manifest.json   ← Para instalar como app en el celular
```

---

## Instalar en el celular como app

**Android (Chrome):**
1. Abrí la URL en Chrome
2. Tocá los 3 puntitos → "Agregar a pantalla de inicio"

**iPhone (Safari):**
1. Abrí la URL en Safari
2. Tocá el botón Compartir → "Agregar a la pantalla de inicio"

---

## Formato del archivo a importar

El archivo Excel o CSV debe tener estas columnas en la primera fila:

| sku | nombre | precio |
|-----|--------|--------|
| 7792070001 | Coca-Cola 500ml | 850 |
| 7791287001 | Galletitas Oreo | 1200 |

- La columna `sku` es obligatoria
- La columna `nombre` (o `name` o `descripcion`) es obligatoria  
- La columna `precio` es opcional

---

## Notas

- Los datos se guardan solo mientras la pestaña del navegador esté abierta.
- Para que persistan entre sesiones, en el futuro se puede agregar guardado con `localStorage`.
- La exportación genera un archivo `.xlsx` compatible con Excel, Calc, y la mayoría de sistemas POS.
