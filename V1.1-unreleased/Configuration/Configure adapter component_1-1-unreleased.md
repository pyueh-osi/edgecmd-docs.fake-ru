---
uid: ConfigureAdapterComponent1-1-unreleased
---

# Configure adapter component

Use EdgeCmd utility to add and delete adapter components, and to configure facets of the components.

**Note:** The examples in this topic are using the default port number `5590`. If you specified a different port number for your adapter, you need to add it in the command. For example:

```cmd
edgecmd -port=5591 Configuration <RestOfTheCommand>
```

**Note:** If a command contains slashes, you must escape them as follows:<br> 
  - In *Windows*, add a second slash.<br> 
       Example: `TestUser\OilCompany` becomes `TestUser\\OilCompany`

  - In *Linux*, add three slashes.<br>
       Example: `TestUser\OilCompany` becomes `TestUser\\\\OilCompany`

## Add components

Complete the following steps to add a new component:

1. Access EdgeCmd utility through the command line.
2. Type the following in the command line, replacing `<componentId>` and `<componentType>` with the values for the component and press Enter.

	**Note:** The only valid component type is the adapter type. For example, if you are trying to register a new Modbus component, use `Modbus` and if you are trying to register an OPC UA component, use `OpcUa`. Refer to the specific adapter's user guide for the adapter's component type.

	```cmd
	edgecmd Configuration System Components componentId=<componentId> componentType=<componentType>
	```

	**Example**: Modbus adapter component registration

	```cmd
	edgecmd Configuration System Components componentId=Modbus1 componentType=Modbus
	```

## Configure a facet of a component

Adapters have the following configurable facets: data source, data selection, and logging. Complete the following steps to configure a facet:

1. Access EdgeCmd utility through the command line.
2. Type the following in the command line, replacing `<componentId>` and `<facetName>` with the values that you want.

	```cmd
	edgecmd Configuration <componentId> <facetName>
	```

3. Add key=value pairs to specify the values to change and press Enter.

	**Example**: Configuration of the data source facet of a Modbus adapter

	```cmd
	edgecmd Configuration Modbus1 DataSource IpAddress=117.23.45.110 port=502 ConnectTimeout=15000 StreamIdPrefix="DataSource1"
	```

For detailed information on how to configure each adapter, see the respective adapter documentation.

## Delete a component

Complete the following steps to delete a component from the adapter:

1. Access EdgeCmd utility through the command line.
2. Type the following in the command line, replacing `<componentId>` with the ID of the component to delete, and press Enter.

	```cmd
	edgecmd Configuration System Components id=<componentId> delete
	```

**Note:** You cannot delete the Egress component because it is required for Edge Data Store to operate.
