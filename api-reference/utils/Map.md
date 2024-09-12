---
title: Map
layout: default
parent: Utils
---

# Map
class
{: .label .laber-notinline .label-dark}

```lua
ContentProvider.get("Utils.Map");
```

An object that maps keys to values. Cannot contain duplicate keys, and one key is mapped to one value.
Values and keys can be of different types.

Map is basically a wrapper for standard lua table, but provides some additional utility methods and changes to iteration in loops to simplify code and remove `pairs()` boilerplate.

| Returns | Constructor | Description |
|:-----------:|:-----------:|:-----------:|
| Map | [Map()](https://sall0-0p.github.io/UwUntu-Docs/api-reference/utils/Map.html#map-1) | Creates empty Map. |
| Map | [Map(table)](https://sall0-0p.github.io/UwUntu-Docs/api-reference/utils/Map.html#maptable) | Creates Map with values from standard Lua table. |

| Returns | Method | Description |
|:-----------:|:-----------:|:-----------:|
| void | [clear()](https://sall0-0p.github.io/UwUntu-Docs/api-reference/utils/Map.html#clear) | Removes all mappings present in the Map. |
| void | [isEmpty()](https://sall0-0p.github.io/UwUntu-Docs/api-reference/utils/Map.html#isempty) | Removes all mappings present in the Map. |
| V? | [compute(key, remappingFunction)](https://sall0-0p.github.io/UwUntu-Docs/api-reference/utils/Map.html#isempty) | Modifies value of certain key with provided function. |
| V? | [computeIfAbsent(key, remappingFunction)](https://sall0-0p.github.io/UwUntu-Docs/api-reference/utils/Map.html#computeifabsentkey-mappingfunctionk-v) | Assings value to certain key using provided function, but only if it is does not have value already assigned. |
| V? | [computeIfPresent(key, remappingFunction)](https://sall0-0p.github.io/UwUntu-Docs/api-reference/utils/Map.html#computeifabsentkey-mappingfunctionk-v) | Assings value to certain key using provided function, but only if it already has value already assigned. |
| boolean | [containsKey(key)](https://sall0-0p.github.io/UwUntu-Docs/api-reference/utils/Map.html#containskeykey) | Returns true if this map contains a mapping for the specified key. |
| boolean | [containsValue(value)](https://sall0-0p.github.io/UwUntu-Docs/api-reference/utils/Map.html#containsvaluevalue) | Returns true if this map maps one or more keys to the specified value. |
| boolean | [equals(map)](https://sall0-0p.github.io/UwUntu-Docs/api-reference/utils/Map.html#equalsmap) | Tests if Map provided has same mappings as your map. |
| void | [forEach(action)](https://sall0-0p.github.io/UwUntu-Docs/api-reference/utils/Map.html#foreachaction) | Performs the given action for each entry in this map. |
| V? | [get(key)](https://sall0-0p.github.io/UwUntu-Docs/api-reference/utils/Map.html#getkey) | Returns the value to which the specified key is mapped. |
| V? | [put(key, value)](https://sall0-0p.github.io/UwUntu-Docs/api-reference/utils/Map.html#putkey-value) | Associates the specified value with the specified key in this map. |
| void | [putAll(map)](https://sall0-0p.github.io/UwUntu-Docs/api-reference/utils/Map.html#putallmap) | Copies all of the mappings from the specified map to this map. |
| V? | [putIfAbsent(key, value)](https://sall0-0p.github.io/UwUntu-Docs/api-reference/utils/Map.html#putifabsentkey-value) | If the key is not already mapped to a value mapps it to the given value. |
| V? | [remove(key)](https://sall0-0p.github.io/UwUntu-Docs/api-reference/utils/Map.html#removekey) | Removes the mapping for a key from this map if it is present. |
| boolean | [remove(key, value)](https://sall0-0p.github.io/UwUntu-Docs/api-reference/utils/Map.html#removekey-value) | Removes the mapping for a key from this map if it is matches value provided. |
| boolean | [replace(key, value)](https://sall0-0p.github.io/UwUntu-Docs/api-reference/utils/Map.html#replacekey-value) | Replaces entry only if it is already mapped to specific value. |
| boolean | [replaceAll(mappingFunction)](https://sall0-0p.github.io/UwUntu-Docs/api-reference/utils/Map.html#replaceallmappingfunctionk-v) | Replaces each entry’s value with the result of invoking the given function on that entry. |
| table | [getKeys()](https://sall0-0p.github.io/UwUntu-Docs/api-reference/utils/Map.html#getkeys) | Returns all keys that are mapped to values in this map. |
| table | [getValues()](https://sall0-0p.github.io/UwUntu-Docs/api-reference/utils/Map.html#getvalues) | Returns all values that are mapped to keys in this map. |

{: .note}
> **🔄 Iterating with Maps**
> {: .note-title}
> 
> Maps support iteration with pairs using `for` loops, or `forEach` method.
> ```lua
> local map = Map(someTable)
> 
> for key, value in map do
>   print(string.format("%s : %s", key, value))
> end
> --> key1 : value1
> --> key2 : value2
> --> key3 : value3
> ```

## `Map()`
{: .divider}
constructor
{: .label .laber-notinline .label-dark}

**Return values**

1. `Map` - object created.

## `Map(table)`
{: .divider}
constructor
{: .label .laber-notinline .label-dark}
Returns `Map` object with data from `table`.

**Parameters**

1. `table` standard Lua table in dictionary form.

**Return values**

1. `Map` - object created.

## `clear()`
{: .divider}
Removes all mappings from the this map.

## `isEmpty()`
{: .divider}
Returns true if this map contains no key-value mappings.

**Return values**

1. `boolean` - true if there are no mappings in this table
   
## `size()`
{: .divider}
Returns the number of key-value mappings in this map.

**Return values**

1. `number` - amount of key-value mappings in this map

## `compute(key, mappingFunction<K, V>)`
{: .divider}
Attempts to compute a mapping for the specified key and its current mapped value (or nil if there is no current mapping).

**Parameters**

1. `key` - key to compute mapping for.
2. `mappingFunction<K, V>` - function used to compute a mapping, accepts key and value, returns value.

**Return values**

1. `V` - value computed.


## `computeIfAbsent(key, mappingFunction<K, V>)`
{: .divider}
If the specified key is not already associated with a value (or is mapped to nil), attempts to compute its value using the given mapping function and enters it into this map unless nil.

**Parameters**

1. `key` - key to compute mapping for.
2. `mappingFunction<K>` - function used to compute a mapping, accepts only key.

**Return values**

1. `V?` - value computed.
   
## `computeIfPresent(key, mappingFunction<K, V>)`
{: .divider}
If the value for the specified key is present, attempts to compute a new mapping given the key and its current mapped value.

**Parameters**

1. `key` - key to compute mapping for.
2. `mappingFunction<K, V>` - function used to compute a mapping, accepts only key.

**Return values**

1. `V?` - value computed.

## `containsKey(key)`
{: .divider}
Returns true if this map contains a mapping for the specified key.

**Parameters**

1. `key` - key whose presence in this map is to be tested.

**Return values**

1. `boolean` - `true` if key is present, `false` if it is missing.

## `containsValue(value)`
{: .divider}
Returns true if this map maps one or more keys to the specified value.

**Parameters**

1. `value` - value whose presence in this map is to be tested.

**Return values**

1. `boolean` - `true` if this map maps one or more keys to the specified value.

## `equals(map)`
{: .divider}
Tests if Map provided has same mappings (key and value combinations) as your map.

**Parameters**

1. `Map` - the map to check for equality.

**Return values**

1. `boolean` - true if mappings are the same, false otherwise.
   
## `forEach(action)`
{: .divider}
Performs the given action for each entry in this map until all entries have been processed or the action errors.

```lua
-- Example for alternate way of iterating for you, JavaScript guys ☕️🗿
local map = Map(someTable)

map.forEach(function(key, value) 
  print(string.format("%s : %s", key, value))
end)

--> key1 : value1
--> key2 : value2
--> key3 : value3
```

**Parameters**

1. `action<K, V>` - the `function` that runs for every mapping in a map.

## `get(key)`
{: .divider}
Returns the value to which the specified key is mapped, or nil if this map contains no mapping for the key.

{: .important}
> You can still use standard lua method of getting data from a table.
> ```lua
> local map = Map(someTable);
> map.key1 = "value1";
> print(map.key1); --> value1
> ```

**Parameters**

1. `key` - the key whose associated value is to be returned.

**Return values**

1. `V?` - the value to which the specified key is mapped, or null if this map contains no mapping for the key.

## `put(key, value)`
{: .divider}
Associates the specified value with the specified key in this map.

{: .important}
> You can still use standard lua method of setting data to the table.
> ```lua
> local map = Map(someTable);
> map.key1 = "value1";
> print(map.key1); --> value1
> ```

**Parameters**

1. `key` - key with which the specified value is to be associated
2. `value` - value to be associated with the specified key

**Return values**

1. `V?` - the previous associated value with key, or nil if there was no previously associated value with a key.

## `putAll(map)`
{: .divider}
Copies all of the mappings from the specified map to this map.

**Parameters**

1. `map` - the map to copy mappings from.

## `putIfAbsent(key, value)`
{: .divider}
If the specified key is not already associated with a value associates it with the given value and returns nil, else returns the current value.

**Parameters**

1. `key` - key with which the specified value is to be associated
2. `value` - value to be associated with the specified key

**Return values**

1. `V?` - the previous value associated with a key, or nil if there was no mapping for a key

## `remove(key)`
{: .divider}
Removes the mapping for a key from this map if it is present, if so - returns previous held value.

**Parameters**

1. `key` - key with which the specified value is associated 

**Return values**

1. `V?` - the previous value associated with key, or null if there was no mapping for key

## `remove(key, value)`
{: .divider}
Removes the entry for the specified key only if it is currently mapped to the specified value.

**Parameters**

1. `key` - key with which the specified value is associated 
2. `value` - value expected to be associated with the specified key

**Return values**

1. `boolean` - true if the value was removed
   
## `replace(key, value)`
{: .divider}
Replaces entry only if it is already mapped to specific value, returns true if value was replaced

**Parameters**

1. `key` - key with which the specified value is associated 
2. `value` - value expected to replace previous value with

**Return values**

1. `boolean` - true if the value was replaced

## `replaceAll(mappingFunction<K, V>)`
{: .divider}
Replaces each entry's value with the result of invoking the given function on that entry until all entries have been processed or function errored.

**Parameters**

1. `mappingFunction<K, V>` - function used to be called to get new value, accepts key and value, returns value.

## `getKeys()`
{: .divider}
Returns all keys that are mapped to values in this map.

**Return values**

1. `table` - contains all keys mapped to values

## `getValues()`
{: .divider}
Returns all values that are mapped to keys in this map.

**Return values**

1. `table` - contains all values mapped to keys