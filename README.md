# Wazuh-Docker-NewCluster
Separation of wazuh Multi-node in docker mode and creation of new Workers node and indexer on separate servers to balance agents and logs horizontally.

I took a default wazuh-muti-node that is downloaded directly from the installation via docker and removed everything related to wazuh.worker and wazuh3.indexer in order to be able to upload as many Worker+Indexers horizontally as I could to take the overhead that I was having it on my server that has only 16gb of memory.

This experiment was necessary due to the high demand for logs that siem was receiving from the 300 servers we have connected to, leaving the wazuh.indexer containers at a maximum load of 4gb each, creating swap for the local disk and making wazuh very slow in a all.
