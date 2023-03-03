## Geth로 Private Network 구축
### Geth 설치
```
sudo apt-get update
sudo apt-get install software-properties-common
sudo add-apt-repository -y ppa:ethereum/ethereum
sudo apt-get install ethereum


mkdir -p dev/eth_localdata
cd dev/eth_localdata
```

### 네트워크 초기 설정
``` $ vi genesis.json ```
genesis.json 파일

  ```
  {
          "config": {
            "chainId": 921,
            "homesteadBlock": 0,
        	  "eip150Block": 0,
            "eip155Block": 0,
            "eip158Block": 0
          },
          "difficulty": "0x10",
          "gasLimit": "9999999",
          "extraData": "0x",
          "nonce": "0xdeadbeefdeadbeef",
          "alloc": {
            "주소": { "balance": "300000" }
          }
        }
  ```

  ``` geth --datadir ~/dev/eth_localdata init ~/dev/eth_localdata/genesis.json ```
