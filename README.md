# Frontend

## Docker Desktop

Abre Docker Desktop en modo de contenedores Linux. Desde la raíz de este
repositorio, usa `compose.yml` para iniciar solo el frontend:

```powershell
docker compose up --build -d
docker compose ps
```

Abre [SGRA](http://localhost:4200). Nginx sirve la compilación y conserva las
rutas internas al recargar. Para usar el inicio de sesión y las demás
funciones de SGRA, inicia el backend desde el `compose.yml` de
`SEG-INF-back-SGRA-Docker` después de completar su `.env.docker`. Nginx
reenvía `/api` y `/archivos-sgra` a `host.docker.internal:8080` y conserva
el mismo origen en el navegador para las cookies de sesión.

Si cambias `SGRA_BACKEND_PORT`, usa el mismo valor al iniciar ambos
proyectos. Usa `SGRA_PORT` para cambiar el puerto local del frontend.
`docker compose down` en esta carpeta detiene solo el frontend.

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
