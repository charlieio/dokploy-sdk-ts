# Admin

## Overview

### Available Operations

* [setupMonitoring](#setupmonitoring)

## setupMonitoring

### Example Usage

<!-- UsageSnippet language="typescript" operationID="admin-setupMonitoring" method="post" path="/admin.setupMonitoring" -->
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

### Standalone function

The standalone function version of this method:

```typescript
import { DokployCore } from "dokploy-sdk/core.js";
import { adminSetupMonitoring } from "dokploy-sdk/funcs/adminSetupMonitoring.js";

// Use `DokployCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const dokploy = new DokployCore({
  apiKeyAuth: process.env["DOKPLOY_API_KEY_AUTH"] ?? "",
});

async function run() {
  const res = await adminSetupMonitoring(dokploy, {
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
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("adminSetupMonitoring failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.AdminSetupMonitoringRequest](../../models/operations/adminsetupmonitoringrequest.md)                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ErrorT](../../models/errort.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.DokployDefaultError | 4XX, 5XX                   | \*/\*                      |