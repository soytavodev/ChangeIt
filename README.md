# ChangeIt!

Conversor de euros a otras monedas. Obtiene las tasas de cambio de una API pública y, si hay una base de datos configurada, guarda cada conversión en un historial.

Fue mi primer proyecto de 1.º de DAM.

Capturas: [gustavo-delnardo.vercel.app/portfolio/changeit](https://gustavo-delnardo.vercel.app/portfolio/changeit)

## Qué hace

- Consulta las tasas de cambio del euro en [open.er-api.com](https://open.er-api.com) (API gratuita que se actualiza una vez al día) y muestra unas 160 monedas con su nombre en español.
- Convierte una cantidad en euros a la moneda elegida.
- Valida la cantidad en el servidor con `filter_input` y comprueba que la moneda exista en la respuesta de la API.
- Guarda cada conversión en la tabla `historial` de MySQL con una consulta preparada (`mysqli`). El historial es opcional: sin base de datos, el conversor funciona igual.
- Si la API no responde, el desplegable muestra un aviso de error.

## Tecnologías

- PHP
- MySQL (opcional, para el historial)
- HTML y CSS
- API REST con respuestas en JSON

## Estructura

```text
ChangeIt/
├── config/
│   └── db.php.example   # Plantilla de conexión (copiar como db.php)
├── css/style.css
├── img/
├── sql/setup.sql        # Base de datos y tablas
└── index.php            # Conversor
```

## Instalación en local

1. Clona el repositorio:
   ```bash
   git clone https://github.com/soytavodev/ChangeIt.git
   cd ChangeIt
   ```
2. Arranca el servidor de PHP y abre `http://localhost:8000`:
   ```bash
   php -S localhost:8000
   ```

Para guardar el historial (opcional):

1. Crea la base de datos con `mysql -u root -p < sql/setup.sql`.
2. Copia `config/db.php.example` como `config/db.php` y pon tus datos de MySQL. Necesitas la extensión `mysqli` de PHP.

## Autor

Gustavo Delnardo · [GitHub](https://github.com/soytavodev) · [Web](https://gustavo-delnardo.vercel.app)
