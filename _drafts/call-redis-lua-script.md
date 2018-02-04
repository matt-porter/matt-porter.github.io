Calling a Lua script in Redis is pretty straightforward. As describe in the [Redis docs][redis-docs-lua],
you need to register the Lua script with Redis, and then call it with the arguments it's expecting and
any keys that it may use.

