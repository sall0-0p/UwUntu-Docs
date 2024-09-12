---
title: ContentProvider
layout: default
parent: Services
has_children: false
---

# ContentProvider
service
{: .label .laber-notinline .label-dark}
internal
{: .label .laber-notinline .label-dark}

```lua
System.getContentProvider();
```

The central place for requesting all Services, Classes, Libraries and other content among system.
Allows content registration and lazy loading files into the system.
Many more features are planned for ContentProvider in future.

See more:

- [service.yml](http://127.0.0.1:4000/api-reference/services/ContentProvider/service.html)
- [class.yml](http://127.0.0.1:4000/api-reference/services/ContentProvider/class.html)

| Returns | Method | Description |
|:-----------:|:-----------:|:-----------:|
| void | [register(configPath, packagePath)](https://sall0-0p.github.io/UwUntu-Docs/api-reference/services/ContentProvider/ContentProvider.html#registerconfigpath-packagepath) | Manually register package at custom package path. |
| void | [registerRecursively(path)](https://sall0-0p.github.io/UwUntu-Docs/api-reference/services/ContentProvider/ContentProvider.html#registerrecursivelypath) | Registers all found packages inside of directory recursively. |
| table? | [get(packagePath)](https://sall0-0p.github.io/UwUntu-Docs/docs/api-reference/services/ContentProvider/ContentProvider.html#getpackagepath) | Tries to retrieve package with determined package path. |

## `register(configPath, packagePath)`
{: .divider}
Returns true if this map contains a mapping for the specified key.

**Parameters**

1. `key: string` - path to package config file stored in `.yml` format
2. `packagePath: path` - string that will be used to request your package in future using [`get`]()

## `registerRecursively(path)`
{: .divider}
Goes thru every child in the file system of defined path and registers packages found. Packages are defined by either `class.yml` or `service.yml`.

**Parameters**

1. `path` - path whose children are to be registered.

## `get(packagePath)`
{: .divider}
Returns contents of package on certain path, or throws error if such package does not exist.

**Parameters**

1. `packagePath` - package to be requested

**Returns**

1. `table?` - contents of a package, or nil if not found
