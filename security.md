# Security

## Hashing Files and Model Integrity

When you’re training—whether it’s the base model or tuning pipelines—and when you’re loading models for inference or scripting, hashing is essential, non-negotiable. 
From `.safetensors` to straight up `.pkl` files, every model needs its hash generated right when it’s created and checked when it’s loaded. 
It's a critical step to certify that no tampered file sneaks in, that no intent is injected into your framework. 

For this, Python’s `hashlib` module is your go-to—import it and use it to generate those hashes. Gives you a solid way to verify what you’re working with. 


