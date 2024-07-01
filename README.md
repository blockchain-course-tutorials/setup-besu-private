# Step 1- Configuration and Setup process
## About

This first stage aims to verify the necessary requirements for the besu blockchain to function. In particular, pay attention to the installation of java and the besu binary.

## Requirements
- Ubuntu 20^
- 8 GB RAM
- Hyperledger Besu 24^
- Java 17

<details>
  <summary> If you don't know how instalation binary Besu, click here</summary>
  - JDK version 
  In your linux terminal, do
  
  ```sh
  which java
  ```
  Expected response
  ```
   /usr/bin/java
  ```
  
  -If note, Do:
  
  ```sh
  sudo apt update
  ```
  ```sh
  sudo apt install openjdk-17-jdk
  ```
 or 

```sh
sudo apt install default-jre default-jdk
```
 ### Testing again:
  ```sh
  which java
  ```
  Expected response
  ```
   /usr/bin/java
  ```
  If note, do
 
  ```sh
  echo 'export JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64' >> ~/.bashrc
  ```
  ```sh
  source ~/.bashrc
  ```
  And try again. 
   ```sh
  which java
  ```
  Expected response
  ```
   /usr/bin/java
  ```
  ### Installation BESU
  Choose the desired version. Pay attention to the version of java that is used. 
  
  
  ```sh
  https://besu.hyperledger.org/en/stable/private-networks/get-started/install/binary-distribution/
  ```
  ```sh
  https://github.com/hyperledger/besu/releases
  ```
  We're using version 21.10.4
  ```sh
  wget https://hyperledger.jfrog.io/artifactory/besu-binaries/besu/24.1.1/besu-24.1.1.zip
  ```
  ```sh
  unzip besu-24.1.1.zip
  ```
  Rename
  ```sh
  mv besu-24.1.1 besu  
  ```
  Test using:
  ```sh
  ls
  ```
  Output
  ```sh
  besu.autocomplete.sh  bin/  lib/  LICENSE  license-dependency.html
  ```
  Testing 
  ```sh
  besu -help
  ```
You will se something like:

```
Usage:

besu [OPTIONS] [COMMAND]

Description:

This command runs the Besu Ethereum client full node.

Options:
      --api-gas-price-blocks=<apiGasPriceBlocks>
                             Number of blocks to consider for eth_gasPrice
                               (default: 100)
      --api-gas-price-max=<apiGasPriceMax>
                             Maximum gas price for eth_gasPrice (default:
                               500000000000)
      --api-gas-price-percentile=<apiGasPricePercentile>
                             Percentile value to measure for eth_gasPrice
                               (default: 50.0)
      --auto-log-bloom-caching-enabled=<autoLogBloomCachingEnabled>
                             Enable automatic log bloom caching (default: true)
      --bonsai-historical-block-limit, 
        --bonsai-maximum-back-layers-to-load=<LONG>
                             Limit of historical layers that can be loaded with
                               BONSAI (default: 512).
 (.....) 

```
If note, try this:
  ```sh
  nano ~/.bashrc
  ```
  
  Add the following line at the end of the file, replacing "/path/to/besu/bin" with the actual path of the directory containing the Besu binary:
  ```sh
  export PATH=/thePath/besu/bin:$PATH
  ```
  ```sh
  source ~/.bashrc
  ```
</details>
