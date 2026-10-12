# PharmasysPreview

Previa de 2019 del sistema de ventas para farmacias Pharmasys: un prototipo en PHP plano, jQuery y Bootstrap que luego dio origen a [Pharmasys](https://github.com/thealejandro/Pharmasys).

- Estado: **archivo histórico**. No se mantiene ni funciona tal cual (ver abajo).
- La página de GitHub Pages del repo (https://xacodev.github.io/PharmasysPreview/) solo muestra el tema Jekyll por defecto; GitHub Pages no ejecuta PHP, así que no sirve la aplicación.

## Relación con otros repos

| Repo | Qué es |
|---|---|
| **XACodev/PharmasysPreview** (este) | Prototipo original de 2019. |
| [thealejandro/Pharmasys](https://github.com/thealejandro/Pharmasys) | Sistema en producción (Laravel 6, privado). |
| [thealejandro/PharmasysApp](https://github.com/thealejandro/PharmasysApp) | Reescritura en Laravel 10 + Livewire, alpha. |
| [thealejandro/xPharma](https://github.com/thealejandro/xPharma) | Esqueleto de 2025 en Laravel 12 + React/TypeScript. |

## Qué contiene

- `InLog.php`: pantalla de inicio de sesión (solo maqueta: `login.js` compara el usuario con un valor fijo y redirige a `Home`, sin validar contra la base).
- `Home.php` + `Home.js`: pantalla principal con el menú del sistema. Cada botón carga en un `iframe` la pantalla correspondiente de `Functions/`: Vender, Ventas, Inventarios, Cierre de Caja, Pedidos, Compras, Vencimientos, Ajustes, Ver Solicitudes y Pedidos Bodega. Ya aparece aquí el conjunto de módulos que después tuvo Pharmasys.
- `Functions/`: una página por módulo con su CSS en `Functions/CSS/`. La más desarrollada es Compras (buscar producto, ver e insertar compras, modificar y devolver, alta de productos); las demás son maquetas.
- `DB/`: scripts PHP que responden a peticiones AJAX de `JS/` consultando una base SQL Server (`sqlsrv_*`): búsqueda de productos, categorías y casas, precios y stock, compras y verificación de facturas.
- `JS/`: scripts jQuery de cada función, más Bootstrap 4, iCheck y jQuery empaquetados.
- `CSS/`, `img/`: estilos y logotipo.

## Stack

| Componente | Detalle |
|---|---|
| Servidor | PHP (hosting compartido con Apache) con la extensión `sqlsrv` |
| Base de datos | Microsoft SQL Server (Azure SQL) |
| Front | HTML, CSS, jQuery 2.2, Bootstrap 4, iCheck |

No hay gestor de dependencias, script de instalación ni esquema de base de datos en el repo; las tablas (`tbproducto`, `tbinventario`, `tbcompra`, `tbcategoria`, `tbcasa`, etc.) solo se conocen por las consultas en `DB/`.

## Ejecutarlo hoy

No es práctico: requiere una base SQL Server con el esquema original y una conexión configurada en `DB/SQLconection.php`. Se conserva como referencia de cómo empezó el proyecto; para el sistema vigente, ver Pharmasys.

## Licencia

Software propietario de XACode. Todos los derechos reservados.
