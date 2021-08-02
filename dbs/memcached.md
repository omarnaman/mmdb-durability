# Memcached
A distributed memory object caching system used for small arbitrary data (strings, objects)

# Data
The data stored in Memcached servers is a simple key:object pair, where the object is raw binary data. Memcached does not have support for data structures and the clients is required to serialize all objects before storing them

# Durability
This is a caching service that does not guarantee any durability on it's own