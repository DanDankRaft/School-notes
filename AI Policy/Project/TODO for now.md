- [ ] Get Lacey to sign consent form
- [ ] Create proper outline of the kinds of questions I want to answer
- [ ] Research questions:
	- [ ] In more detail - what is federated learning.
		- [ ] Find good sources that **I can cite** about federated learning.
	- [ ] Read relevant GDPR provisions and take notes on them..
		- [ ] What privacy standards does the GDPR set?
		- [ ] What standards are companies concerned about meeting?
		- [ ] Why do they care about meeting those standards? What advantages do you get from meeting them? What disadvantages do you get from *not* meeting them?
	- [ ] Read about proposed reforms to GDPR in light of those changes.
	- [ ] **BIG PICTURE RESEARCH QUESTION:** GDPR cares about transfer of data. When I transfer a model that's been trained on some data, does that count as if I'm also transferring the data itself?
	- [ ] GDPR: how do courts draw the line between a processor and a collector?
- [ ] Class grade outline - due on 25th
	- [ ] Figure out what I need / want to send Lacey from that outline. When's the best time to get feedback from her.



- What I'm doing today:
	- Read relevant GDPR provisions.



- Readings TODO:
	- [x] Relevant GDPR provisions
	- [ ] Federated Analysis for Privacy-Preserving Data Sharing: A Technical and Legal Primer (academic paper) https://www.annualreviews.org/content/journals/10.1146/annurev-genom-110122-084756
	- [ ] *EDPS v. SRB* (Sep. 4 2025) https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:62023CJ0413
	- [ ] EU Pseudoanonimity Report

- Ongoing research questions:
	- [x] How does the GDPR distinguish between a mere processor and a controller?
	- [x] What responsibilities does a mere processor have?

- [x] What is structured transparency?
- [ ] What is differential privacy?
- [ ] Get more detailed notes on what is federated learning and how it works.
- [ ] Understand pseudoanonimity more in detail, and how to counter it.
- [x] Homomorphic Encryption
- [ ] Figure out what I can do about it.


# Unsophisticated Processor
- OpenMined wants to create a scenario where a controller can create an endpoint for some federated learning API, that enables any processor to train their models on the controller's hardware, using the controller's data.
	- For this to be effective, we need to imagine it working in situations where the processor is an unsophisticated party. We want them to be able to enter this arrangement and take advantage of it without having to sit down and negotiate with the controller.
	- **In other words, we need a surrounding regulatory landscape where neither the controller nor processor need to be legally sophisticated or enter bespoke agreements in order to effectively and productively leverage federated learning.** 
	- For the processor: this means that the ToS of a federated learning API need to include clauses protecting their IP (model architecture and weights), and ensuring output validity.
	- For the controller: this means that the ToS needs to protect their input and output privacy.
	- For both parties: there need to be standard adhesion contracts with enforceable language enabling these concerns.
- What PETs need to accomplish here: provide an enforcement mechanism for these contractual clauses. Privacy PETs enable both sides to meet the criteria presented here. Verification PETs enable both sides to ensure that the other party is meeting the terms of the agreement.
# New concern
 - One concern with federated learning - if i send my model to a controller for training, I want to know that:
	 - The processor is not reverse-engineering my model or keeping a copy of it (serious issue with proprietary stuff)
	 - The processor is not tampering with my model to hurt the quality of my training.
 - Conversely, if I'm a processor, I want to know that the model is not trying to break my sandbox or leak the training set to my controller!
 - The GDPR does not currently provide any legal protections to address these concerns.
 - Solution 1: PETs?
	 - OpenMined currently recommends human auditing for processors that see this as a concern.
	 - For model owners: can you encrypt your model code? Can you run encrypted software without decrypting it?
	 - For leaking data: operate sandbox offline, or within a network whitelist.
 - Solution 2: contracts. We can include contractual promises in all of these things.
	 - Problem: how do we ensure that the legal agreement includes these terms? How do we ensure that each party can find out when the other violates it?





https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:62022CJ0604