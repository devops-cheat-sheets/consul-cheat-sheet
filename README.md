# Consul Cheat Sheet
 

## Agent Commands

| Command | Description |
|---------|-------------|
| consul agent | Starts a Consul agent with default configuration. |
| consul agent -dev | Starts a development mode Consul agent, useful for local testing. |
| consul agent -config-file=<file> | Starts a Consul agent with the provided configuration file. |
| consul agent -data-dir=<dir> | Specifies the data directory for the Consul agent. |
| consul agent -enable-script-checks | Enables script-based health checks. |
| consul agent -join=<addr> | Specifies an address to join an existing Consul cluster. |
| consul agent -node=<name> | Specifies the node name for the Consul agent. |
| consul agent -bootstrap-expect=<n> | Specifies the number of server nodes to expect when bootstrapping a new cluster. |
| consul agent -ui | Starts the Consul agent with the UI enabled. |

## Catalog Commands

| Command | Description |
|---------|-------------|
| consul catalog datacenters | Lists the datacenters known to the Consul agent. |
| consul catalog nodes | Lists the nodes in the Consul cluster. |
| consul catalog services | Lists the services registered in the Consul cluster. |
| consul catalog service <service-name> | Lists the nodes providing a specific service. |
| consul catalog node <node-name> | Retrieves information about a specific node. |
| consul catalog service <service-name> -tag=<tag> | Lists the nodes providing a specific service with a given tag. |
| consul catalog connect -service=<service-name> | Retrieves the connection information for a service. |
| consul catalog connect -service=<service-name> -tag=<tag> | Retrieves the connection information for a service with a given tag. |

## Key-Value Commands

| Command | Description |
|---------|-------------|
| consul kv put <key> <value> | Sets the value of a key in the key-value store. |
| consul kv get <key> | Retrieves the value of a key from the key-value store. |
| consul kv delete <key> | Deletes a key from the key-value store. |
| consul kv list <prefix> | Lists all keys with a given prefix from the key-value store. |
| consul kv export | Exports all key-value pairs from the key-value store. |
| consul kv import <file> | Imports key-value pairs from a file into the key-value store. |
| consul kv get -recurse | Retrieves all keys and values from the key-value store. |
| consul kv delete -recurse | Deletes all keys and values from the key-value store. |

## Service Commands

| Command | Description |
|---------|-------------|
| consul services register <service-config> | Registers a new service with Consul using the provided configuration. |
| consul services deregister <service-id> | Deregisters a service from Consul using its ID. |
| consul services list | Lists all services registered with Consul. |
| consul services list -service=<service-name> | Lists all instances of a specific service. |
| consul services health | Provides the health status of all services. |
| consul services health -service=<service-name> | Provides the health status of a specific service. |
| consul services maintenance <service-id> -enable | Puts a service into maintenance mode. |
| consul services maintenance <service-id> -disable | Takes a service out of maintenance mode. |

## ACL Commands

| Command | Description |
|---------|-------------|
| consul acl bootstrap | Generates the initial ACL tokens and policy for Consul. |
| consul acl policy create <name> <policy-file> | Creates a new ACL policy with the given name and policy file. |
| consul acl policy read <name> | Reads the details of a specific ACL policy. |
| consul acl policy update <name> <policy-file> | Updates an existing ACL policy with the given name and policy file. |

## Maintenance Commands

| Command | Description |
|---------|-------------|
| consul maintenance enable -reason=<reason> | Puts the Consul agent into maintenance mode with a specific reason. |
| consul maintenance disable | Takes the Consul agent out of maintenance mode. |
| consul maintenance status | Checks the maintenance status of the Consul agent. |

## Event Commands

| Command | Description |
|---------|-------------|
| consul event fire <event-name> | Fires a custom event with the given name. |
| consul event list | Lists all the events in the cluster. |
| consul event list -name=<event-name> | Lists all the instances of a specific event. |
| consul event fire -node=<node-name> <event-name> | Fires a custom event on a specific node. |
| consul event fire -service=<service-name> <event-name> | Fires a custom event on all instances of a specific service. |

## Consul Template Commands

| Command | Description |
|---------|-------------|
| consul-template -consul-addr=<addr> -template=<template-file>:<output-file> | Renders a template file using Consul data and writes the output to a file. |
| consul-template -consul-addr=<addr> -template=<template-file>:<output-command> | Renders a template file using Consul data and executes a command with the output. |
| consul-template -consul-addr=<addr> -template=<template-file>:<output-args> | Renders a template file using Consul data and passes the output as arguments to a command. |
| consul-template -config=<config-file> | Starts Consul Template using the provided configuration file. |

## Health Checking Commands

| Command | Description |
|---------|-------------|
| consul check list | Lists all health checks in the cluster. |
| consul check register <check-file> | Registers a new health check using the provided check definition file. |
| consul check deregister <check-id> | Deregisters a health check using its ID. |
| consul check ttl <check-id> <status> | Updates the status of a TTL-based health check. |
| consul check ttl <check-id> <status> <note> | Updates the status of a TTL-based health check with a note. |
| consul check http <url> <interval> | Registers an HTTP health check with the provided URL and interval. |
| consul check tcp <address> <interval> | Registers a TCP health check with the provided address and interval. |
| consul check script <script-file> <interval> | Registers a script-based health check with the provided script file and interval. |
| consul check http -header=<header> <url> <interval> | Registers an HTTP health check with a custom header. |

This cheat sheet provides a comprehensive list of commands for different aspects of HashiCorp Consul administration, including agent management, catalog management, key-value operations, service registration, ACL management, query execution, snapshot handling, network configuration, maintenance mode, event handling, Consul Template usage, health checking, and more.