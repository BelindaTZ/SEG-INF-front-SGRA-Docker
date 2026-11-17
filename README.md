# Frontend

## Docker Desktop

Abre Docker Desktop en modo de contenedores Linux. Coloca `SEG-INF-front-SGRA-Docker` y
`SEG-INF-back-SGRA-Docker` en la misma carpeta. Prepara el archivo `SEG-INF-back-SGRA-Docker/.env.docker`
siguiendo la sección Docker Desktop del README del backend.

Desde `SEG-INF-front-SGRA-Docker`:

```powershell
docker compose up --build -d
docker compose ps
```

Abre [SGRA](http://localhost:4200). Compose crea dos contenedores en el
proyecto `sgra`. Nginx sirve la compilación de Angular, conserva la
navegación a rutas internas al recargar y reenvía `/api` y `/archivos-sgra`
al backend por la red interna. El navegador usa el mismo origen para las
cookies de sesión. El backend no publica su puerto en el host.

Usa `docker compose logs -f backend` para consultar el arranque y
`docker compose down` para detener ambos servicios. Si necesitas cambiar la
ubicación del backend, configura `SGRA_BACKEND_DIR`. Si el puerto 4200 está
ocupado, configura `SGRA_PORT` antes de ejecutar Compose.

This project was generated using [Angular CLI](https://github.com/angular/angular-cli) version 21.1.4.

## Development server

To start a local development server, run:

```bash
ng serve
```

Once the server is running, open your browser and navigate to `http://localhost:4200/`. The application will automatically reload whenever you modify any of the source files.

## Code scaffolding

Angular CLI includes powerful code scaffolding tools. To generate a new component, run:

```bash
ng generate component component-name
```

For a complete list of available schematics (such as `components`, `directives`, or `pipes`), run:

```bash
ng generate --help
```

## Building

To build the project run:

```bash
ng build
```

This will compile your project and store the build artifacts in the `dist/` directory. By default, the production build optimizes your application for performance and speed.

## Running unit tests

To execute unit tests with the [Vitest](https://vitest.dev/) test runner, use the following command:

```bash
ng test
```

## Running end-to-end tests

For end-to-end (e2e) testing, run:

```bash
ng e2e
```

Angular CLI does not come with an end-to-end testing framework by default. You can choose one that suits your needs.

## Additional Resources

For more information on using the Angular CLI, including detailed command references, visit the [Angular CLI Overview and Command Reference](https://angular.dev/tools/cli) page.
