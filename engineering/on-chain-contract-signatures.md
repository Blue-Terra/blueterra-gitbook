---
description: Let's Talk Transaction Signatures
---

# 🔗 On-chain Contract Signatures

Without diving into the esoterics of modern cryptography, we would like to give our holders a cursory overview of how our use of on-chain KYC and Solana transaction signatures constitute a digital signature and fulfill our regulatory requirements. We feel this is particularly pertinent given  that this project is the first of its kind.&#x20;

Starting from first principles we ask, "_What is required by Bahamian regulation for the distribution of `perpetual leases` under the Blue Terra model?_" and "_How might existing technology and the advent of Blockchain uniquely enable this?_"&#x20;

We begin with the first question. There are two requirements:

1. The reality of land ownership in the Bahamas whether by `Deed` or `Perpetual Lease` is one that requires full and complete information, in addition to various AML and Terrorism checks on property owners. The level of information required to activate the lease embedded in your NFT is similar to what you'd expect a typical lease with some omissions and additions. We label this data, Personal Identifiable Information (`PII`).
2. Holders must read and agree to the lease in a manner that is verifiable and true without a reasonable doubt.&#x20;

Now to address the second question with respect to the two requirements we described above.

1. Web 2.0 gave rise to identity APIs. These apis facilitate both KYC and AML/Terrorism checks typically with a simple curl request. Integrating, these traditional web 3.0 APIs into web 3.0 is a fairly easy task with the right system design. Fortunately, the need for KYC in web 3.0 is well recognized and companies such as our provider `Civic` have built out a market position providing easy to use KYC integrations on-chain.&#x20;
2. On-chain transactions are the primary mechanism by which lease signing will occur. Modern cryptography has enabled us to verify and record with near zero uncertainly whether a given transaction (or program interaction) has occurred on-chain. Relative to web centralized 2.0 database solutions, web 3.0 chains are obviously more secure as transactions are verified on decentralized nodes and there is no chance of data corruption or tampering by bad actors with admin access to the database.

Now take these points together. Web 2.0 identity APIs allow us to tie wallet addresses to `PII` and provides a means of KYC infrastructure to verify and check the backgrounds of customers. On-chain transaction signatures generated through interaction with a custom Solana program give us the ability to then associate wallet addresses with users who have accepted the lease through the Blue Terra `Claim Land Program`.&#x20;

From this, it is easy to see that we can construct a list of Blue Terra Holders who have claim their land (ie: gone through our `Claim Land Program`) and the associated `PII`. A system that is then able to generate such a list clearly meets the regulatory regulations for the distribution of `perpetual leases` under the Blue Terra framework.&#x20;
