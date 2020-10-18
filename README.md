The chaincode for our paper "Consentio: Managing Consent to Data Access using Permissioned Blockchains" accepted at IEEE International Conference on Blockchain and Cryptocurrency (ICBC) 2020 

Please cite this paper if you use our code or system output.

```
@INPROCEEDINGS{9169432,  
author={R. R. {Agarwal} and D. {Kumar} and L. {Golab} and S. {Keshav}},  
booktitle={2020 IEEE International Conference on Blockchain and Cryptocurrency (ICBC)},   
title={Consentio: Managing Consent to Data Access using Permissioned Blockchains},   
year={2020},  
volume={},  
number={},  
pages={1-9},}
```

The full version of the paper is present on [[arXiv]](https://arxiv.org/pdf/1910.07110.pdf). We used the FastFabric implementation of Hyperledger Fabric for all our experiments.

Set of commands that need to be run to invoke the different chaincodes. 

The filename is Consentio_chaincode.go (for the IWS design). The other file is for the RWS design.

```
peer chaincode invoke -o orderer.example.com:7050 --tls --cafile /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/ordererOrganizations/example.com/orderers/orderer.example.com/msp/tlscacerts/tlsca.example.com-cert.pem -C $CHANNEL_NAME -n CHAINCODE_NAME -c '{"Args":["updateConsent", "2", "g","all", "20150101", "20160101","101", "hippa"]}'

peer chaincode invoke -o orderer.example.com:7050 --tls --cafile /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/ordererOrganizations/example.com/orderers/orderer.example.com/msp/tlscacerts/tlsca.example.com-cert.pem -C $CHANNEL_NAME -n CHAINCODE_NAME -c '{"Args":["updateRole","hippa", "all", "dc1","r"]}'

peer chaincode query -C $CHANNEL_NAME -n CHAINCODE_NAME -c '{"Args":["queryConsent", "{\"selector\":{}, \"use_index\":[\"_design/indexConsentDoc\", \"indexConsent\"]}"]}'

peer chaincode invoke -o orderer.example.com:7050 --tls --cafile /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/ordererOrganizations/example.com/orderers/orderer.example.com/msp/tlscacerts/tlsca.example.com-cert.pem -C $CHANNEL_NAME -n CHAINCODE_NAME -c '{"Args":["accessConsent","all", "20150101", "20160101","101", "hippa", "dc1"]}'

```

The 'queryConsent' command only works if the backend database is CouchDB. For LevelDB in Fabric and the hashmap in FastFabric, it does not work.
