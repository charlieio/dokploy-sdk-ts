# DockerGetContainersByAppLabelRequest

## Example Usage

```typescript
import { DockerGetContainersByAppLabelRequest } from "dokploy-sdk/models/operations";

let value: DockerGetContainersByAppLabelRequest = {
  appName: "abc",
  type: "swarm",
};
```

## Fields

| Field                                                                                                        | Type                                                                                                         | Required                                                                                                     | Description                                                                                                  |
| ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| `appName`                                                                                                    | *string*                                                                                                     | :heavy_check_mark:                                                                                           | N/A                                                                                                          |
| `serverId`                                                                                                   | *string*                                                                                                     | :heavy_minus_sign:                                                                                           | N/A                                                                                                          |
| `type`                                                                                                       | [operations.DockerGetContainersByAppLabelType](../../models/operations/dockergetcontainersbyapplabeltype.md) | :heavy_check_mark:                                                                                           | N/A                                                                                                          |