# Differences from other clients

Several attributes separate Mantis from other Ethereum classic clients:

  - Mantis is the only client **built from scratch**, specifically for the Ethereum Classic Network
  - It is built in [**Scala**](https://www.scala-lang.org/), a programming language that allows users to build software using object oriented design on a high level (DDD, hexagonal architecture) and uses functional programming principles: immutability, referential transparency and lazy IO on a low level. Thanks to its advanced type systems, it eliminates many errors. Moreover it supports an actor model that naturally fits the cryptocurrency paradigms, as well as other approaches to concurrency like STM or green fibers. Scala programs running on the JVM have high, enterprise grade reliability.
  - Mantis **implements new ECIP proposal features** that could shape the future of the Ethereum network
  - **Sagano is the new Mantis Testnet** you can use to test these new features
  - Mantis is a **node client and a wallet**, depending on what needs you have, you may choose one or the other
