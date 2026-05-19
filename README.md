# Proyecto The Wine Square v2620

## Creación del proyecto

> [!CAUTION]
> **En el caso de estar en un equipo MAC:**
> - Debe anteceder el comando `sudo` al ejecutar las instrucciones: `ng` y `chown`, y luego ingresar la contraseña del Administrador (`d3v3l0p3rUPC`).
> - Debe ubicarse en la carpeta `/Users/alumnos/IdeaProjects/1asi0729/202620` o en otra de su preferencia.

> [!CAUTION]
> **En el caso de estar en un equipo Windows:**
> - Debe ubicarse en la carpeta `IdeaProjects/` o en otra de su preferencia.

A continuación se detalla las instrucciones para crear un nuevo `workspace` e `initial starter app` de Angular. Más información en: https://angular.dev/tools/cli/setup-local

### Creación de un workspace y un initial application

**Cargar** el `Terminal` del sistema Operativo, ubicarse en la carpeta de su preferencia de acuerdo al Sistema Operativo y **ejecutar** el siguiente CLI command:

```bash
ng new eanrcucode
```

Reemplace `eanrcucode` por el nombre real del proyecto (por ejemplo `ea20262u201821873`).

Después de ejecutar el CLI command, le mostrará diferentes opciones y debe escoger las siguientes:

_? Which stylesheet format would you like to use?_, **Seleccionar**:

```
CSS  [ https://developer.mozilla.org/docs/Web/CSS ]
```

_? Do you want to enable Server-Side Rendering (SSR) and Static Site Generation (SSG/Prerendering)?_, **digitar**:

```
N
```

_? Do you want to create a 'zoneless' application without zone.js? (y/N)_, **digitar**:

```
N
```

_? Which AI tools do you want to configure with Angular best practices?_ `(Press <space> to select, <a> to toggle all, <i> to invert selection, and <enter> to proceed)`, **Seleccionar**:

```
(*) GitHub Copilot
(*) JetBrains AI Assistant
```

Se creará el proyecto e iniciará la instalación de packages.

### Instalación de Angular Material

> [!CAUTION]
> **En el caso de estar en un equipo MAC:**
> - Debe anteceder el comando `sudo` al ejecutar las instrucciones: `ng` y luego ingresar la contraseña del Administrador.

A continuación se detalla las instrucciones para instalar `Angular Material` al proyecto Angular. Más información en: https://material.angular.io/guide/getting-started

**Ingresar** a la carpeta creada con el mismo nombre que el proyecto **ejecutando** el siguiente command:

```
cd eanrcucode
```

**Agregar** Angular Material a la aplicación, **ejecute** el siguiente CLI command:

```
ng add @angular/material
```

Después de ejecutar el CLI command, le mostrará diferentes opciones y debe escoger las siguientes:

_? Select a pair of starter prebuilt color palettes for your Angular Material theme_, **seleccionar**:

```
Azure/Blue   [Preview: https://material.angular.dev?theme=azure-blue]
```

### Instalando Internationalization en/es

A continuación se detalla las instrucciones para instalar los libraries de internacionalización (i18n) para Angular: **@ngx-translate**. Más información en: https://github.com/ngx-translate/core

**Ejecutar** el siguiente command:

```
npm install @ngx-translate/core @ngx-translate/http-loader --save
```

### Instalando Json-server

A continuación se detalla las instrucciones para instalar un `full fake REST API` sin codificación denominado: **JSON Server**. Más información en: https://github.com/typicode/json-server/tree/v0

**Ejecutar** el siguiente command:

```
npm install -g json-server@0.17.4
```

### Cambiar el propietario del proyecto creado con sudo (Solo MAC)

> [!CAUTION]
> **Solo ejecutar si estas en un equipo MAC:**

**Ejecutar** los siguientes commands:

```
cd ..
```

```
sudo chown -R alumnos ./eanrcucode
```

```
ls -l
```

## Desarrollo del proyecto

**Cargar** el JetBrains WebStorm y **abrir** el proyecto ubicado en la carpeta de su preferencia.

**Cargar** el `Terminal` del IDE y **ejecutar** el siguiente CLI command:

```
ng serve --port 4200
```

### Creación de los Archivos de idiomas

**Crear** las carpetas: `assets` e `i18n` en la carpeta :file_folder: `public` ubicado en la raíz del proyecto:

```markdown
- 📂 public
  - 📁 assets
    - 📁 i18n
```

**Crear** los archivos `en.json` y `es.json` en la carpeta :file_folder: `i18n` con el siguiente contenido:

#### en.json

```json
{
  "option": {
    "home": "Home",
    "new-preservation-item": "New Preservation Item"
  },
  "home": {
    "title": "Home",
    "content": "Engineered Products for Wine Cellars.",
    "my-wine-cellars": "My Wine Cellars"
  },
  "cellar-summary": {
    "total-bottles": "Total Bottles",
    "available-capacity": "Available Capacity",
    "empty": "Empty"
  },
  "new-preservation-item": {
    "title": "New Preservation Item",
    "subtitle": "Add Wine Bottles to Your Cellar",
    "wine-type": "Wine Type",
    "wine": "Wine",
    "quantity": "Quantity",
    "create": "Create",
    "cancel": "Cancel",
    "select-wine-type": "Select a wine type",
    "select-wine": "Select a wine",
    "quantity-required": "Quantity is required",
    "quantity-min": "Quantity must be at least 1",
    "quantity-exceeds": "Quantity exceeds available capacity ({{ available }})",
    "wine-required": "Wine is required",
    "wine-type-required": "Wine type is required"
  },
  "wine-type": {
    "reds": "Reds",
    "whites": "Whites",
    "sparkling": "Sparkling",
    "rose": "Rosé",
    "dessert": "Dessert",
    "port": "Port"
  },
  "page-not-found": {
    "title": "Page not found",
    "content": "The path <strong>{{ invalidPath }}</strong> is not valid.",
    "go-home": "Go Home"
  },
  "footer": {
    "rights": "All rights reserved.",
    "powered-by": "Powered by",
    "and": "and"
  }
}
```

#### es.json

```json
{
  "option": {
    "home": "Inicio",
    "new-preservation-item": "Nuevo Artículo de Conservación"
  },
  "home": {
    "title": "Inicio",
    "content": "Productos de ingeniería para bodegas de vino.",
    "my-wine-cellars": "Mis Bodegas de Vino"
  },
  "cellar-summary": {
    "total-bottles": "Total de Botellas",
    "available-capacity": "Capacidad Disponible",
    "empty": "Vacío"
  },
  "new-preservation-item": {
    "title": "Nuevo Artículo de Conservación",
    "subtitle": "Añade botellas de vino a tu bodega",
    "wine-type": "Tipo de Vino",
    "wine": "Vino",
    "quantity": "Cantidad",
    "create": "Crear",
    "cancel": "Cancelar",
    "select-wine-type": "Seleccionar un tipo de vino",
    "select-wine": "Seleccionar un vino",
    "quantity-required": "La cantidad es obligatoria",
    "quantity-min": "La cantidad debe ser al menos 1",
    "quantity-exceeds": "La cantidad excede la capacidad disponible ({{ available }})",
    "wine-required": "El vino es obligatorio",
    "wine-type-required": "El tipo de vino es obligatorio"
  },
  "wine-type": {
    "reds": "Tintos",
    "whites": "Blancos",
    "sparkling": "Espumantes",
    "rose": "Rosados",
    "dessert": "Postre",
    "port": "Oporto"
  },
  "page-not-found": {
    "title": "Página no encontrada",
    "content": "La ruta <strong>{{ invalidPath }}</strong> no es válida.",
    "go-home": "Ir a Inicio"
  },
  "footer": {
    "rights": "Todos los derechos reservados.",
    "powered-by": "Desarrollado con",
    "and": "y"
  }
}
```

### Configuración de JSON-Server

**Crear** la carpeta `server` en la carpeta raíz del proyecto:

```markdown
- 📂 eanrcucode
  - 📁 server
```

**Crear** el archivo `db.json` en la carpeta `server` con el siguiente contenido:

#### db.json

```json
{
  "cellars": [
    { "id": 1, "name": "Reds Cellar",      "wineType": "reds",      "capacity": 500 },
    { "id": 2, "name": "Whites Cellar",    "wineType": "whites",    "capacity": 400 },
    { "id": 3, "name": "Sparkling Cellar", "wineType": "sparkling", "capacity": 300 },
    { "id": 4, "name": "Rosé Cellar",      "wineType": "rose",      "capacity": 250 },
    { "id": 5, "name": "Dessert Cellar",   "wineType": "dessert",   "capacity": 200 },
    { "id": 6, "name": "Port Cellar",      "wineType": "port",      "capacity": 180 }
  ],
  "preservation-items": [
    {
      "id": 1,
      "cellarId": 1,
      "wineType": "reds",
      "wineId": 1,
      "wineName": "Eszencia 1999",
      "quantity": 42,
      "registeredAt": "2026-05-10T14:30:00.000Z"
    },
    {
      "id": 2,
      "cellarId": 1,
      "wineType": "reds",
      "wineId": 12,
      "wineName": "Vega Sicilia Único",
      "quantity": 18,
      "registeredAt": "2026-05-12T09:15:00.000Z"
    },
    {
      "id": 3,
      "cellarId": 2,
      "wineType": "whites",
      "wineId": 101,
      "wineName": "Cloudy Bay Sauvignon Blanc",
      "quantity": 35,
      "registeredAt": "2026-05-13T16:45:00.000Z"
    },
    {
      "id": 4,
      "cellarId": 3,
      "wineType": "sparkling",
      "wineId": 201,
      "wineName": "Moët & Chandon Impérial",
      "quantity": 24,
      "registeredAt": "2026-05-15T11:20:00.000Z"
    },
    {
      "id": 5,
      "cellarId": 4,
      "wineType": "rose",
      "wineId": 301,
      "wineName": "Domaine Ott Rosé",
      "quantity": 15,
      "registeredAt": "2026-05-16T08:00:00.000Z"
    },
    {
      "id": 6,
      "cellarId": 5,
      "wineType": "dessert",
      "wineId": 501,
      "wineName": "Château d'Yquem 2015",
      "quantity": 8,
      "registeredAt": "2026-05-17T10:30:00.000Z"
    },
    {
      "id": 7,
      "cellarId": 2,
      "wineType": "whites",
      "wineId": 2,
      "wineName": "Montrachet Grand Cru 2014",
      "quantity": 15,
      "registeredAt": "2026-05-19T03:47:38.346Z"
    },
    {
      "id": 8,
      "cellarId": 6,
      "wineType": "port",
      "wineId": 1,
      "wineName": "Scion Port 1855",
      "quantity": 20,
      "registeredAt": "2026-05-19T03:47:51.649Z"
    },
    {
      "id": 9,
      "cellarId": 4,
      "wineType": "rose",
      "wineId": 13,
      "wineName": "L'Hydropathe Elite Rosé 2018",
      "quantity": 55,
      "registeredAt": "2026-05-19T06:48:47.333Z"
    }
  ]
}
```

**Cargar** el `Terminal` del IDE y **agregar** un nuevo `Tab`.

**Ejecutar** el siguiente command para iniciar el `json-server`:

```
cd server
json-server --watch db.json
```

**Cargar** el navegador e **ingrese** las siguientes URLs:

- http://localhost:3000/cellars
- http://localhost:3000/preservation-items

### Configuración de environments

A continuación se detalla las instrucciones para definir diferentes `named build configurations` para el proyecto. Más información en: https://angular.dev/tools/cli/environments#configure-environment-specific-defaults

**Cargar** el `Terminal` del IDE y **agregar** un nuevo `Tab`.

**Ejecutar** el siguiente CLI command para crear el directorio `environments` y los archivos de configuración, ubicado en la carpeta `src`:

```bash
ng generate environments
```

**Agregar** los siguientes valores a la constante `environment` del archivo `environment.development.ts` ubicado en la carpeta `/src/environments`:

```ts
production: false,
wineSquareProviderApiBaseUrl: 'http://localhost:3000',
wineSquareProviderCellarsEndpointPath: '/cellars',
wineSquareProviderPreservationItemsEndpointPath: '/preservation-items',
sampleApiProviderApiBaseUrl: 'https://api.sampleapis.com/wines',
sampleApiProviderRedsEndpointPath: '/reds',
sampleApiProviderWhitesEndpointPath: '/whites',
sampleApiProviderSparklingEndpointPath: '/sparkling',
sampleApiProviderRoseEndpointPath: '/rose',
sampleApiProviderDessertEndpointPath: '/dessert',
sampleApiProviderPortEndpointPath: '/port',
```

**Agregar** los siguientes valores a la constante `environment` del archivo `environment.ts` ubicado en la carpeta `environments`:

```ts
production: true,
wineSquareProviderApiBaseUrl: 'http://localhost:3000',
wineSquareProviderCellarsEndpointPath: '/cellars',
wineSquareProviderPreservationItemsEndpointPath: '/preservation-items',
sampleApiProviderApiBaseUrl: 'https://api.sampleapis.com/wines',
sampleApiProviderRedsEndpointPath: '/reds',
sampleApiProviderWhitesEndpointPath: '/whites',
sampleApiProviderSparklingEndpointPath: '/sparkling',
sampleApiProviderRoseEndpointPath: '/rose',
sampleApiProviderDessertEndpointPath: '/dessert',
sampleApiProviderPortEndpointPath: '/port',
```

### Información del HttpClient y provideHttpClient

**HttpClient**:

Realiza HTTP requests. Este servicio está disponible como un injectable class, con métodos para realizar HTTP requests.

Más información en: https://angular.dev/api/common/http/HttpClient

**provideHttpClient**:

Configura el servicio HttpClient de Angular para que esté disponible para injection.

Más información en: https://angular.dev/api/common/http/provideHttpClient

### Configuración del appConfig

**Agregar** los siguientes imports al archivo `app.config.ts` ubicado en la carpeta `/src/app`:

```ts
import { provideAppInitializer, inject } from '@angular/core';
import { provideHttpClient } from '@angular/common/http';
import { provideTranslateService, TranslateService } from '@ngx-translate/core';
import { provideTranslateHttpLoader } from '@ngx-translate/http-loader';
```

**Agregar** los siguientes métodos al array `providers` de la constante `appConfig`:

```ts
provideHttpClient(),
provideTranslateService({
  loader: provideTranslateHttpLoader({ prefix: './assets/i18n/', suffix: '.json' }),
  lang: 'en',
  fallbackLang: 'en'
}),
provideAppInitializer(() => {
  const stored = localStorage.getItem('app.lang');
  const translate = inject(TranslateService);
  const lang = stored || translate.getBrowserLang() || 'en';
  return translate.use(lang);
})
```

### Creación de la estructura del proyecto

**Crear** la siguiente estructura de carpetas en la carpeta :file_folder: `/src/app`:

```markdown
- 📂 src
  - 📂 app
    - 📂 preservation
      - 📁 application
      - 📁 domain
        - 📁 model
      - 📁 infrastructure
      - 📁 presentation
        - 📁 components
        - 📁 views
    - 📂 winery
      - 📁 application
      - 📁 domain
        - 📁 model
      - 📁 infrastructure
    - 📂 shared
      - 📁 infrastructure
      - 📁 presentation
        - 📁 components
        - 📁 views
```

## Creación de los interface y class Base

### Creación de los interface Base

**Ejecutar** el siguiente CLI command para crear la interface `Base` tipo `entity`:

```bash
ng generate interface shared/infrastructure/base-entity
```

**Reemplazar** el contenido de `base-entity.ts`:

```ts
export interface BaseEntity {
  /**
   * The unique identifier for the entity.
   */
  id: number;
}
```

**Ejecutar** el siguiente CLI command para crear la interface `Base` tipo `response`:

```bash
ng generate interface shared/infrastructure/base-response
```

**Reemplazar** el contenido de `base-response.ts`:

```ts
export interface BaseResponse {}

/**
 * Defines a standard structure for API resources/DTOs with a unique identifier.
 */
export interface BaseResource {
  /**
   * The unique identifier for the resource.
   */
  id: number;
}
```

**Ejecutar** el siguiente CLI command para crear la interface `Base` tipo `assembler`:

```bash
ng generate interface shared/infrastructure/base-assembler
```

**Reemplazar** el contenido de `base-assembler.ts`:

```ts
import { BaseResource, BaseResponse } from './base-response';
import { BaseEntity } from './base-entity';

/**
 * Defines a contract for assembler classes that convert between entities, resources, and API responses.
 *
 * @template TEntity - The entity type, must extend BaseEntity.
 * @template TResource - The resource type, must extend BaseResource.
 * @template TResponse - The response type, must extend BaseResponse.
 */
export interface BaseAssembler<
  TEntity extends BaseEntity,
  TResource extends BaseResource,
  TResponse extends BaseResponse
> {
  toEntityFromResource(resource: TResource): TEntity;
  toResourceFromEntity(entity: TEntity): TResource;
  toEntitiesFromResponse(response: TResponse): TEntity[];
}
```

### Creación de los class Base

**Ejecutar** el siguiente CLI command para crear el abstract class `Base` tipo `Api`:

```bash
ng generate class shared/infrastructure/base-api --skip-tests=true
```

**Reemplazar** el contenido de `base-api.ts`:

```ts
/**
 * Abstract base class for API services managing multiple endpoints within a bounded context.
 */
export abstract class BaseApi {
  // No methods defined; child classes will compose endpoint instances
}
```

**Ejecutar** el siguiente CLI command para crear el abstract class `Base` tipo `ApiEndpoint`:

```bash
ng generate class shared/infrastructure/base-api-endpoint --skip-tests=true
```

**Reemplazar** el contenido de `base-api-endpoint.ts`:

```ts
import { HttpClient, HttpErrorResponse } from '@angular/common/http';
import { Observable, throwError } from 'rxjs';
import { catchError, map } from 'rxjs/operators';
import { BaseEntity } from './base-entity';
import { BaseResource, BaseResponse } from './base-response';
import { BaseAssembler } from './base-assembler';

/**
 * Base class for API endpoint operations with generic CRUD functionality.
 *
 * @template TEntity - The entity type, must extend BaseEntity.
 * @template TResource - The resource type, must extend BaseResource.
 * @template TResponse - The response type, must extend BaseResponse.
 * @template TAssembler - The assembler type implementing BaseAssembler.
 */
export abstract class BaseApiEndpoint<
  TEntity extends BaseEntity,
  TResource extends BaseResource,
  TResponse extends BaseResponse,
  TAssembler extends BaseAssembler<TEntity, TResource, TResponse>
> {
  constructor(
    protected http: HttpClient,
    protected endpointUrl: string,
    protected assembler: TAssembler
  ) {}

  /**
   * Retrieves all entities from the API, handling both response objects and arrays.
   * @returns An Observable of an array of entities.
   */
  getAll(): Observable<TEntity[]> {
    return this.http.get<TResponse | TResource[]>(this.endpointUrl).pipe(
      map(response => {
        if (Array.isArray(response)) {
          return response.map(resource => this.assembler.toEntityFromResource(resource));
        }
        return this.assembler.toEntitiesFromResponse(response as TResponse);
      }),
      catchError(this.handleError('Failed to fetch entities'))
    );
  }

  /**
   * Retrieves a single entity by ID.
   * @param id - The ID of the entity.
   */
  getById(id: number): Observable<TEntity> {
    return this.http.get<TResource>(`${this.endpointUrl}/${id}`).pipe(
      map(resource => this.assembler.toEntityFromResource(resource)),
      catchError(this.handleError('Failed to fetch entity'))
    );
  }

  /**
   * Creates a new entity.
   * @param entity - The entity to create.
   */
  create(entity: TEntity): Observable<TEntity> {
    const resource = this.assembler.toResourceFromEntity(entity);
    return this.http.post<TResource>(this.endpointUrl, resource).pipe(
      map(created => this.assembler.toEntityFromResource(created)),
      catchError(this.handleError('Failed to create entity'))
    );
  }

  /**
   * Updates an existing entity.
   * @param entity - The entity to update.
   * @param id - The ID of the entity.
   */
  update(entity: TEntity, id: number): Observable<TEntity> {
    const resource = this.assembler.toResourceFromEntity(entity);
    return this.http.put<TResource>(`${this.endpointUrl}/${id}`, resource).pipe(
      map(updated => this.assembler.toEntityFromResource(updated)),
      catchError(this.handleError('Failed to update entity'))
    );
  }

  /**
   * Deletes an entity by ID.
   * @param id - The ID of the entity to delete.
   */
  delete(id: number): Observable<void> {
    return this.http.delete<void>(`${this.endpointUrl}/${id}`).pipe(
      catchError(this.handleError('Failed to delete entity'))
    );
  }

  protected handleError(operation: string) {
    return (error: HttpErrorResponse): Observable<never> => {
      let errorMessage = operation;
      if (error.status === 404) errorMessage = `${operation}: Resource not found`;
      else if (error.error instanceof ErrorEvent) errorMessage = `${operation}: ${error.error.message}`;
      else errorMessage = `${operation}: ${error.statusText || 'Unexpected error'}`;
      return throwError(() => new Error(errorMessage));
    };
  }
}
```

## Analizando The Wine Square API

### Analizando el endpoint cellars

Diríjase al endpoint local http://localhost:3000/cellars y **evalúe** el json de respuesta:

```json
[
  { "id": 1, "name": "Reds Cellar", "wineType": "reds", "capacity": 500 }
]
```

### Creación de la interface Cellar tipo Response

**Ejecutar** el siguiente CLI command para crear la interface `Cellars` tipo `response`:

```bash
ng generate interface preservation/infrastructure/cellars-response
```

**Reemplazar** el contenido de `cellars-response.ts`:

```ts
import { BaseResource, BaseResponse } from '../../shared/infrastructure/base-response';

/**
 * Represents the response structure for cellar-related API calls.
 * Extends the BaseResponse to include a list of cellar resources.
 *
 * @interface CellarsResponse
 * @extends BaseResponse
 */
export interface CellarsResponse extends BaseResponse {
  cellars: CellarResource[];
}

/**
 * Represents a resource within a cellar management system, extending the functionality of BaseResource.
 * This interface defines the structure of a cellar resource that includes properties for identification,
 * storage capacity, and the type of wine stored.
 *
 * Properties:
 * - `id` (number): A unique identifier for the cellar resource.
 * - `name` (string): The name of the cellar resource.
 * - `wineType` (string): The type of wine associated with the cellar resource.
 * - `capacity` (number): The maximum storage capacity of the cellar resource.
 *
 * Extends:
 * - BaseResource: This interface inherits properties and methods from BaseResource.
 */
export interface CellarResource extends BaseResource {
  id: number;
  name: string;
  wineType: string;
  capacity: number;
}
```

### Creación del class Cellar tipo entity (model)

**Ejecutar** el siguiente CLI command para crear el modelo `cellar`:

```bash
ng generate class preservation/domain/model/cellar --type=entity --skip-tests=true
```

**Agregar** el siguiente `import` y la interface `BaseEntity` a la clase `Cellar`:

```ts
import { BaseEntity } from '../../../shared/infrastructure/base-entity';

/**
 * Represents a cellar entity with details about its properties.
 * This class implements the BaseEntity interface.
 */
export class Cellar implements BaseEntity
```

**Agregar** los siguientes atributos y constructor a la clase `Cellar`:

```ts
private _id!: number;
private _name!: string;
private _wineType!: string;
private _capacity!: number;

/**
 * Constructs an instance of the class with the given cellar details.
 *
 * @param {Object} cellar - The cellar details for initialization.
 * @param {number} cellar.id - The unique identifier of the cellar.
 * @param {string} cellar.name - The name of the cellar.
 * @param {string} cellar.wineType - The type of wine stored in the cellar.
 * @param {number} cellar.capacity - The storage capacity of the cellar.
 */
constructor(cellar: { id: number; name: string; wineType: string; capacity: number }) {
  this._id = cellar.id;
  this._name = cellar.name;
  this._wineType = cellar.wineType;
  this._capacity = cellar.capacity;
}

get id(): number { return this._id; }
set id(value: number) { this._id = value; }

get name(): string { return this._name; }
set name(value: string) { this._name = value; }

get wineType(): string { return this._wineType; }
set wineType(value: string) { this._wineType = value; }

get capacity(): number { return this._capacity; }
set capacity(value: number) { this._capacity = value; }
```

### Creación del class Cellar tipo Assembler

**Ejecutar** el siguiente CLI command:

```bash
ng generate class preservation/infrastructure/cellar-assembler --skip-tests=true
```

**Reemplazar** el contenido de `cellar-assembler.ts`:

```ts
import { BaseAssembler } from '../../shared/infrastructure/base-assembler';
import { Cellar } from '../domain/model/cellar.entity';
import { CellarResource, CellarsResponse } from './cellars-response';

/**
 * The CellarAssembler class is responsible for converting between Cellar entities,
 * CellarResource objects, and CellarsResponse objects. It facilitates the transformation
 * of data to and from different layers of the application.
 *
 * Implements BaseAssembler with the following type parameters:
 * - Cellar: The domain entity representing a cellar.
 * - CellarResource: The resource representation of a cellar for transport or presentation layers.
 * - CellarsResponse: The specialized response object containing multiple cellar resources.
 */
export class CellarAssembler implements BaseAssembler<Cellar, CellarResource, CellarsResponse> {
  /**
   * Converts a CellarsResponse object into an array of Cellar entities.
   *
   * @param {CellarsResponse} response - The response object containing cellar resources.
   * @return {Cellar[]} An array of Cellar entities derived from the response data.
   */
  toEntitiesFromResponse(response: CellarsResponse): Cellar[] {
    return response.cellars.map(r => this.toEntityFromResource(r));
  }

  /**
   * Converts a CellarResource object into a Cellar entity.
   *
   * @param {CellarResource} resource - The resource object to convert.
   * @return {Cellar} The converted Cellar entity.
   */
  toEntityFromResource(resource: CellarResource): Cellar {
    return new Cellar({
      id: resource.id,
      name: resource.name,
      wineType: resource.wineType,
      capacity: resource.capacity
    });
  }

  /**
   * Transforms a Cellar entity into a CellarResource object.
   *
   * @param {Cellar} entity - The Cellar entity to be transformed.
   * @return {CellarResource} The resulting resource representation of the entity.
   */
  toResourceFromEntity(entity: Cellar): CellarResource {
    return {
      id: entity.id,
      name: entity.name,
      wineType: entity.wineType,
      capacity: entity.capacity
    } as CellarResource;
  }
}
```

### Analizando el endpoint preservation-items

Diríjase al endpoint local http://localhost:3000/preservation-items y **evalúe** el json de respuesta:

```json
[
  {
    "id": 1,
    "cellarId": 1,
    "wineType": "reds",
    "wineId": 1,
    "wineName": "Eszencia 1999",
    "quantity": 42,
    "registeredAt": "2026-05-10T14:30:00.000Z"
  }
]
```

### Creación de la interface PreservationItem tipo Response

**Ejecutar** el siguiente CLI command:

```bash
ng generate interface preservation/infrastructure/preservation-items-response
```

**Reemplazar** el contenido de `preservation-items-response.ts`:

```ts
import { BaseResource, BaseResponse } from '../../shared/infrastructure/base-response';

/**
 * Represents the response for preservation item requests.
 * Extends the BaseResponse interface to include additional information
 * specific to preservation items.
 *
 * @interface PreservationItemsResponse
 * @extends BaseResponse
 */
export interface PreservationItemsResponse extends BaseResponse {
  preservationItems: PreservationItemResource[];
}

/**
 * Interface representing a PreservationItemResource.
 *
 * This resource is used to represent a preserved wine item, including its metadata
 * such as identification, type, name, quantity, and registration details.
 *
 * @extends BaseResource
 *
 * @property {number} id - Unique identifier for the preservation item.
 * @property {number} cellarId - Identifier for the cellar where the item is stored.
 * @property {string} wineType - Type of wine (e.g., red, white, sparkling).
 * @property {number} wineId - Identifier for the specific wine.
 * @property {string} wineName - Name of the wine.
 * @property {number} quantity - Quantity of the wine preserved.
 * @property {string} registeredAt - Date and time when the item was registered, in ISO 8601 format.
 */
export interface PreservationItemResource extends BaseResource {
  id: number;
  cellarId: number;
  wineType: string;
  wineId: number;
  wineName: string;
  quantity: number;
  registeredAt: string;
}
```

### Creación del class PreservationItem tipo entity (model)

**Ejecutar** el siguiente CLI command:

```bash
ng generate class preservation/domain/model/preservation-item --type=entity --skip-tests=true
```

**Agregar** el `import` y la interface `BaseEntity` a la clase `PreservationItem`:

```ts
import { BaseEntity } from '../../../shared/infrastructure/base-entity';

/**
 * Represents a preservation item stored in a wine cellar.
 *
 * This class holds information about a specific wine bottle or collection of bottles stored
 * in a wine cellar, including details like the cellar ID, wine type, name, quantity, and registration date.
 */
export class PreservationItem implements BaseEntity
```

**Agregar** los siguientes atributos y constructor:

```ts
private _id!: number;
private _cellarId!: number;
private _wineType!: string;
private _wineId!: number;
private _wineName!: string;
private _quantity!: number;
private _registeredAt!: string;

/**
 * Constructs a new instance of the class using the provided preservation item details.
 *
 * @param {Object} preservationItem An object containing the details of the preservation item.
 * @param {number} preservationItem.id The unique identifier of the preservation item.
 * @param {number} preservationItem.cellarId The identifier of the cellar associated with the preservation item.
 * @param {string} preservationItem.wineType The type of wine (e.g., red, white, sparkling).
 * @param {number} preservationItem.wineId The unique identifier of the wine.
 * @param {string} preservationItem.wineName The name of the wine.
 * @param {number} preservationItem.quantity The quantity of the wine in preservation.
 * @param {string} preservationItem.registeredAt The date and time when the preservation item was registered.
 */
constructor(preservationItem: {
  id: number;
  cellarId: number;
  wineType: string;
  wineId: number;
  wineName: string;
  quantity: number;
  registeredAt: string;
}) {
  this._id = preservationItem.id;
  this._cellarId = preservationItem.cellarId;
  this._wineType = preservationItem.wineType;
  this._wineId = preservationItem.wineId;
  this._wineName = preservationItem.wineName;
  this._quantity = preservationItem.quantity;
  this._registeredAt = preservationItem.registeredAt;
}

get id(): number { return this._id; }
set id(value: number) { this._id = value; }

get cellarId(): number { return this._cellarId; }
set cellarId(value: number) { this._cellarId = value; }

get wineType(): string { return this._wineType; }
set wineType(value: string) { this._wineType = value; }

get wineId(): number { return this._wineId; }
set wineId(value: number) { this._wineId = value; }

get wineName(): string { return this._wineName; }
set wineName(value: string) { this._wineName = value; }

get quantity(): number { return this._quantity; }
set quantity(value: number) { this._quantity = value; }

get registeredAt(): string { return this._registeredAt; }
set registeredAt(value: string) { this._registeredAt = value; }
```

### Creación del class PreservationItem tipo Assembler

**Ejecutar** el siguiente CLI command:

```bash
ng generate class preservation/infrastructure/preservation-item-assembler --skip-tests=true
```

**Reemplazar** el contenido de `preservation-item-assembler.ts`:

```ts
import { BaseAssembler } from '../../shared/infrastructure/base-assembler';
import { PreservationItem } from '../domain/model/preservation-item.entity';
import { PreservationItemResource, PreservationItemsResponse } from './preservation-items-response';

/**
 * The PreservationItemAssembler class is responsible for converting between domain entities, resources,
 * and response objects related to preservation items. This class implements the BaseAssembler interface
 * with specific type mappings for PreservationItem, PreservationItemResource, and PreservationItemsResponse.
 *
 * It provides methods to map from API responses to entities, resources to entities,
 * and entities to resources, facilitating the transformation between various application layers.
 */
export class PreservationItemAssembler
  implements BaseAssembler<PreservationItem, PreservationItemResource, PreservationItemsResponse> {

  /**
   * Converts a PreservationItemsResponse into an array of PreservationItem entities.
   *
   * @param {PreservationItemsResponse} response - The response object containing preservation items.
   * @return {PreservationItem[]} An array of PreservationItem entities extracted from the response.
   */
  toEntitiesFromResponse(response: PreservationItemsResponse): PreservationItem[] {
    return response.preservationItems.map(r => this.toEntityFromResource(r));
  }

  /**
   * Converts a PreservationItemResource object into a PreservationItem entity.
   *
   * @param {PreservationItemResource} resource - The resource object to be converted.
   * @return {PreservationItem} The corresponding PreservationItem entity.
   */
  toEntityFromResource(resource: PreservationItemResource): PreservationItem {
    return new PreservationItem({
      id: resource.id,
      cellarId: resource.cellarId,
      wineType: resource.wineType,
      wineId: resource.wineId,
      wineName: resource.wineName,
      quantity: resource.quantity,
      registeredAt: resource.registeredAt
    });
  }

  /**
   * Converts a PreservationItem entity to a PreservationItemResource.
   *
   * @param {PreservationItem} entity - The PreservationItem entity to be converted.
   * @return {PreservationItemResource} The resulting PreservationItemResource object.
   */
  toResourceFromEntity(entity: PreservationItem): PreservationItemResource {
    return {
      id: entity.id,
      cellarId: entity.cellarId,
      wineType: entity.wineType,
      wineId: entity.wineId,
      wineName: entity.wineName,
      quantity: entity.quantity,
      registeredAt: entity.registeredAt
    } as PreservationItemResource;
  }
}
```

## Creación del PreservationApi Service

### Creación del class Cellars tipo ApiEndpoint

**Ejecutar** el siguiente CLI command:

```bash
ng generate class preservation/infrastructure/cellars-api-endpoint --skip-tests=true
```

**Reemplazar** el contenido de `cellars-api-endpoint.ts`:

```ts
import { BaseApiEndpoint } from '../../shared/infrastructure/base-api-endpoint';
import { Cellar } from '../domain/model/cellar.entity';
import { CellarResource, CellarsResponse } from './cellars-response';
import { CellarAssembler } from './cellar-assembler';
import { HttpClient } from '@angular/common/http';
import { environment } from '../../../environments/environment';

/**
 * Represents the API endpoint for managing cellar-related operations.
 * This class handles the communication with the Wine Square Provider's Cellars API.
 * It extends the functionality of the BaseApiEndpoint to provide type-safe operations
 * for cellar data.
 *
 * @extends BaseApiEndpoint<Cellar, CellarResource, CellarsResponse, CellarAssembler>
 */
export class CellarsApiEndpoint extends BaseApiEndpoint<
  Cellar, CellarResource, CellarsResponse, CellarAssembler
> {
  constructor(http: HttpClient) {
    super(
      http,
      `${environment.wineSquareProviderApiBaseUrl}${environment.wineSquareProviderCellarsEndpointPath}`,
      new CellarAssembler()
    );
  }
}
```

### Creación del class PreservationItem tipo ApiEndpoint

**Ejecutar** el siguiente CLI command:

```bash
ng generate class preservation/infrastructure/preservation-item-api-endpoint --skip-tests=true
```

**Reemplazar** el contenido de `preservation-item-api-endpoint.ts`:

```ts
import { BaseApiEndpoint } from '../../shared/infrastructure/base-api-endpoint';
import { HttpClient } from '@angular/common/http';
import { environment } from '../../../environments/environment';
import { PreservationItem } from '../domain/model/preservation-item.entity';
import { PreservationItemResource, PreservationItemsResponse } from './preservation-items-response';
import { PreservationItemAssembler } from './preservation-item-assembler';

/**
 * PreservationItemApiEndpoint is a service class that interacts with the API endpoints
 * for handling PreservationItem resources.
 *
 * This class extends BaseApiEndpoint, providing standardized methods for CRUD operations
 * on PreservationItem resources. It leverages the PreservationItemAssembler to handle
 * the transformation of data between the application and the API.
 *
 * The API base URL and endpoint path are dynamically constructed using the application's
 * environment configuration.
 *
 * @extends BaseApiEndpoint
 */
export class PreservationItemApiEndpoint extends BaseApiEndpoint<
  PreservationItem, PreservationItemResource, PreservationItemsResponse, PreservationItemAssembler
> {
  constructor(http: HttpClient) {
    super(
      http,
      `${environment.wineSquareProviderApiBaseUrl}${environment.wineSquareProviderPreservationItemsEndpointPath}`,
      new PreservationItemAssembler()
    );
  }
}
```

### Creación del class Preservation tipo Api

**Ejecutar** el siguiente CLI command:

```bash
ng generate service preservation/infrastructure/preservation-api --skip-tests=true
```

**Reemplazar** el contenido de `preservation-api.ts`:

```ts
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';
import { BaseApi } from '../../shared/infrastructure/base-api';
import { PreservationItem } from '../domain/model/preservation-item.entity';
import { Cellar } from '../domain/model/cellar.entity';
import { CellarsApiEndpoint } from './cellars-api-endpoint';
import { PreservationItemApiEndpoint } from './preservation-item-api-endpoint';

/**
 * The PreservationApi class provides methods for interacting with API endpoints
 * related to cellars and preservation items. It acts as a service that wraps
 * the HTTP requests and returns observables for further processing.
 *
 * This service is decorated with @Injectable and is provided at the root level,
 * making it available throughout the application without needing to register it
 * in any specific module.
 *
 * It extends the BaseApi class to encapsulate common API functionalities.
 */
@Injectable({ providedIn: 'root' })
export class PreservationApi extends BaseApi {
  private preservationItemApiEndpoint: PreservationItemApiEndpoint;
  private cellarsApiEndpoint: CellarsApiEndpoint;

  constructor(private http: HttpClient) {
    super();
    this.preservationItemApiEndpoint = new PreservationItemApiEndpoint(http);
    this.cellarsApiEndpoint = new CellarsApiEndpoint(http);
  }

  /**
   * Retrieves a list of cellars from the API endpoint.
   *
   * @return {Observable<Cellar[]>} An observable emitting an array of cellar objects.
   */
  getCellars(): Observable<Cellar[]> {
    return this.cellarsApiEndpoint.getAll();
  }

  /**
   * Retrieves a list of preservation items from the API endpoint.
   *
   * @return {Observable<PreservationItem[]>} An observable that emits an array of preservation items.
   */
  getPreservationItems(): Observable<PreservationItem[]> {
    return this.preservationItemApiEndpoint.getAll();
  }

  /**
   * Creates a new preservation item by sending the provided data to the API endpoint.
   *
   * @param {PreservationItem} item - The preservation item to be created.
   * @return {Observable<PreservationItem>} An observable that emits the created preservation item.
   */
  createPreservationItem(item: PreservationItem): Observable<PreservationItem> {
    return this.preservationItemApiEndpoint.create(item);
  }
}
```

## Analizando SampleAPI (Winery)

Diríjase al endpoint https://api.sampleapis.com/wines/reds y **evalúe** el json de respuesta:

```json
[
  {
    "winery": "Oremus",
    "wine": "Eszencia 1999",
    "rating": { "average": "5.0", "reviews": "34 ratings" },
    "location": "Hungary\n·\nTokaj",
    "image": "https://images.vivino.com/thumbs/_VYRnv4XTfCVEXlvhYw4AA_pb_x300.png",
    "id": 1
  }
]
```

### Creación de la interface Wines tipo Response

**Ejecutar** el siguiente CLI command:

```bash
ng generate interface winery/infrastructure/wines-response
```

**Reemplazar** el contenido de `wines-response.ts`:

```ts
import { BaseResource, BaseResponse } from '../../shared/infrastructure/base-response';

/**
 * Represents a wine resource containing information about a specific wine,
 * its associated winery, location, ratings, and other related details.
 * Extends the BaseResource.
 *
 * @interface WineResource
 * @extends BaseResource
 */
export interface WineResource extends BaseResource {
  winery: string;
  wine: string;
  rating: {
    average: string;
    reviews: string;
  };
  location: string;
  image: string;
  id: number;
}

export type WinesResponse = WineResource[];
```

> [!NOTE]
> SampleAPI devuelve un array plano (no envoltorio con propiedad `wines`). Por eso `WinesResponse` es un alias del array.

### Creación del class Wine tipo entity (model)

**Ejecutar** el siguiente CLI command:

```bash
ng generate class winery/domain/model/wine --type=entity --skip-tests=true
```

**Agregar** el `import` y la interface `BaseEntity` a la clase `Wine`:

```ts
import { BaseEntity } from '../../../shared/infrastructure/base-entity';

/**
 * Represents a Wine entity with properties such as winery, name, rating, location, image, and ID.
 *
 * Implements the BaseEntity interface.
 */
export class Wine implements BaseEntity
```

**Agregar** los siguientes atributos y constructor:

```ts
private _winery!: string;
private _wine!: string;
private _rating!: { average: number; reviews: string };
private _location!: string;
private _image!: string;
private _id!: number;

/**
 * Constructs a new instance of the class with the provided wine data.
 *
 * @param {Object} wine - An object containing the details of a wine.
 * @param {string} wine.winery - The name of the winery.
 * @param {string} wine.wine - The name of the wine.
 * @param {Object} wine.rating - An object containing rating details of the wine.
 * @param {number} wine.rating.average - The average rating of the wine.
 * @param {string} wine.rating.reviews - The reviews count as a descriptive string.
 * @param {string} wine.location - The location of the winery.
 * @param {string} wine.image - The URL of the wine's image.
 * @param {number} wine.id - The unique identifier of the wine.
 */
constructor(wine: {
  winery: string;
  wine: string;
  rating: { average: number; reviews: string };
  location: string;
  image: string;
  id: number;
}) {
  this._winery = wine.winery;
  this._wine = wine.wine;
  this._rating = wine.rating;
  this._location = wine.location;
  this._image = wine.image;
  this._id = wine.id;
}

get winery(): string { return this._winery; }
set winery(value: string) { this._winery = value; }

get wine(): string { return this._wine; }
set wine(value: string) { this._wine = value; }

get rating(): { average: number; reviews: string } { return this._rating; }
set rating(value: { average: number; reviews: string }) { this._rating = value; }

get location(): string { return this._location; }
set location(value: string) { this._location = value; }

get image(): string { return this._image; }
set image(value: string) { this._image = value; }

get id(): number { return this._id; }
set id(value: number) { this._id = value; }
```

### Creación del class Wine tipo Assembler

**Ejecutar** el siguiente CLI command:

```bash
ng generate class winery/infrastructure/wine-assembler --skip-tests=true
```

**Reemplazar** el contenido de `wine-assembler.ts`:

```ts
import { BaseAssembler } from '../../shared/infrastructure/base-assembler';
import { Wine } from '../domain/model/wine.entity';
import { WineResource, WinesResponse } from './wines-response';

/**
 * The WineAssembler class is responsible for converting between `Wine` entities,
 * `WineResource` DTOs, and `WinesResponse` types.
 *
 * @implements {BaseAssembler<Wine, WineResource, WinesResponse>}
 */
export class WineAssembler implements BaseAssembler<Wine, WineResource, WinesResponse> {
  /**
   * Converts a WinesResponse object into an array of Wine entities.
   * @param response - The WinesResponse object containing wine data.
   * @returns An array of Wine entities created from the response.
   */
  toEntitiesFromResponse(response: WinesResponse): Wine[] {
    return response.map(r => this.toEntityFromResource(r));
  }

  /**
   * Converts a WineResource object into a Wine entity.
   *
   * @param {WineResource} resource - The resource object containing wine data to be transformed.
   * @return {Wine} A new Wine entity created from the provided resource data.
   */
  toEntityFromResource(resource: WineResource): Wine {
    return new Wine({
      id: resource.id,
      winery: resource.winery,
      wine: resource.wine,
      rating: {
        average: parseFloat(resource.rating.average),
        reviews: resource.rating.reviews
      },
      location: resource.location,
      image: resource.image
    });
  }

  /**
   * Converts a Wine entity into a WineResource object.
   *
   * @param {Wine} entity - The Wine entity to be converted.
   * @return {WineResource} The transformed WineResource object.
   */
  toResourceFromEntity(entity: Wine): WineResource {
    return {
      id: entity.id,
      winery: entity.winery,
      wine: entity.wine,
      rating: {
        average: entity.rating.average.toString(),
        reviews: entity.rating.reviews
      },
      location: entity.location,
      image: entity.image
    } as WineResource;
  }
}
```

### Creación del class Wines tipo ApiEndpoint

**Ejecutar** el siguiente CLI command:

```bash
ng generate class winery/infrastructure/wines-api-endpoint --skip-tests=true
```

**Reemplazar** el contenido de `wines-api-endpoint.ts`:

```ts
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';
import { catchError, map } from 'rxjs/operators';
import { BaseApiEndpoint } from '../../shared/infrastructure/base-api-endpoint';
import { environment } from '../../../environments/environment';
import { Wine } from '../domain/model/wine.entity';
import { WineResource, WinesResponse } from './wines-response';
import { WineAssembler } from './wine-assembler';

export class WinesApiEndpoint extends BaseApiEndpoint<
  Wine, WineResource, WinesResponse, WineAssembler
> {
  private readonly pathsByType: Record<string, string> = {
    reds: environment.sampleApiProviderRedsEndpointPath,
    whites: environment.sampleApiProviderWhitesEndpointPath,
    sparkling: environment.sampleApiProviderSparklingEndpointPath,
    rose: environment.sampleApiProviderRoseEndpointPath,
    dessert: environment.sampleApiProviderDessertEndpointPath,
    port: environment.sampleApiProviderPortEndpointPath
  };

  constructor(http: HttpClient) {
    super(http, environment.sampleApiProviderApiBaseUrl, new WineAssembler());
  }

  /**
   * Retrieves a list of wines based on the specified wine type.
   *
   * @param wineType The type of wine to filter by (e.g., red, white, rosé).
   * @return An observable containing an array of Wine entities.
   */
  getByWineType(wineType: string): Observable<Wine[]> {
    const path = this.pathsByType[wineType];
    return this.http.get<WineResource[]>(`${this.endpointUrl}${path}`).pipe(
      map(resources => resources.map(r => this.assembler.toEntityFromResource(r))),
      catchError(this.handleError('Failed to fetch wines'))
    );
  }
}
```

### Creación del class Winery tipo Api

**Ejecutar** el siguiente CLI command:

```bash
ng generate service winery/infrastructure/winery-api --skip-tests=true
```

**Reemplazar** el contenido de `winery-api.ts`:

```ts
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';
import { BaseApi } from '../../shared/infrastructure/base-api';
import { Wine } from '../domain/model/wine.entity';
import { WinesApiEndpoint } from './wines-api-endpoint';

@Injectable({ providedIn: 'root' })
export class WineryApi extends BaseApi {
  private winesApiEndpoint: WinesApiEndpoint;

  constructor(private http: HttpClient) {
    super();
    this.winesApiEndpoint = new WinesApiEndpoint(http);
  }

  /**
   * Retrieves wines by type from SampleAPI.
   * @param wineType - The wine type (e.g., 'reds', 'whites').
   * @returns An Observable of an array of Wine objects.
   */
  getByWineType(wineType: string): Observable<Wine[]> {
    return this.winesApiEndpoint.getByWineType(wineType);
  }
}
```

## Application layer

### Creación del Service PreservationStore

**Ejecutar** el siguiente CLI command:

```bash
ng generate service preservation/application/preservation-store --skip-tests=true
```

**Reemplazar** el contenido de `preservation-store.ts`:

```ts
import { Injectable, computed, signal } from '@angular/core';
import { takeUntilDestroyed } from '@angular/core/rxjs-interop';
import { retry } from 'rxjs';
import { PreservationItem } from '../domain/model/preservation-item.entity';
import { Cellar } from '../domain/model/cellar.entity';
import { PreservationApi } from '../infrastructure/preservation-api';

/**
 * PreservationStore manages reactive state for cellars and preservation items.
 */
@Injectable({ providedIn: 'root' })
export class PreservationStore {
  private readonly preservationItemsSignal = signal<PreservationItem[]>([]);
  private readonly cellarsSignal = signal<Cellar[]>([]);

  readonly preservationItems = this.preservationItemsSignal.asReadonly();
  readonly cellars = this.cellarsSignal.asReadonly();

  private readonly loadingSignal = signal(false);
  readonly loading = this.loadingSignal.asReadonly();

  private readonly errorSignal = signal<string | null>(null);
  readonly error = this.errorSignal.asReadonly();

  readonly preservationItemsCount = computed(() => this.preservationItems().length);
  readonly cellarsCount = computed(() => this.cellars().length);

  constructor(private preservationApi: PreservationApi) {
    this.loadPreservationItems();
    this.loadCellars();
  }

  /**
   * Returns the cellar associated with a given wine type.
   *
   * @param wineType The wine type to look up.
   * @returns The matching Cellar or undefined.
   */
  getCellarByWineType(wineType: string): Cellar | undefined {
    return this.cellars().find(c => c.wineType === wineType);
  }

  /**
   * Calculates the available capacity for a given cellar.
   *
   * @param cellarId The cellar identifier.
   * @returns The number of remaining bottle slots in the cellar.
   */
  availableCapacityFor(cellarId: number): number {
    const cellar = this.cellars().find(c => c.id === cellarId);
    if (!cellar) return 0;
    const total = this.preservationItems()
      .filter(p => p.cellarId === cellarId)
      .reduce((s, p) => s + p.quantity, 0);
    return cellar.capacity - total;
  }

  /**
   * Adds a new preservation item to the API and updates the local state.
   *
   * @param item The preservation item entity to persist.
   */
  addPreservationItem(item: PreservationItem): void {
    this.loadingSignal.set(true);
    this.errorSignal.set(null);
    this.preservationApi.createPreservationItem(item).pipe(retry(2)).subscribe({
      next: created => {
        this.preservationItemsSignal.update(items => [...items, created]);
        this.loadingSignal.set(false);
      },
      error: err => {
        this.errorSignal.set(this.formatError(err, 'Failed to create preservation item'));
        this.loadingSignal.set(false);
      }
    });
  }

  private loadPreservationItems(): void {
    this.loadingSignal.set(true);
    this.errorSignal.set(null);
    this.preservationApi.getPreservationItems().pipe(takeUntilDestroyed(), retry(3)).subscribe({
      next: items => {
        this.preservationItemsSignal.set(items);
        this.loadingSignal.set(false);
      },
      error: err => {
        this.errorSignal.set(this.formatError(err, 'Failed to load preservation items'));
        this.loadingSignal.set(false);
      }
    });
  }

  private loadCellars(): void {
    this.loadingSignal.set(true);
    this.errorSignal.set(null);
    this.preservationApi.getCellars().pipe(takeUntilDestroyed(), retry(3)).subscribe({
      next: cellars => {
        this.cellarsSignal.set(cellars);
        this.loadingSignal.set(false);
      },
      error: err => {
        this.errorSignal.set(this.formatError(err, 'Failed to load cellars'));
        this.loadingSignal.set(false);
      }
    });
  }

  private formatError(error: any, fallback: string): string {
    if (error instanceof Error) {
      return error.message.includes('Resource not found')
        ? `${fallback}: Not found`
        : error.message;
    }
    return fallback;
  }
}
```

### Creación del Service WineryStore

**Ejecutar** el siguiente CLI command:

```bash
ng generate service winery/application/winery-store --skip-tests=true
```

**Reemplazar** el contenido de `winery-store.ts`:

```ts
import { Injectable, computed, signal } from '@angular/core';
import { retry } from 'rxjs';
import { Wine } from '../domain/model/wine.entity';
import { WineryApi } from '../infrastructure/winery-api';

/**
 * WineryStore manages reactive state for wines loaded by wine type.
 */
@Injectable({ providedIn: 'root' })
export class WineryStore {
  private readonly winesSignal = signal<Wine[]>([]);
  readonly wines = this.winesSignal.asReadonly();

  private readonly loadingSignal = signal(false);
  readonly loading = this.loadingSignal.asReadonly();

  private readonly errorSignal = signal<string | null>(null);
  readonly error = this.errorSignal.asReadonly();

  readonly winesCount = computed(() => this.wines().length);

  constructor(private wineryApi: WineryApi) {}

  /**
   * Loads wines from the API for the given wine type and stores them in state.
   *
   * @param wineType The wine type (e.g. reds, whites, sparkling).
   */
  loadWinesByType(wineType: string): void {
    this.loadingSignal.set(true);
    this.errorSignal.set(null);
    this.winesSignal.set([]);
    this.wineryApi.getByWineType(wineType).pipe(retry(2)).subscribe({
      next: wines => {
        this.winesSignal.set(wines);
        this.loadingSignal.set(false);
      },
      error: err => {
        this.errorSignal.set(this.formatError(err, 'Failed to load wines'));
        this.loadingSignal.set(false);
      }
    });
  }

  clearWines(): void {
    this.winesSignal.set([]);
  }

  private formatError(error: any, fallback: string): string {
    if (error instanceof Error) {
      return error.message.includes('Resource not found')
        ? `${fallback}: Not found`
        : error.message;
    }
    return fallback;
  }
}
```

## Creación de componentes y vistas

**Ejecutar** los siguientes comandos para la creación de componentes y views (uno a la vez):

```bash
ng generate component shared/presentation/components/language-switcher --skip-tests=true
```

```bash
ng generate component shared/presentation/components/footer-content --skip-tests=true
```

```bash
ng generate component shared/presentation/components/layout --skip-tests=true
```

```bash
ng generate component shared/presentation/views/home --skip-tests=true
```

```bash
ng generate component shared/presentation/views/page-not-found --skip-tests=true
```

```bash
ng generate component preservation/presentation/components/cellar-summary --skip-tests=true
```

```bash
ng generate component preservation/presentation/views/new-preservation-item --skip-tests=true
```

## Configuración del Routes

### Crear y configurar preservation.routes

**Crear** el archivo `preservation.routes.ts` en la carpeta `preservation/presentation/views`:

```ts
import { Routes } from '@angular/router';

const newPreservationItem = () =>
  import('./new-preservation-item/new-preservation-item').then(m => m.NewPreservationItem);

export const preservationRoutes: Routes = [
  { path: 'items/new', loadComponent: newPreservationItem }
];
```

### Configuración del Routes app.routes

**Reemplazar** el contenido del archivo `app.routes.ts`:

```ts
import { Routes } from '@angular/router';
import { Home } from './shared/presentation/views/home/home';

const pageNotFound = () =>
  import('./shared/presentation/views/page-not-found/page-not-found').then(m => m.PageNotFound);

const baseTitle = 'The Wine Square';

export const routes: Routes = [
  { path: 'home', component: Home, title: `${baseTitle} | Home` },
  {
    path: 'preservation',
    loadChildren: () =>
      import('./preservation/presentation/views/preservation.routes').then(m => m.preservationRoutes)
  },
  { path: '', redirectTo: '/home', pathMatch: 'full' },
  { path: '**', loadComponent: pageNotFound, title: `${baseTitle} | Page Not Found` }
];
```

## Modificación de componentes

### Modificación del LanguageSwitcher Component

**Reemplazar** el contenido de `language-switcher.ts`:

```ts
import { Component, DestroyRef, inject } from '@angular/core';
import { MatButtonToggle, MatButtonToggleGroup } from '@angular/material/button-toggle';
import { TranslateService } from '@ngx-translate/core';

@Component({
  selector: 'app-language-switcher',
  imports: [MatButtonToggleGroup, MatButtonToggle],
  templateUrl: './language-switcher.html',
  styleUrl: './language-switcher.css',
})
export class LanguageSwitcher {
  protected currentLang: string = 'en';
  protected languages: string[] = ['en', 'es'];
  private translate: TranslateService;

  constructor() {
    this.translate = inject(TranslateService);
    this.currentLang = this.translate.getCurrentLang() || 'en';
  }

  useLanguage(language: string) {
    this.translate.use(language);
    this.currentLang = language;
    localStorage.setItem('app.lang', language);
  }
}
```

**Reemplazar** el contenido de `language-switcher.html`:

```html
<mat-button-toggle-group [value]="currentLang"
                         appearance="standard"
                         aria-label="Preferred language"
                         name="language">
  @for (language of languages; track language) {
    <mat-button-toggle [value]="language"
                       [aria-label]="language"
                       (click)="useLanguage(language)">
      {{ language.toUpperCase() }}
    </mat-button-toggle>
  }
</mat-button-toggle-group>
```

### Modificación del FooterContent Component

**Reemplazar** el contenido de `footer-content.ts`:

```ts
import { Component } from '@angular/core';
import { TranslatePipe } from '@ngx-translate/core';

@Component({
  selector: 'app-footer-content',
  imports: [TranslatePipe],
  templateUrl: './footer-content.html',
  styleUrl: './footer-content.css'
})
export class FooterContent {}
```

**Reemplazar** el contenido de `footer-content.html`:

```html
<div class="footer-content">
  <p>Copyright &copy; 2025 The Wine Square. {{ 'footer.rights' | translate }}</p>
  <p>{{ 'footer.powered-by' | translate }}
    <a href="https://material.angular.dev/" target="_blank">Angular Material</a>
    {{ 'footer.and' | translate }}
    <a href="https://ngx-translate.org/" target="_blank">ngx-translate</a>
  </p>
</div>
```

**Reemplazar** el contenido de `footer-content.css`:

```css
.footer-content {
  width: 100%;
  background-color: darkslategrey;
  color: white;
  text-align: center;
  padding: 16px;
  box-sizing: border-box;
  margin-top: auto;
}

.footer-content a {
  color: white;
  text-decoration: underline;
}
```

### Modificación del Layout Component

**Reemplazar** el contenido de `layout.ts`:

```ts
import { Component } from '@angular/core';
import { RouterLink, RouterLinkActive, RouterOutlet } from '@angular/router';
import { MatToolbar, MatToolbarRow } from '@angular/material/toolbar';
import { MatButton } from '@angular/material/button';
import { TranslatePipe } from '@ngx-translate/core';
import { LanguageSwitcher } from '../language-switcher/language-switcher';
import { FooterContent } from '../footer-content/footer-content';

@Component({
  selector: 'app-layout',
  imports: [
    RouterOutlet, RouterLink, RouterLinkActive,
    MatToolbar, MatToolbarRow, MatButton,
    TranslatePipe, LanguageSwitcher, FooterContent
  ],
  templateUrl: './layout.html',
  styleUrl: './layout.css'
})
export class Layout {
  options = [
    { link: '/home', label: 'option.home' },
    { link: '/preservation/items/new', label: 'option.new-preservation-item' }
  ];
}
```

**Reemplazar** el contenido de `layout.html`:

```html
<mat-toolbar>
  <mat-toolbar-row class="toolbar-grid">
    <div class="brand">
      <img src="https://img.logo.dev/thewinesquare.com?token=pk_B79Ajy8lSxuZc3W2xNN80A" alt="Thewinesquare" width="32" height="32"/>
      <h1>The Wine Square Cellar Management Platform</h1>
    </div>
    <nav class="nav-center" aria-label="Main navigation">
      @for (option of options; track option.label) {
        <a mat-button [routerLink]="option.link" routerLinkActive="active">{{ option.label | translate }}</a>
      }
    </nav>
    <div class="lang">
      <app-language-switcher/>
    </div>
  </mat-toolbar-row>
</mat-toolbar>
<router-outlet/>
<app-footer-content/>
```

**Reemplazar** el contenido de `layout.css`:

```css
mat-toolbar {
  background-color: darkslategrey;
  color: white;
}

.toolbar-grid {
  display: grid;
  grid-template-columns: 1fr auto 1fr;
  align-items: center;
  width: 100%;
}

.brand {
  justify-self: start;
  display: flex;
  gap: 8px;
  align-items: center;
}

.brand h1 {
  font-size: 1.25rem;
  margin: 0;
  font-weight: 500;
}

.brand img {
  background: white;
  border-radius: 4px;
  padding: 2px;
}

.nav-center {
  justify-self: center;
  display: flex;
  gap: 8px;
}

.nav-center a {
  color: white;
}

.nav-center a.active {
  background-color: rgba(255, 255, 255, 0.15);
}

.lang {
  justify-self: end;
}
```

### Modificación del App

**Reemplazar** el contenido de `app.ts`:

```ts
import { Component } from '@angular/core';
import { Layout } from './shared/presentation/components/layout/layout';

@Component({
  selector: 'app-root',
  imports: [Layout],
  templateUrl: './app.html',
  styleUrl: './app.css'
})
export class App {}
```

**Reemplazar** el contenido de `app.html`:

```html
<app-layout/>
```

### Modificación del Home Component

**Reemplazar** el contenido de `home.ts`:

```ts
import { Component, inject, Signal } from '@angular/core';
import { TranslatePipe } from '@ngx-translate/core';
import { MatGridListModule } from '@angular/material/grid-list';
import { CellarSummary } from '../../../../preservation/presentation/components/cellar-summary/cellar-summary';
import { PreservationStore } from '../../../../preservation/application/preservation-store';
import { Cellar } from '../../../../preservation/domain/model/cellar.entity';
import { PreservationItem } from '../../../../preservation/domain/model/preservation-item.entity';

/**
 * Home view displaying the welcome content and the "My Wine Cellars" section
 * with a grid of CellarSummary components.
 */
@Component({
  selector: 'app-home',
  imports: [TranslatePipe, MatGridListModule, CellarSummary],
  templateUrl: './home.html',
  styleUrl: './home.css'
})
export class Home {
  private readonly store = inject(PreservationStore);

  readonly cellars: Signal<Cellar[]> = this.store.cellars;
  readonly preservationItems: Signal<PreservationItem[]> = this.store.preservationItems;

  /**
   * Returns the preservation items associated with a given cellar id.
   *
   * @param cellarId The cellar identifier to filter items by.
   * @returns A computed array of PreservationItem entities for that cellar.
   */
  itemsByCellar(cellarId: number): PreservationItem[] {
    return this.preservationItems().filter(p => p.cellarId === cellarId);
  }
}
```

**Reemplazar** el contenido de `home.html`:

```html
<section class="home">
  <h1>{{ 'home.title' | translate }}</h1>
  <p class="lead">{{ 'home.content' | translate }}</p>

  <section class="cellars-section" aria-labelledby="my-wine-cellars-title">
    <h2 id="my-wine-cellars-title">{{ 'home.my-wine-cellars' | translate }}</h2>

    <mat-grid-list cols="2" rowHeight="280px" gutterSize="16px">
      @for (cellar of cellars(); track cellar.id) {
        <mat-grid-tile>
          <app-cellar-summary
            [cellar]="cellar"
            [items]="itemsByCellar(cellar.id)" />
        </mat-grid-tile>
      }
    </mat-grid-list>
  </section>
</section>
```

**Reemplazar** el contenido de `home.css`:

```css
:host { display: block; }

.home {
  display: flex;
  flex-direction: column;
  gap: 24px;
  padding: 24px;
  max-width: 1200px;
  margin: 0 auto;
}

.home h1 {
  font-size: 2rem;
  font-weight: 400;
  margin: 0;
  color: darkslategrey;
}

.lead {
  font-size: 1.1rem;
  color: #555;
  margin: 0;
}

.cellars-section h2 {
  font-size: 1.4rem;
  font-weight: 500;
  color: darkslategrey;
  margin: 0 0 16px 0;
  border-bottom: 2px solid darkslategrey;
  padding-bottom: 6px;
}

mat-grid-tile { background: transparent; }

mat-grid-tile ::ng-deep .mat-grid-tile-content {
  align-items: stretch;
}
```

### Modificación del PageNotFound Component

**Reemplazar** el contenido de `page-not-found.ts`:

```ts
import { Component, inject } from '@angular/core';
import { Router, RouterLink } from '@angular/router';
import { MatButtonModule } from '@angular/material/button';
import { TranslatePipe } from '@ngx-translate/core';

@Component({
  selector: 'app-page-not-found',
  imports: [MatButtonModule, RouterLink, TranslatePipe],
  templateUrl: './page-not-found.html',
  styleUrl: './page-not-found.css'
})
export class PageNotFound {
  protected invalidPath = inject(Router).url;
}
```

**Reemplazar** el contenido de `page-not-found.html`:

```html
<section class="page-not-found">
  <h1>{{ 'page-not-found.title' | translate }}</h1>
  <p [innerHTML]="'page-not-found.content' | translate: { invalidPath: invalidPath }"></p>
  <a mat-raised-button color="primary" routerLink="/home">{{ 'page-not-found.go-home' | translate }}</a>
</section>
```

**Reemplazar** el contenido de `page-not-found.css`:

```css
.page-not-found {
  text-align: center;
  padding: 64px 24px;
}

.page-not-found h1 {
  font-size: 3rem;
  color: darkslategrey;
  margin: 0 0 16px 0;
}
```

### Modificación del CellarSummary Component

**Reemplazar** el contenido de `cellar-summary.ts`:

```ts
import { Component, computed, input } from '@angular/core';
import { MatCardModule } from '@angular/material/card';
import { TranslatePipe } from '@ngx-translate/core';
import { Cellar } from '../../../domain/model/cellar.entity';
import { PreservationItem } from '../../../domain/model/preservation-item.entity';

/**
 * CellarSummary component displays a card with cellar name, wines stored,
 * total bottles and available capacity.
 */
@Component({
  selector: 'app-cellar-summary',
  imports: [MatCardModule, TranslatePipe],
  templateUrl: './cellar-summary.html',
  styleUrl: './cellar-summary.css'
})
export class CellarSummary {
  cellar = input.required<Cellar>();
  items = input.required<PreservationItem[]>();

  totalBottles = computed(() => this.items().reduce((s, p) => s + p.quantity, 0));
  availableCapacity = computed(() => this.cellar().capacity - this.totalBottles());
  isEmpty = computed(() => this.items().length === 0);
}
```

**Reemplazar** el contenido de `cellar-summary.html`:

```html
<mat-card appearance="outlined" class="cellar-summary-card" [attr.aria-label]="cellar().name">
  <mat-card-header>
    <mat-card-title>{{ cellar().name }}</mat-card-title>
  </mat-card-header>

  <mat-card-content>
    @if (isEmpty()) {
      <p class="empty">{{ 'cellar-summary.empty' | translate }}</p>
    } @else {
      <ul class="wines">
        @for (item of items(); track item.id) {
          <li>
            <span class="wine-name">{{ item.wineName }}</span>
            <span class="wine-quantity">{{ item.quantity }}</span>
          </li>
        }
      </ul>
    }
  </mat-card-content>

  <mat-card-footer class="card-footer">
    <div class="indicator">
      <span class="label">{{ 'cellar-summary.total-bottles' | translate }}</span>
      <span class="value">{{ totalBottles() }}</span>
    </div>
    <div class="indicator">
      <span class="label">{{ 'cellar-summary.available-capacity' | translate }}</span>
      <span class="value">{{ availableCapacity() }}</span>
    </div>
  </mat-card-footer>
</mat-card>
```

**Reemplazar** el contenido de `cellar-summary.css`:

```css
.cellar-summary-card {
  width: 100%;
  display: flex;
  flex-direction: column;
}

mat-card-header {
  border-bottom: 1px solid rgba(0, 0, 0, 0.08);
  padding-bottom: 12px;
  margin-bottom: 12px;
}

mat-card-title {
  font-size: 1.15rem;
  font-weight: 500;
  color: darkslategrey;
}

mat-card-content {
  flex: 1;
  min-height: 80px;
}

.empty {
  text-align: center;
  color: #888;
  font-style: italic;
  margin: 16px 0;
}

.wines {
  list-style: none;
  padding: 0;
  margin: 0;
}

.wines li {
  display: flex;
  justify-content: space-between;
  padding: 6px 0;
  border-bottom: 1px dashed rgba(0, 0, 0, 0.06);
}

.wines li:last-child { border-bottom: none; }

.wine-name { color: #333; }

.wine-quantity {
  color: darkslategrey;
  font-weight: 500;
}

.card-footer {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  gap: 24px;
  border-top: 1px solid rgba(0, 0, 0, 0.08);
  padding: 16px 8px 8px;
  margin-top: 16px;
}

.indicator {
  display: flex;
  flex-direction: column;
  gap: 4px;
  flex: 1;
}

.indicator:last-child {
  text-align: right;
  align-items: flex-end;
}

.indicator .label {
  font-size: 0.7rem;
  color: #666;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  white-space: nowrap;
}

.indicator .value {
  font-size: 1.4rem;
  font-weight: 500;
  color: darkslategrey;
  line-height: 1;
}
```

### Modificación del NewPreservationItem Component

**Reemplazar** el contenido de `new-preservation-item.ts`:

```ts
import { Component, computed, inject, signal } from '@angular/core';
import { CommonModule } from '@angular/common';
import { FormBuilder, FormControl, ReactiveFormsModule, Validators } from '@angular/forms';
import { Router } from '@angular/router';
import { MatButtonModule } from '@angular/material/button';
import { MatFormFieldModule } from '@angular/material/form-field';
import { MatInputModule } from '@angular/material/input';
import { MatSelectModule } from '@angular/material/select';
import { MatProgressSpinnerModule } from '@angular/material/progress-spinner';
import { TranslatePipe } from '@ngx-translate/core';
import { PreservationStore } from '../../../application/preservation-store';
import { WineryStore } from '../../../../winery/application/winery-store';
import { PreservationItem } from '../../../domain/model/preservation-item.entity';

/**
 * NewPreservationItem view provides a form to register a new preservation item
 * by selecting a wine type, wine, and quantity.
 */
@Component({
  selector: 'app-new-preservation-item',
  imports: [
    CommonModule,
    ReactiveFormsModule,
    MatFormFieldModule,
    MatInputModule,
    MatSelectModule,
    MatButtonModule,
    MatProgressSpinnerModule,
    TranslatePipe
  ],
  templateUrl: './new-preservation-item.html',
  styleUrl: './new-preservation-item.css'
})
export class NewPreservationItem {
  private readonly fb = inject(FormBuilder);
  private readonly router = inject(Router);
  protected readonly preservationStore = inject(PreservationStore);
  protected readonly wineryStore = inject(WineryStore);

  protected readonly wineTypes = ['reds', 'whites', 'sparkling', 'rose', 'dessert', 'port'];

  protected readonly selectedWineType = signal<string | null>(null);
  protected readonly availableCapacity = computed(() => {
    const type = this.selectedWineType();
    if (!type) return 0;
    const cellar = this.preservationStore.getCellarByWineType(type);
    if (!cellar) return 0;
    return this.preservationStore.availableCapacityFor(cellar.id);
  });

  protected readonly form = this.fb.group({
    wineType: new FormControl<string | null>(null, { validators: [Validators.required] }),
    wineId: new FormControl<number | null>(null, { validators: [Validators.required] }),
    quantity: new FormControl<number | null>(null, {
      validators: [Validators.required, Validators.min(1)]
    })
  });

  onWineTypeChange(wineType: string): void {
    this.selectedWineType.set(wineType);
    this.form.patchValue({ wineId: null });
    this.wineryStore.loadWinesByType(wineType);
  }

  submit(): void {
    if (this.form.invalid) return;

    const wineType = this.form.value.wineType!;
    const wineId = this.form.value.wineId!;
    const quantity = this.form.value.quantity!;
    const cellar = this.preservationStore.getCellarByWineType(wineType);

    if (!cellar) return;
    if (quantity > this.availableCapacity()) return;

    const wine = this.wineryStore.wines().find(w => w.id === wineId);
    if (!wine) return;

    const item = new PreservationItem({
      id: 0,
      cellarId: cellar.id,
      wineType,
      wineId: wine.id,
      wineName: wine.wine,
      quantity,
      registeredAt: new Date().toISOString()
    });

    this.preservationStore.addPreservationItem(item);
    this.router.navigate(['/home']).then();
  }

  cancel(): void {
    this.router.navigate(['/home']).then();
  }
}
```

**Reemplazar** el contenido de `new-preservation-item.html`:

```html
<section class="new-preservation-item">
  <header>
    <h1>{{ 'new-preservation-item.title' | translate }}</h1>
    <p class="subtitle">{{ 'new-preservation-item.subtitle' | translate }}</p>
  </header>

  <form [formGroup]="form" (ngSubmit)="submit()" aria-label="New preservation item form">
    <mat-form-field appearance="outline">
      <mat-label>{{ 'new-preservation-item.wine-type' | translate }}</mat-label>
      <mat-select formControlName="wineType"
                  (selectionChange)="onWineTypeChange($event.value)"
                  required>
        @for (type of wineTypes; track type) {
          <mat-option [value]="type">{{ 'wine-type.' + type | translate }}</mat-option>
        }
      </mat-select>
      @if (form.get('wineType')!.touched && form.get('wineType')!.hasError('required')) {
        <mat-error>{{ 'new-preservation-item.wine-type-required' | translate }}</mat-error>
      }
    </mat-form-field>

    <mat-form-field appearance="outline">
      <mat-label>{{ 'new-preservation-item.wine' | translate }}</mat-label>
      <mat-select formControlName="wineId" required>
        @if (wineryStore.loading()) {
          <mat-option disabled>
            <mat-spinner diameter="20"></mat-spinner>
          </mat-option>
        }
        @for (wine of wineryStore.wines(); track wine.id) {
          <mat-option [value]="wine.id">{{ wine.wine }}</mat-option>
        }
      </mat-select>
      @if (form.get('wineId')!.touched && form.get('wineId')!.hasError('required')) {
        <mat-error>{{ 'new-preservation-item.wine-required' | translate }}</mat-error>
      }
    </mat-form-field>

    <mat-form-field appearance="outline">
      <mat-label>{{ 'new-preservation-item.quantity' | translate }}</mat-label>
      <input matInput
             type="number"
             formControlName="quantity"
             min="1"
             [max]="availableCapacity()"
             required />
      @if (form.get('quantity')!.touched && form.get('quantity')!.hasError('required')) {
        <mat-error>{{ 'new-preservation-item.quantity-required' | translate }}</mat-error>
      }
      @if (form.get('quantity')!.touched && form.get('quantity')!.hasError('min')) {
        <mat-error>{{ 'new-preservation-item.quantity-min' | translate }}</mat-error>
      }
      @if (form.get('quantity')!.value && form.get('quantity')!.value! > availableCapacity()) {
        <mat-error>
          {{ 'new-preservation-item.quantity-exceeds' | translate: { available: availableCapacity() } }}
        </mat-error>
      }
    </mat-form-field>

    <div class="actions">
      <button mat-stroked-button type="button" (click)="cancel()">
        {{ 'new-preservation-item.cancel' | translate }}
      </button>
      <button mat-raised-button color="primary" type="submit"
              [disabled]="form.invalid || (form.value.quantity ?? 0) > availableCapacity()">
        {{ 'new-preservation-item.create' | translate }}
      </button>
    </div>
  </form>
</section>
```

**Reemplazar** el contenido de `new-preservation-item.css`:

```css
.new-preservation-item {
  max-width: 600px;
  margin: 0 auto;
  padding: 24px;
  display: flex;
  flex-direction: column;
  gap: 16px;
}

header h1 {
  font-size: 1.8rem;
  font-weight: 400;
  color: darkslategrey;
  margin: 0;
}

.subtitle {
  font-size: 1rem;
  color: #666;
  margin: 4px 0 16px 0;
}

form {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

mat-form-field {
  width: 100%;
}

.actions {
  display: flex;
  justify-content: flex-end;
  gap: 12px;
  margin-top: 16px;
}
```

## Ejecución del proyecto

**Cargar** dos tabs del `Terminal` del IDE.

**Tab 1** - Ejecutar el `json-server`:

```bash
cd server
json-server --watch db.json
```

**Tab 2** - Ejecutar Angular:

```bash
ng serve --port 4200
```

**Cargar** el navegador en http://localhost:4200

## Empaquetado para entrega

Antes de generar el archivo `.zip`:

1. **Eliminar** la carpeta `node_modules`.
2. **Comprimir** el proyecto siguiendo la convención `eanrcucode.zip` (por ejemplo `ea20262u201821873.zip`).

## Actividad

- **Probar** los flujos de Home y New Preservation Item.
- **Verificar** validación de capacidad (`quantity ≤ availableCapacity`).
- **Verificar** que el cellar correcto se asocie según el wine type.
- **Verificar** i18n en/es y ARIA attributes en cada vista.
