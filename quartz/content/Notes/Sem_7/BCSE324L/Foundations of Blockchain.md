
## Basics 

blockchain is a db system. it consists of blocks connected to each other in such a way that block $n$ consists of the hash of block $(n-1)$ and the data of block $n$.

once you commit to a blockchain, the blocks cannot be removed or changed.

thus it forms an immutable ledger of data, and is hence extremely secure.

## Applications

- Finance
- Healthcare
- Retail
etc.

### Finance

blockchain can be applied to the clearing of financial assets. the current issue is that every step of the financial transaction process needs different entities to securely finish the transaction. on the other hand with blockchain, everything can be finished with one single ecosystem, hence it is very secure and useable.

### Retail

blockchain is used as a supply chain management tool for the retail industry, due to it's robust ledger management technology that allows companies to track and find anomalies immediately.

### Healthcare

this is probably the biggest thing for blockchain, in the form of the __EMR__ (Electronic Medical Record).

#### the EMR:
- is the digitial version of a patient's chart in a single hospital or clinic.
- usually owned by the healthcare provider, and this results in interoperability between hospitals a big issue.
- this also makes it quite insecure, since it is privy to tampering, etc.

#### what blockchain does:
- provides a distributed ledger to store a patient's EMR.
- this ensures security while also solving the issue of inter-hospital accessibility, since every hospital shares the same ledger of patient EMRs.
- ##### key benefits include:
    - immutability
    - audit trail
    - interoperability
    - decentralization

typically how it works is that the blockchain stores hashes/pointers pointing to the EMRs. this ensures an additional layer of security and scalability, while allowing heavier applications like AWS S3 to handle the issues of store while the blockchain remains relatively lightweight and useable.
