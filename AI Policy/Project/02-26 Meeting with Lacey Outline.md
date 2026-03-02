- Let Lacey know that I did more reading on PETs and Structured Transparency.
	- To what extent are we worried about the difference between a software sandbox vs hardware secure enclave?
		- These technologies have to work in tandem - the secure enclave has its own encryption key.
		- OpenMined builds software sandboxes on top of existing secure enclaves. The point is to provide attestations to the privacy of the software.
	- Is homomorphic encryption realistic performance-wise in 2026?
		- Email this question to Lacey - they have researchers on their team that are working on this.

- Nail down AIM.
	- Audience - 
		- Primary audience compliance lawyers in industry
		- Secondary audience: policymakers in EU, maybe other regions - especially in context of digital omnibus
		- Tertiary audience: lawyers and technologists in regulatory agencies like FTC, EU equivalent.
	- Intent
		- Demonstrate to stakeholders that federated learning (and other PETs to a lesser extent) can be used to comply with regulatory standards
		- Get lawyers to proactively think about using federated learning to solve their ongoing compliance problems, and reach out to technologists.
			- Turn the internal champion for PETs from an engineer to a lawyer or senior counsel.
			- Demonstrate that PETs have legal value - not just a technological value.
			- PETS ARE NOT JUST A RESEARCH THING - THEY ARE MATURE ENOUGH TO HAVE REAL-WORLD USE CASES.
		- Motivate policymakers and regulators to keep modern PETs in mind when drafting privacy regulations
	- Message
		- PETs, and esp. federated learning are useful for complying with the GDPR in AI training.
		- Specific roadmap of how to comply with the GDPR
			- Give them questions to ask other stakeholders in the organization.
		- PETS ARE NOT JUST A RESEARCH THING - THEY ARE MATURE ENOUGH TO HAVE REAL-WORLD USE CASES.
		- Explain to lawyers that certain technologies can makes it *impossible* for a party to break the law, or remove a legal risk entirely.
			- Ex: smart contracts.


- Go over Dr. Frazer's suggested outline

# Suggested Outline
1. Introduce the situation - one person has the data, another person wants to do the training.
	- Immediately hit them with how this has business value - it's not just "cool."
	- What kinds of business use cases would lead to this situation?
		- Set the scene: introduce a clear cut example of a situation where this issue arises.
	- Introduce federated learning somewhere in here
2. Cover the applicable law - what provisions of the GDPR 
3. What is the potential harm - what happens if the law is broken and who is liable?
4. What you CANNOT do
5. What you may be able to do (legal gray area)
6. What you SHOULD do

- Throughout this paper - weave in how federated learning, especially when used in conjunction with other PETs, is the answer!
	- Especially for sections 4-6.

- Additional themes:
	- Ensuring compliance and trust between processor and controller - what needs to be in the contract? Is there anything that needs to be enforced by a TTP or statutory change? How do we ensure that one party can find out if the other has breached anything?
		- See how technical guarantees work
		- One idea to explore - if there are technological measures in place to ensure trust and compliance on these matters, it is illegal to circumvent those measures.
	- Regurgitation and GDPR - shouldn't be the primary focus. Key to point out is that this is a problem with all LLMs and federated learning doesn't make it worse.
		- OpenMined engineers - a certain combination of PETs make regurgitation impossible or statistically irrelevant?
			- If federated learning is a necessary component of this, then it's worthwhile talking about that. But that doesn't mean broader coversation about regurgitation

# Next Steps
- [ ] Send email w/ technical quesitons for openmined engineers
- [ ] Send "im not a lawyer email"
- [ ] Research more specifics on pseudoanonymity - ask OpenMined EU lawyers.