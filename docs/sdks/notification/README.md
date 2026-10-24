# Notification

## Overview

### Available Operations

* [createDiscord](#creatediscord)
* [createEmail](#createemail)
* [createGotify](#creategotify)
* [createNtfy](#createntfy)
* [createSlack](#createslack)
* [createTelegram](#createtelegram)
* [getEmailProviders](#getemailproviders)
* [get](#get)
* [receiveNotification](#receivenotification)
* [remove](#remove)
* [testDiscordConnection](#testdiscordconnection)
* [testEmailConnection](#testemailconnection)
* [testGotifyConnection](#testgotifyconnection)
* [testNtfyConnection](#testntfyconnection)
* [testSlackConnection](#testslackconnection)
* [testTelegramConnection](#testtelegramconnection)
* [updateDiscord](#updatediscord)
* [updateEmail](#updateemail)
* [updateGotify](#updategotify)
* [updateNtfy](#updatentfy)
* [updateSlack](#updateslack)
* [updateTelegram](#updatetelegram)

## createDiscord

### Example Usage

<!-- UsageSnippet language="typescript" operationID="notification-createDiscord" method="post" path="/notification.createDiscord" -->
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.notification.createDiscord({
    appBuildError: false,
    appDeploy: false,
    databaseBackup: true,
    decoration: true,
    dockerCleanup: true,
    dokployRestart: false,
    name: "<value>",
    serverThreshold: true,
    webhookUrl: "https://tedious-scale.net",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { DokployCore } from "dokploy-sdk/core.js";
import { notificationCreateDiscord } from "dokploy-sdk/funcs/notificationCreateDiscord.js";

// Use `DokployCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const dokploy = new DokployCore({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const res = await notificationCreateDiscord(dokploy, {
    appBuildError: false,
    appDeploy: false,
    databaseBackup: true,
    decoration: true,
    dockerCleanup: true,
    dokployRestart: false,
    name: "<value>",
    serverThreshold: true,
    webhookUrl: "https://tedious-scale.net",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("notificationCreateDiscord failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.NotificationCreateDiscordRequest](../../models/operations/notificationcreatediscordrequest.md)                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ErrorT](../../models/errort.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.DokployDefaultError | 4XX, 5XX                   | \*/\*                      |

## createEmail

### Example Usage

<!-- UsageSnippet language="typescript" operationID="notification-createEmail" method="post" path="/notification.createEmail" -->
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.notification.createEmail({
    appBuildError: false,
    appDeploy: false,
    databaseBackup: false,
    dockerCleanup: false,
    dokployRestart: true,
    fromAddress: "<value>",
    name: "<value>",
    password: "LGAnX2vuZKQTVc9",
    serverThreshold: false,
    smtpPort: 5836.58,
    smtpServer: "<value>",
    toAddresses: [],
    username: "Nathen_Torp90",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { DokployCore } from "dokploy-sdk/core.js";
import { notificationCreateEmail } from "dokploy-sdk/funcs/notificationCreateEmail.js";

// Use `DokployCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const dokploy = new DokployCore({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const res = await notificationCreateEmail(dokploy, {
    appBuildError: false,
    appDeploy: false,
    databaseBackup: false,
    dockerCleanup: false,
    dokployRestart: true,
    fromAddress: "<value>",
    name: "<value>",
    password: "LGAnX2vuZKQTVc9",
    serverThreshold: false,
    smtpPort: 5836.58,
    smtpServer: "<value>",
    toAddresses: [],
    username: "Nathen_Torp90",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("notificationCreateEmail failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.NotificationCreateEmailRequest](../../models/operations/notificationcreateemailrequest.md)                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ErrorT](../../models/errort.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.DokployDefaultError | 4XX, 5XX                   | \*/\*                      |

## createGotify

### Example Usage

<!-- UsageSnippet language="typescript" operationID="notification-createGotify" method="post" path="/notification.createGotify" -->
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.notification.createGotify({
    appBuildError: true,
    appDeploy: true,
    appToken: "<value>",
    databaseBackup: true,
    decoration: true,
    dockerCleanup: true,
    dokployRestart: false,
    name: "<value>",
    priority: 5429.53,
    serverUrl: "https://square-gastropod.com",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { DokployCore } from "dokploy-sdk/core.js";
import { notificationCreateGotify } from "dokploy-sdk/funcs/notificationCreateGotify.js";

// Use `DokployCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const dokploy = new DokployCore({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const res = await notificationCreateGotify(dokploy, {
    appBuildError: true,
    appDeploy: true,
    appToken: "<value>",
    databaseBackup: true,
    decoration: true,
    dockerCleanup: true,
    dokployRestart: false,
    name: "<value>",
    priority: 5429.53,
    serverUrl: "https://square-gastropod.com",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("notificationCreateGotify failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.NotificationCreateGotifyRequest](../../models/operations/notificationcreategotifyrequest.md)                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ErrorT](../../models/errort.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.DokployDefaultError | 4XX, 5XX                   | \*/\*                      |

## createNtfy

### Example Usage

<!-- UsageSnippet language="typescript" operationID="notification-createNtfy" method="post" path="/notification.createNtfy" -->
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.notification.createNtfy({
    accessToken: "<value>",
    appBuildError: false,
    appDeploy: true,
    databaseBackup: true,
    dockerCleanup: true,
    dokployRestart: true,
    name: "<value>",
    priority: 1148.07,
    serverUrl: "https://early-blossom.biz",
    topic: "<value>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { DokployCore } from "dokploy-sdk/core.js";
import { notificationCreateNtfy } from "dokploy-sdk/funcs/notificationCreateNtfy.js";

// Use `DokployCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const dokploy = new DokployCore({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const res = await notificationCreateNtfy(dokploy, {
    accessToken: "<value>",
    appBuildError: false,
    appDeploy: true,
    databaseBackup: true,
    dockerCleanup: true,
    dokployRestart: true,
    name: "<value>",
    priority: 1148.07,
    serverUrl: "https://early-blossom.biz",
    topic: "<value>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("notificationCreateNtfy failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.NotificationCreateNtfyRequest](../../models/operations/notificationcreatentfyrequest.md)                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ErrorT](../../models/errort.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.DokployDefaultError | 4XX, 5XX                   | \*/\*                      |

## createSlack

### Example Usage

<!-- UsageSnippet language="typescript" operationID="notification-createSlack" method="post" path="/notification.createSlack" -->
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.notification.createSlack({
    appBuildError: true,
    appDeploy: false,
    channel: "<value>",
    databaseBackup: true,
    dockerCleanup: false,
    dokployRestart: false,
    name: "<value>",
    serverThreshold: false,
    webhookUrl: "https://early-lid.info/",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { DokployCore } from "dokploy-sdk/core.js";
import { notificationCreateSlack } from "dokploy-sdk/funcs/notificationCreateSlack.js";

// Use `DokployCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const dokploy = new DokployCore({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const res = await notificationCreateSlack(dokploy, {
    appBuildError: true,
    appDeploy: false,
    channel: "<value>",
    databaseBackup: true,
    dockerCleanup: false,
    dokployRestart: false,
    name: "<value>",
    serverThreshold: false,
    webhookUrl: "https://early-lid.info/",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("notificationCreateSlack failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.NotificationCreateSlackRequest](../../models/operations/notificationcreateslackrequest.md)                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ErrorT](../../models/errort.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.DokployDefaultError | 4XX, 5XX                   | \*/\*                      |

## createTelegram

### Example Usage

<!-- UsageSnippet language="typescript" operationID="notification-createTelegram" method="post" path="/notification.createTelegram" -->
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.notification.createTelegram({
    appBuildError: false,
    appDeploy: true,
    botToken: "<value>",
    chatId: "<id>",
    databaseBackup: true,
    dockerCleanup: true,
    dokployRestart: false,
    messageThreadId: "<id>",
    name: "<value>",
    serverThreshold: false,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { DokployCore } from "dokploy-sdk/core.js";
import { notificationCreateTelegram } from "dokploy-sdk/funcs/notificationCreateTelegram.js";

// Use `DokployCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const dokploy = new DokployCore({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const res = await notificationCreateTelegram(dokploy, {
    appBuildError: false,
    appDeploy: true,
    botToken: "<value>",
    chatId: "<id>",
    databaseBackup: true,
    dockerCleanup: true,
    dokployRestart: false,
    messageThreadId: "<id>",
    name: "<value>",
    serverThreshold: false,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("notificationCreateTelegram failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.NotificationCreateTelegramRequest](../../models/operations/notificationcreatetelegramrequest.md)                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ErrorT](../../models/errort.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.DokployDefaultError | 4XX, 5XX                   | \*/\*                      |

## getEmailProviders

### Example Usage

<!-- UsageSnippet language="typescript" operationID="notification-getEmailProviders" method="get" path="/notification.getEmailProviders" -->
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.notification.getEmailProviders();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { DokployCore } from "dokploy-sdk/core.js";
import { notificationGetEmailProviders } from "dokploy-sdk/funcs/notificationGetEmailProviders.js";

// Use `DokployCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const dokploy = new DokployCore({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const res = await notificationGetEmailProviders(dokploy);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("notificationGetEmailProviders failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ErrorT](../../models/errort.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.DokployDefaultError | 4XX, 5XX                   | \*/\*                      |

## get

### Example Usage

<!-- UsageSnippet language="typescript" operationID="notification-one" method="get" path="/notification.one" -->
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.notification.get({
    notificationId: "<id>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { DokployCore } from "dokploy-sdk/core.js";
import { notificationGet } from "dokploy-sdk/funcs/notificationGet.js";

// Use `DokployCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const dokploy = new DokployCore({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const res = await notificationGet(dokploy, {
    notificationId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("notificationGet failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.NotificationOneRequest](../../models/operations/notificationonerequest.md)                                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ErrorT](../../models/errort.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.DokployDefaultError | 4XX, 5XX                   | \*/\*                      |

## receiveNotification

### Example Usage

<!-- UsageSnippet language="typescript" operationID="notification-receiveNotification" method="post" path="/notification.receiveNotification" -->
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.notification.receiveNotification({
    message: "<value>",
    threshold: 5582.57,
    timestamp: "<value>",
    token: "<value>",
    type: "Memory",
    value: 2260.49,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { DokployCore } from "dokploy-sdk/core.js";
import { notificationReceiveNotification } from "dokploy-sdk/funcs/notificationReceiveNotification.js";

// Use `DokployCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const dokploy = new DokployCore({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const res = await notificationReceiveNotification(dokploy, {
    message: "<value>",
    threshold: 5582.57,
    timestamp: "<value>",
    token: "<value>",
    type: "Memory",
    value: 2260.49,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("notificationReceiveNotification failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.NotificationReceiveNotificationRequest](../../models/operations/notificationreceivenotificationrequest.md)                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ErrorT](../../models/errort.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.DokployDefaultError | 4XX, 5XX                   | \*/\*                      |

## remove

### Example Usage

<!-- UsageSnippet language="typescript" operationID="notification-remove" method="post" path="/notification.remove" -->
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.notification.remove({
    notificationId: "<id>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { DokployCore } from "dokploy-sdk/core.js";
import { notificationRemove } from "dokploy-sdk/funcs/notificationRemove.js";

// Use `DokployCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const dokploy = new DokployCore({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const res = await notificationRemove(dokploy, {
    notificationId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("notificationRemove failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.NotificationRemoveRequest](../../models/operations/notificationremoverequest.md)                                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ErrorT](../../models/errort.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.DokployDefaultError | 4XX, 5XX                   | \*/\*                      |

## testDiscordConnection

### Example Usage

<!-- UsageSnippet language="typescript" operationID="notification-testDiscordConnection" method="post" path="/notification.testDiscordConnection" -->
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.notification.testDiscordConnection({
    webhookUrl: "https://radiant-fireplace.net",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { DokployCore } from "dokploy-sdk/core.js";
import { notificationTestDiscordConnection } from "dokploy-sdk/funcs/notificationTestDiscordConnection.js";

// Use `DokployCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const dokploy = new DokployCore({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const res = await notificationTestDiscordConnection(dokploy, {
    webhookUrl: "https://radiant-fireplace.net",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("notificationTestDiscordConnection failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.NotificationTestDiscordConnectionRequest](../../models/operations/notificationtestdiscordconnectionrequest.md)                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ErrorT](../../models/errort.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.DokployDefaultError | 4XX, 5XX                   | \*/\*                      |

## testEmailConnection

### Example Usage

<!-- UsageSnippet language="typescript" operationID="notification-testEmailConnection" method="post" path="/notification.testEmailConnection" -->
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.notification.testEmailConnection({
    fromAddress: "<value>",
    password: "xHtlQtIjbn2x0yV",
    smtpPort: 4799.46,
    smtpServer: "<value>",
    toAddresses: [
      "<value 1>",
      "<value 2>",
    ],
    username: "Rollin96",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { DokployCore } from "dokploy-sdk/core.js";
import { notificationTestEmailConnection } from "dokploy-sdk/funcs/notificationTestEmailConnection.js";

// Use `DokployCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const dokploy = new DokployCore({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const res = await notificationTestEmailConnection(dokploy, {
    fromAddress: "<value>",
    password: "xHtlQtIjbn2x0yV",
    smtpPort: 4799.46,
    smtpServer: "<value>",
    toAddresses: [
      "<value 1>",
      "<value 2>",
    ],
    username: "Rollin96",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("notificationTestEmailConnection failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.NotificationTestEmailConnectionRequest](../../models/operations/notificationtestemailconnectionrequest.md)                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ErrorT](../../models/errort.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.DokployDefaultError | 4XX, 5XX                   | \*/\*                      |

## testGotifyConnection

### Example Usage

<!-- UsageSnippet language="typescript" operationID="notification-testGotifyConnection" method="post" path="/notification.testGotifyConnection" -->
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.notification.testGotifyConnection({
    appToken: "<value>",
    priority: 2139.47,
    serverUrl: "https://firm-bend.com",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { DokployCore } from "dokploy-sdk/core.js";
import { notificationTestGotifyConnection } from "dokploy-sdk/funcs/notificationTestGotifyConnection.js";

// Use `DokployCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const dokploy = new DokployCore({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const res = await notificationTestGotifyConnection(dokploy, {
    appToken: "<value>",
    priority: 2139.47,
    serverUrl: "https://firm-bend.com",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("notificationTestGotifyConnection failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.NotificationTestGotifyConnectionRequest](../../models/operations/notificationtestgotifyconnectionrequest.md)                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ErrorT](../../models/errort.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.DokployDefaultError | 4XX, 5XX                   | \*/\*                      |

## testNtfyConnection

### Example Usage

<!-- UsageSnippet language="typescript" operationID="notification-testNtfyConnection" method="post" path="/notification.testNtfyConnection" -->
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.notification.testNtfyConnection({
    accessToken: "<value>",
    priority: 1272.9,
    serverUrl: "https://good-eyeliner.biz",
    topic: "<value>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { DokployCore } from "dokploy-sdk/core.js";
import { notificationTestNtfyConnection } from "dokploy-sdk/funcs/notificationTestNtfyConnection.js";

// Use `DokployCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const dokploy = new DokployCore({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const res = await notificationTestNtfyConnection(dokploy, {
    accessToken: "<value>",
    priority: 1272.9,
    serverUrl: "https://good-eyeliner.biz",
    topic: "<value>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("notificationTestNtfyConnection failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.NotificationTestNtfyConnectionRequest](../../models/operations/notificationtestntfyconnectionrequest.md)                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ErrorT](../../models/errort.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.DokployDefaultError | 4XX, 5XX                   | \*/\*                      |

## testSlackConnection

### Example Usage

<!-- UsageSnippet language="typescript" operationID="notification-testSlackConnection" method="post" path="/notification.testSlackConnection" -->
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.notification.testSlackConnection({
    channel: "<value>",
    webhookUrl: "https://pointed-institute.com",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { DokployCore } from "dokploy-sdk/core.js";
import { notificationTestSlackConnection } from "dokploy-sdk/funcs/notificationTestSlackConnection.js";

// Use `DokployCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const dokploy = new DokployCore({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const res = await notificationTestSlackConnection(dokploy, {
    channel: "<value>",
    webhookUrl: "https://pointed-institute.com",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("notificationTestSlackConnection failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.NotificationTestSlackConnectionRequest](../../models/operations/notificationtestslackconnectionrequest.md)                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ErrorT](../../models/errort.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.DokployDefaultError | 4XX, 5XX                   | \*/\*                      |

## testTelegramConnection

### Example Usage

<!-- UsageSnippet language="typescript" operationID="notification-testTelegramConnection" method="post" path="/notification.testTelegramConnection" -->
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.notification.testTelegramConnection({
    botToken: "<value>",
    chatId: "<id>",
    messageThreadId: "<id>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { DokployCore } from "dokploy-sdk/core.js";
import { notificationTestTelegramConnection } from "dokploy-sdk/funcs/notificationTestTelegramConnection.js";

// Use `DokployCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const dokploy = new DokployCore({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const res = await notificationTestTelegramConnection(dokploy, {
    botToken: "<value>",
    chatId: "<id>",
    messageThreadId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("notificationTestTelegramConnection failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.NotificationTestTelegramConnectionRequest](../../models/operations/notificationtesttelegramconnectionrequest.md)                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ErrorT](../../models/errort.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.DokployDefaultError | 4XX, 5XX                   | \*/\*                      |

## updateDiscord

### Example Usage

<!-- UsageSnippet language="typescript" operationID="notification-updateDiscord" method="post" path="/notification.updateDiscord" -->
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.notification.updateDiscord({
    discordId: "<id>",
    notificationId: "<id>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { DokployCore } from "dokploy-sdk/core.js";
import { notificationUpdateDiscord } from "dokploy-sdk/funcs/notificationUpdateDiscord.js";

// Use `DokployCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const dokploy = new DokployCore({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const res = await notificationUpdateDiscord(dokploy, {
    discordId: "<id>",
    notificationId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("notificationUpdateDiscord failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.NotificationUpdateDiscordRequest](../../models/operations/notificationupdatediscordrequest.md)                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ErrorT](../../models/errort.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.DokployDefaultError | 4XX, 5XX                   | \*/\*                      |

## updateEmail

### Example Usage

<!-- UsageSnippet language="typescript" operationID="notification-updateEmail" method="post" path="/notification.updateEmail" -->
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.notification.updateEmail({
    emailId: "<id>",
    notificationId: "<id>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { DokployCore } from "dokploy-sdk/core.js";
import { notificationUpdateEmail } from "dokploy-sdk/funcs/notificationUpdateEmail.js";

// Use `DokployCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const dokploy = new DokployCore({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const res = await notificationUpdateEmail(dokploy, {
    emailId: "<id>",
    notificationId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("notificationUpdateEmail failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.NotificationUpdateEmailRequest](../../models/operations/notificationupdateemailrequest.md)                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ErrorT](../../models/errort.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.DokployDefaultError | 4XX, 5XX                   | \*/\*                      |

## updateGotify

### Example Usage

<!-- UsageSnippet language="typescript" operationID="notification-updateGotify" method="post" path="/notification.updateGotify" -->
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.notification.updateGotify({
    gotifyId: "<id>",
    notificationId: "<id>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { DokployCore } from "dokploy-sdk/core.js";
import { notificationUpdateGotify } from "dokploy-sdk/funcs/notificationUpdateGotify.js";

// Use `DokployCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const dokploy = new DokployCore({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const res = await notificationUpdateGotify(dokploy, {
    gotifyId: "<id>",
    notificationId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("notificationUpdateGotify failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.NotificationUpdateGotifyRequest](../../models/operations/notificationupdategotifyrequest.md)                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ErrorT](../../models/errort.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.DokployDefaultError | 4XX, 5XX                   | \*/\*                      |

## updateNtfy

### Example Usage

<!-- UsageSnippet language="typescript" operationID="notification-updateNtfy" method="post" path="/notification.updateNtfy" -->
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.notification.updateNtfy({
    notificationId: "<id>",
    ntfyId: "<id>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { DokployCore } from "dokploy-sdk/core.js";
import { notificationUpdateNtfy } from "dokploy-sdk/funcs/notificationUpdateNtfy.js";

// Use `DokployCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const dokploy = new DokployCore({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const res = await notificationUpdateNtfy(dokploy, {
    notificationId: "<id>",
    ntfyId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("notificationUpdateNtfy failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.NotificationUpdateNtfyRequest](../../models/operations/notificationupdatentfyrequest.md)                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ErrorT](../../models/errort.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.DokployDefaultError | 4XX, 5XX                   | \*/\*                      |

## updateSlack

### Example Usage

<!-- UsageSnippet language="typescript" operationID="notification-updateSlack" method="post" path="/notification.updateSlack" -->
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.notification.updateSlack({
    notificationId: "<id>",
    slackId: "<id>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { DokployCore } from "dokploy-sdk/core.js";
import { notificationUpdateSlack } from "dokploy-sdk/funcs/notificationUpdateSlack.js";

// Use `DokployCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const dokploy = new DokployCore({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const res = await notificationUpdateSlack(dokploy, {
    notificationId: "<id>",
    slackId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("notificationUpdateSlack failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.NotificationUpdateSlackRequest](../../models/operations/notificationupdateslackrequest.md)                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ErrorT](../../models/errort.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.DokployDefaultError | 4XX, 5XX                   | \*/\*                      |

## updateTelegram

### Example Usage

<!-- UsageSnippet language="typescript" operationID="notification-updateTelegram" method="post" path="/notification.updateTelegram" -->
```typescript
import { Dokploy } from "dokploy-sdk";

const dokploy = new Dokploy({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const result = await dokploy.notification.updateTelegram({
    notificationId: "<id>",
    telegramId: "<id>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { DokployCore } from "dokploy-sdk/core.js";
import { notificationUpdateTelegram } from "dokploy-sdk/funcs/notificationUpdateTelegram.js";

// Use `DokployCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const dokploy = new DokployCore({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const res = await notificationUpdateTelegram(dokploy, {
    notificationId: "<id>",
    telegramId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("notificationUpdateTelegram failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.NotificationUpdateTelegramRequest](../../models/operations/notificationupdatetelegramrequest.md)                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ErrorT](../../models/errort.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.DokployDefaultError | 4XX, 5XX                   | \*/\*                      |