rocky-k8s-master-test


Node가 NotReady 상태이고, cordens가 Pending상태인 경우
-----------------------------------------------------------

kubectl patch installation default --type='merge' -p '{  
  "spec": {  
    "calicoNetwork": {  
      "ipPools": [  
        {  
          "cidr": "20.96.0.0/16",  
          "blockSize": 26,  
          "encapsulation": "VXLANCrossSubnet",  
          "natOutgoing": "Enabled",  
          "disableBGPExport": false,  
          "nodeSelector": "all()"  
        }  
      ]  
    }  
  }  
}'  
