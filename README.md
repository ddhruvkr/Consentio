Queries that need to be run

```

peer chaincode invoke -o orderer.example.com:7050 --tls --cafile /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/ordererOrganizations/example.com/orderers/orderer.example.com/msp/tlscacerts/tlsca.example.com-cert.pem -C $CHANNEL_NAME -n d20 -c '{"Args":["updateConsentNewDesign", "2", "g","all", "20150101", "20160101","101,102,103,104,105,106,107,108,109,110", "read", "hippa"]}'

peer chaincode invoke -o orderer.example.com:7050 --tls --cafile /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/ordererOrganizations/example.com/orderers/orderer.example.com/msp/tlscacerts/tlsca.example.com-cert.pem -C $CHANNEL_NAME -n d20 -c '{"Args":["updateConsentNewDesign", "3", "g","all", "20150101", "20160101","101,102,103,104,105,106,107,108,109,110", "read", "hippa"]}'

peer chaincode query -C $CHANNEL_NAME -n d20 -c '{"Args":["queryMarbles", "{\"selector\":{\"c_id\":\"101\",\"acctype_id\":\"read\",\"r_id\":\"all\", \"s_date\":{\"$gt\":\"20140102\"}, \"e_date\":\"20160101\"}, \"use_index\":[\"_design/indexConsentDoc\", \"indexConsent\"]}"]}'

peer chaincode invoke -o orderer.example.com:7050 --tls --cafile /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/ordererOrganizations/example.com/orderers/orderer.example.com/msp/tlscacerts/tlsca.example.com-cert.pem -C $CHANNEL_NAME -n d20 -c '{"Args":["accessConsentNewDesign","all", "20150101", "20160101","101,102,103,104,105,106,107,108,109,110", "read", "hippa"]}'

peer chaincode invoke -o orderer.example.com:7050 --tls --cafile /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/ordererOrganizations/example.com/orderers/orderer.example.com/msp/tlscacerts/tlsca.example.com-cert.pem -C $CHANNEL_NAME -n d20 -c '{"Args":["updateConsentNewDesign", "2", "r","all", "20150101", "20160101","101,102,103,104,105,106,107,108,109,110", "read", "hippa"]}'

peer chaincode query -C $CHANNEL_NAME -n d20 -c '{"Args":["queryMarbles", "{\"selector\":{\"c_id\":\"101\",\"acctype_id\":\"read\",\"r_id\":\"all\", \"s_date\":{\"$gt\":\"20140102\"}, \"e_date\":\"20160101\"}, \"use_index\":[\"_design/indexConsentDoc\", \"indexConsent\"]}"]}'

peer chaincode invoke -o orderer.example.com:7050 --tls --cafile /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/ordererOrganizations/example.com/orderers/orderer.example.com/msp/tlscacerts/tlsca.example.com-cert.pem -C $CHANNEL_NAME -n d20 -c '{"Args":["accessConsentNewDesign","all", "20150101", "20160101","101,102,103,104,105,106,107,108,109,110", "read", "hippa"]}'

peer chaincode invoke -o orderer.example.com:7050 --tls --cafile /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/ordererOrganizations/example.com/orderers/orderer.example.com/msp/tlscacerts/tlsca.example.com-cert.pem -C $CHANNEL_NAME -n d20 -c '{"Args":["updateConsentNewDesign", "3", "r","all", "20150101", "20160101","101,102,103,104,105,106,107,108,109,110", "read", "hippa"]}'

peer chaincode query -C $CHANNEL_NAME -n d20 -c '{"Args":["queryMarbles", "{\"selector\":{\"c_id\":\"101\",\"acctype_id\":\"read\",\"r_id\":\"all\", \"s_date\":{\"$gt\":\"20140102\"}, \"e_date\":\"20160101\"}, \"use_index\":[\"_design/indexConsentDoc\", \"indexConsent\"]}"]}'

peer chaincode invoke -o orderer.example.com:7050 --tls --cafile /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/ordererOrganizations/example.com/orderers/orderer.example.com/msp/tlscacerts/tlsca.example.com-cert.pem -C $CHANNEL_NAME -n d20 -c '{"Args":["accessConsentNewDesign","all", "20150101", "20160101","101,102,103,104,105,106,107,108,109,110", "read", "hippa"]}'

```


These set of commands are for the new design, similar commands (which changed function names) would work for the original design.
Just change the chaincode name. It is set to d20 currently.
