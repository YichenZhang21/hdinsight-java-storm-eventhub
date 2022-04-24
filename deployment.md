
scp ./target/EventHubExample-1.0-SNAPSHOT.jar sshuser@storm-IoT-ssh.azurehdinsight.net:EventHubExample-1.0-SNAPSHOT.jar

scp dev.properties sshuser@storm-IoT-ssh.azurehdinsight.net:dev.properties

ssh sshuser@storm-IoT-ssh.azurehdinsight.net

password: Gatechteam18!

storm jar EventHubExample-1.0-SNAPSHOT.jar org.apache.storm.flux.Flux --remote -R /writer.yaml --filter dev.properties
storm jar EventHubExample-1.0-SNAPSHOT.jar org.apache.storm.flux.Flux --remote -R /reader.yaml --filter dev.properties

[https://storm-IoT.azurehdinsight.net/stormui](https://storm-IoT.azurehdinsight.net/stormui)


storm jar EventHubExample-1.0-SNAPSHOT.jar org.apache.storm.flux.Flux --remote -R /readtofile.yaml --filter dev.properties

hdfs dfs -ls /stormdata
hdfs dfs -text /stormdata/hdfs-bolt-5-0-1650771451571.txt
