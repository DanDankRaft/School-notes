- The test:
	1. pursuit of a legitimate interest by the controller or third party
	2. personal data necessary to be processed for the purpose of the legitimate interest pursued.
	3. pursuing the legitimate interest(s) does not take precedence over interests or fundamental freedoms or rights of the data subjects.
	   Curious - how does right to privacy fit into this?

# First Step
- There is no definitive list of "legitimate" interests.
- But some criteria:
	- The interest is lawful - mention this in paper, say data-controller should double-check with the laws of their own country.
	- The interest must be clearly and precisely articulated.
		- Not about informing the data subject about it, but
		- Yes about being able to determine whether it goes against any interests or fundamental rights of the data subject
		- Shedding additional light - will the model enable insights that can be used to hurt people? Who will have access to this model?
			- E.g., a model used to determine whether someone is more likely to develop certain diseases - very useful in the hands of doctors, potentially dangerous if put in the hands of insurance providers.
- "legitimate interests pursued by the controller or by a third party"
	- If it's the controller's interest, must be an interest related to the actual activities of the controller.
	- If it's the third party's interest, must be an interest related to the actual activities of the third party.
- Some main contexts where personal data may be processed in the interest of a third party:
	- *Historical or other kinds of scientific research* - may fit here if the model-controller is doing this for research purposes. Puts us in a legal gray area if they're doing so.
			- PAGE 11, PARAGRAPH 24 AND FOOTNOTE 36
# Second Step
- Informed by "data minimization" GDPR, Article 5(1)(c)
	- "adequate, relevant and limited to what is necessary in relation to the purposes for which they are processed."
- "If there are reasonable, just as effective, but less intrusive alternatives, the processing may not be considered necessary"
- One compliance measure: the model-controller needs to justify why they need each data field they request. This can be tricky - a lot of model refinement is done by iteratively adding and removing fields from training and seeing how they affect the accuracy of the model's predictions.
- Federated learning is uniquely effective at meeting this threshold
	- The main appeal of using existing databases is that the best data for training models was already collected before before large language models became mainstream.
	- The additional protections afforded by federated learning make these *less* intrusive.
# Third Step
- This is a "balancing exercise"
- What are we balancing:
	- "interests of data subjects" - e.g., financial interests, social interests, personal interests.
	- The nature of data being processed - the more sensitive it is, the more likely it is to have a negative impact on the data subject. See Article 9 categories for an illustrative example.
	- The context of processing - scale of data (how many data subjects, how much data on each subject), how this data is combined with other data sets
		- Extra attention when the data subject is a child. pg. 15, Recital 38, *Meta v. Bundeskartellamt*
	- Further consequences of processing - can this lead to personal risks to data subjects, legal consequences, discrimination, emotional harm, risk to physical safety?
## Recital 47
"\[a\]t any rate the existence of a legitimate interest would need careful assessment including whether a data subject can reasonably expect at the time and in the context of the collection of the personal data that processing for that purpose may take place. The interests and fundamental rights of the data subject could in particular override the interest of the data controller where personal data is processed in circumstances where data subjects do not reasonably expect further processing."
- This matters wrt how it factors to the risks to the data subject.
> The fact that certain types of personal data are commonly processed in a given sector does not necessarily mean that the data subject can reasonably expect such processing.
- Factors to consider:
	- The relationship between the data-controller and the data subject, including the service provided and whether the subject would've expected such data to be collected about them in this relationship.
	- The characteristics of the "average" data subject in this database - age, public notoriety, level of professional expertise or professional expectations.
- "It should be noted that contractual provisions regarding personal data may have a bearing on the reasonable expectations of data subjects." This is probably only applicable if we can expect the "average user" to know the terms of their contract with a service.

## Mitigating measures
- If you think that your legitimate interest fails the balancing test, you can implement "mitigating measures" that shift the test in your favor.
- Whether a measure is already required for compliance with the GDPR has no impact on whether it is a sufficient "mitigating measure." Thus, to be safe, you should probably implement more measures beyond what the GDPR requires.

- Applying to real world contexts:
	- Since a major goal of federated learning is to open up existing databases to machine learning, we should presume that no reasonable expectation exists here. BUT, an avoidance of sensitive data, the employment additional PETs that minimize the risk of regurgitation (e.g. differential privacy), and some controls on who can use the model can do a lot here.


---
# Proposed Changes in omnibus
- Clarify that legitimate interest can be a useful basis for AI development.
- I think that as long as regurgitation continues to be a risk, however small, we should still funnel developers towards prioritizing consent as the main basis for AI development. But maybe we should loosen the requirements for valid consent when the purpose is AI development and training.

---


- Limitation: this paper presumes that the right to privacy under EU law is primarily motivated by letting data subjects control who they share their personal information with. The motive to control *how* their data is used *and to what ends* is very similar, but federated learning. Under traditional processing approaches, it is impossible to let any party leverage one's data without granting them complete access to that data. With this complete access, these parties 

- Up to this point, EU law presumed that disclosure is necessary for the processing of data. The presumption has been that there is no technical mechanism that allows a party to process personal data without "receiving" it, in one form or another. And furthermore, that once a party "receives" personal data, there are no technical mechanisms that can effectively prevent it from processing it in whatever manner and for whatever purpose it desires. Thus, the job of privacy law is to protect the rights of data subjects by imposing legal restrictions on collection and processing where technology cannot. And since it is hard to control the processing of data once it has been received, most of these restrictions apply before a party collects or receives personal data.

- Federated learning does not conform to these presumptions. The key innovation of federated learning (and other PETs such as homomorphic encryption) is that they decouple disclosure from processing. A party no longer has to "receive" personal data in the traditional sense in order to process it. And even once it gains access to data in this new unorthodox manner, we have technological measures that can effectively control how it leverages that data.

- Where EU law succeeds:
	1. Since EU law anticipates technological innovation and does not tie itself into any specific technological measures, it encourages and perhaps even mandates the adoption of federated learning in some situations, because it is more effective at protecting users' privacy.
	2. The granularity 
- Where EU law fails:
	1. Since EU law does not anticipate processing without disclosure, it is unclear when and how a lot of the restrictions on disclosure of data apply.
	2. On a more fundamental level, EU law occasionally fails to distinguish between two different interests underlying the right to privacy:
		1. The interest in controlling who has my personal data
		2. The interest in controlling how my personal data is used
	   Up until now, this was fine, because every instance of data processing always implicated both interests. (E.g., Article 9 prohibits processing of particularly sensitive categories of personal data in all but a few enumerated circumstances. Each of those circumstances only refers to how that data is used, but not to who processes that data; )
	   
	   But now, there are now some instances where EU law gets in the way of responsible innovation, because measures that are only aimed at defending the first interest still apply to federated learning, which only implicates the second interest. (e.g., requiring a consent statement to name each controller who will process the personal data before the user consents).