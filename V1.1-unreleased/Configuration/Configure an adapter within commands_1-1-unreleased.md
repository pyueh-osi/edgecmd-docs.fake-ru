---
uid: ConfigureAnAdapterWithinCommands1-1-unreleased
---

# Configure an adapter within commands

Use EdgeCmd utility to configure an adapter using only commands or by pointing to JSON files. For more information, see [Configure an adapter with JSON files](xref:ConfigureAnAdapterWithJsonFiles1-1).

**Note:** The examples in this topic are using the default port number `5590`. If you specified a different port number for your adapter, you need to add it in the command. For example:

```cmd
edgecmd -port=5591 Configuration <RestOfTheCommand>
```

**Note:** If a command contains slashes, you must escape them as follows:<br> 
  - In *Windows*, add a second slash.<br> 
       Example: `TestUser\OilCompany` becomes `TestUser\\OilCompany`

  - In *Linux*, add three slashes.<br>
       Example: `TestUser\OilCompany` becomes `TestUser\\\\OilCompany`

## Change all values of a facet

Complete the following steps to change all values of a facet:

1. Access EdgeCmd utility through the command line.
2. Type `edgecmd Configuration` and then the `componentId` and `facetName`, followed by the key=value pairs. Then press Enter.

   **Example:** Change all values in the 'Logging' facet:

   ```cmd
   edgecmd Configuration Modbus1 Logging LogLevel=Warning LogFileSizeLimitBytes=32768 LogFileCountLimit=5
   ```

## Configure key=value pairs in a facet

Complete the following steps to configure any number of valid key=value pairs in a facet:

1. Access EdgeCmd utility through the command line.
2. Type `edgecmd Configuration` and then the `componentId` and `facetName` followed by the key=value pairs to change, and press Enter.

   **Example:** Change a single value in the 'Logging' facet:

   ```cmd
   edgecmd Configuration Modbus1 Logging LogFileCountLimit=5
   ```

## Add an entry to a collection configuration

Complete the following steps to add an entry to a collection configuration:

1. Access EdgeCmd utility through the command line.
2. Type `edgecmd Configuration` and then the `componentId` and `facetName` followed by the key=value pairs, and press Enter.

   **Example:** Add the 'Health Endpoints' facet to the 'System' component:

   ```cmd
   edgecmd Configuration Modbus1 HealthEndpoints Id=endpoint_1 Endpoint=endpointURL UserName=UserName Password=Password
   ```

   **Note:** If an entry with the specified ID already exists, it is updated based on the new key=value pairs.
