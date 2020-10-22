---
uid: RetrieveExistingConfiguration1-1-unreleased
---

# Retrieve existing configuration

Use EdgeCmd utility to view the configuration for each part of the adapter.

**Note:** The examples in this topic are using the default port number `5590`. If you specified a different port number for your adapter, you need to add it in the command. For example:

```cmd
edgecmd -port=5591 Configuration <RestOfTheCommand>
```

**Note:** If a command contains slashes, you must escape them as follows:<br> 
  - In *Windows*, add a second slash.<br> 
       Example: `TestUser\OilCompany` becomes `TestUser\\OilCompany`

  - In *Linux*, add three slashes.<br>
       Example: `TestUser\OilCompany` becomes `TestUser\\\\OilCompany`

## View adapter configuration

Complete the following steps to view the configuration for the adapter:

1. Access EdgeCmd utility through the command line.
2. Type the following in the command line and press Enter.

   ```cmd
   edgecmd Configuration
   ```
  
   Under [Examples](#examples), see **View the configuration of the adapter**.
  
## View configured components

Complete the following steps to view the components currently configured on the adapter:

1. Access EdgeCmd utility through the command line.
2. Type the following in the command line and press Enter.

   ```cmd
   edgecmd Configuration System Components
   ```
  
## View a specific component configuration

Complete the following steps to view the configuration of a specific component:

1. Access EdgeCmd utility through the command line.
2. Type the following in the command line, replacing `<componentId>` with the ID of the component, and press Enter.

   ```cmd
   edgecmd Configuration <componentId>
   ```
  
   Under [Examples](#examples), see **View the configuration of the System component**.

## View a specific facet configuration

Complete the following steps to view the configuration of a specific facet of an adapter component:

1. Access EdgeCmd utility through the command line.
2. Type the following in the command line, replacing `<componentId>` and `<facetName>` with the ID of the component and the facet name, and press Enter.

   ```cmd
   edgecmd Configuration <componentId> <facetName>
   ```
  
   Under [Examples](#examples), see **View the configuration of the Logging facet within the OmfEgress component**.
  
## View a specific facet entry configuration

Complete the following steps to view the configuration of a specific facet entry of a component:

1. Access EdgeCmd utility through the command line.
2. Type the following in the command line, replacing `<componentId>` and `<facetName>` with the ID of the component and the facet name.

   ```cmd
   edgecmd Configuration <componentId> <facetName> id=IndexToRetrieve
   ```

3. Add the key=value pairs for the facet to configure, for example `id=IndexToRetrieve`, and press Enter.

   Under [Examples](#examples), see **View the configuration of a specific entry in the HealthEndpoints facet within the System component**.

### Examples

<details>
    <summary>View the configuration of the adapter</summary>
    <pre>

      edgecmd Configuration
      {
        "System": {
          "Logging": {
            "logLevel": "Information",
            "logFileSizeLimitBytes": 34636833,
            "logFileCountLimit": 31
          },
          "HealthEndpoints": [],
          "Diagnostics": {
            "enableDiagnostics": true
          },
          "Components": [
            {
              "componentId": "Modbus1",
              "componentType": "Modbus"
            },
            {
              "componentId": "Egress",
              "componentType": "OmfEgress"
            }
          ],
          "Buffering": {
            "bufferLocation": "C:/ProgramData/OSIsoft/Adapters/Modbus/Modbus/Buffers",
            "maxBufferSizeMB": -1,
            "enableBuffering": true
          }
        },
        "Modbus1": {
          "Logging": {
            "logLevel": "Information",
            "logFileSizeLimitBytes": 34636833,
            "logFileCountLimit": 31
          },
          "DataSource": {},
          "DataSelection": []
        },
        "OmfEgress": {
          "Logging": {
            "logLevel": "Information",
            "logFileSizeLimitBytes": 34636833,
            "logFileCountLimit": 31
          },
          "DataEndpoints": [],
          "Buffering": {
            "onDiskBufferLocation": "C:/ProgramData/OSIsoft/Adapters/Modbus/Modbus/Buffers",
            "onDiskMaxBufferSizeMB": -1
          }
        }
      }

 </pre>
</details>

<details>
    <summary>View the configuration of the System component</summary>
    <pre>

    edgecmd Configuration System
    {
      "Logging": {
        "logLevel": "Information",
        "logFileSizeLimitBytes": 34636833,
        "logFileCountLimit": 31
      },
      "HealthEndpoints": [],
      "Diagnostics": {
        "enableDiagnostics": true
      },
      "Components": [
        {
          "componentId": "Modbus1",
          "componentType": "Modbus"
        },
        {
          "componentId": "Egress",
          "componentType": "OmfEgress"
        }
      ],
      "Buffering": {
        "bufferLocation": "C:/ProgramData/OSIsoft/Adapters/Modbus/Modbus/Buffers",
        "maxBufferSizeMB": -1,
        "enableBuffering": true
      }
    }

 </pre>
</details>

<details>
    <summary>View the configuration of the Logging facet within the OmfEgress component</summary>
    <pre>

      edgecmd Configuration OmfEgress Logging
      {
        "logLevel": "Information",
        "logFileSizeLimitBytes": 34636833,
        "logFileCountLimit": 31
      }

 </pre>
</details>

<details>
    <summary>View the configuration of a specific entry in the HealthEndpoints facet within the System component</summary>
    <pre>

      edgecmd Configuration System HealthEndpoints id=Endpoint_1
      {
        "id": "Endpoint_1",
        "endpoint": "https://localhost:5821",
        "userName": "user_54",
        "password": "***************",
        "clientId": null,
        "clientSecret": null,
        "tokenEndpoint": null,
        "validateEndpointCertificate": true
      }

 </pre>
</details>
