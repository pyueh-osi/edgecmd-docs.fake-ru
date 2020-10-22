---
uid: ConfigureAnAdapterWithJsonFiles1-1-unreleased
---

# Configure an adapter with JSON Files

Use EdgeCmd utility to  import a JSON file that contains the adapter configuration into the adapter. A file import completely replaces the existing configurations; therefore, you cannot use it to change individual values in a facet without modifying others.

**Note:** The examples in this topic are using the default port number `5590`. If you specified a different port number for your adapter, you need to add it in the command. For example:

```cmd
edgecmd -port=5591 Configuration <RestOfTheCommand>
```

## Import bulk configuration

Complete the following steps to import a bulk configuration:

1. Access EdgeCmd utility through the command line.
2. Type the following in the command line, replacing `<PathToJsonFile>` with the path to the file, and press Enter.

   ```cmd
   edgecmd Configuration file=<PathToJsonFile>
   ```

## Import facet specific configuration

Complete the following steps to import a facet specific configuration file for a component:

1. Access EdgeCmd utility through the command line.
2. Type the following in the command line, replacing `<componentId>` with the ID of the component, `<facetName>` with the name of the facet, and `<PathToJsonFile>` with the path to the file. Then press Enter.

   ```cmd
   edgecmd Configuration <componentId> <facetName> file=<PathToJsonFile>
   ```

## Import facets configuration in bulk

Complete the following steps to import a file with configuration for individual facets, but not individual values of a facet, as a bulk file import operation:<br><br>
**Note:** The file must contain only information for the given component ID.

1. Access EdgeCmd utility through the command line.
2. Type the file name as shown in the _Logging.json_ example and press Enter.

   ```cmd
   edgecmd Configuration file="~/Logging.json"
   ```

   **Example:**

   ```json
   {
      "Modbus1": {
        "Logging": {
          "logLevel": "Warning",
          "logFileSizeLimitBytes": 19283,
          "logFileCountLimit": 999
         }
      }
   }
    ```

   **Note:** The command only affects the specified key=value pairs for the 'Logging' facet in the 'Modbus1' component, it does not change any other components or facets. However, import affects all key=value pairs in the facet. If you import the following example JSON file, the 'logLevel' and 'logFileSizeLimitBytes' values are modified and the remaining values in the 'Logging' facet are reset to their default values (logFileCountLimit).

   ```json
   {
      "Modbus1": {
        "Logging": {
          "logLevel": "Warning",
          "logFileSizeLimitBytes": 19283
         }
      }
   }
   ```
