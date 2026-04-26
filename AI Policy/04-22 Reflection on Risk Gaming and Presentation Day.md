# Riskgaming
- Class is largely skeptical. Thinks they don't buy into it!

# The News
- Anthropic's Mythos model was possibly breached.
	- Unauthorized access from one of its third-party vendor environments.
- Weird tension: Anthropic has been classified as a supply-chain risk by DoD. But a lot of people in the government wants to use Mythos!

# Emma's Presentation
- How does non-determinism in LLMs apply to US liability standards? Case study on healthcare
- Gaps created by nondeterministic features:
	- Auditability - how do you audit an LLM to determine if its safe? How do you log?
	- Data retention - HIPPA.

# Taylor's Presentation - AI and War
- How is AI used in non-weapons military systems.
	- International Humanitarian Law (IHL). 
- Client is a Prof. at West Point.
- Case studies on US, Ukraine, Israel

- US: Project Maven - using AI to gain useful insights of huge, already existing databases. Used for **targeting.**
- Ukraine: data aggregation and monitoring. Web scraping to learn about Russian troop movement.
- Israel: Lavender. Uses pattern recognition to estimate whether individuals are associated with terrorist groups and then target them.

- Human In The Loop - human has to approve each action
- Human On The Loop - human doesn't need to approve each action, but can veto or overturn AI decisions. What Lavender uses.

- IHL principles:
	- Proportionality - are the casualties acceptable given the military advantage.
	- 
	- Precautions - combatants have to take all **feasible** precautions to minimize civilian harm.

- AI undermines assumption under international law: decision to kill is made by humans. Since AI makes decisions at such a high velocity, it effectively supersedes any human decision-making.
- Black box problem: you can't reach certain burdens of proof (like beyond reasonable doubt).
- How do you do accountability?

Solutions:
- REAIM - require AI to be auditable, have explicit use cases, follow a continuous testing program.
- *Decision Support Tools* - enshrine substantive human decision-making. Ensure that it's not just rubber stamping!
- Binding testing standards - ensure international standards around accuracy and bias.
	- Lavender has a 10% error rate - that's super high!!

Ongoing problem: how do you get militaries to actually comply with this? Esp. since their tools are sooo classified.

- Are rules for human targeting and identification being programmed into AI targeting systems? 
# Maddie - Tort Liability for AI
- Especially about different parts of the AI stack
	- Data supplier
	- Cloud storage provider
	- Foundation model developer
	- deployer / integrator
	- End user
		- Harmed party is not always the end user!

- Whether a party is liable should be related to the level of responsibility they have over actually causing the harm.
	- Ex: if a user uses a calculator incorrectly and thus does tax fraud, calculator manufacturer shouldn't be held liable.
	- Ex: if user correctly uses calculator but it makes an error, human user shouldn't be held liable.

Raw material product liability:
- Suppliers of raw materials are exempted from product liability for harm caused by final product UNLESS:
	- Component is defective AND defect causes harm; OR
	- Substantially involved in integrating the component into the final product, and the integration process caused the harm.

- Data supplier - not really a raw material. Liability unlikely out of extreme circumstances
- Foundation model - might be a raw material! Take into consideration whether it's being used in the way it's supposed to be used. How does the developer use the foundation model API?
- Deployer - is the harm caused by fine-tuning made by the application developer?

- Threshhold of foreseeability in tort law is the hardest thing to apply to AI. The nature of AI makes things unforeseeable.
	- Potential solution: require developers to use less black-box features
	- Another solution: lower threshhold for foreseeability.

- Product liability presumes that the product is a tangible, defined good. But the whole problem with AI is non-deterministic!