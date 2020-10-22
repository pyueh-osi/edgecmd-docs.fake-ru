---
uid: RetrieveEdgeCmdUtilityHelp1-1-unreleased
---

# Retrieve EdgeCmd utility help

The EdgeCmd utility provides instructions on how to use EdgeCmd utility.

**Note:** The examples in this topic are using the default port number `5590`. If you specified a different port number for your adapter, you need to add it in the command. For example:

```cmd
edgecmd -help -port=5591 Configuration <RestOfTheCommand>
```

**Note:** If a command contains slashes, you must escape them as follows:<br> 
  - In *Windows*, add a second slash.<br> 
       Example: `TestUser\OilCompany` becomes `TestUser\\OilCompany`

  - In *Linux*, add three slashes.<br>
       Example: `TestUser\OilCompany` becomes `TestUser\\\\OilCompany`

## View general help instructions

Complete the following steps to view help instructions on how to use the Edgecmd utility:

1. Access EdgeCmd utility through the command line.
2. Type the following in the command line and press Enter.

    ```cmd
    edgecmd -help
    ```

## View component help instructions

Complete the following steps to view help instructions for configuration of a registered component that the adapter supports:

1. Access EdgeCmd utility through the command line.
2. Type the following in the command line, replacing `<componentId>` with the value that you want, and press Enter.

   ```cmd
   edgecmd -help Configuration <componentId>
   ```

 Under [Examples](#examples), see **Configuration help for the System component**.

  **Note:** The help output also provides examples of commands that you can run to configure the component.

## View component facet help instructions

Complete the following steps to view configuration help instructions for a specific facet within a component that the adapter supports:

1. Access EdgeCmd utility through the command line.
2. Type the following in the command line, replacing `<componentId>` and `<facetName>` with the value that you want, and press Enter.

   ```cmd
   edgecmd -help Configuration <componentId> <facetName>
   ```

 Under [Examples](#examples), see **Configuration help for the buffering facet within the System component**.

### Examples

<details>
    <summary>Configuration help for the System component</summary>
    <pre>

    edgecmd -help Configuration System

    -------------------------------------------------------------------------------------------------
    Component System command-line options => 'Logging'
    -------------------------------------------------------------------------------------------------
    LogLevel                    [Required] Desired log level settings. Options: Verbose, Information, Warning, Error, Fatal.
    LogFileSizeLimitBytes       [Required] Maximum size in bytes of log files that the service will create for this component. Must be no less than 1000.
    LogFileCountLimit           [Required] Maximum number of log files that the service will create for this component. Must be a positive integer.

    Example: .\edgecmd Configuration System Logging LogLevel=Warning
    Example: .\edgecmd Configuration System Logging LogFileSizeLimitBytes=32768
    Example: .\edgecmd Configuration System Logging LogFileCountLimit=5


    -------------------------------------------------------------------------------------------------
    Component System command-line options => 'HealthEndpoints'
    -------------------------------------------------------------------------------------------------
    Id                           [Optional] Id of existing configuration to be edited of removed.
    Endpoint                     [Required] URL of OMF destination
    UserName                     [Required group 1]  User name used for authentication to PI Web API OMF endpoint.
    Password                     [Required group 1]  Password used for authentication to PI Web API OMF endpoint.
    ClientId                     [Required group 2]  Client ID used for authentication to OSIsoft Cloud Services.
    ClientSecret                 [Required group 2]  Client Secret used for authentication to OSIsoft Cloud Services.
    TokenEndpoint                [Optional group 2] URL of OMF destinations token service.
    ValidateEndpointCertificate  [Optional] If true, endpoint certificate is validated (recommended). If false, any endpoint certificate is accepted. OSIsoft strongly recommends using disabled endpoint certificate validation for testing purposes only.

    Note: Only one Required group must be specified. Group 1 for PI Web API or Group 2 for OCS.
    Example:
    Add a new endpoint:
      .\edgecmd.exe Configuration System HealthEndpoints Endpoint=endpointURL UserName=UserName Password=Password
    Update fields of an existing endpoint:
      .\edgecmd.exe Configuration System HealthEndpoints Id=Endpoint1 Password=newPassword
    View existing endpoints:
      .\edgecmd.exe Configuration System HealthEndpoints
    File Import (replaces current endpoints):
      .\edgecmd.exe Configuration System HealthEndpoints File=endpoints.json
    Delete an endpoint:
      .\edgecmd.exe Configuration System HealthEndpoints Id=Endpoint1 Delete

    -------------------------------------------------------------------------------------------------
    Component System command-line options => 'Components'
    -------------------------------------------------------------------------------------------------
    ComponentId                        [Required] ID of the hosted component.
    ComponentType                      [Required] Type of the hosted component.

    Example: .\edgecmd Configuration System Components ComponentId=Modus1 ComponentType=Modbus

 </pre>
</details>

<details>
    <summary>Configuration help for the Buffering facet within the System component</summary>
    <pre>

    edgecmd -help Configuration System Buffering

    ---------------------------------------------------------------------------------------------------------
    Component System command-line options => 'Buffering'
    ---------------------------------------------------------------------------------------------------------
    BufferLocation                 Location of the on-disk buffers
    MaxBufferSizeMB                Maximum size of the on-disk buffers (-1 = restricted only by available free disk space)
    EnableBuffering                Enable or disable buffering

 </pre>
</details>
