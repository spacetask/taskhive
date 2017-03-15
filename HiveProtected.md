# HiveProtected

---

**DISCLAIMER: This document does not constitute legal advice and should not be relied upon for commercial transactions or conducting litigation. Consult a local lawyer in your jurisdiction if legal advice is needed.**

**NOTICE: This document is a work in progress and will be updated from time-to-time.**

---

## What is an HiveProtected contract?

HiveProtected contracts take advantage of Taskhive's security features to create agreements that are clear and easily enforceable. Users are able to form contracts that protect their identities and guarantee secure communications channels, and to take advantage of Taskhive's web of trust to engage reputable escrow and arbitration services that safeguard their agreements.

The realisation of HiveProtected contracts is based on two design principles. Firstly, the system is designed to be modular: each component of the contracts are intended to be discrete, allowing for future changes to be made to each module without significantly affecting other modules. This approach should be feasible given contracts tend to be quite modular and, as will be seen below, can be broken into reasonably independent components. Secondly, the system is designed to be pragmatic: although Taskhive is intended to embody free market principles, some restrictions have been necessary due to practical and technical constraints, and to ensure a useable system can be launched. In accordance with its modularity, new features can be easily added over time.

This document sets out the general considerations for HiveProtected contracts going forward, and makes recommendations for immediate features. Future documents will follow post-launch, outlining new features that could be added to better realise Taskhive's goals. For now, this document makes suggestions on a set of features that should, at minimum, be included in the first launch of Taskhive.

## Offer or invitation to treat?

**NOTE: This section discusses common law contract principles. These principles are found in legal system descended from English law, including Australia, Canada (except Quebec), England & Wales, Ireland, New Zealand, Northern Ireland, the United States (except Louisiana) and are present in certain mixed systems such as Malysia and South Africa.**

Contracts generally begin with an offer-acceptance pair. One party will make an offer to form an agreement on particular terms, and another party will accept. Offer and acceptance indicate that the parties are of one mind as to the terms of the agreement. In essence, an offer must be able to be accepted 'as-is', without further negotiation. If a party wishes to accept an offer with modifications they are in fact making a counter-offer, which reverses the roles of the parties (the original offeror is now the offerree and vice versa).

An offer may be made in such a way that any person may accept it; it may be made 'to the world', as it were. An offer may be made similarly broad, but in such a way as to restrict the number of offerrees to a specific class or classes: perhaps the offeror wishes to allow only residents of a particular territory to accept. Alternatively, an offer may be made to a specific person.

There are some circumstances in which a party will not be making an offer to contract, but instead be indicating a willingness to negotiate a contract. This is called an 'invitation to treat' and acceptance will not create a binding agreement. An invitation to treat allows a party express their interest in forming an agreement without being bound. The difference between an offer and an invitation is important for determining when an agreement becomes binding.

The point at which a HiveProtected contract is formed will be when both parties' cryptographic signatures are affixed, as well as the signatures of the escrow agent and arbitrator (who must agree to act in the enforcement of the agreement). From that point on it will be considered binding on all involved. In accordance with general principles of contract, offers should be binding and able to be accepted until they are revoked, and offers should be revocable until they are accepted.

Eventually, Taskhive should cover all eventualities: 'bare' offers which can only be accepted; offers with an indication of a willingness to consider counter-offers; and invitations to treat. Contractual freedom is a key aspect of a free market, and while it might be tempting to force negotiation (or at least the consideration of counter-offers) on the basis that it would encourage parties to form an agreement, this is paternalistic and contrary to the notion that individuals should be free to make their own economic decisions. Initially, however, contracts will be formed only after negotiation.

---

**Short-term approach:**

- All task postings shall be considered **invitations to treat**.
- The task-specific addresses shall be used to negotiate the terms of the agreement.
- Once the parties have agreement as to the terms, the creator of the task posting shall sign, making an **offer**.
- The offer shall be binding until accepted or revoked; revocation shall be permitted until the offer is accepted.
- If the other party agrees to the terms they shall sign, making an **acceptance**.
- Once accepted, the contract becomes binding.

---

**Long-term approach:**

- A user posting a task should be able to choose between making
	- an offer,
	- an offer with willingness to consider counter-offers, or
	- an invitation to treat.
- A user posting a task should be able to choose between making an offer or invitation to treat to
	- all users,
	- some users (limited by class, eg a minimum reputation score), or
	- to a specific user.

---

## Parties

Traditionally it has been essential to the enforceability of a contract that its parties are identified with precision. Without a high degree of precision, the parties would find it difficult to prove that they are entitled to enforce the agreement, and against whom they are entitled to enforce it. Details typically included are the full names and legal forms of the parties, business or corporate registration numbers, and places of incorporation. Business addresses are also included to both identify the parties and facilitate the service of legal documents in the event of a dispute.

These details form a necessary interface between the parties and the court or tribunal adjudicating a contractual dispute. In Taskhive, however, each user has a unique public key (analogous to a parties' names) and each task has a set of unique electronic addresses by which parties and potential parties may communicate (analogous to parties' addresses). Although useless to a court (because without a name and physical address, identification, service of documents and enforcement of a judgment will generally be impossible), in the internal arbitration and escrow process described in subsequent sections below, a public key and electronic address will be sufficient to enforce the agreement.

Parties can be described as 'vendors' or 'vendees', depending on their role in the contract. The Vendor is the person providing a good or service, and the Vendee is the person receiving the good or service. In common terminology, this pair might be called 'seller and buyer' or 'service provider and client', however 'vendor' and 'vendee' are more universal.

It is recommended that each party be described as either 'the Vendor' or 'the Vendee' to avoid confusion. A public key is not particularly human-readable, so inserting each party's key each time they are referred to may lead to errors, especially by an arbitrator. If a user is offering to provide a service, they will be identified throughout the agreement as 'the Vendor'; if a user is requesting the provision of a service, they will be 'the Vendee'.

---

Recommended parties clause:

> **Parties**
>
> (1) This agreement is between:
>
> (a) `VENDOR'S PUBLIC KEY`, address `VENDOR'S ELECTRONIC ADDRESS` (hereafter 'the Vendor'), and
>
> (b) `VENDEE'S PUBLIC KEY`, address `VENDEE'S ELECTRONIC ADDRESS` (hereafter 'the Vendee').

---

## Definitions and governing law

The definitions section ensures that terms used in the agreement are interpreted consistently (rather than relying on context to determine the intended meaning), which is especially important where an ambiguous word is used, or a word is used in an unusual sense. A definitions section can also be useful to refer readers to relevant sections if they are looking for how a word is defined. For example: '"the Vendor" means the party identified in clause (1)(a)' not only defines the term consistently, but refers the reader to the relevant provision.

Definitions should be fixed to ensure that users with limited knowledge or understanding cannot erroneously change the effect of clauses dependent on those definitions. There are likely to be only a few terms which need to be defined in the definitions section, and users generally shouldn't need to see them until the contract is prepared. The recommended clause below contains some of the terms to be defined.

A governing law clause specifies the jurisdiction under which a contract is made. The governing law clause determines which law applies when enforcing and interpreting the agreement. It does not specify _where_ or _how_ an agreement is to be enforced, but which law is to apply. This can affect both the formal and substantive aspects of a contract, and determines how it is to be interpreted.

For example, under English law (and in many other common law legal systems), contracts for the sale of land must be in writing and be signed by both parties. Contracts may be void for illegality if the subject of the transaction is prohibited (eg, a contract for murder or the sale of illicit drugs). Each legal system has rules for interpreting agreements when a court or arbitrator is adjudicating a dispute.

In the absence of a governing law clause, the laws of a relevant jurisdiction will typically apply. 'Relevant' may be the jurisdiction in which the contract was made, or in which either of the parties is ordinarily resident or headquartered, or in which the contract is to be performed. Traditionally, however, best practice has been to specify which jurisdiction's laws apply.

Parties generally choose the governing law on the basis of their locations or familiarity with the legal systems, or the particular suitability of a jurisdictions' laws. The complexity of governing law clauses in the context of HiveProtected contracts merits extensive consideration. Therefore, several identified options are examined below to provide background for the recommendation.

All options below have no effect on the	formal provisions of HiveProtected contracts, as all contracts will be in writing and signed. However, some options would affect the substantive provisions, and where applicable this has been noted. Each option primarily affects the interpretation of the contracts in the case of a dispute.

It must be acknowledged that the advantage of using the laws of any particular jurisdiction to govern the interpretation of a contract is likely to be minimal. There may be slight variations in rules, but the ultimate objective of those rules is to give effect to the intention of the parties.

### Governing law — flexible approaches

There are essentially two flexible approaches, both allowing users to choose the governing law clause. The first flexible approach is to provide a field in which users can enter a jurisdiction of their choice. The second approach is to provide a dropdown list from which users can select a jurisdiction. Both have considerable practical drawbacks.

Allowing users to enter a jurisdiction would be the most flexible approach. However, this provides significant scope for user error. HiveProtected contracts are intended to be suitable for users with little-to-no legal knowledge, and while some users may have sufficient knowledge to correctly choose an appropriate jurisdiction, it is expected that most will not. The results would be minimal benefit (as noted previously) with enormous risk. Consider the following examples:

**Scenario 1 — a user inputs 'the United Kingdom' as the jurisdiction.** The United Kingdom is a complex mesh of legal systems. English law and Scottish law are distinct in many aspects, including contracts, as is Northern Irish law to some extent. Devolved legislatures in Northern Ireland, Scotland and Wales have changed the legal landscape, and will continue to do so. 'The United Kingdom' is therefore too imprecise for an arbitrator to know which principles to apply in interpreting the contract.

**Scenario 2 — a user inputs 'Australia' or 'Canada' as the jurisdiction.** Australia and Canada consist of states and territories. While both nations have unified common law systems, this is subject to statutory modification in those subnational units, which has produced slight variations between them. The Canadian state of Quebec is a special case: it has a civi law legal system rather than a common law legal system. Again, 'Australia' and 'Canada' are too imprecise.

**Scenario 3 — a user inputs 'the United States' or 'the European Union' as the jurisdiction.** These are perhaps the vaguest jurisdictions likely to be entered. The US and EU are very similar in constitutional structure, having central governments with limited power, but US states and EU members possess almost all of the law-making authority. The US and EU are significantly more fragmented than Australia and Canada, and an arbitrator would find it impossible to determine which law ought to apply.

An alternative to an input field is a dropdown list, but compiling such a list would be an herculean task. There are about 210 sovereign states, of which some 30 are federations (eg, Australia, Canada, Germany, Russia and the United States), and several others of which have devolved legislatures or separate regional legal systems (eg, Belgium, France, Spain and the United Kingdom). Potentially there are over 700 separate jurisdictions under whose laws a contract could be made. This would make for a very long list.

A side-effect of both approaches outlined is the creation of a gap in enforceability where an arbitrator could not be found who was familiar with the law in question. This would be particularly problematic following the launch of the software, when the number of users is likely to be small. It would be fairly easy to find arbitrators familiar with common law systems (especially English and American law), and perhaps even Chinese, French, German and Japanese law (and possibly others), but the likelihood of finding an arbitrator familiar with South Sudanese law would be slim.

### Governing law — rigid approaches

Instead of allowing users to choose their own governing law (the flexible approaches), rigid approaches which use non-modifiable clauses would be more beneficial. As with flexible approaches, there are two rigid approaches which would be viable. The first is to include a clause specifying a single governing law in _all_ contracts, and the second is to include a clause containing all the rules and principles of interpretation. As will be seen, the second is preferable.

Including a mandatory governing law clause that specifies the same governing law for _every_ HiveProtected contract would ensure consistency of interpretation and avoid user errors which could be fatal to the enforceability of a contract. Choosing English law, Californian law or New York law would likely ensure availability of arbitrators familiar with the principles of contract interpretation under those laws. However, this brings its own problems.

The first problem is that it initially locks out users who may be skilled arbitrators. Secondly, it requires potential arbitrators to familiarise themselves with the contract law specified, and all arbitrators to keep their knowledge of that law up-to-date. Thirdly, and most importantly, it introduces the potential for contracts being found void on grounds of unlawfulness (which is also introduced with the flexible approaches).

Unlawfulness in this context simply means the contract has some aspect contrary to law, whether that be that the service provided is prohibited, or the form of payment is prohibited, or a party lacks capacity under the law to form a contract, and so on. While it may be desirable, from a moral or ethical perspective, to discourage illegal behaviour, the reality is that the scope of what is illegal varies from jurisdiction-to-jurisdiction. For example, providing legal advice without having legal qualifications is contrary to law in many jurisdictions, but other jurisdictions have unregulated or deregulated legal professions.

Is it desirable to allow arbitrators to determine that a contract cannot be enforced because it is void? Most likely not given the variations in laws and their constant change produce unpredictable results as to what is and may be, or stop being, illegal. Specifying a particular jurisdiction in a governing law clause imports this enormous concern, and is why agreements complex enough to need to be in writing tend to be drafted by legal professionals who are aware of these issues.

An alternative approach is to incorporate principles of interpretation directly into every contract. A single, mandatory clause which sets out the rules by which a contract is to be enforced has many advantages. Firstly, there is no scope for user error, meaning the contracts will be robust and consistent in interpretation. Secondly, it allows arbitrators to determine disputes without requiring knowledge of any specific contract law. Thirdly, it allows users to understand how the agreement will be interpreted. Fourthly, it is jurisdiction-agnostic, removing the possibility that the agreement will be void for illegality, and is not affected by changes in the law, but can be updated if and when necessary.

English law has well-established principles for contract interpretation, as does American, Australian and Canadian law. Principles for interpreting HiveProtected contracts can easily be derived from English-based common law rules. Examples of these rules would include: that preference should be given to literal interpretation; that in case of ambiguity, reference may be made to other materials such as messages between parties; and that clauses preventing a party from seeking a remedy are invalid. he rules should be included as an appendix (Appendix I) for ease of reading (they will be considered separately below also).

---

Recommended interpretation clause:

> **Interpretation**
>
> (2) This contract shall be interpreted in accordance with the definitions in Clause (3) and the interpretation rules in Appendix I.
>
> (3) In this contract:
> 
> (a) 'the Arbitrator' means the person identified in Clause (5),
>
> (b) 'the Escrow Agent' means the person identified in Clause (?)(?),
> 
> (c) 'the Vendee' means the party identified in Clause (1)(b), and
>
> (d) 'the Vendor' means the party identified in Clause (1)(c).

---

## Forum selection

In contrast to a governing law clause, a forum selection clause establishes _where_ a contract can be enforced. This may be a specific court or tribunal, or courts within a specified geographic area. A forum selection clause not only covers courts, but also arbitration — parties may agree to arbitration in accordance with specified rules (usually a set of rules promulgated by one of a number of arbitration bodies such as the American Arbitration Association) and nominates an arbitrator or process for appointing an arbitrator (or defers to the rules).

A mandatory arbitration clause is necessary because the parties will be insufficiently identified to be able to file disputes in court. Arbitration will be conducted by a Taskhive user agreed to by the parties in advance, whose services will be engaged for a fee payable in the event a dispute arises. Their fee will be determined by negotiation, and incorporated into the contract. They will interpret the contract in accordance with the interpretation rules specified in the agreement.

The procedural rules for arbitration are less important, as all existing rules have been professionally drafted by or on behalf of their promulgating organisations. However, modifications will be required to adapt any set of rules to Taskhive, with a focus on online dispute resolution and efficient resolution. The United Nations Commission on International Trade Law ('UNCITRAL') has published a mature set of arbitration rules, last updated in 2013, which has many provisions well-suited for online dispute resolution, and which is specifically designed with international contracts in mind.

It is recommended that, like the interpretation rules, the arbitration rules be directly incorporated into the contracts as a mandatory clause which cannot be modified by users. These rules should use the UNCITRAL rules as a base, with adaptations to make them suitable for HiveProtected contracts. The rules should be included as an appendix (Appendix II) for ease of reading (they will be considered separately below also).

---

Recommended arbitration clauses:

> **Dispute resolution**
>
> (4) Any dispute, controversy or claim arising out of or relating to this contract, or the breach, termination or invalidity thereof, shall be settled by arbitration in accordance with the rules in Appendix II.
> 
> (5) The Arbitrator shall be `ARBITRATOR'S PUBLIC KEY`, address `ARBITRATORS'S ELECTRONIC ADDRESS` (hereafter 'the Arbitrator').
> 
> (6) The Arbitrator's fees shall be `AMOUNT` per determined dispute, controversy or claim.
>
> (7) Liability for the Arbitrator's fees shall be determined in accordance with the rules in Appendix II.
>
> (8) The language to be used in the arbitral proceedings shall be `LANGUAGE`.

## Escrow

To mitigate the risk of parties defaulting on an agreement, the use of an escrow agent should be mandatory. Escrow gives the vendor confidence that the vendee actually has the necessary funds to perform the contract, ensures that the vendor will be paid, and allows an arbitrator to make various awards. Escrow involves one party transferring something of value to a third party, who releases it to another party if certain conditions are met. Escrow could be used for holding not only the contract price, but also amounts for arbitrator's fees, and damages in the event either party defaults. The exact arrangements may vary according to party needs.

The vendee will ordinarily pay into escrow the contract price, plus the escrow agent's fees. It may also be appropriate to require the vendor to pay in some agreed amount in case they fail to perform the contract. In contract law, damages are a remedy intended to place a party in the position they would be in _if the contract had been performed_. This can be difficult to quantify, but if a vendor fails to perform a contract, the vendee should generally be entitled to compensation sufficient to engage a comparable replacement.

Suppose, for example, the vendor agrees to create a widget for a website. The vendee agrees to pay US $500, and transfers this to the escrow agent. The vendor defaults, and the vendee is entitled to reclaim their $500. However, the vendee then has to find someone else to perform the work to at least the same standard. If such a replacement would cost $700, the vendee would be entitled to the $200 difference, payable by the defaulter. This does not even take into account damages to compensate for the lost revenue suffered by the vendee.

There will be interactions between escrow, damages and arbitration. The precise amounts each party pays into escrow will vary according to the contract, but there should be separate sections dealing with how much each party agrees to pay into escrow, the quantification of damages, and the arbitration and escrow fees.

Because escrow guarantees the availability of funds, it is desirable that funds be placed in escrow before the substantive aspects of the contract are performed. The exact amounts are unlikely to be known until after the negotiations are complete. Therefore, funds should be placed in escrow after the contract has been signed, but before performance begins. As a safeguard, a right of termination should arise in the event one party does not place the required funds in escrow. This ensures a vendee can recover their funds without penalty, and a vendor can be released from a contract early. 

---

Recommended escrow clauses:

> **Escrow**
> 
> (9) The Escrow Agent shall be `ESCROW AGENT'S PUBLIC KEY`, address `ESCROW AGENT'S ELECTRONIC ADDRESS` (hereafter 'the Escrow Agent').
> 
> (10) The Vendee shall transfer the sum of `AMOUNT AND CURRENCY` to be held in escrow by the Escrow Agent.
>
> (11) The Vendor shall transfer the sum of `AMOUNT AND CURRENCY` to be held in escrow by the Escrow Agent.
>
> (12) Upon receiving the amount in clause (10) or clause (11), the Escrow Agent shall notify the other party to confirm receipt.
>
> (13) If either party fails to comply with clause (10) or clause (11) within `NUMBER` days of the execution of this contract, the other party may terminate the contract without further notice.
>
> (14) A party may exercise its right of termination under clause (12) until compliance with clause (10) or (11) is met.
>
> (15) If a party exercises its right of termination under clause (12) the amount paid into escrow by that party shall be returned without penalty.

---

## Substantive provisions

TBD.

## Intellectual property provisions

TBD.

## Signature and date

TBD.
