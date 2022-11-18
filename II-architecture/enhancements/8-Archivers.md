At 1GBPS, a blockchain network will generate 4 petabytes of data a year for the ledger. Storing the data would quickly become the primary centralization vector, defeating the very purpose of blockchain implementation in the process.

On Solana, data storage is offloaded from validators to a network of nodes called Archivers. Archivers do not participate in consensus. The history of the state is broken into many pieces and erasure coded. Archivers store small parts of the state. Every so often, the network will ask the Archivers to prove that they’re storing the data they are supposed to. Solana leverages Proofs of Replication (PoRep), which are borrowed heavily from Filecoin.

We are able to use Proof of History — our clock before consensus — to optimize how PoReps are created. Archiver nodes, which do not participate in consensus, use PoH to generate lightweight proofs by which pieces of the ledger have been replicated, and validators are able to verify them in very large batches across GPUs.

Archivers can be lightweight nodes (e.g. laptops). With erasure codes and redundancy, a network of Archivers can offer data availability guarantees exceeding anything AWS or GCE could ever hope to provide.