# Proyecto Clearpath Robotics Fleet Management

> Aplicación Vue 3 + Vite + JavaScript con arquitectura DDD (Domain Driven Design) por capas, PrimeVue para componentes UI, Pinia para state management, Vue Router para enrutamiento, Vue I18n para internacionalización y Axios para HTTP. El backend simulado utiliza `json-server`.

## Creación del proyecto

> [!CAUTION]
> **En el caso de estar en un equipo MAC:**
> - Debe anteceder el comando `sudo` al ejecutar instrucciones globales `npm install -g` y `chown`, y luego ingresar la contraseña del Administrador (`d3v3l0p3rUPC`).
> - Debe ubicarse en la carpeta `/Users/alumnos/IdeaProjects/1asi0730/202610` o en otra de su preferencia.

> [!CAUTION]
> **En el caso de estar en un equipo Windows:**
> - Debe ubicarse en la carpeta `IdeaProjects/` o en otra de su preferencia.

A continuación se detalla las instrucciones para crear una nueva aplicación con `Vue 3` y `Vite`. Más información en: https://vuejs.org/guide/quick-start.html

### Creación de la initial application

**Cargar** el `Terminal` del Sistema Operativo, ubicarse en la carpeta de su preferencia y **ejecutar** el siguiente command:

```bash
npm create vue@latest eanrcucode
```

Reemplace `eanrcucode` por el nombre real del proyecto (por ejemplo `ea12190u201821873`).

Después de ejecutar el command, le mostrará diferentes opciones y debe escoger las siguientes:

_? Project name?_, **digitar**:

```
eanrcucode
```

_? Select features to include in your project?_, **NO seleccionar nada** (se instalará todo manualmente):

```
( ) TypeScript
( ) JSX Support
( ) Router (SPA development)
( ) Pinia (state management)
( ) Vitest (unit testing)
( ) End-to-End Testing
( ) ESLint (error prevention)
( ) Prettier (code formatting)
```

Se creará el proyecto. **Ingresar** a la carpeta creada:

```bash
cd eanrcucode
```

**Instalar** los packages base de Vue:

```bash
npm install
```

### Instalación de PrimeVue, PrimeFlex y PrimeIcons

A continuación se detalla las instrucciones para instalar `PrimeVue` (component library), `PrimeFlex` (utilidades CSS) y `PrimeIcons` (iconos). Más información en: https://primevue.org/installation/

**Ejecutar** los siguientes commands:

```bash
npm install primevue @primeuix/themes primeflex primeicons
```

### Instalación de Vue Router

A continuación se detalla las instrucciones para instalar el library oficial de enrutamiento de Vue. Más información en: https://router.vuejs.org/installation.html

**Ejecutar** el siguiente command:

```bash
npm install vue-router@4
```

### Instalación de Pinia

A continuación se detalla las instrucciones para instalar `Pinia`, el state management oficial de Vue. Más información en: https://pinia.vuejs.org/getting-started.html

**Ejecutar** el siguiente command:

```bash
npm install pinia
```

### Instalación de Vue I18n

A continuación se detalla las instrucciones para instalar el library de internacionalización (i18n) `vue-i18n`. Más información en: https://vue-i18n.intlify.dev/guide/installation.html

**Ejecutar** el siguiente command:

```bash
npm install vue-i18n@11
```

### Instalación de Axios

A continuación se detalla las instrucciones para instalar el HTTP client `axios`. Más información en: https://axios-http.com/docs/intro

**Ejecutar** el siguiente command:

```bash
npm install axios
```

### Instalación de Json-server

A continuación se detalla las instrucciones para instalar un `full fake REST API` sin codificación denominado: **JSON Server**. Más información en: https://github.com/typicode/json-server/tree/v0

**Ejecutar** el siguiente command:

```bash
npm install -g json-server@0.17.4
```

### Cambiar el propietario del proyecto creado con sudo (Solo MAC)

> [!CAUTION]
> **Solo ejecutar si estas en un equipo MAC:**

**Ejecutar** los siguientes commands:

```bash
cd ..
```

```bash
sudo chown -R alumnos ./eanrcucode
```

```bash
ls -l
```

## Desarrollo del proyecto

**Cargar** el JetBrains WebStorm y **abrir** el proyecto ubicado en la carpeta de su preferencia.

**Cargar** el `Terminal` del IDE y **ejecutar** el siguiente command para verificar que la aplicación inicie correctamente:

```bash
npm run dev
```

Por defecto Vite expone el servidor en http://localhost:5173

### Creación de los Archivos de idiomas

**Crear** la carpeta `locales` en la carpeta :file_folder: `src` ubicada en la raíz del proyecto:

```markdown
- 📂 src
  - 📁 locales
```

**Crear** los archivos `en.json` y `es.json` en la carpeta :file_folder: `locales` con el siguiente contenido:

#### en.json

```json
{
  "option": {
    "home": "Home",
    "new-inventory-item": "New Inventory Item"
  },
  "authoring-phrase": {
    "intro": "Made with ",
    "use": " using ",
    "author": " by {brand} Developer Team"
  },
  "home": {
    "title": "Home",
    "content": "Engineered Platforms for Robot Fleets.",
    "my-robot-fleets": "My Robot Fleets"
  },
  "fleet-summary": {
    "empty": "Empty",
    "total-robots": "Total Robots",
    "available-capacity": "Available Capacity"
  },
  "new-inventory-item": {
    "title": "New Inventory Item",
    "subtitle": "Add Robots to Your Fleet",
    "robot-type": "Robot Type",
    "robot": "Robot",
    "quantity": "Quantity",
    "create": "Create",
    "cancel": "Cancel",
    "select-robot-type": "Select a robot type",
    "select-robot": "Select a robot",
    "capacity-exceeded": "Quantity exceeds the available capacity for this fleet.",
    "success": "Inventory item registered successfully."
  },
  "page-not-found": {
    "title": "Page Not Found",
    "content": "The path {unavailable-route} is not available.",
    "go-home": "Go Home"
  },
  "errors": {
    "occurred": "Errors occurred"
  }
}
```

#### es.json

```json
{
  "option": {
    "home": "Inicio",
    "new-inventory-item": "Nuevo Ítem de Inventario"
  },
  "authoring-phrase": {
    "intro": "Hecho con ",
    "use": " utilizando ",
    "author": " por el equipo de Desarrollo de {brand}"
  },
  "home": {
    "title": "Inicio",
    "content": "Plataformas diseñadas para flotas de robots.",
    "my-robot-fleets": "Mis Flotas de Robots"
  },
  "fleet-summary": {
    "empty": "Vacío",
    "total-robots": "Total de Robots",
    "available-capacity": "Capacidad Disponible"
  },
  "new-inventory-item": {
    "title": "Nuevo Ítem de Inventario",
    "subtitle": "Agregar Robots a Tu Flota",
    "robot-type": "Tipo de Robot",
    "robot": "Robot",
    "quantity": "Cantidad",
    "create": "Crear",
    "cancel": "Cancelar",
    "select-robot-type": "Selecciona un tipo de robot",
    "select-robot": "Selecciona un robot",
    "capacity-exceeded": "La cantidad supera la capacidad disponible para esta flota.",
    "success": "Ítem de inventario registrado exitosamente."
  },
  "page-not-found": {
    "title": "Página no encontrada",
    "content": "La ruta {unavailable-route} no está disponible.",
    "go-home": "Ir al Inicio"
  },
  "errors": {
    "occurred": "Ocurrieron errores"
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
  "fleets": [
    { "id": 1, "name": "Humanoid Fleet Alpha",        "robotType": "humanoids",  "capacity": 10 },
    { "id": 2, "name": "Heavy Industrial Arms",        "robotType": "arms",       "capacity": 15 },
    { "id": 3, "name": "Autonomous Exploration Rovers","robotType": "rovers",     "capacity": 8  },
    { "id": 4, "name": "Surveillance Drones Wing",     "robotType": "drones",     "capacity": 20 },
    { "id": 5, "name": "Quadruped Inspection Squad",   "robotType": "quadrupeds", "capacity": 12 },
    { "id": 6, "name": "Warehouse Logistics AGVs",     "robotType": "agvs",       "capacity": 25 }
  ],
  "inventory-items": [
    {
      "id": 1, "fleetId": 1, "robotType": "humanoids",
      "robotId": 1, "robotName": "Atlas v2",
      "quantity": 2, "registeredAt": "2026-05-22T10:00:00.000Z"
    },
    {
      "id": 2, "fleetId": 2, "robotType": "arms",
      "robotId": 3, "robotName": "KUKA LBR iisy",
      "quantity": 5, "registeredAt": "2026-05-22T11:15:00.000Z"
    },
    {
      "id": 3, "fleetId": 5, "robotType": "quadrupeds",
      "robotId": 1, "robotName": "Spot 2024",
      "quantity": 3, "registeredAt": "2026-05-22T12:30:00.000Z"
    }
  ]
}
```

**Cargar** el `Terminal` del IDE y **agregar** un nuevo `Tab`.

**Ejecutar** el siguiente command para iniciar el `json-server`:

```bash
cd server
json-server --watch db.json --port 3000
```

**Cargar** el navegador e **ingresar** las siguientes URLs:

- http://localhost:3000/fleets
- http://localhost:3000/inventory-items

### Configuración de environments (.env)

A continuación se detalla las instrucciones para definir variables de entorno utilizadas por Vite. Más información en: https://vitejs.dev/guide/env-and-mode.html

**Crear** el archivo `.env.development` en la carpeta raíz del proyecto:

#### .env.development

```dotenv
VITE_FLEET_MANAGEMENT_API_URL=http://localhost:3000
VITE_FLEETS_ENDPOINT_PATH=/fleets
VITE_INVENTORY_ITEMS_ENDPOINT_PATH=/inventory-items
VITE_ROBOTICS_API_URL=https://api.sampleapis.com/robots
VITE_LOGO_DEV_API_URL=https://img.logo.dev
```

**Crear** el archivo `.env.production` en la carpeta raíz del proyecto:

#### .env.production

```dotenv
VITE_FLEET_MANAGEMENT_API_URL=http://localhost:3000
VITE_FLEETS_ENDPOINT_PATH=/fleets
VITE_INVENTORY_ITEMS_ENDPOINT_PATH=/inventory-items
VITE_ROBOTICS_API_URL=https://api.sampleapis.com/robots
VITE_LOGO_DEV_API_URL=https://img.logo.dev
```

> [!NOTE]
> Vite expone únicamente las variables prefijadas con `VITE_` al frontend a través de `import.meta.env`.

### Configuración del alias `@/` (path mapping)

A continuación se detalla las instrucciones para usar el alias `@/` apuntando a `src/` tanto en Vite (runtime) como en WebStorm/VSCode (autocompletado).

**Reemplazar** el contenido del archivo `vite.config.js` ubicado en la raíz:

```js
import { fileURLToPath, URL } from 'node:url'
import { defineConfig } from 'vite'
import vue from '@vitejs/plugin-vue'

export default defineConfig({
  plugins: [vue()],
  resolve: {
    alias: {
      '@': fileURLToPath(new URL('./src', import.meta.url))
    }
  }
})
```

**Crear** el archivo `jsconfig.json` en la raíz del proyecto:

#### jsconfig.json

```json
{
  "compilerOptions": {
    "paths": {
      "@/*": ["./src/*"]
    }
  },
  "exclude": ["node_modules", "dist"]
}
```

### Creación de la estructura del proyecto

**Crear** la siguiente estructura de carpetas en la carpeta :file_folder: `src`:

```markdown
- 📂 src
  - 📂 assets
  - 📂 locales
  - 📂 fleeting
    - 📁 application
    - 📁 domain
      - 📁 model
    - 📁 infrastructure
    - 📁 presentation
      - 📁 components
      - 📁 views
  - 📂 robotics
    - 📁 application
    - 📁 domain
      - 📁 model
    - 📁 infrastructure
    - 📁 presentation
      - 📁 components
  - 📂 shared
    - 📁 infrastructure
    - 📁 presentation
      - 📁 components
      - 📁 views
```

## Creación de los class Base

### Creación del class BaseApi

**Crear** el archivo `base-api.js` en `src/shared/infrastructure`:

```js
import axios from "axios";

const fleetManagementApi = import.meta.env.VITE_FLEET_MANAGEMENT_API_URL;

/**
 * Abstract base class for API services managing HTTP connections to the fleet management platform.
 * @summary Provides a pre-configured Axios instance for subclass use.
 * @author [Tu Nombre y Apellido]
 */
export class BaseApi {

    #http;

    constructor() {
        this.#http = axios.create({
            baseURL: fleetManagementApi,
            headers: {
                'Content-Type': 'application/json',
                'Access-Control-Allow-Origin': '*'
            },
        });
    }

    get http() {
        return this.#http;
    }
}
```

### Creación del class BaseEndpoint

**Crear** el archivo `base-endpoint.js` en `src/shared/infrastructure` con los métodos CRUD genéricos:

```js
/**
 * Generic CRUD endpoint class for REST API operations.
 * @summary Provides getAll, getById, create, update, and delete methods for any REST endpoint.
 * @author [Tu Nombre y Apellido]
 */
export class BaseEndpoint {

    constructor(baseApi, endpointPath) {
        this.http = baseApi.http;
        this.endpointPath = endpointPath;
    }

    /** @summary Retrieves all resources from the endpoint. */
    getAll()             { return this.http.get(this.endpointPath); }

    /** @summary Retrieves a single resource by its ID. */
    getById(id)          { return this.http.get(`${this.endpointPath}/${id}`); }

    /** @summary Creates a new resource. */
    create(resource)     { return this.http.post(this.endpointPath, resource); }

    /** @summary Updates an existing resource by its ID. */
    update(id, resource) { return this.http.put(`${this.endpointPath}/${id}`, resource); }

    /** @summary Deletes a resource by its ID. */
    delete(id)           { return this.http.delete(`${this.endpointPath}/${id}`); }
}
```

## Analizando el Clearpath Robotics Fleet Management API

### Analizando el endpoint fleets

Diríjase al endpoint local http://localhost:3000/fleets y **evalúe** el json de respuesta:

```json
[
  { "id": 1, "name": "Humanoid Fleet Alpha", "robotType": "humanoids", "capacity": 10 }
]
```

### Creación del class Fleet tipo entity (model)

**Crear** el archivo `fleet.entity.js` en `src/fleeting/domain/model`:

```js
/**
 * Domain entity representing a robot fleet.
 * @summary Holds fleet identity, robot type, and capacity information.
 * @author [Tu Nombre y Apellido]
 */
export class Fleet {
    constructor({ id = null, name = '', robotType = '', capacity = 0 } = {}) {
        this.id = id;
        this.name = name;
        this.robotType = robotType;
        this.capacity = capacity;
    }
}
```

### Creación del class Fleet tipo Assembler

**Crear** el archivo `fleet.assembler.js` en `src/fleeting/infrastructure`:

```js
import { Fleet } from "@/fleeting/domain/model/fleet.entity.js";

/**
 * Maps raw API response data to Fleet domain entities.
 * @summary Converts Axios responses and resource objects into Fleet instances.
 * @author [Tu Nombre y Apellido]
 */
export class FleetAssembler {

    /**
     * Converts a single API resource object to a Fleet entity.
     * @param {Object} resource - Raw resource from API.
     * @returns {Fleet}
     */
    static toEntityFromResource(resource) {
        return new Fleet({ ...resource });
    }

    /**
     * Converts an array of API resources to Fleet entities.
     * @param {Object} response - Axios response object.
     * @returns {Fleet[]}
     */
    static toEntitiesFromResponse(response) {
        if (response.status !== 200) {
            console.error(`${response.status} - ${response.statusText}`);
            return [];
        }
        const resources = response.data instanceof Array
            ? response.data
            : response.data['fleets'];
        return resources.map(resource => this.toEntityFromResource(resource));
    }
}
```

### Analizando el endpoint inventory-items

Diríjase al endpoint local http://localhost:3000/inventory-items y **evalúe** el json de respuesta:

```json
[
  {
    "id": 1,
    "fleetId": 1,
    "robotType": "humanoids",
    "robotId": 1,
    "robotName": "Atlas v2",
    "quantity": 2,
    "registeredAt": "2026-05-22T10:00:00.000Z"
  }
]
```

### Creación del class InventoryItem tipo entity (model)

**Crear** el archivo `inventory-item.entity.js` en `src/fleeting/domain/model`:

```js
/**
 * Domain entity representing a robot inventory item within a fleet.
 * @summary Holds robot assignment data including fleet association, type, and quantity.
 * @author [Tu Nombre y Apellido]
 */
export class InventoryItem {
    constructor({
        id = null,
        fleetId = null,
        robotType = '',
        robotId = null,
        robotName = '',
        quantity = 0,
        registeredAt = null
    } = {}) {
        this.id = id;
        this.fleetId = fleetId;
        this.robotType = robotType;
        this.robotId = robotId;
        this.robotName = robotName;
        this.quantity = quantity;
        this.registeredAt = registeredAt;
    }
}
```

### Creación del class InventoryItem tipo Assembler

**Crear** el archivo `inventory-item.assembler.js` en `src/fleeting/infrastructure`:

```js
import { InventoryItem } from "@/fleeting/domain/model/inventory-item.entity.js";

/**
 * Maps raw API response data to InventoryItem domain entities.
 * @summary Converts Axios responses and resource objects into InventoryItem instances.
 * @author [Tu Nombre y Apellido]
 */
export class InventoryItemAssembler {

    /**
     * Converts a single API resource object to an InventoryItem entity.
     * @param {Object} resource - Raw resource from API.
     * @returns {InventoryItem}
     */
    static toEntityFromResource(resource) {
        return new InventoryItem({ ...resource });
    }

    /**
     * Converts an array of API resources to InventoryItem entities.
     * @param {Object} response - Axios response object.
     * @returns {InventoryItem[]}
     */
    static toEntitiesFromResponse(response) {
        if (response.status !== 200) {
            console.error(`${response.status} - ${response.statusText}`);
            return [];
        }
        const resources = response.data instanceof Array
            ? response.data
            : response.data['inventory-items'];
        return resources.map(resource => this.toEntityFromResource(resource));
    }
}
```

### Analizando el endpoint de SampleAPI (Robotics)

Diríjase al endpoint externo https://api.sampleapis.com/robots/humanoids y **evalúe** el json de respuesta:

```json
[
  {
    "manufacturer": "Boston Dynamics",
    "model": "Spot 2024",
    "rating": { "average": "5.0", "reviews": "34 ratings" },
    "origin": "USA Massachusetts",
    "image": "https://images.example.com/thumbs/spot_x300.png",
    "id": 1
  }
]
```

Los tipos de robot disponibles son: `humanoids`, `arms`, `rovers`, `drones`, `quadrupeds`, `agvs`. Cada tipo corresponde a un endpoint del servicio SampleAPI.

### Creación del class Robot tipo entity (model)

**Crear** el archivo `robot.entity.js` en `src/robotics/domain/model`:

```js
/**
 * Domain entity representing a robot from the SampleAPI Robotics service.
 * @summary Holds robot identification, manufacturer, model, and image data.
 * @author [Tu Nombre y Apellido]
 */
export class Robot {
    constructor({ id = null, manufacturer = '', model = '', origin = '', image = '' } = {}) {
        this.id = id;
        this.manufacturer = manufacturer;
        this.model = model;
        this.origin = origin;
        this.image = image;
    }
}
```

### Creación del class Robot tipo Assembler

**Crear** el archivo `robot.assembler.js` en `src/robotics/infrastructure`:

```js
import { Robot } from "@/robotics/domain/model/robot.entity.js";

/**
 * Maps raw SampleAPI response data to Robot domain entities.
 * @summary Converts Axios responses and resource objects into Robot instances.
 * @author [Tu Nombre y Apellido]
 */
export class RobotAssembler {

    /**
     * Converts a single API resource object to a Robot entity.
     * @param {Object} resource - Raw resource from SampleAPI.
     * @returns {Robot}
     */
    static toEntityFromResource(resource) {
        return new Robot({
            id:           resource.id,
            manufacturer: resource.manufacturer,
            model:        resource.model,
            origin:       resource.origin,
            image:        resource.image
        });
    }

    /**
     * Converts an array of API resources to Robot entities.
     * @param {Object} response - Axios response object.
     * @returns {Robot[]}
     */
    static toEntitiesFromResponse(response) {
        if (response.status !== 200) {
            console.error(`${response.status} - ${response.statusText}`);
            return [];
        }
        const resources = response.data instanceof Array ? response.data : [];
        return resources.map(resource => this.toEntityFromResource(resource));
    }
}
```

## Creación de los API Services

### Creación del FleetingApi Service

**Crear** el archivo `fleeting-api.js` en `src/fleeting/infrastructure`. Este class extiende `BaseApi` y compone dos `BaseEndpoint` (fleets e inventory-items) leyendo los paths desde las variables `VITE_*`:

```js
import { BaseApi }      from "@/shared/infrastructure/base-api.js";
import { BaseEndpoint } from "@/shared/infrastructure/base-endpoint.js";

const fleetsEndpointPath         = import.meta.env.VITE_FLEETS_ENDPOINT_PATH;
const inventoryItemsEndpointPath = import.meta.env.VITE_INVENTORY_ITEMS_ENDPOINT_PATH;

/**
 * API service for fleeting operations. Composes fleet and inventory-item endpoints.
 * @summary Provides all CRUD operations for fleets and inventory items against the local json-server.
 * @author [Tu Nombre y Apellido]
 */
export class FleetingApi extends BaseApi {
    #fleetsEndpoint;
    #inventoryItemsEndpoint;

    constructor() {
        super();
        this.#fleetsEndpoint         = new BaseEndpoint(this, fleetsEndpointPath);
        this.#inventoryItemsEndpoint = new BaseEndpoint(this, inventoryItemsEndpointPath);
    }

    /** @summary Fetches all fleets. */
    getFleets()                    { return this.#fleetsEndpoint.getAll(); }

    /** @summary Fetches all inventory items. */
    getInventoryItems()            { return this.#inventoryItemsEndpoint.getAll(); }

    /** @summary Fetches a fleet by ID. */
    getFleetById(id)               { return this.#fleetsEndpoint.getById(id); }

    /** @summary Creates a new inventory item. */
    createInventoryItem(resource)  { return this.#inventoryItemsEndpoint.create(resource); }
}
```

### Creación del RoboticsApi Service

**Crear** el archivo `robotics-api.js` en `src/robotics/infrastructure`. Este class usa Axios directamente con la URL base de SampleAPI:

```js
import axios from "axios";

const roboticsApiUrl = import.meta.env.VITE_ROBOTICS_API_URL;

/**
 * API service for robotics information from SampleAPI.
 * @summary Fetches robot data by robot type from the external SampleAPI Robotics service.
 * @author [Tu Nombre y Apellido]
 */
export class RoboticsApi {
    #http;

    constructor() {
        this.#http = axios.create({
            baseURL: roboticsApiUrl,
            headers: { 'Content-Type': 'application/json' }
        });
    }

    /**
     * Fetches all robots for a given robot type.
     * @param {string} robotType - One of: humanoids, arms, rovers, drones, quadrupeds, agvs.
     * @returns {Promise}
     */
    getRobotsByType(robotType) { return this.#http.get(`/${robotType}`); }
}
```

## Application layer

### Creación del Pinia Store FleetingStore

**Crear** el archivo `fleeting.store.js` en `src/fleeting/application`. Pinia se usa con `defineStore` en estilo `composition API`:

```js
import { defineStore }          from "pinia";
import { computed, ref }        from "vue";
import { FleetingApi }          from "@/fleeting/infrastructure/fleeting-api.js";
import { FleetAssembler }       from "@/fleeting/infrastructure/fleet.assembler.js";
import { InventoryItemAssembler } from "@/fleeting/infrastructure/inventory-item.assembler.js";

const fleetingApi = new FleetingApi();

/**
 * Pinia store for fleeting state management (fleets and inventory items).
 * @summary Manages fetch, create, and local state operations for fleets and inventory items.
 * @author [Tu Nombre y Apellido]
 */
const useFleetingStore = defineStore('fleeting', () => {
    const fleets              = ref([]);
    const inventoryItems      = ref([]);
    const errors              = ref([]);
    const fleetsLoaded        = ref(false);
    const inventoryLoaded     = ref(false);

    const fleetsCount         = computed(() => fleetsLoaded.value    ? fleets.value.length         : 0);
    const inventoryItemsCount = computed(() => inventoryLoaded.value ? inventoryItems.value.length : 0);

    /** @summary Fetches all fleets from the API. */
    function fetchFleets() {
        fleetingApi.getFleets().then(response => {
            fleets.value = FleetAssembler.toEntitiesFromResponse(response);
            fleetsLoaded.value = true;
        }).catch(error => errors.value.push(error));
    }

    /** @summary Fetches all inventory items from the API. */
    function fetchInventoryItems() {
        fleetingApi.getInventoryItems().then(response => {
            inventoryItems.value = InventoryItemAssembler.toEntitiesFromResponse(response);
            inventoryLoaded.value = true;
        }).catch(error => errors.value.push(error));
    }

    /** @summary Returns the fleet matching the given robot type. */
    function getFleetByRobotType(robotType) {
        return fleets.value.find(f => f.robotType === robotType) || null;
    }

    /**
     * Returns the total robots (sum of quantity) for a given fleet ID.
     * @param {number} fleetId
     * @returns {number}
     */
    function getTotalRobotsByFleetId(fleetId) {
        return inventoryItems.value
            .filter(item => item.fleetId === fleetId)
            .reduce((sum, item) => sum + item.quantity, 0);
    }

    /**
     * Returns the available capacity for a given fleet.
     * @param {number} fleetId
     * @returns {number}
     */
    function getAvailableCapacity(fleetId) {
        const fleet = fleets.value.find(f => f.id === fleetId);
        if (!fleet) return 0;
        return fleet.capacity - getTotalRobotsByFleetId(fleetId);
    }

    /**
     * Returns only the inventory items belonging to a given fleet.
     * @param {number} fleetId
     * @returns {InventoryItem[]}
     */
    function getItemsByFleetId(fleetId) {
        return inventoryItems.value.filter(item => item.fleetId === fleetId);
    }

    /** @summary Creates an inventory item via API and appends it to the store. */
    function addInventoryItem(inventoryItem) {
        return fleetingApi.createInventoryItem(inventoryItem).then(response => {
            const newItem = InventoryItemAssembler.toEntityFromResource(response.data);
            inventoryItems.value.push(newItem);
        }).catch(error => errors.value.push(error));
    }

    return {
        fleets, inventoryItems,
        errors,
        fleetsLoaded, inventoryLoaded,
        fleetsCount, inventoryItemsCount,
        fetchFleets, fetchInventoryItems,
        getFleetByRobotType,
        getTotalRobotsByFleetId,
        getAvailableCapacity,
        getItemsByFleetId,
        addInventoryItem
    };
});

export default useFleetingStore;
```

### Creación del Pinia Store RoboticsStore

**Crear** el archivo `robotics.store.js` en `src/robotics/application`:

```js
import { defineStore }   from "pinia";
import { ref }           from "vue";
import { RoboticsApi }   from "@/robotics/infrastructure/robotics-api.js";
import { RobotAssembler } from "@/robotics/infrastructure/robot.assembler.js";

const roboticsApi = new RoboticsApi();

/**
 * Pinia store for robotics state management (robots by type from SampleAPI).
 * @summary Manages on-demand fetching of robot collections per robot type.
 * @author [Tu Nombre y Apellido]
 */
const useRoboticsStore = defineStore('robotics', () => {
    const robotsByType = ref({});
    const errors       = ref([]);

    /**
     * Fetches robots for a given type and caches them in the store.
     * @param {string} robotType - e.g. "humanoids", "arms", "rovers", etc.
     */
    function fetchRobotsByType(robotType) {
        if (robotsByType.value[robotType]) return;
        roboticsApi.getRobotsByType(robotType).then(response => {
            robotsByType.value[robotType] = RobotAssembler.toEntitiesFromResponse(response);
        }).catch(error => errors.value.push(error));
    }

    /**
     * Returns the robot list for a given type (empty array if not loaded yet).
     * @param {string} robotType
     * @returns {Robot[]}
     */
    function getRobotsByType(robotType) {
        return robotsByType.value[robotType] || [];
    }

    return {
        robotsByType, errors,
        fetchRobotsByType, getRobotsByType
    };
});

export default useRoboticsStore;
```

## Configuración de Pinia, I18n y Router

### Creación del archivo pinia.js

**Crear** el archivo `pinia.js` en `src/`:

```js
import { createPinia } from 'pinia';

/**
 * Pinia instance for application-wide state management.
 * @summary Shared Pinia instance registered in main.js.
 * @author [Tu Nombre y Apellido]
 */
const pinia = createPinia();

export default pinia;
```

### Creación del archivo i18n.js

**Crear** el archivo `i18n.js` en `src/`:

```js
import { createI18n } from "vue-i18n";
import en from "./locales/en.json";
import es from "./locales/es.json";

/**
 * Shared internationalization service for the Clearpath Robotics application.
 * @summary Configures vue-i18n with English as default and Spanish as alternative locale.
 * @author [Tu Nombre y Apellido]
 */
const i18n = createI18n({
    legacy: false,
    locale: "en",
    fallbackLocale: "en",
    messages: { en, es }
});

export default i18n;
```

### Creación del Routes fleeting-routes

**Crear** el archivo `fleeting-routes.js` en `src/fleeting/presentation`. Cada vista se importa de forma `lazy` para reducir el bundle inicial:

```js
const newInventoryItem = () => import('./views/new-inventory-item.vue');

/**
 * Route definitions for the fleeting module (inventory items).
 * @summary Defines child routes for the /inventory path with lazy-loaded views.
 * @author [Tu Nombre y Apellido]
 */
const fleetingRoutes = [
    {
        path: 'items/new',
        name: 'inventory-items-new',
        component: newInventoryItem,
        meta: { title: 'New Inventory Item' }
    }
];

export default fleetingRoutes;
```

### Creación del Router router.js

**Crear** el archivo `router.js` en `src/`:

```js
import { createRouter, createWebHistory } from 'vue-router';
import Home from "@/shared/presentation/views/home.vue";
import fleetingRoutes from "@/fleeting/presentation/fleeting-routes.js";

const pageNotFound = () => import("@/shared/presentation/views/page-not-found.vue");

/**
 * Application router configuration with lazy-loaded routes.
 * @summary Defines top-level routes including home, inventory child routes, and 404 fallback.
 * @author [Tu Nombre y Apellido]
 */
const routes = [
    { path: '/home',                name: 'home',       component: Home,        meta: { title: 'Home' } },
    { path: '/inventory',           name: 'inventory',  children: fleetingRoutes },
    { path: '/',                    redirect: '/home' },
    { path: '/:pathMatch(.*)*',     name: 'not-found',  component: pageNotFound, meta: { title: 'Page Not Found' } }
];

const router = createRouter({
    history: createWebHistory(import.meta.env.BASE_URL),
    routes
});

router.beforeEach((to) => {
    const baseTitle = 'Clearpath Robotics';
    document.title = `${baseTitle} - ${to.meta['title'] ?? ''}`;
    return true;
});

export default router;
```

> [!NOTE]
> En vue-router 4 los navigation guards modernos **retornan** el valor en vez de llamar `next()`. Usar `return true` (permitir), `return false` (cancelar) o `return { name: 'home' }` (redirigir).

## Creación de componentes y vistas

A continuación se detalla las instrucciones para crear todas las vistas y componentes. **Crear** los siguientes archivos:

```markdown
- 📂 src
  - 📂 shared/presentation
    - 📂 components
      - 📄 layout.vue
      - 📄 footer-content.vue
      - 📄 language-switcher.vue
    - 📂 views
      - 📄 home.vue
      - 📄 page-not-found.vue
  - 📂 fleeting/presentation
    - 📂 components
      - 📄 fleet-summary.vue
    - 📂 views
      - 📄 new-inventory-item.vue
```

### Modificación del global styles

**Crear** los archivos `base.css` y `main.css` en `src/assets`:

#### base.css

```css
:root {
  --color-primary: #c8102e;
  --color-primary-hover: #a50d26;
  --color-primary-light: #fdecea;
  --color-bg: #f4f4f4;
  --color-surface: #ffffff;
  --color-text: #1a1a1a;
  --color-text-muted: #616161;
  --color-accent: #1b1b1b;
  --color-border: rgba(0, 0, 0, 0.08);
  --shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.08);
  --shadow-md: 0 4px 12px rgba(0, 0, 0, 0.1);
  --radius: 8px;
}

*, *::before, *::after { box-sizing: border-box; }

html, body {
  margin: 0;
  padding: 0;
  min-height: 100vh;
  background-color: var(--color-bg);
  color: var(--color-text);
  font-family: 'Segoe UI', Roboto, -apple-system, BlinkMacSystemFont, sans-serif;
  font-size: 15px;
  line-height: 1.6;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

a { color: inherit; }
```

#### main.css

```css
@import './base.css';

#app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

.surface-card {
  background-color: var(--color-surface);
  border-radius: var(--radius);
  box-shadow: var(--shadow-sm);
  padding: 24px;
}

.page-title {
  font-size: 1.75rem;
  font-weight: 500;
  color: var(--color-primary);
  margin: 0 0 16px 0;
}
```

### Modificación del LanguageSwitcher Component

**Reemplazar** el contenido de `language-switcher.vue`:

```vue
<script setup>
/**
 * Shared component for switching application language (en/es).
 * @summary Renders a SelectButton that toggles the active vue-i18n locale.
 * @author [Tu Nombre y Apellido]
 */
import { useI18n } from "vue-i18n";

const { locale, availableLocales } = useI18n();
</script>

<template>
  <pv-select-button
    v-model="locale"
    :options="availableLocales"
    aria-label="Language switcher">
    <template #option="slotProps">
      <span>{{ slotProps.option.toUpperCase() }}</span>
    </template>
  </pv-select-button>
</template>
```

### Modificación del FooterContent Component

**Reemplazar** el contenido de `footer-content.vue`:

```vue
<script setup>
/**
 * Shared footer component with copyright and technology credits.
 * @summary Displays copyright notice and tech stack attribution using i18n.
 * @author [Tu Nombre y Apellido]
 */
import { useI18n } from "vue-i18n";

const { t } = useI18n();
</script>

<template>
  <footer class="footer-content" role="contentinfo">
    <p>Copyright &copy; 2026. Clearpath Robotics</p>
    <p class="powered">
      {{ t('authoring-phrase.intro') }}<i class="pi pi-heart" aria-hidden="true"/>
      {{ t('authoring-phrase.use') }}
      <a href="https://primevue.org/" target="_blank" rel="noopener">PrimeVue</a>
      {{ t('authoring-phrase.author', { brand: 'Clearpath' }) }}
    </p>
  </footer>
</template>

<style scoped>
.footer-content {
  width: 100%;
  margin-top: auto;
  padding: 20px 24px;
  background-color: var(--color-accent);
  color: #fff;
  text-align: center;
  font-size: 0.85rem;
}
.footer-content p { margin: 6px 0; }
.footer-content a { color: #ffcc02; text-decoration: underline; }
.footer-content .pi-heart { margin: 0 4px; color: #ff6b6b; }
</style>
```

### Modificación del Layout Component

**Reemplazar** el contenido de `layout.vue`. El toolbar usa un grid de 3 columnas (`brand | nav | lang`), permanece `sticky` arriba, y el footer queda anclado al fondo gracias al flex layout de `#app`:

```vue
<script setup>
/**
 * Main layout component. Coordinates toolbar, navigation, router-view and footer.
 * @summary Renders the sticky toolbar with logo, nav links, language switcher, and wraps page content.
 * @author [Tu Nombre y Apellido]
 */
import { useI18n } from "vue-i18n";
import LanguageSwitcher from "@/shared/presentation/components/language-switcher.vue";
import FooterContent    from "@/shared/presentation/components/footer-content.vue";

const { t } = useI18n();

const logoDevUrl = import.meta.env.VITE_LOGO_DEV_API_URL;

const items = [
  { label: 'option.home',               path: '/home' },
  { label: 'option.new-inventory-item', path: '/inventory/items/new' }
];
</script>

<template>
  <pv-toast/>
  <header class="toolbar" role="banner">
    <div class="brand">
      <img
        :src="`${logoDevUrl}/clearpathrobotics.com?token=pk_e8Spi8nRR6KhSTFpEFGk1g`"
        alt="Clearpath Robotics logo"
        class="brand-logo"
        height="36"/>
      <span class="brand-name">Custom Robotic Platforms Manufacturers</span>
    </div>
    <nav class="nav-center" aria-label="Main navigation">
      <router-link
        v-for="item in items"
        :key="item.label"
        :to="item.path"
        class="nav-link"
        active-class="active">
        {{ t(item.label) }}
      </router-link>
    </nav>
    <div class="lang">
      <language-switcher/>
    </div>
  </header>
  <main class="main-content" role="main">
    <router-view/>
  </main>
  <footer-content/>
</template>

<style scoped>
.toolbar {
  position: sticky;
  top: 0;
  z-index: 10;
  display: grid;
  grid-template-columns: 1fr auto 1fr;
  align-items: center;
  gap: 16px;
  padding: 14px 28px;
  background-color: #1b1b1b;
  color: #fff;
  box-shadow: var(--shadow-md);
}
.brand { justify-self: start; display: flex; align-items: center; gap: 12px; }
.brand-logo { object-fit: contain; }
.brand-name { font-size: 0.95rem; font-weight: 600; color: #fff; }
.nav-center { justify-self: center; display: flex; gap: 6px; flex-wrap: wrap; }
.nav-link {
  color: #fff;
  text-decoration: none;
  padding: 8px 16px;
  border-radius: var(--radius);
  font-size: 0.9rem;
  font-weight: 500;
  transition: background-color 0.15s ease;
}
.nav-link:hover  { background-color: rgba(255, 255, 255, 0.12); }
.nav-link.active { background-color: var(--color-primary); }
.lang { justify-self: end; }

@media (max-width: 768px) {
  .toolbar { grid-template-columns: 1fr; justify-items: center; text-align: center; }
  .brand, .nav-center, .lang { justify-self: center; }
  .brand-name { display: none; }
}
.main-content { flex: 1; width: 100%; max-width: 1200px; margin: 0 auto; padding: 28px; }
</style>
```

### Modificación del App

**Reemplazar** el contenido de `App.vue`:

```vue
<script setup>
/**
 * Root application component. Mounts the main layout.
 * @summary Entry component that renders the shared Layout wrapper.
 * @author [Tu Nombre y Apellido]
 */
import Layout from "@/shared/presentation/components/layout.vue";
</script>

<template>
  <layout/>
</template>
```

### Modificación del Home View

**Reemplazar** el contenido de `home.vue`:

```vue
<script setup>
/**
 * Home view component displaying welcome content and fleet summaries.
 * @summary Loads fleets and inventory items on mount, then renders the fleet grid.
 * @author [Tu Nombre y Apellido]
 */
import { onMounted, toRefs } from "vue";
import { useI18n }           from "vue-i18n";
import useFleetingStore      from "@/fleeting/application/fleeting.store.js";
import FleetSummary          from "@/fleeting/presentation/components/fleet-summary.vue";

const { t }   = useI18n();
const store   = useFleetingStore();
const { fleets, fleetsLoaded } = toRefs(store);

onMounted(() => {
  if (!store.fleetsLoaded)    store.fetchFleets();
  if (!store.inventoryLoaded) store.fetchInventoryItems();
});
</script>

<template>
  <section class="home" aria-labelledby="home-title">
    <h1 id="home-title" class="page-title">{{ t('home.title') }}</h1>
    <p class="lead">{{ t('home.content') }}</p>

    <h2 class="section-title">{{ t('home.my-robot-fleets') }}</h2>
    <div v-if="fleetsLoaded" class="fleet-grid" role="list">
      <fleet-summary
        v-for="fleet in fleets"
        :key="fleet.id"
        :fleet="fleet"
        role="listitem"/>
    </div>
    <div v-else class="loading-placeholder" aria-busy="true">
      <i class="pi pi-spin pi-spinner" aria-hidden="true"/> Loading fleets...
    </div>
  </section>
</template>

<style scoped>
.home          { display: flex; flex-direction: column; gap: 20px; padding: 16px 0; }
.lead          { font-size: 1.1rem; color: var(--color-text-muted); margin: 0; }
.section-title { font-size: 1.4rem; font-weight: 500; color: var(--color-text); margin: 8px 0 4px 0; }
.fleet-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
}
@media (max-width: 768px) {
  .fleet-grid { grid-template-columns: 1fr; }
}
.loading-placeholder { color: var(--color-text-muted); display: flex; align-items: center; gap: 8px; }
</style>
```

### Creación del FleetSummary Component

**Reemplazar** el contenido de `fleet-summary.vue`:

```vue
<script setup>
/**
 * Fleet Summary component displaying a card for a single fleet.
 * @summary Shows fleet name, its inventory items with quantities, total robots, and available capacity.
 * @author [Tu Nombre y Apellido]
 */
import { computed }     from "vue";
import { useI18n }      from "vue-i18n";
import useFleetingStore from "@/fleeting/application/fleeting.store.js";

const props = defineProps({
  /** @type {import('@/fleeting/domain/model/fleet.entity.js').Fleet} */
  fleet: { type: Object, required: true }
});

const { t }   = useI18n();
const store   = useFleetingStore();

const items            = computed(() => store.getItemsByFleetId(props.fleet.id));
const totalRobots      = computed(() => store.getTotalRobotsByFleetId(props.fleet.id));
const availableCapacity = computed(() => store.getAvailableCapacity(props.fleet.id));
</script>

<template>
  <pv-card class="fleet-card" :aria-label="`Fleet: ${fleet.name}`">
    <template #header>
      <div class="card-header">
        <span class="fleet-name">{{ fleet.name }}</span>
      </div>
    </template>
    <template #content>
      <div v-if="items.length > 0" class="item-list" role="list">
        <div
          v-for="item in items"
          :key="item.id"
          class="item-row"
          role="listitem">
          <span class="item-name">{{ item.robotName }}</span>
          <span class="item-qty">{{ item.quantity }}</span>
        </div>
      </div>
      <p v-else class="empty-msg">{{ t('fleet-summary.empty') }}</p>
    </template>
    <template #footer>
      <div class="card-footer">
        <span>{{ t('fleet-summary.total-robots') }}: <strong>{{ totalRobots }}</strong></span>
        <span>{{ t('fleet-summary.available-capacity') }}: <strong>{{ availableCapacity }}</strong></span>
      </div>
    </template>
  </pv-card>
</template>

<style scoped>
.fleet-card   { width: 100%; }
.card-header  { padding: 12px 16px; background-color: var(--color-primary); border-radius: var(--radius) var(--radius) 0 0; }
.fleet-name   { color: #fff; font-weight: 600; font-size: 1rem; }
.item-list    { display: flex; flex-direction: column; gap: 8px; }
.item-row     { display: flex; justify-content: space-between; align-items: center; padding: 6px 0; border-bottom: 1px solid var(--color-border); }
.item-name    { color: var(--color-text); }
.item-qty     { font-weight: 600; color: var(--color-primary); }
.empty-msg    { color: var(--color-text-muted); font-style: italic; }
.card-footer  { display: flex; justify-content: space-between; flex-wrap: wrap; gap: 8px; font-size: 0.9rem; color: var(--color-text-muted); }
</style>
```

### Modificación del PageNotFound View

**Reemplazar** el contenido de `page-not-found.vue`:

```vue
<script setup>
/**
 * Page not found view displayed for invalid routes.
 * @summary Shows the unmatched path and provides a button to navigate back to Home.
 * @author [Tu Nombre y Apellido]
 */
import { useRouter } from "vue-router";
import { useI18n }   from "vue-i18n";

const router           = useRouter();
const unavailableRoute = router.currentRoute.value.fullPath;
const { t }            = useI18n();
</script>

<template>
  <section class="page-not-found" aria-labelledby="not-found-title">
    <h1 id="not-found-title">{{ t('page-not-found.title') }}</h1>
    <p>{{ t('page-not-found.content', { 'unavailable-route': unavailableRoute }) }}</p>
    <router-link class="go-home" to="/home">{{ t('page-not-found.go-home') }}</router-link>
  </section>
</template>

<style scoped>
.page-not-found {
  text-align: center;
  padding: 80px 24px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
}
.page-not-found h1 { font-size: 3rem; color: var(--color-primary); margin: 0; }
.page-not-found p  { color: var(--color-text-muted); margin: 0; font-size: 1.1rem; }
.go-home {
  display: inline-block;
  padding: 12px 24px;
  background-color: var(--color-primary);
  color: #fff;
  text-decoration: none;
  border-radius: var(--radius);
  font-weight: 500;
  transition: background-color 0.15s ease;
}
.go-home:hover { background-color: var(--color-primary-hover); }
</style>
```

### Modificación del NewInventoryItem View

**Reemplazar** el contenido de `new-inventory-item.vue`:

```vue
<script setup>
/**
 * New Inventory Item view for creating a robot inventory entry within a fleet.
 * @summary Provides a form to select robot type, robot, and quantity; validates against fleet capacity before saving.
 * @author [Tu Nombre y Apellido]
 */
import { computed, ref, watch }  from "vue";
import { useRouter }             from "vue-router";
import { useI18n }               from "vue-i18n";
import { useToast }              from "primevue/usetoast";
import useFleetingStore          from "@/fleeting/application/fleeting.store.js";
import useRoboticsStore          from "@/robotics/application/robotics.store.js";
import { InventoryItem }         from "@/fleeting/domain/model/inventory-item.entity.js";

const { t }         = useI18n();
const router        = useRouter();
const toast         = useToast();
const fleetingStore = useFleetingStore();
const roboticsStore = useRoboticsStore();

const robotTypes = ['humanoids', 'arms', 'rovers', 'drones', 'quadrupeds', 'agvs'];

const form = ref({
  robotType: null,
  robot:     null,
  quantity:  1
});

const robots = computed(() =>
  form.value.robotType ? roboticsStore.getRobotsByType(form.value.robotType) : []
);

const currentFleet = computed(() =>
  form.value.robotType ? fleetingStore.getFleetByRobotType(form.value.robotType) : null
);

const availableCapacity = computed(() =>
  currentFleet.value ? fleetingStore.getAvailableCapacity(currentFleet.value.id) : 0
);

const capacityExceeded = computed(() =>
  form.value.quantity > availableCapacity.value
);

watch(() => form.value.robotType, (newType) => {
  form.value.robot    = null;
  form.value.quantity = 1;
  if (newType) roboticsStore.fetchRobotsByType(newType);
});

const saveInventoryItem = () => {
  if (capacityExceeded.value) {
    toast.add({ severity: 'warn', summary: 'Warning', detail: t('new-inventory-item.capacity-exceeded'), life: 4000 });
    return;
  }
  const item = new InventoryItem({
    fleetId:      currentFleet.value.id,
    robotType:    form.value.robotType,
    robotId:      form.value.robot.id,
    robotName:    form.value.robot.model,
    quantity:     form.value.quantity,
    registeredAt: new Date().toISOString()
  });
  fleetingStore.addInventoryItem(item).then(() => {
    toast.add({ severity: 'success', summary: 'Success', detail: t('new-inventory-item.success'), life: 3000 });
    navigateBack();
  });
};

const navigateBack = () => router.push({ name: 'home' });
</script>

<template>
  <div class="form-page" aria-labelledby="form-title">
    <h1 id="form-title" class="page-title">{{ t('new-inventory-item.title') }}</h1>
    <p class="subtitle">{{ t('new-inventory-item.subtitle') }}</p>
    <form class="surface-card" @submit.prevent="saveInventoryItem" novalidate>

      <div class="field">
        <label for="robot-type">{{ t('new-inventory-item.robot-type') }}</label>
        <pv-select
          id="robot-type"
          v-model="form.robotType"
          :options="robotTypes"
          :placeholder="t('new-inventory-item.select-robot-type')"
          class="w-full"
          aria-required="true"/>
      </div>

      <div class="field">
        <label for="robot">{{ t('new-inventory-item.robot') }}</label>
        <pv-select
          id="robot"
          v-model="form.robot"
          :options="robots"
          option-label="model"
          :placeholder="t('new-inventory-item.select-robot')"
          :disabled="!form.robotType"
          class="w-full"
          aria-required="true"/>
      </div>

      <div class="field">
        <label for="quantity">{{ t('new-inventory-item.quantity') }}</label>
        <pv-input-number
          id="quantity"
          v-model="form.quantity"
          :min="1"
          :max="availableCapacity || 9999"
          class="w-full"
          aria-required="true"/>
        <small v-if="currentFleet" class="capacity-info">
          {{ t('fleet-summary.available-capacity') }}: {{ availableCapacity }}
        </small>
        <small v-if="capacityExceeded" class="capacity-error" role="alert">
          {{ t('new-inventory-item.capacity-exceeded') }}
        </small>
      </div>

      <div class="actions">
        <pv-button
          :label="t('new-inventory-item.cancel')"
          severity="secondary"
          type="button"
          @click="navigateBack"/>
        <pv-button
          :label="t('new-inventory-item.create')"
          type="submit"
          icon="pi pi-check"
          :disabled="!form.robot || !form.robotType || capacityExceeded"/>
      </div>
    </form>

    <div v-if="fleetingStore.errors.length" class="error-banner" role="alert">
      {{ t('errors.occurred') }}: {{ fleetingStore.errors.map(e => e.message).join(', ') }}
    </div>
  </div>
</template>

<style scoped>
.form-page     { display: flex; flex-direction: column; gap: 16px; max-width: 560px; }
.subtitle      { color: var(--color-text-muted); margin: -8px 0 0 0; font-size: 1rem; }
.field         { display: flex; flex-direction: column; gap: 6px; margin-bottom: 20px; }
.field label   { font-weight: 500; color: var(--color-text); }
.capacity-info { color: var(--color-text-muted); font-size: 0.82rem; }
.capacity-error { color: #b71c1c; font-size: 0.82rem; }
.actions       { display: flex; gap: 10px; justify-content: flex-end; }
.error-banner  { background-color: #fdecea; color: #b71c1c; padding: 12px 16px; border-radius: var(--radius); font-size: 0.9rem; }
</style>
```

## Configuración del main.js

**Reemplazar** el contenido del archivo `main.js` ubicado en `src/`. Aquí se registran globalmente PrimeVue (con tema Material en modo light pineado), Pinia, Router, I18n, y todos los componentes PrimeVue con prefijo `pv-`:

```js
import './assets/main.css';

import { createApp } from 'vue';
import App from './App.vue';

import 'primeflex/primeflex.css';
import 'primeicons/primeicons.css';
import Material          from '@primeuix/themes/material';
import PrimeVue          from 'primevue/config';
import {
    Button, Card, Column,
    ConfirmationService, ConfirmDialog, DataTable,
    DialogService, FloatLabel, IconField,
    InputIcon, InputNumber, InputText,
    Select, SelectButton, Tag, Textarea, Toast,
    ToastService, Toolbar, Tooltip
} from "primevue";

import i18n   from "@/i18n.js";
import pinia  from "@/pinia.js";
import router from "@/router.js";

/**
 * Application entry point. Registers plugins, global PrimeVue components, and directives.
 * @summary Bootstraps the Vue 3 app with all required plugins and component registrations.
 * @author [Tu Nombre y Apellido]
 */
createApp(App)
    .use(i18n)
    .use(PrimeVue, {
        theme: {
            preset: Material,
            options: {
                darkModeSelector: false,
                cssLayer: false
            }
        },
        ripple: true
    })
    .use(ConfirmationService)
    .use(DialogService)
    .use(ToastService)
    .component('pv-button',        Button)
    .component('pv-card',          Card)
    .component('pv-column',        Column)
    .component('pv-confirm-dialog',ConfirmDialog)
    .component('pv-data-table',    DataTable)
    .component('pv-float-label',   FloatLabel)
    .component('pv-icon-field',    IconField)
    .component('pv-input-icon',    InputIcon)
    .component('pv-input-text',    InputText)
    .component('pv-input-number',  InputNumber)
    .component('pv-select',        Select)
    .component('pv-select-button', SelectButton)
    .component('pv-tag',           Tag)
    .component('pv-textarea',      Textarea)
    .component('pv-toolbar',       Toolbar)
    .component('pv-toast',         Toast)
    .directive('tooltip',          Tooltip)
    .use(router)
    .use(pinia)
    .mount('#app');
```

> [!NOTE]
> `darkModeSelector: false` pinea PrimeVue en modo light. Sin esta opción, el tema se cambia automáticamente según `prefers-color-scheme` del sistema operativo del usuario, generando inconsistencia con los estilos personalizados de la página.

### Modificación del index.html

**Reemplazar** el contenido del archivo `index.html` ubicado en la raíz del proyecto:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <link rel="icon" href="/favicon.ico">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Clearpath Robotics</title>
  </head>
  <body>
    <div id="app"></div>
    <script type="module" src="/src/main.js"></script>
  </body>
</html>
```

## README.md

**Crear** el archivo `README.md` en la raíz del proyecto con el siguiente contenido:

```markdown
# Clearpath Robotics Fleet Management

## Description
Web application for managing robot fleets and inventory items for Clearpath Robotics.
Allows users to visualize fleet summaries including total robots and available capacity,
and register new inventory items by selecting robot type, robot, and quantity.

## Features
- Home view displaying "My Robot Fleets" as a 2-column grid of Fleet Summary cards
- Fleet Summary card showing robot items, total robots count, and available capacity
- New Inventory Item form with robot type → robot cascade selection and capacity validation
- Capacity guard: prevents registering items that exceed the fleet's available capacity
- Automatic population of `registeredAt` timestamp on item creation
- English / Spanish language switching (i18n)
- Page-not-found view for unsupported routes
- Dynamic document title per route

## Stack
- **Frontend:** Vue 3 + Vite
- **UI:** PrimeVue (Material preset) + PrimeFlex + PrimeIcons
- **State:** Pinia
- **Router:** Vue Router 4
- **i18n:** vue-i18n
- **HTTP:** axios
- **Backend (local):** json-server
- **External API:** SampleAPI Robotics (https://api.sampleapis.com/robots)
- **Logo:** Logo.dev Logo API

## Setup

### Prerequisites
- Node.js >= 18
- json-server 0.17.4 installed globally

### Running the backend
```bash
cd server
json-server --watch db.json --port 3000
```

### Running the frontend
```bash
npm install
npm run dev
```

Open http://localhost:5173

## Author
- **Code:** [eanrcucode]
- **Name:** [Tu Nombre y Apellido]
- **Course:** Aplicaciones Web (1ASI0730)
- **NRC:** 12190
- **Professors:** Bautista Ubillús, Efraín Ricardo / Castro Veramendi, Rafael Oswaldo / Flores Ingaruca, José Miguel / Mori Paiva, Hugo Allan / Sánchez Ponce, Alex Humberto / Velásquez Núñez, Ángel Augusto / Villafuerte Bazán, Óscar Iván
```

## Ejecución del proyecto

**Cargar** dos tabs del `Terminal` del IDE.

**Tab 1** - Ejecutar el `json-server`:

```bash
cd server
json-server --watch db.json --port 3000
```

**Tab 2** - Ejecutar Vite en modo development:

```bash
npm run dev
```

**Cargar** el navegador en http://localhost:5173

## Empaquetado para entrega

Antes de generar el archivo `.zip`:

1. **Eliminar** la carpeta `node_modules`.
2. **Eliminar** la carpeta `dist` (si existe).
3. **Comprimir** el proyecto siguiendo la convención `eanrcucode.zip` (por ejemplo `ea12190u201821873.zip`).

## Actividad

- **Probar** los flujos de Home y New Inventory Item.
- **Verificar** que la vista Home muestre el grid "My Robot Fleets" con los datos correctos de fleets e inventory items.
- **Verificar** que cada Fleet Summary card calcule correctamente `Total Robots` y `Available Capacity`.
- **Verificar** que los fleets sin inventory items muestren "Empty" en el contenido del card.
- **Verificar** que el formulario New Inventory Item cargue dinámicamente los robots desde SampleAPI según el tipo seleccionado.
- **Verificar** que la validación de capacidad impida registrar un quantity mayor al `Available Capacity` del fleet.
- **Verificar** que `registeredAt` se genere automáticamente al crear un inventory item.
- **Verificar** que el `language-switcher` cambie entre `en` y `es` y que todas las vistas reaccionen.
- **Verificar** que el `title` del documento (`document.title`) se actualice al navegar entre rutas gracias al `router.beforeEach`.
- **Verificar** que la vista `page-not-found` muestre la ruta inválida y el botón para regresar a Home.
- **Verificar** que las llamadas HTTP usen correctamente las variables de entorno `VITE_*`.

## Estructura final del proyecto

```
eanrcucode/
├── server/
│   └── db.json
├── src/
│   ├── assets/
│   │   ├── base.css
│   │   └── main.css
│   ├── locales/
│   │   ├── en.json
│   │   └── es.json
│   ├── fleeting/
│   │   ├── application/
│   │   │   └── fleeting.store.js
│   │   ├── domain/
│   │   │   └── model/
│   │   │       ├── fleet.entity.js
│   │   │       └── inventory-item.entity.js
│   │   ├── infrastructure/
│   │   │   ├── fleet.assembler.js
│   │   │   ├── fleeting-api.js
│   │   │   └── inventory-item.assembler.js
│   │   └── presentation/
│   │       ├── fleeting-routes.js
│   │       ├── components/
│   │       │   └── fleet-summary.vue
│   │       └── views/
│   │           └── new-inventory-item.vue
│   ├── robotics/
│   │   ├── application/
│   │   │   └── robotics.store.js
│   │   ├── domain/
│   │   │   └── model/
│   │   │       └── robot.entity.js
│   │   ├── infrastructure/
│   │   │   ├── robot.assembler.js
│   │   │   └── robotics-api.js
│   │   └── presentation/
│   │       └── components/
│   ├── shared/
│   │   ├── infrastructure/
│   │   │   ├── base-api.js
│   │   │   └── base-endpoint.js
│   │   └── presentation/
│   │       ├── components/
│   │       │   ├── footer-content.vue
│   │       │   ├── language-switcher.vue
│   │       │   └── layout.vue
│   │       └── views/
│   │           ├── home.vue
│   │           └── page-not-found.vue
│   ├── App.vue
│   ├── i18n.js
│   ├── main.js
│   ├── pinia.js
│   └── router.js
├── .env.development
├── .env.production
├── jsconfig.json
├── vite.config.js
├── index.html
├── README.md
└── package.json
```
