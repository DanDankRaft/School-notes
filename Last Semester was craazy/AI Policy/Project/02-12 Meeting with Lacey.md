# Agenda
1. Send not-an-attorney letter
2. GDPR review:
	1. Controller v. Processor - that's a major question. But I'm leaning towards processor.
		1. Most legally conservative thing to do - treat model owner as a processor. Explore both paths.
		2. When a computation is run on a controller's service, is this computation a processing done by the controller or by the model owner.
	2. Obligations on readying data for processing:
		1. The data subject must give the controller explicit consent to use their data for this specific processing; or
		2. The processing serves a "legitimate interest"
	3. The relationship between controller and processor:
		1. MUST BE ESTABLISHED VIA A BINDING CONTRACT.
		2. Controller has a general responsibility to ensure that the processor complies with GDPR
		3. This contract must establish what the processor is "instructed" to process. The processor cannot do any processing that they are not "instructed" to do.
			1. In practice: this also means that the controller has an obligation to know at all times "what, why, and how" the processor is using their data.
		4. The controller cannot give the processor more data than is permitted under Article 6 and necessary to perform the processing.
	4. Some more responsibilities of the controller:
		1. handle right to be forgotten, recitification, withdrawal of consent, etc from data subjects.
	5. Security considerations:
		1. Data Subjects have a right to privacy. The controller must, in accordance with the state of the art, cost of implementation, nature, scope, context and purposes of processing, and the risk and severity of privacy rights being infringed, implement security measures.
			1. This is where federated learning kicks in.
			2. Example 1: sandboxing enhances pseudoanonymization
			3. Example 2: federated learning can ease anonimity worries from right to be forgotten requests.
			4. I've heard from Peter that there are worries that existing pseudoanonymization techniques are indadequate, and that the EU might consider requiring controllers to encrypt all their data before sending it to processors. Federated learning resolves that.
		2. Security of Processing: both the controller and processor must implement appropriate technical and organizational measures to ensure a level of security appropriate to the risk...
			1. Under traditional approaches, this places some burden of security on the processor that may increase the barrier to entry.
			2. Under a federated learning model, this burden is lowered. For example: any persons authorized to handle the data must be legally bound to confidentiality. Under a federated approach, no person from the processor's side has access to the data, so you don't need to find some legal mechanism to enforce that

- Data transfer and international certification: an important detail to keep in mind for a report.
	- Useful example: US based researcher working with data in France. The French lawyers found that they didn't trigger GDPR bc they never got access to the PII.

- Feel free to shoot messages to Peter.
- Peter is in charge of advocacy within the EU. if we want to push for a recital, he's the person we should reach out to.
- Cite a few case studies for what terms of service looks like.
	- What about opt-in to training that's separate from the main TOS
- Oura ring allows you to opt-in to certain medical studies that's separate from terms of service.

- Check if you need consent to access encrypted or completely anonymized data.

- Normative interest: if there are ways that we can explain that there are legally and technically feasible ways to add specificity to the restrictions, balance privacy and innovation.

- Technical paradigm to explore: controller no longer gives copies of the data away, so they no longer have a duty to enforce it all the time.

- Only concern with pseudoanonymization is reconstruction attacks.

- PETs can be deployed at the controller level to make data more accessible.

- Information flow - *structured transparency.*
	- Input privacy and input verification - responsibility of the data controller.
	- Output privacy and verification - responsibility of processor, in some cases of the controller.
- At each of those stages, there are different PETs that help with those steps.

- Executive Director Andrew Trask - there's an atypical use of differential privacy where if the output of the analysis it's differentially private it will be statistically significant in a way that's not real.


- In the US - there was a case where they released pseudoanonymized data and they reconstructed it.
	- There's also details about HIPPA's standards not being strict enough.