## Before you begin you need to run the following:
1. git clone -b jedis-3.2.0 https://github.com/redis/jedis.git .
2. cd jedis

# Run individual tests
mvn test -Dtest="AllKindOfValuesCommandsTest,!AllKindOfValuesCommandsTest#restoreReplace+flushAll+flushDB+keys+move+persist+pexpire+pttl+randomKey+renamenx+swapDB+touch+dumpAndRestore"
mvn test -Dtest="BinaryValuesCommandsTest,!BinaryValuesCommandsTest#msetnx+setnx+substr"
mvn test -Dtest="BitCommandsTest,!BitCommandsTest#setAndgetrange+bitCount+bitOp+bitOpNot+bitpos+bitposBinary+bitposWithNoMatchingBitExist+bitposWithNoMatchingBitExistWithinRange+setAndgetbit+testBinaryBitfield+testBitfield"
mvn test -Dtest="ConnectionHandlingCommandsTest"
mvn test -Dtest="ControlCommandsTest,!ControlCommandsTest#bgrewriteaof+clientPause+configSet+configGet+memoryDoctorBinary+memoryDoctorString+monitor+waitReplicas"
mvn test -Dtest="HashesCommandsTest,!HashesCommandsTest#hdel+hexists+hgetAll+hgetAllPipeline+hincrByFloat+hkeys+hlen+hmget+hmset+hscan+hscanCount+hscanMatch+hvals+testBinaryHstrLen+testHstrLen"
mvn test -Dtest="ListCommandsTest,!ListCommandsTest#brpoplpush+brpop+linsert+rpoplpush"
mvn test -Dtest="ScriptingCommandsTest"
mvn test -Dtest="SetCommandsTest,!SetCommandsTest#srandmember"
mvn test -Dtest="StringValuesCommandsTest,!StringValuesCommandsTest#incrByFloat+msetnx+setnx+substr"
mvn test -Dtest="TransactionCommandsTest,!TransactionCommandsTest#discard+select+testCloseable+testResetStateWhenInMulti+testResetStateWhenInWatch+unwatch+unwatchWithinMulti+watch"
mvn test -Dtest="VariadicCommandsTest,!VariadicCommandsTest#hdel"


# issues that needs to be resolved
mvn test -Dtest="AllKindOfValuesCommandsTest#psetex+scanMatch"
mvn test -Dtest="BitCommandsTest#setAndgetrange"
mvn test -Dtest="ControlCommandsTest#debug"
mvn test -Dtest="ControlCommandsTest#bgsave"
mvn test -Dtest="HashesCommandsTest#hincrBy+hsetnx+testHstrLen_EmptyHash"
mvn test -Dtest="ListCommandsTest#lset"
mvn test -Dtest="ScriptingCommandsTest#evalMultiBulk"
mvn test -Dtest="ScriptingCommandsTest"
mvn test -Dtest="SetCommandsTest#sdiffstore"
mvn test -Dtest="SetCommandsTest#spopWithCount"
mvn test -Dtest="SetCommandsTest#sscanCount+sscanMatch"
mvn test -Dtest="TransactionCommandsTest#testResetStateWhenInMultiWithinPipeline"

# Not implemented at all
mvn test -Dtest="ClientCommandsTest"
mvn test -Dtest="ClusterBinaryJedisCommandsTest"
mvn test -Dtest="ClusterCommandsTest"
mvn test -Dtest="ClusterScriptingCommandsTest"
mvn test -Dtest="GeoCommandsTest"
mvn test -Dtest="HyperLogLogCommandsTest"
mvn test -Dtest="MigrateTest"
mvn test -Dtest="ObjectCommandsTest"
mvn test -Dtest="PublishSubscribeCommandsTest"
mvn test -Dtest="SlowlogCommandsTest"
mvn test -Dtest="SortedSetCommandsTest"
mvn test -Dtest="SortingCommandsTest"
mvn test -Dtest="StreamsCommandsTest"
