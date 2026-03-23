# Article 25(1) Data Protection by Design
- Controller's obligation to implement appropriate technical and organizational measures and necessary safeguards into processing:
	- Technical *and* organizational measures: things like organizational structure and personnel training are just as applicable as encryption or pseudoanonymization for compliance here.
- Implement data protection principles in an effective manner and protecting the data subjects' rights and freedoms
	- Data protection principles - ARTICLE 5!
	- and "the right to the protection of personal data," which is the overarching goal of the GDPR - Article 1(2). This is also useful for an introduction.
- Whatever safeguards/measures implemented must be *designed* (ie, not incidental) - pg. 7
### Effectiveness
- The safeguards/measures should actually produce the intended results within for any processing foreseen by the controller.
	- Does this mean the data-controller is off the hook if the model-controller goes rogue?
	- No, but the data-controller should anticipate common ways in which the model-controller might go rogue and implement safeguards against them.

## Elements of effectiveness to take into account
- **State of the art** - take into account the current state of technology, including both what security measures you can take and what exploits exist.
	- This should be continuously assessed for as long as the product is deployed.
- **Cost of implementation** - includes time, money, and human resources. This means you do not always have to take the most effective measures, so long as they are disproportionately expensive relative to the advantages that they provide.
- **Nature, scope, context and purpose of processing**:
	- Nature - characteristics wrt the type of personal data, the types of data subjects, power relations, unpredictability, etc
	- Scope - size and range of processing
	- Context - circumstances. **LIKE FEDERATED LEARNING**
	- Purpose - aim of processing. **Up to the model controller**
- **Risk and likelihood and severity for rights and freedoms of natural persons** - this is where regurgitation factors in.
	- What kinds of outputs will this model produce?
	- Who will have access to this model?
	- What measures are taken to reduce the risk of regurgitation?
	- What other datasets is this model trained on?
		- THIS IS IMPORTANT: even if all training was done via federated learning, does the combination of any of the datasets potentially identify any data subject?
			- Ex: dataset 1 has first names and birthday, but no other information. dataset 2 has dates of birth and country of origin, but no other information. Each dataset individually might be pseudanonymous, but the combination of the two can reveal personally-identifying information
	- **Time aspect** - DPbDD should be evaluated both: before the controller decides how processing will be conducted, and at the time of processing itself.
# Article 25(2) Data Protection by Default
- Basically, make sure that all the default settings and processes you choose maximize privacy while doing what is "strictly necessary" for achieving the lawful purpose.
	- What are we maximizing: data minimization. Don't process more than what's strictly necessary.
- Dimensions of minimization:
	- **Amount of personal data collected**: kind of irrelevant, bc we're assuming that the data has already been collected.
	- **The extent of the processing**: don't provide a model-controller more data fields than strictly necessary 
	- **The period of their storage**: federated learning already provides a huge advantage here! The model-controller never has to store this data!
	- **Their accessibility**: the controller should limit who has access to which types of personal data based on necessity.
		- "The controller shall give the data subject the possibility to intervene before publishing or otherwise making available personal data about the data subject to an indefinite number of natural persons" how do we interpret this? Seems like its non-applicable to federated learning.

- Problem with machine learning: it's hard to know in advance what fields of data are "necessary" for training a model, because model development and refinement is an inherently iterative process. One way to solve this with federated learning is to provide a "sandbox-experiment" approach:
	1. The model-controller explains what their model intends to do, and requests access to an initial set of data fields.
	2. The data-controller does a sanity check, rejecting any fields that have no possibility of being related to the use case.
	3. The model-controller sends their training program and performs the federated learning on the data-controller's hardware, using every combination of the agreed-upon data fields.
	4. Each combination is then tested for accuracy on the data-controller's hardware.
	5. Based on some agreed-upon criteria, the model-controller and data-controller agree on the best combination, balancing out accuracy and the parameters used.
		- E.g., if combination A uses much more sensitive data than combination B, but only provides a small increase in accuracy, then combination B is preferrable.
	6. The model-controller only gets back the updated weights for the agreed-upon model, and the data-controller discards all data used in the sandbox experiment.


---
# Some useful safeguards to implement by default
- Completely cut off the training enclave from the internet.
- Have some sort of review mechanism (manual or automatic) of the model training script.
- Verify the model-trainer's identity - check if the contact information they provided makes sense, and if it lines up with what they aim to achieve with their model.
- 