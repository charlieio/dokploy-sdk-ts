# dokploy-sdk

Developer-friendly & type-safe Typescript SDK specifically catered to leverage *dokploy* API.

<div align="left">
    <a href="https://www.speakeasy.com/?utm_source=dokploy-sdk&utm_campaign=typescript"><img src="https://www.speakeasy.com/assets/badges/built-by-speakeasy.svg" /></a>
    <a href="https://opensource.org/licenses/MIT">
        <img src="https://img.shields.io/badge/License-MIT-blue.svg" style="width: 100px; height: 28px;" />
    </a>
</div>

<!-- Start Summary [summary] -->
## Summary

Dokploy API: Endpoints for dokploy

More information about the API can be found at http://localhost:3000/api/settings.getOpenApiDocument
<!-- End Summary [summary] -->

<!-- Start Table of Contents [toc] -->
## Table of Contents
<!-- $toc-max-depth=2 -->
* [dokploy-sdk](#dokploy-sdk)
  * [SDK Installation](#sdk-installation)
  * [Requirements](#requirements)
  * [SDK Example Usage](#sdk-example-usage)
  * [Authentication](#authentication)
  * [Available Resources and Operations](#available-resources-and-operations)
  * [Standalone functions](#standalone-functions)
  * [Retries](#retries)
  * [Error Handling](#error-handling)
  * [Server Selection](#server-selection)
  * [Custom HTTP Client](#custom-http-client)
  * [Debugging](#debugging)
* [Development](#development)
  * [Maturity](#maturity)
  * [Contributions](#contributions)

<!-- End Table of Contents [toc] -->

<!-- Start SDK Installation [installation] -->
## SDK Installation

The SDK can be installed with either [npm](https://www.npmjs.com/), [pnpm](https://pnpm.io/), [bun](https://bun.sh/) or [yarn](https://classic.yarnpkg.com/en/) package managers.

### NPM

```bash
npm add dokploy-sdk
```

### PNPM

```bash
pnpm add dokploy-sdk
```

### Bun

```bash
bun add dokploy-sdk
```

### Yarn

```bash
yarn add dokploy-sdk
```

> [!NOTE]
> This package is published with CommonJS and ES Modules (ESM) support.
<!-- End SDK Installation [installation] -->

<!-- Start Requirements [requirements] -->
## Requirements

For supported JavaScript runtimes, please consult [RUNTIMES.md](RUNTIMES.md).
<!-- End Requirements [requirements] -->

<!-- Start SDK Example Usage [usage] -->
## SDK Example Usage

### Example

```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.admin.setupMonitoring({
    metricsConfig: {
      containers: {
        refreshRate: 7401.48,
        services: {},
      },
      server: {
        cronJob: "<value>",
        port: 8537.41,
        refreshRate: 4397.9,
        retentionDays: 6999.95,
        thresholds: {
          cpu: 5497.84,
          memory: 6419.22,
        },
        token: "<value>",
        urlCallback: "https://majestic-scratch.org",
      },
    },
  });

  console.log(result);
}

run();

```
<!-- End SDK Example Usage [usage] -->

<!-- Start Authentication [security] -->
## Authentication

### Per-Client Security Schemes

This SDK supports the following security scheme globally:

| Name         | Type   | Scheme  | Environment Variable   |
| ------------ | ------ | ------- | ---------------------- |
| `apiKeyAuth` | apiKey | API key | `DOKPLOY_API_KEY_AUTH` |

To authenticate with the API the `apiKeyAuth` parameter must be set when initializing the SDK client instance. For example:
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.admin.setupMonitoring({
    metricsConfig: {
      containers: {
        refreshRate: 7401.48,
        services: {},
      },
      server: {
        cronJob: "<value>",
        port: 8537.41,
        refreshRate: 4397.9,
        retentionDays: 6999.95,
        thresholds: {
          cpu: 5497.84,
          memory: 6419.22,
        },
        token: "<value>",
        urlCallback: "https://majestic-scratch.org",
      },
    },
  });

  console.log(result);
}

run();

```
<!-- End Authentication [security] -->

<!-- Start Available Resources and Operations [operations] -->
## Available Resources and Operations

<details open>
<summary>Available methods</summary>

### [Admin](docs/sdks/admin/README.md)

* [setupMonitoring](docs/sdks/admin/README.md#setupmonitoring)

### [Ai](docs/sdks/ai/README.md)

* [create](docs/sdks/ai/README.md#create)
* [delete](docs/sdks/ai/README.md#delete)
* [deploy](docs/sdks/ai/README.md#deploy)
* [get](docs/sdks/ai/README.md#get)
* [getAll](docs/sdks/ai/README.md#getall)
* [getModels](docs/sdks/ai/README.md#getmodels)
* [getOne](docs/sdks/ai/README.md#getone)
* [suggest](docs/sdks/ai/README.md#suggest)
* [update](docs/sdks/ai/README.md#update)

### [Application](docs/sdks/application/README.md)

* [cancelDeployment](docs/sdks/application/README.md#canceldeployment)
* [cleanQueues](docs/sdks/application/README.md#cleanqueues)
* [create](docs/sdks/application/README.md#create)
* [delete](docs/sdks/application/README.md#delete)
* [deploy](docs/sdks/application/README.md#deploy)
* [disconnectGitProvider](docs/sdks/application/README.md#disconnectgitprovider)
* [markRunning](docs/sdks/application/README.md#markrunning)
* [get](docs/sdks/application/README.md#get)
* [readAppMonitoring](docs/sdks/application/README.md#readappmonitoring)
* [redeploy](docs/sdks/application/README.md#redeploy)
* [reload](docs/sdks/application/README.md#reload)
* [saveBitbucketProvider](docs/sdks/application/README.md#savebitbucketprovider)
* [saveBuildType](docs/sdks/application/README.md#savebuildtype)
* [saveDockerProvider](docs/sdks/application/README.md#savedockerprovider)
* [saveEnvironment](docs/sdks/application/README.md#saveenvironment)
* [saveGitProdiver](docs/sdks/application/README.md#savegitprodiver)
* [saveGiteaProvider](docs/sdks/application/README.md#savegiteaprovider)
* [saveGitlabProvider](docs/sdks/application/README.md#savegitlabprovider)
* [stop](docs/sdks/application/README.md#stop)
* [update](docs/sdks/application/README.md#update)
* [updateTraefikConfig](docs/sdks/application/README.md#updatetraefikconfig)

### [Applications](docs/sdks/applications/README.md)

* [move](docs/sdks/applications/README.md#move)
* [readTraefikConfig](docs/sdks/applications/README.md#readtraefikconfig)
* [refreshToken](docs/sdks/applications/README.md#refreshtoken)
* [saveGithubProvider](docs/sdks/applications/README.md#savegithubprovider)
* [start](docs/sdks/applications/README.md#start)

### [Backup](docs/sdks/backup/README.md)

* [create](docs/sdks/backup/README.md#create)
* [listFiles](docs/sdks/backup/README.md#listfiles)
* [manualBackupCompose](docs/sdks/backup/README.md#manualbackupcompose)
* [manualBackupMariadb](docs/sdks/backup/README.md#manualbackupmariadb)
* [manualBackupMongo](docs/sdks/backup/README.md#manualbackupmongo)
* [manualBackupMySql](docs/sdks/backup/README.md#manualbackupmysql)
* [manualBackupPostgres](docs/sdks/backup/README.md#manualbackuppostgres)
* [manualBackupWebServer](docs/sdks/backup/README.md#manualbackupwebserver)
* [one](docs/sdks/backup/README.md#one)
* [remove](docs/sdks/backup/README.md#remove)
* [update](docs/sdks/backup/README.md#update)

### [Bitbucket](docs/sdks/bitbucket/README.md)

* [create](docs/sdks/bitbucket/README.md#create)
* [getBranches](docs/sdks/bitbucket/README.md#getbranches)
* [getRepositories](docs/sdks/bitbucket/README.md#getrepositories)
* [getOne](docs/sdks/bitbucket/README.md#getone)
* [testConnection](docs/sdks/bitbucket/README.md#testconnection)
* [update](docs/sdks/bitbucket/README.md#update)

#### [Bitbucket.Get](docs/sdks/bitbucketget/README.md)

* [providers](docs/sdks/bitbucketget/README.md#providers)

### [Certificates](docs/sdks/certificates/README.md)

* [getAll](docs/sdks/certificates/README.md#getall)
* [create](docs/sdks/certificates/README.md#create)
* [get](docs/sdks/certificates/README.md#get)
* [remove](docs/sdks/certificates/README.md#remove)

### [Cluster](docs/sdks/cluster/README.md)

* [addManager](docs/sdks/cluster/README.md#addmanager)
* [addWorker](docs/sdks/cluster/README.md#addworker)
* [getNodes](docs/sdks/cluster/README.md#getnodes)
* [removeWorker](docs/sdks/cluster/README.md#removeworker)

### [Compose](docs/sdks/compose/README.md)

* [cancelDeployment](docs/sdks/compose/README.md#canceldeployment)
* [cleanQueues](docs/sdks/compose/README.md#cleanqueues)
* [create](docs/sdks/compose/README.md#create)
* [delete](docs/sdks/compose/README.md#delete)
* [deploy](docs/sdks/compose/README.md#deploy)
* [deployTemplate](docs/sdks/compose/README.md#deploytemplate)
* [disconnectGitprovider](docs/sdks/compose/README.md#disconnectgitprovider)
* [fetchSourceType](docs/sdks/compose/README.md#fetchsourcetype)
* [getConvertedCompose](docs/sdks/compose/README.md#getconvertedcompose)
* [getDefaultCommand](docs/sdks/compose/README.md#getdefaultcommand)
* [getTags](docs/sdks/compose/README.md#gettags)
* [import](docs/sdks/compose/README.md#import)
* [isolatedDeployment](docs/sdks/compose/README.md#isolateddeployment)
* [loadMountsByService](docs/sdks/compose/README.md#loadmountsbyservice)
* [move](docs/sdks/compose/README.md#move)
* [one](docs/sdks/compose/README.md#one)
* [processTemplate](docs/sdks/compose/README.md#processtemplate)
* [randomizeCompose](docs/sdks/compose/README.md#randomizecompose)
* [redeploy](docs/sdks/compose/README.md#redeploy)
* [refreshToken](docs/sdks/compose/README.md#refreshtoken)
* [start](docs/sdks/compose/README.md#start)
* [stop](docs/sdks/compose/README.md#stop)
* [getTemplates](docs/sdks/compose/README.md#gettemplates)
* [update](docs/sdks/compose/README.md#update)

### [Deployment](docs/sdks/deployment/README.md)

* [all](docs/sdks/deployment/README.md#all)
* [getAllByCompose](docs/sdks/deployment/README.md#getallbycompose)
* [allByServer](docs/sdks/deployment/README.md#allbyserver)
* [getAllByType](docs/sdks/deployment/README.md#getallbytype)
* [killProcess](docs/sdks/deployment/README.md#killprocess)

### [Destination](docs/sdks/destination/README.md)

* [getAll](docs/sdks/destination/README.md#getall)
* [create](docs/sdks/destination/README.md#create)
* [get](docs/sdks/destination/README.md#get)
* [remove](docs/sdks/destination/README.md#remove)
* [testConnection](docs/sdks/destination/README.md#testconnection)
* [update](docs/sdks/destination/README.md#update)

### [Docker](docs/sdks/docker/README.md)

* [getConfig](docs/sdks/docker/README.md#getconfig)
* [getContainers](docs/sdks/docker/README.md#getcontainers)
* [getContainersByAppLabel](docs/sdks/docker/README.md#getcontainersbyapplabel)
* [getContainersByAppNameMatch](docs/sdks/docker/README.md#getcontainersbyappnamematch)
* [restartContainer](docs/sdks/docker/README.md#restartcontainer)

#### [Docker.Get](docs/sdks/dockerget/README.md)

* [serviceContainersByAppName](docs/sdks/dockerget/README.md#servicecontainersbyappname)
* [stackContainersByAppName](docs/sdks/dockerget/README.md#stackcontainersbyappname)

### [Domain](docs/sdks/domain/README.md)

* [byApplicationId](docs/sdks/domain/README.md#byapplicationid)
* [getByComposeId](docs/sdks/domain/README.md#getbycomposeid)
* [canGenerateTraefikDomains](docs/sdks/domain/README.md#cangeneratetraefikdomains)
* [create](docs/sdks/domain/README.md#create)
* [delete](docs/sdks/domain/README.md#delete)
* [generateDomain](docs/sdks/domain/README.md#generatedomain)
* [update](docs/sdks/domain/README.md#update)
* [validateDomain](docs/sdks/domain/README.md#validatedomain)

### [Domains](docs/sdks/domains/README.md)

* [get](docs/sdks/domains/README.md#get)

### [Environment](docs/sdks/environment/README.md)

* [byProjectId](docs/sdks/environment/README.md#byprojectid)
* [create](docs/sdks/environment/README.md#create)
* [duplicate](docs/sdks/environment/README.md#duplicate)
* [get](docs/sdks/environment/README.md#get)
* [remove](docs/sdks/environment/README.md#remove)
* [update](docs/sdks/environment/README.md#update)

### [Gitea](docs/sdks/gitea/README.md)

* [create](docs/sdks/gitea/README.md#create)
* [getBranches](docs/sdks/gitea/README.md#getbranches)
* [getRepositories](docs/sdks/gitea/README.md#getrepositories)
* [getUrl](docs/sdks/gitea/README.md#geturl)
* [getProviders](docs/sdks/gitea/README.md#getproviders)
* [get](docs/sdks/gitea/README.md#get)
* [testConnection](docs/sdks/gitea/README.md#testconnection)
* [update](docs/sdks/gitea/README.md#update)

### [Github](docs/sdks/github/README.md)

* [getGithubRepositories](docs/sdks/github/README.md#getgithubrepositories)
* [getProviders](docs/sdks/github/README.md#getproviders)
* [one](docs/sdks/github/README.md#one)
* [testConnection](docs/sdks/github/README.md#testconnection)
* [update](docs/sdks/github/README.md#update)

#### [Github.Get](docs/sdks/githubget/README.md)

* [branches](docs/sdks/githubget/README.md#branches)

### [Gitlab](docs/sdks/gitlab/README.md)

* [create](docs/sdks/gitlab/README.md#create)
* [getBranches](docs/sdks/gitlab/README.md#getbranches)
* [getGitlabRepositories](docs/sdks/gitlab/README.md#getgitlabrepositories)
* [getProviders](docs/sdks/gitlab/README.md#getproviders)
* [one](docs/sdks/gitlab/README.md#one)
* [testConnection](docs/sdks/gitlab/README.md#testconnection)
* [update](docs/sdks/gitlab/README.md#update)

### [Gitprovider](docs/sdks/gitprovider/README.md)

* [remove](docs/sdks/gitprovider/README.md#remove)

### [GitProviders](docs/sdks/gitproviders/README.md)

* [getAll](docs/sdks/gitproviders/README.md#getall)

### [Mariadb](docs/sdks/mariadb/README.md)

* [changeStatus](docs/sdks/mariadb/README.md#changestatus)
* [create](docs/sdks/mariadb/README.md#create)
* [deploy](docs/sdks/mariadb/README.md#deploy)
* [move](docs/sdks/mariadb/README.md#move)
* [get](docs/sdks/mariadb/README.md#get)
* [rebuild](docs/sdks/mariadb/README.md#rebuild)
* [reload](docs/sdks/mariadb/README.md#reload)
* [remove](docs/sdks/mariadb/README.md#remove)
* [saveEnvironment](docs/sdks/mariadb/README.md#saveenvironment)
* [saveExternalPort](docs/sdks/mariadb/README.md#saveexternalport)
* [start](docs/sdks/mariadb/README.md#start)
* [stop](docs/sdks/mariadb/README.md#stop)
* [update](docs/sdks/mariadb/README.md#update)

### [Mongo](docs/sdks/mongo/README.md)

* [changeStatus](docs/sdks/mongo/README.md#changestatus)
* [create](docs/sdks/mongo/README.md#create)
* [deploy](docs/sdks/mongo/README.md#deploy)
* [move](docs/sdks/mongo/README.md#move)
* [getOne](docs/sdks/mongo/README.md#getone)
* [rebuild](docs/sdks/mongo/README.md#rebuild)
* [reload](docs/sdks/mongo/README.md#reload)
* [remove](docs/sdks/mongo/README.md#remove)
* [saveEnvironment](docs/sdks/mongo/README.md#saveenvironment)
* [saveExternalPort](docs/sdks/mongo/README.md#saveexternalport)
* [start](docs/sdks/mongo/README.md#start)
* [stop](docs/sdks/mongo/README.md#stop)
* [update](docs/sdks/mongo/README.md#update)

### [Mounts](docs/sdks/mounts/README.md)

* [allNamedByApplicationId](docs/sdks/mounts/README.md#allnamedbyapplicationid)
* [create](docs/sdks/mounts/README.md#create)
* [get](docs/sdks/mounts/README.md#get)
* [remove](docs/sdks/mounts/README.md#remove)
* [update](docs/sdks/mounts/README.md#update)

### [Mysql](docs/sdks/mysql/README.md)

* [changeStatus](docs/sdks/mysql/README.md#changestatus)
* [create](docs/sdks/mysql/README.md#create)
* [deploy](docs/sdks/mysql/README.md#deploy)
* [move](docs/sdks/mysql/README.md#move)
* [get](docs/sdks/mysql/README.md#get)
* [rebuild](docs/sdks/mysql/README.md#rebuild)
* [reload](docs/sdks/mysql/README.md#reload)
* [remove](docs/sdks/mysql/README.md#remove)
* [saveEnvironment](docs/sdks/mysql/README.md#saveenvironment)
* [saveExternalPort](docs/sdks/mysql/README.md#saveexternalport)
* [start](docs/sdks/mysql/README.md#start)
* [stop](docs/sdks/mysql/README.md#stop)
* [update](docs/sdks/mysql/README.md#update)

### [Notification](docs/sdks/notification/README.md)

* [createDiscord](docs/sdks/notification/README.md#creatediscord)
* [createEmail](docs/sdks/notification/README.md#createemail)
* [createGotify](docs/sdks/notification/README.md#creategotify)
* [createNtfy](docs/sdks/notification/README.md#createntfy)
* [createSlack](docs/sdks/notification/README.md#createslack)
* [createTelegram](docs/sdks/notification/README.md#createtelegram)
* [getEmailProviders](docs/sdks/notification/README.md#getemailproviders)
* [get](docs/sdks/notification/README.md#get)
* [receiveNotification](docs/sdks/notification/README.md#receivenotification)
* [remove](docs/sdks/notification/README.md#remove)
* [testDiscordConnection](docs/sdks/notification/README.md#testdiscordconnection)
* [testEmailConnection](docs/sdks/notification/README.md#testemailconnection)
* [testGotifyConnection](docs/sdks/notification/README.md#testgotifyconnection)
* [testNtfyConnection](docs/sdks/notification/README.md#testntfyconnection)
* [testSlackConnection](docs/sdks/notification/README.md#testslackconnection)
* [testTelegramConnection](docs/sdks/notification/README.md#testtelegramconnection)
* [updateDiscord](docs/sdks/notification/README.md#updatediscord)
* [updateEmail](docs/sdks/notification/README.md#updateemail)
* [updateGotify](docs/sdks/notification/README.md#updategotify)
* [updateNtfy](docs/sdks/notification/README.md#updatentfy)
* [updateSlack](docs/sdks/notification/README.md#updateslack)
* [updateTelegram](docs/sdks/notification/README.md#updatetelegram)

### [Notifications](docs/sdks/notifications/README.md)

* [getAll](docs/sdks/notifications/README.md#getall)

### [Organization](docs/sdks/organization/README.md)

* [getAll](docs/sdks/organization/README.md#getall)
* [allInvitations](docs/sdks/organization/README.md#allinvitations)
* [create](docs/sdks/organization/README.md#create)
* [delete](docs/sdks/organization/README.md#delete)
* [get](docs/sdks/organization/README.md#get)
* [removeInvitation](docs/sdks/organization/README.md#removeinvitation)
* [update](docs/sdks/organization/README.md#update)

### [Port](docs/sdks/port/README.md)

* [create](docs/sdks/port/README.md#create)
* [delete](docs/sdks/port/README.md#delete)
* [get](docs/sdks/port/README.md#get)
* [update](docs/sdks/port/README.md#update)

### [Postgres](docs/sdks/postgres/README.md)

* [changeStatus](docs/sdks/postgres/README.md#changestatus)
* [create](docs/sdks/postgres/README.md#create)
* [deploy](docs/sdks/postgres/README.md#deploy)
* [move](docs/sdks/postgres/README.md#move)
* [get](docs/sdks/postgres/README.md#get)
* [rebuild](docs/sdks/postgres/README.md#rebuild)
* [reload](docs/sdks/postgres/README.md#reload)
* [remove](docs/sdks/postgres/README.md#remove)
* [saveEnvironment](docs/sdks/postgres/README.md#saveenvironment)
* [saveExternalPort](docs/sdks/postgres/README.md#saveexternalport)
* [start](docs/sdks/postgres/README.md#start)
* [stop](docs/sdks/postgres/README.md#stop)
* [update](docs/sdks/postgres/README.md#update)

### [PreviewDeployment](docs/sdks/previewdeployment/README.md)

* [getAll](docs/sdks/previewdeployment/README.md#getall)
* [delete](docs/sdks/previewdeployment/README.md#delete)
* [get](docs/sdks/previewdeployment/README.md#get)

### [Project](docs/sdks/project/README.md)

* [getAll](docs/sdks/project/README.md#getall)
* [create](docs/sdks/project/README.md#create)
* [duplicate](docs/sdks/project/README.md#duplicate)
* [get](docs/sdks/project/README.md#get)
* [update](docs/sdks/project/README.md#update)

### [Projects](docs/sdks/projects/README.md)

* [remove](docs/sdks/projects/README.md#remove)

### [Redirects](docs/sdks/redirects/README.md)

* [create](docs/sdks/redirects/README.md#create)
* [delete](docs/sdks/redirects/README.md#delete)
* [get](docs/sdks/redirects/README.md#get)
* [update](docs/sdks/redirects/README.md#update)

### [Redis](docs/sdks/redis/README.md)

* [changeStatus](docs/sdks/redis/README.md#changestatus)
* [create](docs/sdks/redis/README.md#create)
* [deploy](docs/sdks/redis/README.md#deploy)
* [move](docs/sdks/redis/README.md#move)
* [getOne](docs/sdks/redis/README.md#getone)
* [rebuild](docs/sdks/redis/README.md#rebuild)
* [reload](docs/sdks/redis/README.md#reload)
* [remove](docs/sdks/redis/README.md#remove)
* [saveEnvironment](docs/sdks/redis/README.md#saveenvironment)
* [saveExternalPort](docs/sdks/redis/README.md#saveexternalport)
* [start](docs/sdks/redis/README.md#start)
* [stop](docs/sdks/redis/README.md#stop)
* [update](docs/sdks/redis/README.md#update)

### [Registry](docs/sdks/registry/README.md)

* [getAll](docs/sdks/registry/README.md#getall)
* [create](docs/sdks/registry/README.md#create)
* [one](docs/sdks/registry/README.md#one)
* [remove](docs/sdks/registry/README.md#remove)
* [testRegistry](docs/sdks/registry/README.md#testregistry)
* [update](docs/sdks/registry/README.md#update)

### [Rollback](docs/sdks/rollback/README.md)

* [delete](docs/sdks/rollback/README.md#delete)
* [execute](docs/sdks/rollback/README.md#execute)

### [Schedule](docs/sdks/schedule/README.md)

* [create](docs/sdks/schedule/README.md#create)
* [delete](docs/sdks/schedule/README.md#delete)
* [list](docs/sdks/schedule/README.md#list)
* [get](docs/sdks/schedule/README.md#get)
* [runManually](docs/sdks/schedule/README.md#runmanually)
* [update](docs/sdks/schedule/README.md#update)

### [Security](docs/sdks/security/README.md)

* [create](docs/sdks/security/README.md#create)
* [delete](docs/sdks/security/README.md#delete)
* [get](docs/sdks/security/README.md#get)
* [update](docs/sdks/security/README.md#update)

### [Server](docs/sdks/server/README.md)

* [getAll](docs/sdks/server/README.md#getall)
* [count](docs/sdks/server/README.md#count)
* [create](docs/sdks/server/README.md#create)
* [getDefaultCommand](docs/sdks/server/README.md#getdefaultcommand)
* [getServerMetrics](docs/sdks/server/README.md#getservermetrics)
* [get](docs/sdks/server/README.md#get)
* [publicIp](docs/sdks/server/README.md#publicip)
* [remove](docs/sdks/server/README.md#remove)
* [getSecurity](docs/sdks/server/README.md#getsecurity)
* [setup](docs/sdks/server/README.md#setup)
* [setupMonitoring](docs/sdks/server/README.md#setupmonitoring)
* [update](docs/sdks/server/README.md#update)
* [validate](docs/sdks/server/README.md#validate)

### [Servers](docs/sdks/servers/README.md)

* [getWithSshKey](docs/sdks/servers/README.md#getwithsshkey)

### [Settings](docs/sdks/settings/README.md)

* [assignDomainServer](docs/sdks/settings/README.md#assigndomainserver)
* [checkGpuStatus](docs/sdks/settings/README.md#checkgpustatus)
* [cleanAll](docs/sdks/settings/README.md#cleanall)
* [cleanDockerBuilder](docs/sdks/settings/README.md#cleandockerbuilder)
* [cleanDockerPrune](docs/sdks/settings/README.md#cleandockerprune)
* [cleanMonitoring](docs/sdks/settings/README.md#cleanmonitoring)
* [cleanRedis](docs/sdks/settings/README.md#cleanredis)
* [cleanSshPrivateKey](docs/sdks/settings/README.md#cleansshprivatekey)
* [cleanStoppedContainers](docs/sdks/settings/README.md#cleanstoppedcontainers)
* [cleanUnusedImages](docs/sdks/settings/README.md#cleanunusedimages)
* [cleanUnusedVolumes](docs/sdks/settings/README.md#cleanunusedvolumes)
* [getDokployCloudIps](docs/sdks/settings/README.md#getdokploycloudips)
* [getDokployVersion](docs/sdks/settings/README.md#getdokployversion)
* [getIp](docs/sdks/settings/README.md#getip)
* [getLogCleanupStatus](docs/sdks/settings/README.md#getlogcleanupstatus)
* [getOpenApiDocument](docs/sdks/settings/README.md#getopenapidocument)
* [getReleaseTag](docs/sdks/settings/README.md#getreleasetag)
* [getTraefikPorts](docs/sdks/settings/README.md#gettraefikports)
* [getUpdateData](docs/sdks/settings/README.md#getupdatedata)
* [haveActivateRequests](docs/sdks/settings/README.md#haveactivaterequests)
* [haveTraefikDashboardPortEnabled](docs/sdks/settings/README.md#havetraefikdashboardportenabled)
* [get](docs/sdks/settings/README.md#get)
* [isCloud](docs/sdks/settings/README.md#iscloud)
* [isUserSubscribed](docs/sdks/settings/README.md#isusersubscribed)
* [readDirectories](docs/sdks/settings/README.md#readdirectories)
* [readMiddlewareTraefikConfig](docs/sdks/settings/README.md#readmiddlewaretraefikconfig)
* [readTraefikConfig](docs/sdks/settings/README.md#readtraefikconfig)
* [readTraefikEnv](docs/sdks/settings/README.md#readtraefikenv)
* [readTraefikFile](docs/sdks/settings/README.md#readtraefikfile)
* [readWebserverTraefikConfig](docs/sdks/settings/README.md#readwebservertraefikconfig)
* [reloadRedis](docs/sdks/settings/README.md#reloadredis)
* [reloadServer](docs/sdks/settings/README.md#reloadserver)
* [reloadTraefik](docs/sdks/settings/README.md#reloadtraefik)
* [saveSshPrivateKey](docs/sdks/settings/README.md#savesshprivatekey)
* [setupGpu](docs/sdks/settings/README.md#setupgpu)
* [toggleDashboard](docs/sdks/settings/README.md#toggledashboard)
* [toggleRequests](docs/sdks/settings/README.md#togglerequests)
* [updateDockerCleanup](docs/sdks/settings/README.md#updatedockercleanup)
* [updateLogCleanup](docs/sdks/settings/README.md#updatelogcleanup)
* [updateMiddlewareTraefikConfig](docs/sdks/settings/README.md#updatemiddlewaretraefikconfig)
* [updateServer](docs/sdks/settings/README.md#updateserver)
* [updateTraefikConfig](docs/sdks/settings/README.md#updatetraefikconfig)
* [updateTraefikFile](docs/sdks/settings/README.md#updatetraefikfile)
* [updateTraefikPorts](docs/sdks/settings/README.md#updatetraefikports)
* [updateWebServerTraefikConfig](docs/sdks/settings/README.md#updatewebservertraefikconfig)
* [writeTraefikEnv](docs/sdks/settings/README.md#writetraefikenv)

### [SshKeys](docs/sdks/sshkeys/README.md)

* [generate](docs/sdks/sshkeys/README.md#generate)

### [SshKey](docs/sdks/sshkey/README.md)

* [all](docs/sdks/sshkey/README.md#all)
* [create](docs/sdks/sshkey/README.md#create)
* [get](docs/sdks/sshkey/README.md#get)
* [remove](docs/sdks/sshkey/README.md#remove)
* [update](docs/sdks/sshkey/README.md#update)

### [Stripe](docs/sdks/stripe/README.md)

* [canCreateMoreServers](docs/sdks/stripe/README.md#cancreatemoreservers)
* [createCheckoutSession](docs/sdks/stripe/README.md#createcheckoutsession)
* [createCustomerPortalSession](docs/sdks/stripe/README.md#createcustomerportalsession)
* [getProducts](docs/sdks/stripe/README.md#getproducts)

### [Swarm](docs/sdks/swarm/README.md)

* [getNodeApps](docs/sdks/swarm/README.md#getnodeapps)
* [getNodeInfo](docs/sdks/swarm/README.md#getnodeinfo)
* [getNodes](docs/sdks/swarm/README.md#getnodes)

### [User](docs/sdks/user/README.md)

* [getAll](docs/sdks/user/README.md#getall)
* [assignPermissions](docs/sdks/user/README.md#assignpermissions)
* [checkUserOrganizations](docs/sdks/user/README.md#checkuserorganizations)
* [createApiKey](docs/sdks/user/README.md#createapikey)
* [deleteApiKey](docs/sdks/user/README.md#deleteapikey)
* [generateToken](docs/sdks/user/README.md#generatetoken)
* [get](docs/sdks/user/README.md#get)
* [getBackups](docs/sdks/user/README.md#getbackups)
* [getContainerMetrics](docs/sdks/user/README.md#getcontainermetrics)
* [getInvitations](docs/sdks/user/README.md#getinvitations)
* [getMetricsToken](docs/sdks/user/README.md#getmetricstoken)
* [getServerMetrics](docs/sdks/user/README.md#getservermetrics)
* [getUserByToken](docs/sdks/user/README.md#getuserbytoken)
* [haveRootAccess](docs/sdks/user/README.md#haverootaccess)
* [getOne](docs/sdks/user/README.md#getone)
* [sendInvitation](docs/sdks/user/README.md#sendinvitation)
* [update](docs/sdks/user/README.md#update)

### [Users](docs/sdks/users/README.md)

* [remove](docs/sdks/users/README.md#remove)

### [VolumeBackups](docs/sdks/volumebackups/README.md)

* [create](docs/sdks/volumebackups/README.md#create)
* [delete](docs/sdks/volumebackups/README.md#delete)
* [list](docs/sdks/volumebackups/README.md#list)
* [runManually](docs/sdks/volumebackups/README.md#runmanually)
* [update](docs/sdks/volumebackups/README.md#update)
* [get](docs/sdks/volumebackups/README.md#get)

</details>
<!-- End Available Resources and Operations [operations] -->

<!-- Start Standalone functions [standalone-funcs] -->
## Standalone functions

All the methods listed above are available as standalone functions. These
functions are ideal for use in applications running in the browser, serverless
runtimes or other environments where application bundle size is a primary
concern. When using a bundler to build your application, all unused
functionality will be either excluded from the final bundle or tree-shaken away.

To read more about standalone functions, check [FUNCTIONS.md](./FUNCTIONS.md).

<details>

<summary>Available standalone functions</summary>

- [`adminSetupMonitoring`](docs/sdks/admin/README.md#setupmonitoring)
- [`aiCreate`](docs/sdks/ai/README.md#create)
- [`aiDelete`](docs/sdks/ai/README.md#delete)
- [`aiDeploy`](docs/sdks/ai/README.md#deploy)
- [`aiGet`](docs/sdks/ai/README.md#get)
- [`aiGetAll`](docs/sdks/ai/README.md#getall)
- [`aiGetModels`](docs/sdks/ai/README.md#getmodels)
- [`aiGetOne`](docs/sdks/ai/README.md#getone)
- [`aiSuggest`](docs/sdks/ai/README.md#suggest)
- [`aiUpdate`](docs/sdks/ai/README.md#update)
- [`applicationCancelDeployment`](docs/sdks/application/README.md#canceldeployment)
- [`applicationCleanQueues`](docs/sdks/application/README.md#cleanqueues)
- [`applicationCreate`](docs/sdks/application/README.md#create)
- [`applicationDelete`](docs/sdks/application/README.md#delete)
- [`applicationDeploy`](docs/sdks/application/README.md#deploy)
- [`applicationDisconnectGitProvider`](docs/sdks/application/README.md#disconnectgitprovider)
- [`applicationGet`](docs/sdks/application/README.md#get)
- [`applicationMarkRunning`](docs/sdks/application/README.md#markrunning)
- [`applicationReadAppMonitoring`](docs/sdks/application/README.md#readappmonitoring)
- [`applicationRedeploy`](docs/sdks/application/README.md#redeploy)
- [`applicationReload`](docs/sdks/application/README.md#reload)
- [`applicationSaveBitbucketProvider`](docs/sdks/application/README.md#savebitbucketprovider)
- [`applicationSaveBuildType`](docs/sdks/application/README.md#savebuildtype)
- [`applicationSaveDockerProvider`](docs/sdks/application/README.md#savedockerprovider)
- [`applicationSaveEnvironment`](docs/sdks/application/README.md#saveenvironment)
- [`applicationSaveGiteaProvider`](docs/sdks/application/README.md#savegiteaprovider)
- [`applicationSaveGitlabProvider`](docs/sdks/application/README.md#savegitlabprovider)
- [`applicationSaveGitProdiver`](docs/sdks/application/README.md#savegitprodiver)
- [`applicationsMove`](docs/sdks/applications/README.md#move)
- [`applicationsReadTraefikConfig`](docs/sdks/applications/README.md#readtraefikconfig)
- [`applicationsRefreshToken`](docs/sdks/applications/README.md#refreshtoken)
- [`applicationsSaveGithubProvider`](docs/sdks/applications/README.md#savegithubprovider)
- [`applicationsStart`](docs/sdks/applications/README.md#start)
- [`applicationStop`](docs/sdks/application/README.md#stop)
- [`applicationUpdate`](docs/sdks/application/README.md#update)
- [`applicationUpdateTraefikConfig`](docs/sdks/application/README.md#updatetraefikconfig)
- [`backupCreate`](docs/sdks/backup/README.md#create)
- [`backupListFiles`](docs/sdks/backup/README.md#listfiles)
- [`backupManualBackupCompose`](docs/sdks/backup/README.md#manualbackupcompose)
- [`backupManualBackupMariadb`](docs/sdks/backup/README.md#manualbackupmariadb)
- [`backupManualBackupMongo`](docs/sdks/backup/README.md#manualbackupmongo)
- [`backupManualBackupMySql`](docs/sdks/backup/README.md#manualbackupmysql)
- [`backupManualBackupPostgres`](docs/sdks/backup/README.md#manualbackuppostgres)
- [`backupManualBackupWebServer`](docs/sdks/backup/README.md#manualbackupwebserver)
- [`backupOne`](docs/sdks/backup/README.md#one)
- [`backupRemove`](docs/sdks/backup/README.md#remove)
- [`backupUpdate`](docs/sdks/backup/README.md#update)
- [`bitbucketCreate`](docs/sdks/bitbucket/README.md#create)
- [`bitbucketGetBranches`](docs/sdks/bitbucket/README.md#getbranches)
- [`bitbucketGetOne`](docs/sdks/bitbucket/README.md#getone)
- [`bitbucketGetProviders`](docs/sdks/bitbucketget/README.md#providers)
- [`bitbucketGetRepositories`](docs/sdks/bitbucket/README.md#getrepositories)
- [`bitbucketTestConnection`](docs/sdks/bitbucket/README.md#testconnection)
- [`bitbucketUpdate`](docs/sdks/bitbucket/README.md#update)
- [`certificatesCreate`](docs/sdks/certificates/README.md#create)
- [`certificatesGet`](docs/sdks/certificates/README.md#get)
- [`certificatesGetAll`](docs/sdks/certificates/README.md#getall)
- [`certificatesRemove`](docs/sdks/certificates/README.md#remove)
- [`clusterAddManager`](docs/sdks/cluster/README.md#addmanager)
- [`clusterAddWorker`](docs/sdks/cluster/README.md#addworker)
- [`clusterGetNodes`](docs/sdks/cluster/README.md#getnodes)
- [`clusterRemoveWorker`](docs/sdks/cluster/README.md#removeworker)
- [`composeCancelDeployment`](docs/sdks/compose/README.md#canceldeployment)
- [`composeCleanQueues`](docs/sdks/compose/README.md#cleanqueues)
- [`composeCreate`](docs/sdks/compose/README.md#create)
- [`composeDelete`](docs/sdks/compose/README.md#delete)
- [`composeDeploy`](docs/sdks/compose/README.md#deploy)
- [`composeDeployTemplate`](docs/sdks/compose/README.md#deploytemplate)
- [`composeDisconnectGitprovider`](docs/sdks/compose/README.md#disconnectgitprovider)
- [`composeFetchSourceType`](docs/sdks/compose/README.md#fetchsourcetype)
- [`composeGetConvertedCompose`](docs/sdks/compose/README.md#getconvertedcompose)
- [`composeGetDefaultCommand`](docs/sdks/compose/README.md#getdefaultcommand)
- [`composeGetTags`](docs/sdks/compose/README.md#gettags)
- [`composeGetTemplates`](docs/sdks/compose/README.md#gettemplates)
- [`composeImport`](docs/sdks/compose/README.md#import)
- [`composeIsolatedDeployment`](docs/sdks/compose/README.md#isolateddeployment)
- [`composeLoadMountsByService`](docs/sdks/compose/README.md#loadmountsbyservice)
- [`composeMove`](docs/sdks/compose/README.md#move)
- [`composeOne`](docs/sdks/compose/README.md#one)
- [`composeProcessTemplate`](docs/sdks/compose/README.md#processtemplate)
- [`composeRandomizeCompose`](docs/sdks/compose/README.md#randomizecompose)
- [`composeRedeploy`](docs/sdks/compose/README.md#redeploy)
- [`composeRefreshToken`](docs/sdks/compose/README.md#refreshtoken)
- [`composeStart`](docs/sdks/compose/README.md#start)
- [`composeStop`](docs/sdks/compose/README.md#stop)
- [`composeUpdate`](docs/sdks/compose/README.md#update)
- [`deploymentAll`](docs/sdks/deployment/README.md#all)
- [`deploymentAllByServer`](docs/sdks/deployment/README.md#allbyserver)
- [`deploymentGetAllByCompose`](docs/sdks/deployment/README.md#getallbycompose)
- [`deploymentGetAllByType`](docs/sdks/deployment/README.md#getallbytype)
- [`deploymentKillProcess`](docs/sdks/deployment/README.md#killprocess)
- [`destinationCreate`](docs/sdks/destination/README.md#create)
- [`destinationGet`](docs/sdks/destination/README.md#get)
- [`destinationGetAll`](docs/sdks/destination/README.md#getall)
- [`destinationRemove`](docs/sdks/destination/README.md#remove)
- [`destinationTestConnection`](docs/sdks/destination/README.md#testconnection)
- [`destinationUpdate`](docs/sdks/destination/README.md#update)
- [`dockerGetConfig`](docs/sdks/docker/README.md#getconfig)
- [`dockerGetContainers`](docs/sdks/docker/README.md#getcontainers)
- [`dockerGetContainersByAppLabel`](docs/sdks/docker/README.md#getcontainersbyapplabel)
- [`dockerGetContainersByAppNameMatch`](docs/sdks/docker/README.md#getcontainersbyappnamematch)
- [`dockerGetServiceContainersByAppName`](docs/sdks/dockerget/README.md#servicecontainersbyappname)
- [`dockerGetStackContainersByAppName`](docs/sdks/dockerget/README.md#stackcontainersbyappname)
- [`dockerRestartContainer`](docs/sdks/docker/README.md#restartcontainer)
- [`domainByApplicationId`](docs/sdks/domain/README.md#byapplicationid)
- [`domainCanGenerateTraefikDomains`](docs/sdks/domain/README.md#cangeneratetraefikdomains)
- [`domainCreate`](docs/sdks/domain/README.md#create)
- [`domainDelete`](docs/sdks/domain/README.md#delete)
- [`domainGenerateDomain`](docs/sdks/domain/README.md#generatedomain)
- [`domainGetByComposeId`](docs/sdks/domain/README.md#getbycomposeid)
- [`domainsGet`](docs/sdks/domains/README.md#get)
- [`domainUpdate`](docs/sdks/domain/README.md#update)
- [`domainValidateDomain`](docs/sdks/domain/README.md#validatedomain)
- [`environmentByProjectId`](docs/sdks/environment/README.md#byprojectid)
- [`environmentCreate`](docs/sdks/environment/README.md#create)
- [`environmentDuplicate`](docs/sdks/environment/README.md#duplicate)
- [`environmentGet`](docs/sdks/environment/README.md#get)
- [`environmentRemove`](docs/sdks/environment/README.md#remove)
- [`environmentUpdate`](docs/sdks/environment/README.md#update)
- [`giteaCreate`](docs/sdks/gitea/README.md#create)
- [`giteaGet`](docs/sdks/gitea/README.md#get)
- [`giteaGetBranches`](docs/sdks/gitea/README.md#getbranches)
- [`giteaGetProviders`](docs/sdks/gitea/README.md#getproviders)
- [`giteaGetRepositories`](docs/sdks/gitea/README.md#getrepositories)
- [`giteaGetUrl`](docs/sdks/gitea/README.md#geturl)
- [`giteaTestConnection`](docs/sdks/gitea/README.md#testconnection)
- [`giteaUpdate`](docs/sdks/gitea/README.md#update)
- [`githubGetBranches`](docs/sdks/githubget/README.md#branches)
- [`githubGetGithubRepositories`](docs/sdks/github/README.md#getgithubrepositories)
- [`githubGetProviders`](docs/sdks/github/README.md#getproviders)
- [`githubOne`](docs/sdks/github/README.md#one)
- [`githubTestConnection`](docs/sdks/github/README.md#testconnection)
- [`githubUpdate`](docs/sdks/github/README.md#update)
- [`gitlabCreate`](docs/sdks/gitlab/README.md#create)
- [`gitlabGetBranches`](docs/sdks/gitlab/README.md#getbranches)
- [`gitlabGetGitlabRepositories`](docs/sdks/gitlab/README.md#getgitlabrepositories)
- [`gitlabGetProviders`](docs/sdks/gitlab/README.md#getproviders)
- [`gitlabOne`](docs/sdks/gitlab/README.md#one)
- [`gitlabTestConnection`](docs/sdks/gitlab/README.md#testconnection)
- [`gitlabUpdate`](docs/sdks/gitlab/README.md#update)
- [`gitproviderRemove`](docs/sdks/gitprovider/README.md#remove)
- [`gitProvidersGetAll`](docs/sdks/gitproviders/README.md#getall)
- [`mariadbChangeStatus`](docs/sdks/mariadb/README.md#changestatus)
- [`mariadbCreate`](docs/sdks/mariadb/README.md#create)
- [`mariadbDeploy`](docs/sdks/mariadb/README.md#deploy)
- [`mariadbGet`](docs/sdks/mariadb/README.md#get)
- [`mariadbMove`](docs/sdks/mariadb/README.md#move)
- [`mariadbRebuild`](docs/sdks/mariadb/README.md#rebuild)
- [`mariadbReload`](docs/sdks/mariadb/README.md#reload)
- [`mariadbRemove`](docs/sdks/mariadb/README.md#remove)
- [`mariadbSaveEnvironment`](docs/sdks/mariadb/README.md#saveenvironment)
- [`mariadbSaveExternalPort`](docs/sdks/mariadb/README.md#saveexternalport)
- [`mariadbStart`](docs/sdks/mariadb/README.md#start)
- [`mariadbStop`](docs/sdks/mariadb/README.md#stop)
- [`mariadbUpdate`](docs/sdks/mariadb/README.md#update)
- [`mongoChangeStatus`](docs/sdks/mongo/README.md#changestatus)
- [`mongoCreate`](docs/sdks/mongo/README.md#create)
- [`mongoDeploy`](docs/sdks/mongo/README.md#deploy)
- [`mongoGetOne`](docs/sdks/mongo/README.md#getone)
- [`mongoMove`](docs/sdks/mongo/README.md#move)
- [`mongoRebuild`](docs/sdks/mongo/README.md#rebuild)
- [`mongoReload`](docs/sdks/mongo/README.md#reload)
- [`mongoRemove`](docs/sdks/mongo/README.md#remove)
- [`mongoSaveEnvironment`](docs/sdks/mongo/README.md#saveenvironment)
- [`mongoSaveExternalPort`](docs/sdks/mongo/README.md#saveexternalport)
- [`mongoStart`](docs/sdks/mongo/README.md#start)
- [`mongoStop`](docs/sdks/mongo/README.md#stop)
- [`mongoUpdate`](docs/sdks/mongo/README.md#update)
- [`mountsAllNamedByApplicationId`](docs/sdks/mounts/README.md#allnamedbyapplicationid)
- [`mountsCreate`](docs/sdks/mounts/README.md#create)
- [`mountsGet`](docs/sdks/mounts/README.md#get)
- [`mountsRemove`](docs/sdks/mounts/README.md#remove)
- [`mountsUpdate`](docs/sdks/mounts/README.md#update)
- [`mysqlChangeStatus`](docs/sdks/mysql/README.md#changestatus)
- [`mysqlCreate`](docs/sdks/mysql/README.md#create)
- [`mysqlDeploy`](docs/sdks/mysql/README.md#deploy)
- [`mysqlGet`](docs/sdks/mysql/README.md#get)
- [`mysqlMove`](docs/sdks/mysql/README.md#move)
- [`mysqlRebuild`](docs/sdks/mysql/README.md#rebuild)
- [`mysqlReload`](docs/sdks/mysql/README.md#reload)
- [`mysqlRemove`](docs/sdks/mysql/README.md#remove)
- [`mysqlSaveEnvironment`](docs/sdks/mysql/README.md#saveenvironment)
- [`mysqlSaveExternalPort`](docs/sdks/mysql/README.md#saveexternalport)
- [`mysqlStart`](docs/sdks/mysql/README.md#start)
- [`mysqlStop`](docs/sdks/mysql/README.md#stop)
- [`mysqlUpdate`](docs/sdks/mysql/README.md#update)
- [`notificationCreateDiscord`](docs/sdks/notification/README.md#creatediscord)
- [`notificationCreateEmail`](docs/sdks/notification/README.md#createemail)
- [`notificationCreateGotify`](docs/sdks/notification/README.md#creategotify)
- [`notificationCreateNtfy`](docs/sdks/notification/README.md#createntfy)
- [`notificationCreateSlack`](docs/sdks/notification/README.md#createslack)
- [`notificationCreateTelegram`](docs/sdks/notification/README.md#createtelegram)
- [`notificationGet`](docs/sdks/notification/README.md#get)
- [`notificationGetEmailProviders`](docs/sdks/notification/README.md#getemailproviders)
- [`notificationReceiveNotification`](docs/sdks/notification/README.md#receivenotification)
- [`notificationRemove`](docs/sdks/notification/README.md#remove)
- [`notificationsGetAll`](docs/sdks/notifications/README.md#getall)
- [`notificationTestDiscordConnection`](docs/sdks/notification/README.md#testdiscordconnection)
- [`notificationTestEmailConnection`](docs/sdks/notification/README.md#testemailconnection)
- [`notificationTestGotifyConnection`](docs/sdks/notification/README.md#testgotifyconnection)
- [`notificationTestNtfyConnection`](docs/sdks/notification/README.md#testntfyconnection)
- [`notificationTestSlackConnection`](docs/sdks/notification/README.md#testslackconnection)
- [`notificationTestTelegramConnection`](docs/sdks/notification/README.md#testtelegramconnection)
- [`notificationUpdateDiscord`](docs/sdks/notification/README.md#updatediscord)
- [`notificationUpdateEmail`](docs/sdks/notification/README.md#updateemail)
- [`notificationUpdateGotify`](docs/sdks/notification/README.md#updategotify)
- [`notificationUpdateNtfy`](docs/sdks/notification/README.md#updatentfy)
- [`notificationUpdateSlack`](docs/sdks/notification/README.md#updateslack)
- [`notificationUpdateTelegram`](docs/sdks/notification/README.md#updatetelegram)
- [`organizationAllInvitations`](docs/sdks/organization/README.md#allinvitations)
- [`organizationCreate`](docs/sdks/organization/README.md#create)
- [`organizationDelete`](docs/sdks/organization/README.md#delete)
- [`organizationGet`](docs/sdks/organization/README.md#get)
- [`organizationGetAll`](docs/sdks/organization/README.md#getall)
- [`organizationRemoveInvitation`](docs/sdks/organization/README.md#removeinvitation)
- [`organizationUpdate`](docs/sdks/organization/README.md#update)
- [`portCreate`](docs/sdks/port/README.md#create)
- [`portDelete`](docs/sdks/port/README.md#delete)
- [`portGet`](docs/sdks/port/README.md#get)
- [`portUpdate`](docs/sdks/port/README.md#update)
- [`postgresChangeStatus`](docs/sdks/postgres/README.md#changestatus)
- [`postgresCreate`](docs/sdks/postgres/README.md#create)
- [`postgresDeploy`](docs/sdks/postgres/README.md#deploy)
- [`postgresGet`](docs/sdks/postgres/README.md#get)
- [`postgresMove`](docs/sdks/postgres/README.md#move)
- [`postgresRebuild`](docs/sdks/postgres/README.md#rebuild)
- [`postgresReload`](docs/sdks/postgres/README.md#reload)
- [`postgresRemove`](docs/sdks/postgres/README.md#remove)
- [`postgresSaveEnvironment`](docs/sdks/postgres/README.md#saveenvironment)
- [`postgresSaveExternalPort`](docs/sdks/postgres/README.md#saveexternalport)
- [`postgresStart`](docs/sdks/postgres/README.md#start)
- [`postgresStop`](docs/sdks/postgres/README.md#stop)
- [`postgresUpdate`](docs/sdks/postgres/README.md#update)
- [`previewDeploymentDelete`](docs/sdks/previewdeployment/README.md#delete)
- [`previewDeploymentGet`](docs/sdks/previewdeployment/README.md#get)
- [`previewDeploymentGetAll`](docs/sdks/previewdeployment/README.md#getall)
- [`projectCreate`](docs/sdks/project/README.md#create)
- [`projectDuplicate`](docs/sdks/project/README.md#duplicate)
- [`projectGet`](docs/sdks/project/README.md#get)
- [`projectGetAll`](docs/sdks/project/README.md#getall)
- [`projectsRemove`](docs/sdks/projects/README.md#remove)
- [`projectUpdate`](docs/sdks/project/README.md#update)
- [`redirectsCreate`](docs/sdks/redirects/README.md#create)
- [`redirectsDelete`](docs/sdks/redirects/README.md#delete)
- [`redirectsGet`](docs/sdks/redirects/README.md#get)
- [`redirectsUpdate`](docs/sdks/redirects/README.md#update)
- [`redisChangeStatus`](docs/sdks/redis/README.md#changestatus)
- [`redisCreate`](docs/sdks/redis/README.md#create)
- [`redisDeploy`](docs/sdks/redis/README.md#deploy)
- [`redisGetOne`](docs/sdks/redis/README.md#getone)
- [`redisMove`](docs/sdks/redis/README.md#move)
- [`redisRebuild`](docs/sdks/redis/README.md#rebuild)
- [`redisReload`](docs/sdks/redis/README.md#reload)
- [`redisRemove`](docs/sdks/redis/README.md#remove)
- [`redisSaveEnvironment`](docs/sdks/redis/README.md#saveenvironment)
- [`redisSaveExternalPort`](docs/sdks/redis/README.md#saveexternalport)
- [`redisStart`](docs/sdks/redis/README.md#start)
- [`redisStop`](docs/sdks/redis/README.md#stop)
- [`redisUpdate`](docs/sdks/redis/README.md#update)
- [`registryCreate`](docs/sdks/registry/README.md#create)
- [`registryGetAll`](docs/sdks/registry/README.md#getall)
- [`registryOne`](docs/sdks/registry/README.md#one)
- [`registryRemove`](docs/sdks/registry/README.md#remove)
- [`registryTestRegistry`](docs/sdks/registry/README.md#testregistry)
- [`registryUpdate`](docs/sdks/registry/README.md#update)
- [`rollbackDelete`](docs/sdks/rollback/README.md#delete)
- [`rollbackExecute`](docs/sdks/rollback/README.md#execute)
- [`scheduleCreate`](docs/sdks/schedule/README.md#create)
- [`scheduleDelete`](docs/sdks/schedule/README.md#delete)
- [`scheduleGet`](docs/sdks/schedule/README.md#get)
- [`scheduleList`](docs/sdks/schedule/README.md#list)
- [`scheduleRunManually`](docs/sdks/schedule/README.md#runmanually)
- [`scheduleUpdate`](docs/sdks/schedule/README.md#update)
- [`securityCreate`](docs/sdks/security/README.md#create)
- [`securityDelete`](docs/sdks/security/README.md#delete)
- [`securityGet`](docs/sdks/security/README.md#get)
- [`securityUpdate`](docs/sdks/security/README.md#update)
- [`serverCount`](docs/sdks/server/README.md#count)
- [`serverCreate`](docs/sdks/server/README.md#create)
- [`serverGet`](docs/sdks/server/README.md#get)
- [`serverGetAll`](docs/sdks/server/README.md#getall)
- [`serverGetDefaultCommand`](docs/sdks/server/README.md#getdefaultcommand)
- [`serverGetSecurity`](docs/sdks/server/README.md#getsecurity)
- [`serverGetServerMetrics`](docs/sdks/server/README.md#getservermetrics)
- [`serverPublicIp`](docs/sdks/server/README.md#publicip)
- [`serverRemove`](docs/sdks/server/README.md#remove)
- [`serverSetup`](docs/sdks/server/README.md#setup)
- [`serverSetupMonitoring`](docs/sdks/server/README.md#setupmonitoring)
- [`serversGetWithSshKey`](docs/sdks/servers/README.md#getwithsshkey)
- [`serverUpdate`](docs/sdks/server/README.md#update)
- [`serverValidate`](docs/sdks/server/README.md#validate)
- [`settingsAssignDomainServer`](docs/sdks/settings/README.md#assigndomainserver)
- [`settingsCheckGpuStatus`](docs/sdks/settings/README.md#checkgpustatus)
- [`settingsCleanAll`](docs/sdks/settings/README.md#cleanall)
- [`settingsCleanDockerBuilder`](docs/sdks/settings/README.md#cleandockerbuilder)
- [`settingsCleanDockerPrune`](docs/sdks/settings/README.md#cleandockerprune)
- [`settingsCleanMonitoring`](docs/sdks/settings/README.md#cleanmonitoring)
- [`settingsCleanRedis`](docs/sdks/settings/README.md#cleanredis)
- [`settingsCleanSshPrivateKey`](docs/sdks/settings/README.md#cleansshprivatekey)
- [`settingsCleanStoppedContainers`](docs/sdks/settings/README.md#cleanstoppedcontainers)
- [`settingsCleanUnusedImages`](docs/sdks/settings/README.md#cleanunusedimages)
- [`settingsCleanUnusedVolumes`](docs/sdks/settings/README.md#cleanunusedvolumes)
- [`settingsGet`](docs/sdks/settings/README.md#get)
- [`settingsGetDokployCloudIps`](docs/sdks/settings/README.md#getdokploycloudips)
- [`settingsGetDokployVersion`](docs/sdks/settings/README.md#getdokployversion)
- [`settingsGetIp`](docs/sdks/settings/README.md#getip)
- [`settingsGetLogCleanupStatus`](docs/sdks/settings/README.md#getlogcleanupstatus)
- [`settingsGetOpenApiDocument`](docs/sdks/settings/README.md#getopenapidocument)
- [`settingsGetReleaseTag`](docs/sdks/settings/README.md#getreleasetag)
- [`settingsGetTraefikPorts`](docs/sdks/settings/README.md#gettraefikports)
- [`settingsGetUpdateData`](docs/sdks/settings/README.md#getupdatedata)
- [`settingsHaveActivateRequests`](docs/sdks/settings/README.md#haveactivaterequests)
- [`settingsHaveTraefikDashboardPortEnabled`](docs/sdks/settings/README.md#havetraefikdashboardportenabled)
- [`settingsIsCloud`](docs/sdks/settings/README.md#iscloud)
- [`settingsIsUserSubscribed`](docs/sdks/settings/README.md#isusersubscribed)
- [`settingsReadDirectories`](docs/sdks/settings/README.md#readdirectories)
- [`settingsReadMiddlewareTraefikConfig`](docs/sdks/settings/README.md#readmiddlewaretraefikconfig)
- [`settingsReadTraefikConfig`](docs/sdks/settings/README.md#readtraefikconfig)
- [`settingsReadTraefikEnv`](docs/sdks/settings/README.md#readtraefikenv)
- [`settingsReadTraefikFile`](docs/sdks/settings/README.md#readtraefikfile)
- [`settingsReadWebserverTraefikConfig`](docs/sdks/settings/README.md#readwebservertraefikconfig)
- [`settingsReloadRedis`](docs/sdks/settings/README.md#reloadredis)
- [`settingsReloadServer`](docs/sdks/settings/README.md#reloadserver)
- [`settingsReloadTraefik`](docs/sdks/settings/README.md#reloadtraefik)
- [`settingsSaveSshPrivateKey`](docs/sdks/settings/README.md#savesshprivatekey)
- [`settingsSetupGpu`](docs/sdks/settings/README.md#setupgpu)
- [`settingsToggleDashboard`](docs/sdks/settings/README.md#toggledashboard)
- [`settingsToggleRequests`](docs/sdks/settings/README.md#togglerequests)
- [`settingsUpdateDockerCleanup`](docs/sdks/settings/README.md#updatedockercleanup)
- [`settingsUpdateLogCleanup`](docs/sdks/settings/README.md#updatelogcleanup)
- [`settingsUpdateMiddlewareTraefikConfig`](docs/sdks/settings/README.md#updatemiddlewaretraefikconfig)
- [`settingsUpdateServer`](docs/sdks/settings/README.md#updateserver)
- [`settingsUpdateTraefikConfig`](docs/sdks/settings/README.md#updatetraefikconfig)
- [`settingsUpdateTraefikFile`](docs/sdks/settings/README.md#updatetraefikfile)
- [`settingsUpdateTraefikPorts`](docs/sdks/settings/README.md#updatetraefikports)
- [`settingsUpdateWebServerTraefikConfig`](docs/sdks/settings/README.md#updatewebservertraefikconfig)
- [`settingsWriteTraefikEnv`](docs/sdks/settings/README.md#writetraefikenv)
- [`sshKeyAll`](docs/sdks/sshkey/README.md#all)
- [`sshKeyCreate`](docs/sdks/sshkey/README.md#create)
- [`sshKeyGet`](docs/sdks/sshkey/README.md#get)
- [`sshKeyRemove`](docs/sdks/sshkey/README.md#remove)
- [`sshKeysGenerate`](docs/sdks/sshkeys/README.md#generate)
- [`sshKeyUpdate`](docs/sdks/sshkey/README.md#update)
- [`stripeCanCreateMoreServers`](docs/sdks/stripe/README.md#cancreatemoreservers)
- [`stripeCreateCheckoutSession`](docs/sdks/stripe/README.md#createcheckoutsession)
- [`stripeCreateCustomerPortalSession`](docs/sdks/stripe/README.md#createcustomerportalsession)
- [`stripeGetProducts`](docs/sdks/stripe/README.md#getproducts)
- [`swarmGetNodeApps`](docs/sdks/swarm/README.md#getnodeapps)
- [`swarmGetNodeInfo`](docs/sdks/swarm/README.md#getnodeinfo)
- [`swarmGetNodes`](docs/sdks/swarm/README.md#getnodes)
- [`userAssignPermissions`](docs/sdks/user/README.md#assignpermissions)
- [`userCheckUserOrganizations`](docs/sdks/user/README.md#checkuserorganizations)
- [`userCreateApiKey`](docs/sdks/user/README.md#createapikey)
- [`userDeleteApiKey`](docs/sdks/user/README.md#deleteapikey)
- [`userGenerateToken`](docs/sdks/user/README.md#generatetoken)
- [`userGet`](docs/sdks/user/README.md#get)
- [`userGetAll`](docs/sdks/user/README.md#getall)
- [`userGetBackups`](docs/sdks/user/README.md#getbackups)
- [`userGetContainerMetrics`](docs/sdks/user/README.md#getcontainermetrics)
- [`userGetInvitations`](docs/sdks/user/README.md#getinvitations)
- [`userGetMetricsToken`](docs/sdks/user/README.md#getmetricstoken)
- [`userGetOne`](docs/sdks/user/README.md#getone)
- [`userGetServerMetrics`](docs/sdks/user/README.md#getservermetrics)
- [`userGetUserByToken`](docs/sdks/user/README.md#getuserbytoken)
- [`userHaveRootAccess`](docs/sdks/user/README.md#haverootaccess)
- [`userSendInvitation`](docs/sdks/user/README.md#sendinvitation)
- [`usersRemove`](docs/sdks/users/README.md#remove)
- [`userUpdate`](docs/sdks/user/README.md#update)
- [`volumeBackupsCreate`](docs/sdks/volumebackups/README.md#create)
- [`volumeBackupsDelete`](docs/sdks/volumebackups/README.md#delete)
- [`volumeBackupsGet`](docs/sdks/volumebackups/README.md#get)
- [`volumeBackupsList`](docs/sdks/volumebackups/README.md#list)
- [`volumeBackupsRunManually`](docs/sdks/volumebackups/README.md#runmanually)
- [`volumeBackupsUpdate`](docs/sdks/volumebackups/README.md#update)

</details>
<!-- End Standalone functions [standalone-funcs] -->

<!-- Start Retries [retries] -->
## Retries

Some of the endpoints in this SDK support retries.  If you use the SDK without any configuration, it will fall back to the default retry strategy provided by the API.  However, the default retry strategy can be overridden on a per-operation basis, or across the entire SDK.

To change the default retry strategy for a single API call, simply provide a retryConfig object to the call:
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.admin.setupMonitoring({
    metricsConfig: {
      containers: {
        refreshRate: 7401.48,
        services: {},
      },
      server: {
        cronJob: "<value>",
        port: 8537.41,
        refreshRate: 4397.9,
        retentionDays: 6999.95,
        thresholds: {
          cpu: 5497.84,
          memory: 6419.22,
        },
        token: "<value>",
        urlCallback: "https://majestic-scratch.org",
      },
    },
  }, {
    retries: {
      strategy: "backoff",
      backoff: {
        initialInterval: 1,
        maxInterval: 50,
        exponent: 1.1,
        maxElapsedTime: 100,
      },
      retryConnectionErrors: false,
    },
  });

  console.log(result);
}

run();

```

If you'd like to override the default retry strategy for all operations that support retries, you can provide a retryConfig at SDK initialization:
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  retryConfig: {
    strategy: "backoff",
    backoff: {
      initialInterval: 1,
      maxInterval: 50,
      exponent: 1.1,
      maxElapsedTime: 100,
    },
    retryConnectionErrors: false,
  },
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.admin.setupMonitoring({
    metricsConfig: {
      containers: {
        refreshRate: 7401.48,
        services: {},
      },
      server: {
        cronJob: "<value>",
        port: 8537.41,
        refreshRate: 4397.9,
        retentionDays: 6999.95,
        thresholds: {
          cpu: 5497.84,
          memory: 6419.22,
        },
        token: "<value>",
        urlCallback: "https://majestic-scratch.org",
      },
    },
  });

  console.log(result);
}

run();

```
<!-- End Retries [retries] -->

<!-- Start Error Handling [errors] -->
## Error Handling

[`DokployError`](./src/models/errors/dokployerror.ts) is the base class for all HTTP error responses. It has the following properties:

| Property            | Type       | Description                                            |
| ------------------- | ---------- | ------------------------------------------------------ |
| `error.message`     | `string`   | Error message                                          |
| `error.statusCode`  | `number`   | HTTP response status code eg `404`                     |
| `error.headers`     | `Headers`  | HTTP response headers                                  |
| `error.body`        | `string`   | HTTP body. Can be empty string if no body is returned. |
| `error.rawResponse` | `Response` | Raw HTTP response                                      |

### Example
```typescript
import { Dokploy } from "dokploy-sdk";
import * as errors from "dokploy-sdk/models/errors";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  try {
    const result = await dokploy.admin.setupMonitoring({
      metricsConfig: {
        containers: {
          refreshRate: 7401.48,
          services: {},
        },
        server: {
          cronJob: "<value>",
          port: 8537.41,
          refreshRate: 4397.9,
          retentionDays: 6999.95,
          thresholds: {
            cpu: 5497.84,
            memory: 6419.22,
          },
          token: "<value>",
          urlCallback: "https://majestic-scratch.org",
        },
      },
    });

    console.log(result);
  } catch (error) {
    if (error instanceof errors.DokployError) {
      console.log(error.message);
      console.log(error.statusCode);
      console.log(error.body);
      console.log(error.headers);
    }
  }
}

run();

```

### Error Classes
**Primary error:**
* [`DokployError`](./src/models/errors/dokployerror.ts): The base class for HTTP error responses.

<details><summary>Less common errors (6)</summary>

<br />

**Network errors:**
* [`ConnectionError`](./src/models/errors/httpclienterrors.ts): HTTP client was unable to make a request to a server.
* [`RequestTimeoutError`](./src/models/errors/httpclienterrors.ts): HTTP request timed out due to an AbortSignal signal.
* [`RequestAbortedError`](./src/models/errors/httpclienterrors.ts): HTTP request was aborted by the client.
* [`InvalidRequestError`](./src/models/errors/httpclienterrors.ts): Any input used to create a request is invalid.
* [`UnexpectedClientError`](./src/models/errors/httpclienterrors.ts): Unrecognised or unexpected error.


**Inherit from [`DokployError`](./src/models/errors/dokployerror.ts)**:
* [`ResponseValidationError`](./src/models/errors/responsevalidationerror.ts): Type mismatch between the data returned from the server and the structure expected by the SDK. See `error.rawValue` for the raw value and `error.pretty()` for a nicely formatted multi-line string.

</details>
<!-- End Error Handling [errors] -->

<!-- Start Server Selection [server] -->
## Server Selection

### Override Server URL Per-Client

The default server can be overridden globally by passing a URL to the `serverURL: string` optional parameter when initializing the SDK client instance. For example:
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  serverURL: "http://localhost:3000/api",
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.admin.setupMonitoring({
    metricsConfig: {
      containers: {
        refreshRate: 7401.48,
        services: {},
      },
      server: {
        cronJob: "<value>",
        port: 8537.41,
        refreshRate: 4397.9,
        retentionDays: 6999.95,
        thresholds: {
          cpu: 5497.84,
          memory: 6419.22,
        },
        token: "<value>",
        urlCallback: "https://majestic-scratch.org",
      },
    },
  });

  console.log(result);
}

run();

```
<!-- End Server Selection [server] -->

<!-- Start Custom HTTP Client [http-client] -->
## Custom HTTP Client

The TypeScript SDK makes API calls using an `HTTPClient` that wraps the native
[Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API). This
client is a thin wrapper around `fetch` and provides the ability to attach hooks
around the request lifecycle that can be used to modify the request or handle
errors and response.

The `HTTPClient` constructor takes an optional `fetcher` argument that can be
used to integrate a third-party HTTP client or when writing tests to mock out
the HTTP client and feed in fixtures.

The following example shows how to:
- route requests through a proxy server using [undici](https://www.npmjs.com/package/undici)'s ProxyAgent
- use the `"beforeRequest"` hook to add a custom header and a timeout to requests
- use the `"requestError"` hook to log errors

```typescript
import { Dokploy } from "dokploy-sdk";
import { ProxyAgent } from "undici";
import { HTTPClient } from "dokploy-sdk/lib/http";

const dispatcher = new ProxyAgent("http://proxy.example.com:8080");

const httpClient = new HTTPClient({
  // 'fetcher' takes a function that has the same signature as native 'fetch'.
  fetcher: (input, init) =>
    // 'dispatcher' is specific to undici and not part of the standard Fetch API.
    fetch(input, { ...init, dispatcher } as RequestInit),
});

httpClient.addHook("beforeRequest", (request) => {
  const nextRequest = new Request(request, {
    signal: request.signal || AbortSignal.timeout(5000)
  });

  nextRequest.headers.set("x-custom-header", "custom value");

  return nextRequest;
});

httpClient.addHook("requestError", (error, request) => {
  console.group("Request Error");
  console.log("Reason:", `${error}`);
  console.log("Endpoint:", `${request.method} ${request.url}`);
  console.groupEnd();
});

const sdk = new Dokploy({ httpClient: httpClient });
```
<!-- End Custom HTTP Client [http-client] -->

<!-- Start Debugging [debug] -->
## Debugging

You can setup your SDK to emit debug logs for SDK requests and responses.

You can pass a logger that matches `console`'s interface as an SDK option.

> [!WARNING]
> Beware that debug logging will reveal secrets, like API tokens in headers, in log messages printed to a console or files. It's recommended to use this feature only during local development and not in production.

```typescript
import { Dokploy } from "dokploy-sdk";

const sdk = new Dokploy({ debugLogger: console });
```

You can also enable a default debug logger by setting an environment variable `DOKPLOY_DEBUG` to true.
<!-- End Debugging [debug] -->

<!-- Placeholder for Future Speakeasy SDK Sections -->

# Development

## Maturity

This SDK is in beta, and there may be breaking changes between versions without a major version update. Therefore, we recommend pinning usage
to a specific package version. This way, you can install the same version each time without breaking changes unless you are intentionally
looking for the latest version.

## Contributions

While we value open-source contributions to this SDK, this library is generated programmatically. Any manual changes added to internal files will be overwritten on the next generation. 
We look forward to hearing your feedback. Feel free to open a PR or an issue with a proof of concept and we'll do our best to include it in a future release. 

### SDK Created by [Speakeasy](https://www.speakeasy.com/?utm_source=dokploy-sdk&utm_campaign=typescript)
