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



# Outline for this section
- Data Protection (~3-4 pages)
- Data Protection By Design (Article 25(1))
- Statutory background:
- Controllers are obligated to implement appropriate technical and organizational measures and safeguards into processing.
- These safeguards and measures must be intentionally designed into the processing - not incidental.
- What makes measures or safeguards appropriate? If they’re effective at protecting the data subject’s rights and freedoms.
- Which rights and freedoms? The data protection principles in Article 5, and the “right ot the protection of personal data,” which is derived from the EU Charter of Fundamental Rights, and which the GDPR attempts to enforce.
- What makes a measure effective? If it actually produces the intended results, based on any processing foreseen by the controller.
- Federated learning and effective data protection measures
- What are the actual risks we’re concerned about?
- A malicious model-controller intentionally leaking or stealing training data via their training script - this is something that is mostly within the data-controller’s power to prevent, via the implementation of common safeguards and PETs.
- A model leaking personal data via regurgitation - this is mostly up to the model-controller, but the data controller should exercise its discretion by requiring the model-controller to implement specific measures or call off training entirely if the risk is too great.
- Some common factors push for the implementation of federated learning whenever possible:
- State of the art - Federated learning is an effective, state of the art technique for mitigating malicious data leaks.
- Cost of implementation - as federated learning becomes cheaper and easier to implement, the imperative to adopt it becomes stronger. This is especially true for data-controllers that are uniquely suited for federated learning (like companies with easy access to training hardware).
    
- Nature, scope, and context of processing - machine learning inherently requires vast quantities of data. Federated learning is uinquely effective when dealing with large quantities of data coming from multiple different sources.
    

- Some common factors to consider when exercising discretion with specific models and model-controllers:
    

- How sensitive is this data? - incl. Article 9 categories.
    
- What is the purpose of this processing? What kinds of outputs will this model produce? Who will have access to it? - especially consider Articles 9,10.
    
- Unique concern for federated learning - what other datasets was this model trained on? If pseudoanonymity no longer exists for a single party with access to all of these datasets, then the risk of 
    

- Practical takeaway: implement federated learning in a way that minimizes the risk of the model-controller learning any personal data. Talk with your engineers about implementing safeguards such as:
    

- Ensuring that all training data is pseudoanonymized for the model-controller, especially when considering what other datasets they are using.
    
- Running model training in a secure enclave, or at least software sandboxing. - this one is the most expensive, but most benefits of federated learning are moot if this is not possible.
    
- Restricting the training program’s access to the internet (to prevent “phoning home”)
    
- “Sanitize” any debugging outputs to remove information about the training data before sending them back to the model-controller.
    
- Review the training program for ways in which it might leak training data or try to access data that it is not permitted to use. This can be done with traditional automated testing pipelines. But in extreme cases, human review or formal verification may be necessary. These last two require a high degree of cooperation and trust between the data-controller and model-controller.
    

- Under formal verification, the model controller will need to write their training program with formal verification in mind.
    
- Under manual review, the model-controller needs to trust a human to actually read their training program, which potentially includes trade secrets.
    

- Data Protection by Default (Article 25(2)):
    

- Statutory background: basically, make sure that the default settings and processes you have in place allow you to do what’s “strictly necessary” for training while maximizing adherence to Article 5 principles.
    
- Federated learning helps us with limiting the period of data storage (Article 5(1)(e)) - the model-controller never stores any of the training data!
    
- Major obstacle for machine learning: Data minimization (Article 5(1)(c)).
    

- Machine learning is an inherently iterative process. It’s hard for a model-controller to know in advance how much data is “not enough” or “too much” for their purposes.
    
- Potential solution: allow the model-controller to experiment with multiple combinations of data fields and datasets, but only let them retrieve the updated model weights for one of those combinations, after making a joint determination of which training set does the best job of balancing accuracy and data minimization.
    

Additional requirement: Each controller must maintain a record of processing activities (Article 30)