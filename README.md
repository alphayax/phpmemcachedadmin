# PHPMemcachedAdmin

### Graphic stand-alone administration for memcached to monitor and debug purpose

This program allows to see in **real-time** (top-like) or from the start of the server, **stats for get, set, delete, increment, decrement, evictions, reclaimed, cas command**, as well as **server stats** (network, items, server version) with googlecharts and  **server internal configuration**

You can go further to **see each server slabs, occupation, memory wasted and items** (**key & value**).

Another part can execute commands to any memcached server : get, set, delete, flush\_all, as well as execute any commands (like stats) with telnet

## Feature list

### Statistics
- Stats for each or all memcached servers, items, evicted, reclaimed ...<br>
- Stats for every command : set, get, delete, incr, decr, cas ...
- Slabs stats (Memory, pages, memory wasted, items)<br>
- Items stats (View items in slabs, then data for each key)<br>
- Network stats (Traffic, bandwidth)</li></ul>

### Commands
- Execute commands : get, set, delete, flush_all on servers to administrate or debug it<br>
- Get data with key on servers<br>
- Delete keys on servers<br>
- Flush servers<br>
- Execute telnet command directly from phpMemcachedAdmin<br>
- Search for specific pattern into all keys</li></ul>

### Live Stats
- Top-like real time stats with configurable alerts</li></ul>


### Configuration
- Edit configuration directly from web page<br>
- phpMemcachedAdmin can use socket communication, PECL Memcache or Memcached API<br>
- Organize your servers into cluster</li></ul>

## Security

phpMemcachedAdmin does not provide any security system, you need to add this feature by yourself.

## Usage

### How to use this image

```bash
docker run \
    -p 80:80 \
    -v <path_to_config>:/var/www/html/Config/Memcache.php \
    --name phpmemcachedadmin \
    alphayax/phpmemcachedadmin
```

### Example of config file

```php
<?php
return array (
  'stats_api' => 'Server',
  'slabs_api' => 'Server',
  'items_api' => 'Server',
  'get_api' => 'Server',
  'set_api' => 'Server',
  'delete_api' => 'Server',
  'flush_all_api' => 'Server',
  'connection_timeout' => '1',
  'max_item_dump' => '100',
  'refresh_rate' => 2,
  'memory_alert' => '80',
  'hit_rate_alert' => '90',
  'eviction_alert' => '0',
  'file_path' => 'Temp/',
  'servers' => 
  array (
    'Default' => 
    array (
      '127.0.0.1:11211' => 
      array (
        'hostname' => '127.0.0.1',
        'port' => '11211',
      ),
      '127.0.0.2:11211' => 
      array (
        'hostname' => '127.0.0.2',
        'port' => '11211',
      ),
      '127.0.0.3:11211' => 
      array (
        'hostname' => '127.0.0.1',
        'port' => '11211',
      ),
      '127.0.0.4:11211' => 
      array (
        'hostname' => '127.0.0.1',
        'port' => '11211',
      ),
    ),
  ),
);
```

## More 

More information in https://blog.elijaa.org/phpmemcachedadmin-installation-guide/
