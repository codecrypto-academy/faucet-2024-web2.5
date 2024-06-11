```bash
docker run -d --rm \
  -v ./pwd.txt:/p.txt \
  -v ./datos:/data \
  -p  5556:8545 \
  ethereum/client-go:latest  \
 --datadir /data \
 --unlock e29d05b0e166d5e5fb694a478984b7868e44d2db \
 --allow-insecure-unlock \
 --mine \
 --miner.etherbase e29d05b0e166d5e5fb694a478984b7868e44d2db \
 --password /p.txt \
 --nodiscover \
 --http \
 --http.addr "0.0.0.0" \
 --http.api "admin,eth,debug,miner,net,txpool,personal,web3" \
 --http.corsdomain "*" 
```

```bash
  docker run \
  -v ./genesis.json:/gen.json \
  -v ./datos:/data ethereum/client-go:latest \
  init --datadir /data /gen.json
```

```bash
docker run \ 
  -v ./pwd.txt:/p.txt \
  -v ./datos:/data \
  ethereum/client-go:latest \
  account new --datadir /data --password /p.txt
```