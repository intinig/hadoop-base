# Hadoop Learning Project

This repository documents my journey in learning and experimenting with Apache Hadoop. It contains configuration files and scripts for setting up a local Hadoop cluster using Docker, as well as various Hadoop-related projects and exercises.

## Current Contents

- `docker-compose.yaml`: Docker Compose file for setting up a local Hadoop cluster
- `config`: Configuration file for Hadoop services

## Setup Instructions

1. Ensure you have Docker and Docker Compose installed on your system.

2. Clone this repository:

```bash
git clone https://github.com/intinig/hadoop-base.git
cd hadoop-base
```

3. Create necessary directories on the host machine:

```bash
sudo mkdir -p /mnt/data/hadoop/namenode /mnt/data/hadoop/datanode /mnt/data/hadoop/nodemanager
sudo chown -R 1000:1000 /mnt/data/hadoop
sudo chmod -R 755 /mnt/data/hadoop
```

4. Start the Hadoop cluster:

```bash
docker compose up -d
```

5. Verify the cluster is running:

```bash
docker-compose ps
```

6. Access the web interfaces:
- NameNode: http://localhost:9870
- ResourceManager: http://localhost:8088

## Running Examples

To run the Pi calculation example:

1. Enter the namenode container:

```bash
docker compose exec namenode bash
```

2. Run the Pi job:

```bash
yarn jar $HADOOP_HOME/share/hadoop/mapreduce/hadoop-mapreduce-examples-*.jar pi 10 100
```

## Future Plans

This repository will be updated with:
- Custom MapReduce jobs
- Hadoop ecosystem tool configurations (Hive, Pig, HBase)
- Data processing workflows
- Notes and learnings from Hadoop studies

## Contributing

This is a personal learning project, but suggestions and advice are welcome. Feel free to open an issue or submit a pull request.

## License

This project is open source and available under the [MIT License](LICENSE).
