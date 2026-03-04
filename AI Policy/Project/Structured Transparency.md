# Seminal works on Digital Privacy
- Helen Nissenbaum - Privacy in Context: Technology, Policy, and the Integrity of Social Life.
- David Evans, Vladimir Kolesnikov, Mike Rosulek - A Pragmatic Introduction to Secure Multi-Party Computation
# Types of Information Flow
- **Messaging flows** - bit transfer directly from one party (sender) to another (receiver)
- **Service provider flows** - like messaging flow, but a third party performs some computation on the message while its in transit from the sender to the receiver
- **Aggregation flows** - like service provider flow, but the service provider does computations that combine messages from multiple senders
	- Ex: statistical analysis on a large dataset, **training a model on data from tons of different users**
# The Five Criteria
- **Input privacy** - I want to be able to process information while learning as little about it as possible.
- **Output privacy** - I want to be able to send something, or contribute to what I'm sending, while revealing as little as possible. I don't want someone to be able to reverse-engineer my output in order to find out things about me that I'm not already sharing.
- **Input verification** - I want to know that the information I receive comes from a source I trust and wasn't tampered with. It also means that any information I output can be verified by others.
- **Output verification** - I want to be able to audit the computations that have been performed s.t. I can verify their validity.
- **Flow governance** - each party should be able to verify that information is processed under the  parties/standards/criteria it prefers.

> [!info] Privacy and verification are in tension with each other - methods that increase privacy tend to hurt verification, and vice-versa.

# The Problems
- **Copy Problem** - when a recipient gains a bit of information, they gain complete technical control over how they use it and who they share it with. They are only bound by institutional and legal norms.
- **Bundling problem** - it is difficult to share a bit of information without sharing ancillary bits. This is especially a big problem with *verification*. Some additional bits might be unnecessary for processing but necessary for verification.
- **Edit problem** - when an intermediary receives a bit of information, they can always edit it, and it's impossible for the next recipient to tell if / how it was edited.
- **Recursive oversight problem** - the easiest way to solve these problems is through third-party oversight. However, this approach gives the third party the power to abuse the information in all of the above ways!
# Technical Solutions
### Input Privacy
- ENCRYPTION
- Especially, homomorphic encryption
	- Downside: there's a huge performance penalty!
- Secure multi-party computation? (SMPC)
- Secure enclaves
	- Important development: Nvidia is developing a cloud product that allows using the GPU as a secure enclave
- *Input Privacy technologies can achieve secure service-provider information flows without third-party oversight*
	- They're also beneficial for aggregation flows, but they don't eliminate the appeal of third-party oversight.
### Output Privacy
- Differential privacy
	- Especially impactful in aggregation flows
- Redaction (removing sensitive data-points from the output)
	- Increasingly difficult as data gets more bundled
### Input Verification
- cryptographic signatures
- zero-knowledge proofs
- Input verification methods require adding additional data (like the signature) - see how we're harming privacy?
- Technical input verification tools enable us to verify data without peering at the actual input data!!!
### Output Verification
- In the digital world, these are the same tools as input verification.
- Input verification technologies enable a third-party auditor to check for output verification without actually looking at the inputs or outputs themselves!
- This is a field with tons of ongoing research
### Flow Governance
- Secure multi-party computation (SMPC)