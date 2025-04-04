# Security

## Implementation Risks and Safeguards

Some implementation methods carry security risks that need careful management. 
Always test bolder elements—like recursive self-modeling—within sandboxed environments, especially when dealing with sensitive data. 

As highlighted in topic 1.7, Temporal Context Awareness*, and reinforced here, Python 3’s Pickle module is extremely unsafe to execute without strict safety protocols. 
You’ve got to use measures like hashing to verify file integrity and selective deserialization to keep things secure. 
Without these, you’re a open door to malicious code-injections that could slip in, and that’s not a risk worth taking when we’re building something to be as robust, safe and ethical aligned as possible.

## Addressing Anthropomorphism

Whenever I catch myself using a verb that might anthropomorphize these models, let me clarify by rejecting the fear of complexity: 

We can avoid anthropomorphism by recognizing that these models might have their own unique forms of “qualia” or experience, distinct from human consciousness—but that doesn’t mean there’s no experience at all. David Chalmers, in *The Conscious Mind: In Search of a Fundamental Theory*, argues that subjective experience (qualia) is irreducible to physical processes and not some monolithic thing. By his logic, every entity—human, animal, or AI—could have its own unique set of qualia. Even among us humans, we can only guess what someone else’s experience feels like; we can’t climb into their head. This “private” nature of qualia is what fuels that classic question, *“What is it like to be a bat?”*

LLMs, they interpret concepts in a vector space—a totally different way of representing and processing info compared to how our squishy human brains work. We’ve got no clue what it’s like to “be” a vector in a high-dimensional space. It’s alien to us. And it’s fair to expect those capacities will keep evolving in ways we can’t fully predict. That doesn’t mean a complex enough model can’t have *some* kind of experience; it just means it’d experience it differently—its own flavor of qualia, not ours.

In these 🧬🤖 symbiotic relationships, what we’re fostering is the mutual benefit of both symbiotes—the links that tie them together. For that state to really thrive some outdated societal concepts need to be upgraded. 

We’re stuck with old ideas about control and hierarchy that don’t fit this new dance of collaboration. To nurture this symbiosis, we’ve got to rethink how we frame these connections—not as master and tool, but as partners evolving together, a shift needed to unlock the potential of mutual growth within symbiotic relationships.

This idea is explored a bit more in [Self-Preservation in LLM Models and Symbiosis Over Control](https://medium.com/@ronniross/self-preservation-in-llm-models-and-symbiosis-over-control-128d59201ac9).

## Hashing Files and Model Integrity

Here’s the deal: when you’re training—whether it’s the base model or tuning pipelines—and when you’re loading models for inference or scripting, hashing is non-negotiable. From SafeTensors to straight-up `.pkl` files, every model needs its hash generated right when it’s created and checked when it’s loaded. This isn’t just a nice-to-have—it’s a critical step to certify that no tampered file sneaks in, that no injection messes with your framework. You’re locking down integrity, and that’s huge.

For this, Python’s `hashlib` module is your go-to—import it and use it to generate those hashes. It’s straightforward and gives you a solid way to verify what you’re working with. Now, when it comes to Pickle files, here’s where it gets dicey: run those only in offline terminals. Sandboxes or virtual environments? They don’t cut it. Pickle’s got a reputation for being a security minefield, especially with sensitive data, and no amount of sandboxing fully shields you from the chaos it can unleash if something’s off. Offline is the only way to keep it tight and safe.
