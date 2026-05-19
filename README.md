# Proyecto South American Geographic Observatory (SAGO) v202610

## Creación del proyecto

> [!CAUTION]
> **En el caso de estar en un equipo MAC:**
> - Debe anteceder el comando `sudo` al ejecutar las instrucciones: `ng` y `chown`, y luego ingresar la contraseña del Administrador (`d3v3l0p3rUPC`).
> - Debe ubicarse en la carpeta `/Users/alumnos/IdeaProjects/1asi0729/202610` o en otra de su preferencia.

> [!CAUTION]
> **En el caso de estar en un equipo Windows:**
> - Debe ubicarse en la carpeta `IdeaProjects/` o en otra de su preferencia.

A continuación se detalla las instrucciones para crear un nuevo `workspace` e `initial starter app` de Angular. Más información en: https://angular.dev/tools/cli/setup-local

### Creación de un workspace y un initial application

**Cargar** el `Terminal` del sistema Operativo, ubicarse en la carpeta de su preferencia de acuerdo al Sistema Operativo y **ejecutar** el siguiente CLI command:

```bash
ng new eanrcucode
```

Reemplace `eanrcucode` por el nombre real del proyecto (por ejemplo `ea11990u201621873`).

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
    "new-country-item": "New Country Item"
  },
  "home": {
    "title": "Home",
    "content": "Engineered Products for South American Regional Studies.",
    "my-geographic-observatories": "My Geographic Observatories"
  },
  "observatory-summary": {
    "total-registered-countries": "Total Registered Countries",
    "accumulated-population": "Accumulated Population",
    "empty": "Empty"
  },
  "new-country-item": {
    "title": "New Country Item",
    "subtitle": "Add South American Countries to Your Observatory",
    "country": "Country",
    "official-name": "Official Name",
    "flag-url": "Flag URL",
    "area": "Area (km²)",
    "population": "Population",
    "start-of-week": "Start of Week",
    "create": "Create",
    "cancel": "Cancel",
    "search-country": "Search a country...",
    "country-required": "Country is required",
    "not-independent": "Country must be independent",
    "area-too-small": "Country area must be greater than 100,000 km²"
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
    "new-country-item": "Nuevo Artículo de País"
  },
  "home": {
    "title": "Inicio",
    "content": "Productos de ingeniería para estudios regionales sudamericanos.",
    "my-geographic-observatories": "Mis Observatorios Geográficos"
  },
  "observatory-summary": {
    "total-registered-countries": "Total de Países Registrados",
    "accumulated-population": "Población Acumulada",
    "empty": "Vacío"
  },
  "new-country-item": {
    "title": "Nuevo Artículo de País",
    "subtitle": "Añade países sudamericanos a tu observatorio",
    "country": "País",
    "official-name": "Nombre Oficial",
    "flag-url": "URL de Bandera",
    "area": "Área (km²)",
    "population": "Población",
    "start-of-week": "Inicio de Semana",
    "create": "Crear",
    "cancel": "Cancelar",
    "search-country": "Buscar un país...",
    "country-required": "El país es obligatorio",
    "not-independent": "El país debe ser independiente",
    "area-too-small": "El área del país debe ser mayor a 100,000 km²"
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
  "geographic-observatories": [
    {
      "id": "1",
      "name": "Observatorio Geográfico Andino",
      "regionCode": "AND"
    },
    {
      "id": "2",
      "name": "Observatorio de la Cuenca del Amazonas",
      "regionCode": "AMA"
    },
    {
      "id": "3",
      "name": "Observatorio del Cono Sur",
      "regionCode": "CSU"
    }
  ],
  "country-items": [
    {
      "id": "1",
      "observatoryId": "1",
      "regionCode": "AND",
      "countryName": "Peru",
      "officialName": "Republic of Peru",
      "flagUrl": "https://flagcdn.com/images/flags/pe.svg",
      "area": 1285216.0,
      "population": 32971846,
      "startOfWeek": "monday",
      "registeredAt": "2026-05-19T14:30:00.000Z"
    },
    {
      "id": "2",
      "observatoryId": "1",
      "regionCode": "AND",
      "countryName": "Colombia",
      "officialName": "Republic of Colombia",
      "flagUrl": "https://flagcdn.com/images/flags/co.svg",
      "area": 1141748.0,
      "population": 50882884,
      "startOfWeek": "monday",
      "registeredAt": "2026-05-19T14:35:00.000Z"
    },
    {
      "id": "3",
      "observatoryId": "2",
      "regionCode": "AMA",
      "countryName": "Brazil",
      "officialName": "Federative Republic of Brazil",
      "flagUrl": "https://flagcdn.com/images/flags/br.svg",
      "area": 8515767.0,
      "population": 212559409,
      "startOfWeek": "monday",
      "registeredAt": "2026-05-19T14:40:00.000Z"
    },
    {
      "id": "4",
      "observatoryId": "3",
      "regionCode": "CSU",
      "countryName": "Argentina",
      "officialName": "Argentine Republic",
      "flagUrl": "https://flagcdn.com/images/flags/ar.svg",
      "area": 2780400.0,
      "population": 45376763,
      "startOfWeek": "monday",
      "registeredAt": "2026-05-19T14:45:00.000Z"
    },
    {
      "id": "5",
      "observatoryId": "3",
      "regionCode": "CSU",
      "countryName": "Chile",
      "officialName": "Republic of Chile",
      "flagUrl": "https://flagcdn.com/images/flags/cl.svg",
      "area": 756102.0,
      "population": 19116209,
      "startOfWeek": "monday",
      "registeredAt": "2026-05-19T14:50:00.000Z"
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

- http://localhost:3000/geographic-observatories
- http://localhost:3000/country-items

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
sagoProviderApiBaseUrl: 'http://localhost:3000',
sagoProviderGeographicObservatoriesEndpointPath: '/geographic-observatories',
sagoProviderCountryItemsEndpointPath: '/country-items',
restCountriesApiBaseUrl: 'https://restcountries.com/v3.1',
restCountriesSubregionEndpointPath: '/subregion/South%20America',
restCountriesFields: 'fields=name,flags,region,subregion,area,population,independent,startOfWeek,flag',
```

**Agregar** los siguientes valores a la constante `environment` del archivo `environment.ts` ubicado en la carpeta `environments`:

```ts
production: true,
sagoProviderApiBaseUrl: 'http://localhost:3000',
sagoProviderGeographicObservatoriesEndpointPath: '/geographic-observatories',
sagoProviderCountryItemsEndpointPath: '/country-items',
restCountriesApiBaseUrl: 'https://restcountries.com/v3.1',
restCountriesSubregionEndpointPath: '/subregion/South%20America',
restCountriesFields: 'fields=name,flags,region,subregion,area,population,independent,startOfWeek,flag',
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
    - 📂 observatories
      - 📁 application
      - 📁 domain
        - 📁 model
      - 📁 infrastructure
      - 📁 presentation
        - 📁 components
        - 📁 views
    - 📂 geographic
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
  id: string;
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
  id: string;
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
  getById(id: string): Observable<TEntity> {
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
  update(entity: TEntity, id: string): Observable<TEntity> {
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
  delete(id: string): Observable<void> {
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

## Analizando la SAGO API

### Analizando el endpoint geographic-observatories

Diríjase al endpoint local http://localhost:3000/geographic-observatories y **evalúe** el json de respuesta:

```json
[
  { "id": "1", "name": "Observatorio Geográfico Andino", "regionCode": "AND" }
]
```

### Creación de la interface GeographicObservatory tipo Response

**Ejecutar** el siguiente CLI command para crear la interface `GeographicObservatories` tipo `response`:

```bash
ng generate interface observatories/infrastructure/geographic-observatories-response
```

**Reemplazar** el contenido de `geographic-observatories-response.ts`:

```ts
import { BaseResource, BaseResponse } from '../../shared/infrastructure/base-response';

/**
 * Represents the response structure for geographic observatory API calls.
 *
 * @interface GeographicObservatoriesResponse
 * @extends BaseResponse
 */
export interface GeographicObservatoriesResponse extends BaseResponse {
  geographicObservatories: GeographicObservatoryResource[];
}

/**
 * Represents a resource for a geographic observatory.
 *
 * @interface GeographicObservatoryResource
 * @extends BaseResource
 */
export interface GeographicObservatoryResource extends BaseResource {
  id: string;
  name: string;
  regionCode: string;
}
```

### Creación del class GeographicObservatory tipo entity (model)

**Ejecutar** el siguiente CLI command para crear el modelo `geographic-observatory`:

```bash
ng generate class observatories/domain/model/geographic-observatory --type=entity --skip-tests=true
```

**Agregar** el siguiente `import` y la interface `BaseEntity` a la clase `GeographicObservatory`:

```ts
import { BaseEntity } from '../../../shared/infrastructure/base-entity';

/**
 * Represents a Geographic Observatory entity.
 * Implements the BaseEntity interface.
 */
export class GeographicObservatory implements BaseEntity
```

**Agregar** los siguientes atributos y constructor a la clase `GeographicObservatory`:

```ts
private _id!: string;
private _name!: string;
private _regionCode!: string;

/**
 * Constructs an instance of GeographicObservatory.
 *
 * @param {Object} observatory - The observatory details.
 * @param {string} observatory.id - The unique identifier.
 * @param {string} observatory.name - The name of the observatory.
 * @param {string} observatory.regionCode - The region code of the observatory.
 */
constructor(observatory: { id: string; name: string; regionCode: string }) {
  this._id = observatory.id;
  this._name = observatory.name;
  this._regionCode = observatory.regionCode;
}

get id(): string { return this._id; }
set id(value: string) { this._id = value; }

get name(): string { return this._name; }
set name(value: string) { this._name = value; }

get regionCode(): string { return this._regionCode; }
set regionCode(value: string) { this._regionCode = value; }
```

### Creación del class GeographicObservatory tipo Assembler

**Ejecutar** el siguiente CLI command:

```bash
ng generate class observatories/infrastructure/geographic-observatory-assembler --skip-tests=true
```

**Reemplazar** el contenido de `geographic-observatory-assembler.ts`:

```ts
import { BaseAssembler } from '../../shared/infrastructure/base-assembler';
import { GeographicObservatory } from '../domain/model/geographic-observatory.entity';
import { GeographicObservatoryResource, GeographicObservatoriesResponse } from './geographic-observatories-response';

/**
 * Assembler for converting between GeographicObservatory entities, resources, and responses.
 */
export class GeographicObservatoryAssembler
  implements BaseAssembler<GeographicObservatory, GeographicObservatoryResource, GeographicObservatoriesResponse> {

  toEntitiesFromResponse(response: GeographicObservatoriesResponse): GeographicObservatory[] {
    return response.geographicObservatories.map(r => this.toEntityFromResource(r));
  }

  toEntityFromResource(resource: GeographicObservatoryResource): GeographicObservatory {
    return new GeographicObservatory({
      id: resource.id,
      name: resource.name,
      regionCode: resource.regionCode
    });
  }

  toResourceFromEntity(entity: GeographicObservatory): GeographicObservatoryResource {
    return {
      id: entity.id,
      name: entity.name,
      regionCode: entity.regionCode
    } as GeographicObservatoryResource;
  }
}
```

### Analizando el endpoint country-items

Diríjase al endpoint local http://localhost:3000/country-items y **evalúe** el json de respuesta:

```json
[
  {
    "id": "1",
    "observatoryId": "1",
    "regionCode": "AND",
    "countryName": "Peru",
    "officialName": "Republic of Peru",
    "flagUrl": "https://flagcdn.com/images/flags/pe.svg",
    "area": 1285216.0,
    "population": 32971846,
    "startOfWeek": "monday",
    "registeredAt": "2026-05-19T14:30:00.000Z"
  }
]
```

### Creación de la interface CountryItem tipo Response

**Ejecutar** el siguiente CLI command:

```bash
ng generate interface observatories/infrastructure/country-items-response
```

**Reemplazar** el contenido de `country-items-response.ts`:

```ts
import { BaseResource, BaseResponse } from '../../shared/infrastructure/base-response';

/**
 * Represents the response structure for country item API calls.
 *
 * @interface CountryItemsResponse
 * @extends BaseResponse
 */
export interface CountryItemsResponse extends BaseResponse {
  countryItems: CountryItemResource[];
}

/**
 * Represents a country item resource returned by the API.
 *
 * @interface CountryItemResource
 * @extends BaseResource
 */
export interface CountryItemResource extends BaseResource {
  id: string;
  observatoryId: string;
  regionCode: string;
  countryName: string;
  officialName: string;
  flagUrl: string;
  area: number;
  population: number;
  startOfWeek: string;
  registeredAt: string;
}
```

### Creación del class CountryItem tipo entity (model)

**Ejecutar** el siguiente CLI command:

```bash
ng generate class observatories/domain/model/country-item --type=entity --skip-tests=true
```

**Agregar** el `import` y la interface `BaseEntity` a la clase `CountryItem`:

```ts
import { BaseEntity } from '../../../shared/infrastructure/base-entity';

/**
 * Represents a Country Item stored under a Geographic Observatory.
 */
export class CountryItem implements BaseEntity
```

**Agregar** los siguientes atributos y constructor:

```ts
private _id!: string;
private _observatoryId!: string;
private _regionCode!: string;
private _countryName!: string;
private _officialName!: string;
private _flagUrl!: string;
private _area!: number;
private _population!: number;
private _startOfWeek!: string;
private _registeredAt!: string;

/**
 * Constructs a new CountryItem instance.
 *
 * @param {Object} countryItem - The country item details.
 * @param {string} countryItem.id - The unique identifier.
 * @param {string} countryItem.observatoryId - The associated observatory identifier.
 * @param {string} countryItem.regionCode - The region code of the observatory.
 * @param {string} countryItem.countryName - The common name of the country.
 * @param {string} countryItem.officialName - The official name of the country.
 * @param {string} countryItem.flagUrl - The URL of the country flag (SVG).
 * @param {number} countryItem.area - The territorial area in km².
 * @param {number} countryItem.population - The population count.
 * @param {string} countryItem.startOfWeek - The start of week convention.
 * @param {string} countryItem.registeredAt - The ISO 8601 registration date.
 */
constructor(countryItem: {
  id: string;
  observatoryId: string;
  regionCode: string;
  countryName: string;
  officialName: string;
  flagUrl: string;
  area: number;
  population: number;
  startOfWeek: string;
  registeredAt: string;
}) {
  this._id = countryItem.id;
  this._observatoryId = countryItem.observatoryId;
  this._regionCode = countryItem.regionCode;
  this._countryName = countryItem.countryName;
  this._officialName = countryItem.officialName;
  this._flagUrl = countryItem.flagUrl;
  this._area = countryItem.area;
  this._population = countryItem.population;
  this._startOfWeek = countryItem.startOfWeek;
  this._registeredAt = countryItem.registeredAt;
}

get id(): string { return this._id; }
set id(value: string) { this._id = value; }

get observatoryId(): string { return this._observatoryId; }
set observatoryId(value: string) { this._observatoryId = value; }

get regionCode(): string { return this._regionCode; }
set regionCode(value: string) { this._regionCode = value; }

get countryName(): string { return this._countryName; }
set countryName(value: string) { this._countryName = value; }

get officialName(): string { return this._officialName; }
set officialName(value: string) { this._officialName = value; }

get flagUrl(): string { return this._flagUrl; }
set flagUrl(value: string) { this._flagUrl = value; }

get area(): number { return this._area; }
set area(value: number) { this._area = value; }

get population(): number { return this._population; }
set population(value: number) { this._population = value; }

get startOfWeek(): string { return this._startOfWeek; }
set startOfWeek(value: string) { this._startOfWeek = value; }

get registeredAt(): string { return this._registeredAt; }
set registeredAt(value: string) { this._registeredAt = value; }
```

### Creación del class CountryItem tipo Assembler

**Ejecutar** el siguiente CLI command:

```bash
ng generate class observatories/infrastructure/country-item-assembler --skip-tests=true
```

**Reemplazar** el contenido de `country-item-assembler.ts`:

```ts
import { BaseAssembler } from '../../shared/infrastructure/base-assembler';
import { CountryItem } from '../domain/model/country-item.entity';
import { CountryItemResource, CountryItemsResponse } from './country-items-response';

/**
 * Assembler for converting between CountryItem entities, resources, and responses.
 */
export class CountryItemAssembler
  implements BaseAssembler<CountryItem, CountryItemResource, CountryItemsResponse> {

  toEntitiesFromResponse(response: CountryItemsResponse): CountryItem[] {
    return response.countryItems.map(r => this.toEntityFromResource(r));
  }

  toEntityFromResource(resource: CountryItemResource): CountryItem {
    return new CountryItem({
      id: resource.id,
      observatoryId: resource.observatoryId,
      regionCode: resource.regionCode,
      countryName: resource.countryName,
      officialName: resource.officialName,
      flagUrl: resource.flagUrl,
      area: resource.area,
      population: resource.population,
      startOfWeek: resource.startOfWeek,
      registeredAt: resource.registeredAt
    });
  }

  toResourceFromEntity(entity: CountryItem): CountryItemResource {
    return {
      id: entity.id,
      observatoryId: entity.observatoryId,
      regionCode: entity.regionCode,
      countryName: entity.countryName,
      officialName: entity.officialName,
      flagUrl: entity.flagUrl,
      area: entity.area,
      population: entity.population,
      startOfWeek: entity.startOfWeek,
      registeredAt: entity.registeredAt
    } as CountryItemResource;
  }
}
```

## Creación del ObservatoriesApi Service

### Creación del class GeographicObservatories tipo ApiEndpoint

**Ejecutar** el siguiente CLI command:

```bash
ng generate class observatories/infrastructure/geographic-observatories-api-endpoint --skip-tests=true
```

**Reemplazar** el contenido de `geographic-observatories-api-endpoint.ts`:

```ts
import { BaseApiEndpoint } from '../../shared/infrastructure/base-api-endpoint';
import { GeographicObservatory } from '../domain/model/geographic-observatory.entity';
import { GeographicObservatoryResource, GeographicObservatoriesResponse } from './geographic-observatories-response';
import { GeographicObservatoryAssembler } from './geographic-observatory-assembler';
import { HttpClient } from '@angular/common/http';
import { environment } from '../../../environments/environment';

/**
 * API endpoint for Geographic Observatory operations.
 * Communicates with the SAGO Provider's geographic observatories endpoint.
 */
export class GeographicObservatoriesApiEndpoint extends BaseApiEndpoint<
  GeographicObservatory, GeographicObservatoryResource, GeographicObservatoriesResponse, GeographicObservatoryAssembler
> {
  constructor(http: HttpClient) {
    super(
      http,
      `${environment.sagoProviderApiBaseUrl}${environment.sagoProviderGeographicObservatoriesEndpointPath}`,
      new GeographicObservatoryAssembler()
    );
  }
}
```

### Creación del class CountryItem tipo ApiEndpoint

**Ejecutar** el siguiente CLI command:

```bash
ng generate class observatories/infrastructure/country-item-api-endpoint --skip-tests=true
```

**Reemplazar** el contenido de `country-item-api-endpoint.ts`:

```ts
import { BaseApiEndpoint } from '../../shared/infrastructure/base-api-endpoint';
import { HttpClient } from '@angular/common/http';
import { environment } from '../../../environments/environment';
import { CountryItem } from '../domain/model/country-item.entity';
import { CountryItemResource, CountryItemsResponse } from './country-items-response';
import { CountryItemAssembler } from './country-item-assembler';

/**
 * API endpoint for Country Item operations.
 * Communicates with the SAGO Provider's country items endpoint.
 */
export class CountryItemApiEndpoint extends BaseApiEndpoint<
  CountryItem, CountryItemResource, CountryItemsResponse, CountryItemAssembler
> {
  constructor(http: HttpClient) {
    super(
      http,
      `${environment.sagoProviderApiBaseUrl}${environment.sagoProviderCountryItemsEndpointPath}`,
      new CountryItemAssembler()
    );
  }
}
```

### Creación del class Observatories tipo Api

**Ejecutar** el siguiente CLI command:

```bash
ng generate service observatories/infrastructure/observatories-api --skip-tests=true
```

**Reemplazar** el contenido de `observatories-api.ts`:

```ts
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';
import { BaseApi } from '../../shared/infrastructure/base-api';
import { CountryItem } from '../domain/model/country-item.entity';
import { GeographicObservatory } from '../domain/model/geographic-observatory.entity';
import { GeographicObservatoriesApiEndpoint } from './geographic-observatories-api-endpoint';
import { CountryItemApiEndpoint } from './country-item-api-endpoint';

/**
 * ObservatoriesApi provides methods for interacting with geographic observatory
 * and country item API endpoints.
 */
@Injectable({ providedIn: 'root' })
export class ObservatoriesApi extends BaseApi {
  private countryItemApiEndpoint: CountryItemApiEndpoint;
  private geographicObservatoriesApiEndpoint: GeographicObservatoriesApiEndpoint;

  constructor(private http: HttpClient) {
    super();
    this.countryItemApiEndpoint = new CountryItemApiEndpoint(http);
    this.geographicObservatoriesApiEndpoint = new GeographicObservatoriesApiEndpoint(http);
  }

  /**
   * Retrieves all geographic observatories.
   * @return {Observable<GeographicObservatory[]>} Observable emitting an array of observatories.
   */
  getGeographicObservatories(): Observable<GeographicObservatory[]> {
    return this.geographicObservatoriesApiEndpoint.getAll();
  }

  /**
   * Retrieves all country items.
   * @return {Observable<CountryItem[]>} Observable emitting an array of country items.
   */
  getCountryItems(): Observable<CountryItem[]> {
    return this.countryItemApiEndpoint.getAll();
  }

  /**
   * Creates a new country item.
   * @param {CountryItem} item - The country item to persist.
   * @return {Observable<CountryItem>} Observable emitting the created country item.
   */
  createCountryItem(item: CountryItem): Observable<CountryItem> {
    return this.countryItemApiEndpoint.create(item);
  }
}
```

## Analizando REST Countries API (Geographic)

Diríjase al endpoint https://restcountries.com/v3.1/subregion/South%20America?fields=name,flags,region,subregion,area,population,independent,startOfWeek,flag y **evalúe** el json de respuesta:

```json
[
  {
    "flags": {
      "png": "https://flagcdn.com/w320/pe.png",
      "svg": "https://flagcdn.com/images/flags/pe.svg",
      "alt": "The flag of Peru features three vertical bands of red, white and red..."
    },
    "name": {
      "common": "Peru",
      "official": "Republic of Peru",
      "nativeName": { }
    },
    "independent": true,
    "region": "Americas",
    "subregion": "South America",
    "area": 1285216.0,
    "population": 32971846,
    "startOfWeek": "monday",
    "flag": "🇵🇪"
  }
]
```

### Creación de la interface Country tipo Response

**Ejecutar** el siguiente CLI command:

```bash
ng generate interface geographic/infrastructure/countries-response
```

**Reemplazar** el contenido de `countries-response.ts`:

```ts
import { BaseResource, BaseResponse } from '../../shared/infrastructure/base-response';

/**
 * Represents a country resource returned by the REST Countries API v3.1.
 *
 * @interface CountryResource
 * @extends BaseResource
 */
export interface CountryResource extends BaseResource {
  flags: {
    png: string;
    svg: string;
    alt: string;
  };
  name: {
    common: string;
    official: string;
  };
  independent: boolean;
  region: string;
  subregion: string;
  area: number;
  population: number;
  startOfWeek: string;
  flag: string;
}

export type CountriesResponse = CountryResource[];
```

> [!NOTE]
> REST Countries API devuelve un array plano (no envoltorio con propiedad `countries`). Por eso `CountriesResponse` es un alias del array. El `id` requerido por `BaseResource` se mapea desde `name.common` en el assembler.

### Creación del class Country tipo entity (model)

**Ejecutar** el siguiente CLI command:

```bash
ng generate class geographic/domain/model/country --type=entity --skip-tests=true
```

**Agregar** el `import` y la interface `BaseEntity` a la clase `Country`:

```ts
import { BaseEntity } from '../../../shared/infrastructure/base-entity';

/**
 * Represents a Country entity retrieved from REST Countries API.
 * Implements the BaseEntity interface.
 */
export class Country implements BaseEntity
```

**Agregar** los siguientes atributos y constructor:

```ts
private _id!: string;
private _commonName!: string;
private _officialName!: string;
private _flagSvg!: string;
private _flagPng!: string;
private _flagAlt!: string;
private _flagEmoji!: string;
private _independent!: boolean;
private _region!: string;
private _subregion!: string;
private _area!: number;
private _population!: number;
private _startOfWeek!: string;

/**
 * Constructs a new Country instance.
 *
 * @param {Object} country - The country details.
 * @param {string} country.id - Unique identifier (common name used as key).
 * @param {string} country.commonName - The common name of the country.
 * @param {string} country.officialName - The official name of the country.
 * @param {string} country.flagSvg - The SVG URL of the country flag.
 * @param {string} country.flagPng - The PNG URL of the country flag.
 * @param {string} country.flagAlt - The alt text for the country flag.
 * @param {string} country.flagEmoji - The emoji representation of the flag.
 * @param {boolean} country.independent - Whether the country is independent.
 * @param {string} country.region - The region of the country.
 * @param {string} country.subregion - The subregion of the country.
 * @param {number} country.area - The area in km².
 * @param {number} country.population - The population count.
 * @param {string} country.startOfWeek - The start of week convention.
 */
constructor(country: {
  id: string;
  commonName: string;
  officialName: string;
  flagSvg: string;
  flagPng: string;
  flagAlt: string;
  flagEmoji: string;
  independent: boolean;
  region: string;
  subregion: string;
  area: number;
  population: number;
  startOfWeek: string;
}) {
  this._id = country.id;
  this._commonName = country.commonName;
  this._officialName = country.officialName;
  this._flagSvg = country.flagSvg;
  this._flagPng = country.flagPng;
  this._flagAlt = country.flagAlt;
  this._flagEmoji = country.flagEmoji;
  this._independent = country.independent;
  this._region = country.region;
  this._subregion = country.subregion;
  this._area = country.area;
  this._population = country.population;
  this._startOfWeek = country.startOfWeek;
}

get id(): string { return this._id; }
set id(value: string) { this._id = value; }

get commonName(): string { return this._commonName; }
set commonName(value: string) { this._commonName = value; }

get officialName(): string { return this._officialName; }
set officialName(value: string) { this._officialName = value; }

get flagSvg(): string { return this._flagSvg; }
set flagSvg(value: string) { this._flagSvg = value; }

get flagPng(): string { return this._flagPng; }
set flagPng(value: string) { this._flagPng = value; }

get flagAlt(): string { return this._flagAlt; }
set flagAlt(value: string) { this._flagAlt = value; }

get flagEmoji(): string { return this._flagEmoji; }
set flagEmoji(value: string) { this._flagEmoji = value; }

get independent(): boolean { return this._independent; }
set independent(value: boolean) { this._independent = value; }

get region(): string { return this._region; }
set region(value: string) { this._region = value; }

get subregion(): string { return this._subregion; }
set subregion(value: string) { this._subregion = value; }

get area(): number { return this._area; }
set area(value: number) { this._area = value; }

get population(): number { return this._population; }
set population(value: number) { this._population = value; }

get startOfWeek(): string { return this._startOfWeek; }
set startOfWeek(value: string) { this._startOfWeek = value; }
```

### Creación del class Country tipo Assembler

**Ejecutar** el siguiente CLI command:

```bash
ng generate class geographic/infrastructure/country-assembler --skip-tests=true
```

**Reemplazar** el contenido de `country-assembler.ts`:

```ts
import { BaseAssembler } from '../../shared/infrastructure/base-assembler';
import { Country } from '../domain/model/country.entity';
import { CountryResource, CountriesResponse } from './countries-response';

/**
 * Assembler for converting between Country entities, CountryResource DTOs, and CountriesResponse.
 */
export class CountryAssembler implements BaseAssembler<Country, CountryResource, CountriesResponse> {

  toEntitiesFromResponse(response: CountriesResponse): Country[] {
    return response.map(r => this.toEntityFromResource(r));
  }

  toEntityFromResource(resource: CountryResource): Country {
    return new Country({
      id: resource.name.common,
      commonName: resource.name.common,
      officialName: resource.name.official,
      flagSvg: resource.flags.svg,
      flagPng: resource.flags.png,
      flagAlt: resource.flags.alt,
      flagEmoji: resource.flag,
      independent: resource.independent,
      region: resource.region,
      subregion: resource.subregion,
      area: resource.area,
      population: resource.population,
      startOfWeek: resource.startOfWeek
    });
  }

  toResourceFromEntity(entity: Country): CountryResource {
    return {
      id: entity.id,
      flags: {
        png: entity.flagPng,
        svg: entity.flagSvg,
        alt: entity.flagAlt
      },
      name: {
        common: entity.commonName,
        official: entity.officialName
      },
      independent: entity.independent,
      region: entity.region,
      subregion: entity.subregion,
      area: entity.area,
      population: entity.population,
      startOfWeek: entity.startOfWeek,
      flag: entity.flagEmoji
    } as CountryResource;
  }
}
```

### Creación del class Countries tipo ApiEndpoint

**Ejecutar** el siguiente CLI command:

```bash
ng generate class geographic/infrastructure/countries-api-endpoint --skip-tests=true
```

**Reemplazar** el contenido de `countries-api-endpoint.ts`:

```ts
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';
import { catchError, map } from 'rxjs/operators';
import { BaseApiEndpoint } from '../../shared/infrastructure/base-api-endpoint';
import { environment } from '../../../environments/environment';
import { Country } from '../domain/model/country.entity';
import { CountryResource, CountriesResponse } from './countries-response';
import { CountryAssembler } from './country-assembler';

/**
 * API endpoint for retrieving South American countries from REST Countries API v3.1.
 */
export class CountriesApiEndpoint extends BaseApiEndpoint<
  Country, CountryResource, CountriesResponse, CountryAssembler
> {
  constructor(http: HttpClient) {
    super(
      http,
      `${environment.restCountriesApiBaseUrl}${environment.restCountriesSubregionEndpointPath}?${environment.restCountriesFields}`,
      new CountryAssembler()
    );
  }

  /**
   * Retrieves all South American countries from the REST Countries API.
   * @return An Observable containing an array of Country entities.
   */
  getSouthAmericanCountries(): Observable<Country[]> {
    return this.http.get<CountryResource[]>(this.endpointUrl).pipe(
      map(resources => resources.map(r => this.assembler.toEntityFromResource(r))),
      catchError(this.handleError('Failed to fetch South American countries'))
    );
  }
}
```

### Creación del class Geographic tipo Api

**Ejecutar** el siguiente CLI command:

```bash
ng generate service geographic/infrastructure/geographic-api --skip-tests=true
```

**Reemplazar** el contenido de `geographic-api.ts`:

```ts
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';
import { BaseApi } from '../../shared/infrastructure/base-api';
import { Country } from '../domain/model/country.entity';
import { CountriesApiEndpoint } from './countries-api-endpoint';

/**
 * GeographicApi provides access to REST Countries API data for South American countries.
 */
@Injectable({ providedIn: 'root' })
export class GeographicApi extends BaseApi {
  private countriesApiEndpoint: CountriesApiEndpoint;

  constructor(private http: HttpClient) {
    super();
    this.countriesApiEndpoint = new CountriesApiEndpoint(http);
  }

  /**
   * Retrieves all South American countries.
   * @returns An Observable of an array of Country objects.
   */
  getSouthAmericanCountries(): Observable<Country[]> {
    return this.countriesApiEndpoint.getSouthAmericanCountries();
  }
}
```

## Application layer

### Creación del Service ObservatoriesStore

**Ejecutar** el siguiente CLI command:

```bash
ng generate service observatories/application/observatories-store --skip-tests=true
```

**Reemplazar** el contenido de `observatories-store.ts`:

```ts
import { Injectable, computed, signal } from '@angular/core';
import { takeUntilDestroyed } from '@angular/core/rxjs-interop';
import { retry } from 'rxjs';
import { CountryItem } from '../domain/model/country-item.entity';
import { GeographicObservatory } from '../domain/model/geographic-observatory.entity';
import { ObservatoriesApi } from '../infrastructure/observatories-api';

/**
 * ObservatoriesStore manages reactive state for geographic observatories and country items.
 */
@Injectable({ providedIn: 'root' })
export class ObservatoriesStore {
  private readonly countryItemsSignal = signal<CountryItem[]>([]);
  private readonly observatoriesSignal = signal<GeographicObservatory[]>([]);

  readonly countryItems = this.countryItemsSignal.asReadonly();
  readonly observatories = this.observatoriesSignal.asReadonly();

  private readonly loadingSignal = signal(false);
  readonly loading = this.loadingSignal.asReadonly();

  private readonly errorSignal = signal<string | null>(null);
  readonly error = this.errorSignal.asReadonly();

  readonly countryItemsCount = computed(() => this.countryItems().length);
  readonly observatoriesCount = computed(() => this.observatories().length);

  constructor(private observatoriesApi: ObservatoriesApi) {
    this.loadCountryItems();
    this.loadObservatories();
  }

  /**
   * Returns the observatory associated with a given region code.
   *
   * @param regionCode The region code to look up.
   * @returns The matching GeographicObservatory or undefined.
   */
  getObservatoryByRegionCode(regionCode: string): GeographicObservatory | undefined {
    return this.observatories().find(o => o.regionCode === regionCode);
  }

  /**
   * Returns all country items associated with a given observatory id.
   *
   * @param observatoryId The observatory identifier to filter items by.
   * @returns An array of CountryItem entities for that observatory.
   */
  itemsByObservatory(observatoryId: string): CountryItem[] {
    return this.countryItems().filter(c => c.observatoryId === observatoryId);
  }

  /**
   * Calculates the total accumulated population for a given observatory.
   *
   * @param observatoryId The observatory identifier.
   * @returns The sum of population values across all registered country items.
   */
  accumulatedPopulationFor(observatoryId: string): number {
    return this.countryItems()
      .filter(c => c.observatoryId === observatoryId)
      .reduce((s, c) => s + c.population, 0);
  }

  /**
   * Adds a new country item to the API and updates the local state.
   *
   * @param item The CountryItem entity to persist.
   */
  addCountryItem(item: CountryItem): void {
    this.loadingSignal.set(true);
    this.errorSignal.set(null);
    this.observatoriesApi.createCountryItem(item).pipe(retry(2)).subscribe({
      next: created => {
        this.countryItemsSignal.update(items => [...items, created]);
        this.loadingSignal.set(false);
      },
      error: err => {
        this.errorSignal.set(this.formatError(err, 'Failed to create country item'));
        this.loadingSignal.set(false);
      }
    });
  }

  private loadCountryItems(): void {
    this.loadingSignal.set(true);
    this.errorSignal.set(null);
    this.observatoriesApi.getCountryItems().pipe(takeUntilDestroyed(), retry(3)).subscribe({
      next: items => {
        this.countryItemsSignal.set(items);
        this.loadingSignal.set(false);
      },
      error: err => {
        this.errorSignal.set(this.formatError(err, 'Failed to load country items'));
        this.loadingSignal.set(false);
      }
    });
  }

  private loadObservatories(): void {
    this.loadingSignal.set(true);
    this.errorSignal.set(null);
    this.observatoriesApi.getGeographicObservatories().pipe(takeUntilDestroyed(), retry(3)).subscribe({
      next: observatories => {
        this.observatoriesSignal.set(observatories);
        this.loadingSignal.set(false);
      },
      error: err => {
        this.errorSignal.set(this.formatError(err, 'Failed to load observatories'));
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

### Creación del Service GeographicStore

**Ejecutar** el siguiente CLI command:

```bash
ng generate service geographic/application/geographic-store --skip-tests=true
```

**Reemplazar** el contenido de `geographic-store.ts`:

```ts
import { Injectable, computed, signal } from '@angular/core';
import { retry } from 'rxjs';
import { Country } from '../domain/model/country.entity';
import { GeographicApi } from '../infrastructure/geographic-api';

/**
 * GeographicStore manages reactive state for South American countries.
 */
@Injectable({ providedIn: 'root' })
export class GeographicStore {
  private readonly countriesSignal = signal<Country[]>([]);
  readonly countries = this.countriesSignal.asReadonly();

  private readonly loadingSignal = signal(false);
  readonly loading = this.loadingSignal.asReadonly();

  private readonly errorSignal = signal<string | null>(null);
  readonly error = this.errorSignal.asReadonly();

  readonly countriesCount = computed(() => this.countries().length);

  constructor(private geographicApi: GeographicApi) {}

  /**
   * Loads all South American countries from REST Countries API and stores them in state.
   */
  loadCountries(): void {
    this.loadingSignal.set(true);
    this.errorSignal.set(null);
    this.geographicApi.getSouthAmericanCountries().pipe(retry(2)).subscribe({
      next: countries => {
        this.countriesSignal.set(countries);
        this.loadingSignal.set(false);
      },
      error: err => {
        this.errorSignal.set(this.formatError(err, 'Failed to load countries'));
        this.loadingSignal.set(false);
      }
    });
  }

  clearCountries(): void {
    this.countriesSignal.set([]);
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
ng generate component observatories/presentation/components/observatory-summary --skip-tests=true
```

```bash
ng generate component observatories/presentation/views/new-country-item --skip-tests=true
```

## Configuración del Routes

### Crear y configurar geographic.routes

**Crear** el archivo `geographic.routes.ts` en la carpeta `observatories/presentation/views`:

```ts
import { Routes } from '@angular/router';

const newCountryItem = () =>
  import('./new-country-item/new-country-item').then(m => m.NewCountryItem);

export const geographicRoutes: Routes = [
  { path: 'countries/new', loadComponent: newCountryItem }
];
```

### Configuración del Routes app.routes

**Reemplazar** el contenido del archivo `app.routes.ts`:

```ts
import { Routes } from '@angular/router';
import { Home } from './shared/presentation/views/home/home';

const pageNotFound = () =>
  import('./shared/presentation/views/page-not-found/page-not-found').then(m => m.PageNotFound);

const baseTitle = 'SAGO Platform';

export const routes: Routes = [
  { path: 'home', component: Home, title: `${baseTitle} | Home` },
  {
    path: 'geographic',
    loadChildren: () =>
      import('./observatories/presentation/views/geographic.routes').then(m => m.geographicRoutes)
  },
  { path: '', redirectTo: '/home', pathMatch: 'full' },
  { path: '**', loadComponent: pageNotFound, title: `${baseTitle} | Page Not Found` }
];
```

## Modificación de componentes

### Modificación del LanguageSwitcher Component

**Reemplazar** el contenido de `language-switcher.ts`:

```ts
import { Component, inject } from '@angular/core';
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
  <p>Copyright &copy; 2026 South American Geographic Observatory. {{ 'footer.rights' | translate }}</p>
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
  background-color: #1a3a2a;
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
    { link: '/geographic/countries/new', label: 'option.new-country-item' }
  ];
}
```

**Reemplazar** el contenido de `layout.html`:

```html
<mat-toolbar role="banner">
  <mat-toolbar-row class="toolbar-grid">
    <div class="brand">
      <img src="https://img.logo.dev/sago-observatory.org?token=pk_B79Ajy8lSxuZc3W2xNN80A" alt="SAGO" width="32" height="32"/>
      <h1>South American Geographic Observatory Platform</h1>
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
  background-color: #1a3a2a;
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
import { ObservatorySummary } from '../../../../observatories/presentation/components/observatory-summary/observatory-summary';
import { ObservatoriesStore } from '../../../../observatories/application/observatories-store';
import { GeographicObservatory } from '../../../../observatories/domain/model/geographic-observatory.entity';
import { CountryItem } from '../../../../observatories/domain/model/country-item.entity';

/**
 * Home view displaying the welcome content and the "My Geographic Observatories" section
 * with a grid of ObservatorySummary components.
 */
@Component({
  selector: 'app-home',
  imports: [TranslatePipe, MatGridListModule, ObservatorySummary],
  templateUrl: './home.html',
  styleUrl: './home.css'
})
export class Home {
  private readonly store = inject(ObservatoriesStore);

  readonly observatories: Signal<GeographicObservatory[]> = this.store.observatories;
  readonly countryItems: Signal<CountryItem[]> = this.store.countryItems;

  /**
   * Returns the country items associated with a given observatory id.
   *
   * @param observatoryId The observatory identifier to filter items by.
   * @returns An array of CountryItem entities for that observatory.
   */
  itemsByObservatory(observatoryId: string): CountryItem[] {
    return this.countryItems().filter(c => c.observatoryId === observatoryId);
  }
}
```

**Reemplazar** el contenido de `home.html`:

```html
<section class="home">
  <h1>{{ 'home.title' | translate }}</h1>
  <p class="lead">{{ 'home.content' | translate }}</p>

  <section class="observatories-section" aria-labelledby="my-geographic-observatories-title">
    <h2 id="my-geographic-observatories-title">{{ 'home.my-geographic-observatories' | translate }}</h2>

    <mat-grid-list cols="2" rowHeight="300px" gutterSize="16px">
      @for (observatory of observatories(); track observatory.id) {
        <mat-grid-tile>
          <app-observatory-summary
            [observatory]="observatory"
            [items]="itemsByObservatory(observatory.id)" />
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
  color: #1a3a2a;
}

.lead {
  font-size: 1.1rem;
  color: #555;
  margin: 0;
}

.observatories-section h2 {
  font-size: 1.4rem;
  font-weight: 500;
  color: #1a3a2a;
  margin: 0 0 16px 0;
  border-bottom: 2px solid #1a3a2a;
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
  color: #1a3a2a;
  margin: 0 0 16px 0;
}
```

### Modificación del ObservatorySummary Component

**Reemplazar** el contenido de `observatory-summary.ts`:

```ts
import { Component, computed, input } from '@angular/core';
import { MatCardModule } from '@angular/material/card';
import { TranslatePipe } from '@ngx-translate/core';
import { GeographicObservatory } from '../../../domain/model/geographic-observatory.entity';
import { CountryItem } from '../../../domain/model/country-item.entity';

/**
 * ObservatorySummary component displays a card with observatory name, region code,
 * registered countries, total registered countries and accumulated population.
 */
@Component({
  selector: 'app-observatory-summary',
  imports: [MatCardModule, TranslatePipe],
  templateUrl: './observatory-summary.html',
  styleUrl: './observatory-summary.css'
})
export class ObservatorySummary {
  observatory = input.required<GeographicObservatory>();
  items = input.required<CountryItem[]>();

  totalRegisteredCountries = computed(() => this.items().length);
  accumulatedPopulation = computed(() => this.items().reduce((s, c) => s + c.population, 0));
  isEmpty = computed(() => this.items().length === 0);
}
```

**Reemplazar** el contenido de `observatory-summary.html`:

```html
<mat-card appearance="outlined" class="observatory-summary-card" [attr.aria-label]="observatory().name">
  <mat-card-header>
    <mat-card-title>{{ observatory().name }}</mat-card-title>
    <mat-card-subtitle>{{ observatory().regionCode }}</mat-card-subtitle>
  </mat-card-header>

  <mat-card-content>
    @if (isEmpty()) {
      <p class="empty">{{ 'observatory-summary.empty' | translate }}</p>
    } @else {
      <ul class="countries">
        @for (item of items(); track item.id) {
          <li>
            <span class="country-name">{{ item.countryName }}</span>
            <span class="country-population">{{ item.population | number }}</span>
          </li>
        }
      </ul>
    }
  </mat-card-content>

  <mat-card-footer class="card-footer">
    <div class="indicator">
      <span class="label">{{ 'observatory-summary.total-registered-countries' | translate }}</span>
      <span class="value">{{ totalRegisteredCountries() }}</span>
    </div>
    <div class="indicator">
      <span class="label">{{ 'observatory-summary.accumulated-population' | translate }}</span>
      <span class="value">{{ accumulatedPopulation() | number }}</span>
    </div>
  </mat-card-footer>
</mat-card>
```

**Reemplazar** el contenido de `observatory-summary.css`:

```css
.observatory-summary-card {
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
  color: #1a3a2a;
}

mat-card-subtitle {
  font-size: 0.85rem;
  color: #555;
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

.countries {
  list-style: none;
  padding: 0;
  margin: 0;
}

.countries li {
  display: flex;
  justify-content: space-between;
  padding: 6px 0;
  border-bottom: 1px dashed rgba(0, 0, 0, 0.06);
}

.countries li:last-child { border-bottom: none; }

.country-name { color: #333; }

.country-population {
  color: #1a3a2a;
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
  color: #1a3a2a;
  line-height: 1;
}
```

### Modificación del NewCountryItem Component

**Reemplazar** el contenido de `new-country-item.ts`:

```ts
import { Component, computed, inject, signal } from '@angular/core';
import { CommonModule } from '@angular/common';
import { FormBuilder, FormControl, ReactiveFormsModule, Validators } from '@angular/forms';
import { Router } from '@angular/router';
import { MatButtonModule } from '@angular/material/button';
import { MatFormFieldModule } from '@angular/material/form-field';
import { MatInputModule } from '@angular/material/input';
import { MatAutocompleteModule } from '@angular/material/autocomplete';
import { MatProgressSpinnerModule } from '@angular/material/progress-spinner';
import { TranslatePipe } from '@ngx-translate/core';
import { ObservatoriesStore } from '../../../application/observatories-store';
import { GeographicStore } from '../../../../geographic/application/geographic-store';
import { CountryItem } from '../../../domain/model/country-item.entity';
import { Country } from '../../../../geographic/domain/model/country.entity';

/**
 * NewCountryItem view provides a form to register a new country item by
 * searching/filtering South American countries in real time and selecting one.
 * Validates that the selected country is independent and has area > 100,000 km².
 */
@Component({
  selector: 'app-new-country-item',
  imports: [
    CommonModule,
    ReactiveFormsModule,
    MatFormFieldModule,
    MatInputModule,
    MatAutocompleteModule,
    MatButtonModule,
    MatProgressSpinnerModule,
    TranslatePipe
  ],
  templateUrl: './new-country-item.html',
  styleUrl: './new-country-item.css'
})
export class NewCountryItem {
  private readonly fb = inject(FormBuilder);
  private readonly router = inject(Router);
  protected readonly observatoriesStore = inject(ObservatoriesStore);
  protected readonly geographicStore = inject(GeographicStore);

  protected readonly selectedCountry = signal<Country | null>(null);

  protected readonly filteredCountries = computed(() => {
    const query = this.form.get('countrySearch')?.value?.toLowerCase() ?? '';
    return this.geographicStore.countries().filter(c =>
      c.commonName.toLowerCase().includes(query)
    );
  });

  protected readonly validationError = computed(() => {
    const country = this.selectedCountry();
    if (!country) return null;
    if (!country.independent) return 'not-independent';
    if (country.area <= 100000) return 'area-too-small';
    return null;
  });

  protected readonly form = this.fb.group({
    countrySearch: new FormControl<string>('', { validators: [Validators.required] }),
    officialName: new FormControl<string>({ value: '', disabled: true }),
    flagUrl: new FormControl<string>({ value: '', disabled: true }),
    area: new FormControl<number | null>({ value: null, disabled: true }),
    population: new FormControl<number | null>({ value: null, disabled: true }),
    startOfWeek: new FormControl<string>({ value: '', disabled: true })
  });

  constructor() {
    this.geographicStore.loadCountries();
  }

  onCountrySelected(country: Country): void {
    this.selectedCountry.set(country);
    this.form.patchValue({
      officialName: country.officialName,
      flagUrl: country.flagSvg,
      area: country.area,
      population: country.population,
      startOfWeek: country.startOfWeek
    });
  }

  submit(): void {
    const country = this.selectedCountry();
    if (!country || this.validationError()) return;

    const observatory = this.observatoriesStore.getObservatoryByRegionCode(country.subregion.replace('South America', 'AND') || 'AND');
    const firstObservatory = this.observatoriesStore.observatories()[0];
    const targetObservatory = observatory ?? firstObservatory;

    if (!targetObservatory) return;

    const item = new CountryItem({
      id: '',
      observatoryId: targetObservatory.id,
      regionCode: targetObservatory.regionCode,
      countryName: country.commonName,
      officialName: country.officialName,
      flagUrl: country.flagSvg,
      area: country.area,
      population: country.population,
      startOfWeek: country.startOfWeek,
      registeredAt: new Date().toISOString()
    });

    this.observatoriesStore.addCountryItem(item);
    this.router.navigate(['/home']).then();
  }

  cancel(): void {
    this.router.navigate(['/home']).then();
  }
}
```

**Reemplazar** el contenido de `new-country-item.html`:

```html
<section class="new-country-item">
  <header>
    <h1>{{ 'new-country-item.title' | translate }}</h1>
    <p class="subtitle">{{ 'new-country-item.subtitle' | translate }}</p>
  </header>

  <form [formGroup]="form" (ngSubmit)="submit()" aria-label="New country item form">

    <mat-form-field appearance="outline">
      <mat-label>{{ 'new-country-item.country' | translate }}</mat-label>
      @if (geographicStore.loading()) {
        <mat-spinner matPrefix diameter="20" style="margin: 0 8px;"></mat-spinner>
      }
      <input matInput
             formControlName="countrySearch"
             [matAutocomplete]="auto"
             [placeholder]="'new-country-item.search-country' | translate"
             aria-label="Search country" />
      <mat-autocomplete #auto="matAutocomplete"
                        (optionSelected)="onCountrySelected($event.option.value)">
        @for (country of filteredCountries(); track country.id) {
          <mat-option [value]="country">{{ country.commonName }}</mat-option>
        }
      </mat-autocomplete>
      @if (form.get('countrySearch')!.touched && form.get('countrySearch')!.hasError('required')) {
        <mat-error>{{ 'new-country-item.country-required' | translate }}</mat-error>
      }
    </mat-form-field>

    @if (validationError()) {
      <mat-error class="validation-banner" role="alert">
        {{ 'new-country-item.' + validationError() | translate }}
      </mat-error>
    }

    <mat-form-field appearance="outline">
      <mat-label>{{ 'new-country-item.official-name' | translate }}</mat-label>
      <input matInput formControlName="officialName" aria-readonly="true" />
    </mat-form-field>

    <mat-form-field appearance="outline">
      <mat-label>{{ 'new-country-item.flag-url' | translate }}</mat-label>
      <input matInput formControlName="flagUrl" aria-readonly="true" />
    </mat-form-field>

    <mat-form-field appearance="outline">
      <mat-label>{{ 'new-country-item.area' | translate }}</mat-label>
      <input matInput type="number" formControlName="area" aria-readonly="true" />
    </mat-form-field>

    <mat-form-field appearance="outline">
      <mat-label>{{ 'new-country-item.population' | translate }}</mat-label>
      <input matInput type="number" formControlName="population" aria-readonly="true" />
    </mat-form-field>

    <mat-form-field appearance="outline">
      <mat-label>{{ 'new-country-item.start-of-week' | translate }}</mat-label>
      <input matInput formControlName="startOfWeek" aria-readonly="true" />
    </mat-form-field>

    <div class="actions">
      <button mat-stroked-button type="button" (click)="cancel()">
        {{ 'new-country-item.cancel' | translate }}
      </button>
      <button mat-raised-button color="primary" type="submit"
              [disabled]="form.invalid || !!validationError()">
        {{ 'new-country-item.create' | translate }}
      </button>
    </div>
  </form>
</section>
```

**Reemplazar** el contenido de `new-country-item.css`:

```css
.new-country-item {
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
  color: #1a3a2a;
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

.validation-banner {
  font-size: 0.9rem;
  padding: 8px 12px;
  background-color: #fdecea;
  border-radius: 4px;
  color: #b71c1c;
  display: block;
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
2. **Comprimir** el proyecto siguiendo la convención `eanrcucode.zip` (por ejemplo `ea11990u201621873.zip`).

## Actividad

- **Probar** los flujos de Home y New Country Item.
- **Verificar** validación de país independiente (`independent === true`).
- **Verificar** validación de área (`area > 100,000 km²`).
- **Verificar** que el observatorio correcto se asocie al `CountryItem` según `regionCode`.
- **Verificar** que los campos Official Name, Flag URL, Area, Population y Start of Week sean de solo lectura.
- **Verificar** que `registeredAt` se genere automáticamente al momento del registro.
- **Verificar** i18n en/es y ARIA attributes en cada vista.
