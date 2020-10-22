---
uid: EdgeCmdCommands1-1-unreleased
---

# EdgeCmd commands

The following tables provide a description of every command available in EdgeCmd utility. Every command used with the EdgeCmd utility has to be preceded by `edgecmd`.

**Note:** The examples in this topic are using the default port number `5590`. If you specified a different port number for your adapter, you need to add it in the command. For example:

```cmd
edgecmd -port=5591 Configuration <RestOfTheCommand>
```

**Note:** If a command contains slashes, you must escape them as follows:<br> 
  - In *Windows*, add a second slash.<br> 
       Example: `TestUser\OilCompany` becomes `TestUser\\OilCompany`

  - In *Linux*, add three slashes.<br>
       Example: `TestUser\OilCompany` becomes `TestUser\\\\OilCompany`

## Help

| edgecmd command | Description | Examples |
|-----------------|-------------|----------|
|```edgecmd -help```| Display general instructions on how to use the edgecmd utility. |
|```edgecmd -help Configuration <componentId>```| Display help for a specific adapter component.| ```edgecmd -help Configuration System```|
|```edgecmd -help Configuration <componentId> <facetName>``` | Display help for a specific facet of an adapter component. | ```edgecmd -help Configuration System Logging```|

## Configuration

### System

| edgecmd command | Description | Examples |
|-----------------|-------------|----------|
|```edgecmd Configuration```| Display the entire configuration for every adapter component. |
|```edgecmd Configuration System Components``` | Display the components that are currently configured. |
|```edgecmd Configuration System Components componentId=<componentId> componentType=<componentType>``` | Add a new component.  | ```edgecmd Configuration System Components componentId=Modbus1 componentType=Modbus```|
|```edgecmd Configuration System Components id=<componentId> delete``` | Delete a component. | ```edgecmd Configuration System Components id=Modbus1 delete``` |

### Components

| edgecmd command | Description | Examples |
|-----------------|-------------|----------|
|```edgecmd Configuration <componentId>``` | Display component specific configuration. | ```edgecmd Configuration System```<br>or<br>```edgecmd  Configuration OpcUa1```|
|```edgecmd Configuration <componentId> <facetName>``` | Display facet specific configuration of a component. | ```edgecmd Configuration System Logging```|
|```edgecmd Configuration <componentId> <facetName> id=<IndexToRetrieve>```| Display the configuration of a specific entry of a facet. | ```edgecmd Configuration System HealthEndpoints id=Endpoint1``` |
|```edgecmd Configuration <componentId> DataSource``` | Configure the data source for the adapter. | For examples, see [PI Adapter for OPC UA data source configuration](https://osisoft.github.io/OSIsoft-Adapter-OPC-UA-Docs/V1/Configuration/OSIsoft%20Adapter%20for%20OPC%20UA%20data%20source%20configuration.html) and [PI Adapter For Modbus TCP data source configuration](https://osisoft.github.io/OSIsoft-Adapter-Modbus-Docs/V1/Configuration/OSIsoft%20Adapter%20for%20Modbus%20TCP%20data%20source%20configuration.html)|
|```edgecmd Configuration <componentId> DataSelection``` | Configure the data selection for the adapter. | For examples, see [PI Adapter for OPC UA data selection configuration](https://osisoft.github.io/OSIsoft-Adapter-OPC-UA-Docs/V1/Configuration/OSIsoft%20Adapter%20for%20OPC%20UA%20data%20selection%20configuration.html) and [PI Adapter for Modbus TCP data selection configuration](https://osisoft.github.io/OSIsoft-Adapter-Modbus-Docs/V1/Configuration/OSIsoft%20Adapter%20for%20Modbus%20TCP%20data%20selection%20configuration.html)|
|```edgecmd Configuration <componentId> Logging``` | Configure logging for a component. | ```edgecmd Configuration OpcUa1 Logging``` |

## Configuration with JSON files

| edgecmd command | Description | Examples |
|-----------------|-------------|----------|
| ```edgecmd Configuration file=<PathToJsonFile>``` | Import a bulk configuration through a JSON file. | ```edgecmd Configuration file="~/Bulk_Storage_Runtime.json"```|
| ```edgecmd Configuration <componentId> <facetName> file=<PathToJsonFile>``` | Import a facet specific configuration file for a component. | ```edgecmd Configuration Modbus1 DataSource file="~/System_Logging.json"```|

## Administration

| edgecmd command | Description | Examples |
|-----------------|-------------|----------|
| ```edgecmd Administration <componentId> Stop``` | Stops a component. Only applicable for adapter type components. | ```edgecmd Administration Modbus1 Stop```|
| ```edgecmd Administration <componentId> Start``` | Starts a component. Only applicable for adapter type components. | ```edgecmd Administration Modbus1 Start```|
