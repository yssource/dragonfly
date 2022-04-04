
## Before you begin you need to run the following:
1. git clone https://github.com/redis/redis.git
2. git checkout origin/7.0
3. comment out https://github.com/redis/redis/blob/7.0/tests/support/server.tcl#L352 (#r function flush)
4. ./dragonfly --logtostderr  -port 6379 --vmodule=main_service=2

## Run individual tests

./runtest --host localhost --port 6379 --tags -cluster:skip --ignore-encoding --quiet --singledb --single unit/type/string --skiptest SETNX --skiptest GETEX --skiptest GETDEL --skiptest SETBIT --skiptest GETBIT --skiptest "Extended SET" --skiptest LCS 

./runtest --host localhost --port 6379 --tags -cluster:skip --ignore-encoding --quiet --singledb --single unit/type/incr --skiptest "INCR uses shared objects" --skiptest "INCR can modify objects" --skiptest INCRBYFLOAT --skiptest "No negative zero" --skiptest "string to double with null terminator"

./runtest --host localhost --port 6379 --tags -cluster:skip --ignore-encoding --ignore-digest --quiet --singledb --single unit/type/set --skiptest SMISMEMBER --skiptest "DEBUG RELOAD" --skiptest SINTERCARD --skiptest SRANDMEMBER --skiptest WATCH --skiptest "SMOVE only notify dstset when the addition is successful"






## issues that needs to be resolved
./runtest --host localhost --port 6379 --tags -cluster:skip --ignore-encoding --quiet --singledb --single unit/type/string --only "SETRANGE against non-existing key"

./runtest --host localhost --port 6379 --tags -cluster:skip --ignore-encoding --quiet --singledb --single unit/type/string --only "Very big payload random access"

./runtest --host localhost --port 6379 --tags -cluster:skip --ignore-encoding --quiet --singledb --single unit/type/string --only GETRANGE

./runtest --host localhost --port 6379 --tags -cluster:skip --ignore-encoding --quiet --singledb --single unit/type/incr --only "DECRBY negation overflow"

./runtest --host localhost --port 6379 --tags -cluster:skip --ignore-encoding --ignore-digest --quiet --singledb --single unit/type/set --only "SADD an integer larger than 64 bits"

./runtest --host localhost --port 6379 --tags -cluster:skip --ignore-encoding --ignore-digest --quiet --singledb --single unit/type/set --only SRANDMEMBER

./runtest --host localhost --port 6379 --tags -cluster:skip --ignore-encoding --ignore-digest --quiet --singledb --single unit/type/set --only "SDIFF against non-set should throw error"

./runtest --host localhost --port 6379 --tags -cluster:skip --ignore-encoding --ignore-digest --quiet --singledb --single unit/type/set --only "SDIFFSTORE against non-set should throw error"

./runtest --host localhost --port 6379 --tags -cluster:skip --ignore-encoding --ignore-digest --quiet --singledb --single unit/type/set --only "SINTER against non-set should throw error"