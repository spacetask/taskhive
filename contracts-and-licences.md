# Contracts and Licences White Paper

---

**DISCLAIMER: This document does not constitute legal advice and should not be relied upon for commercial transactions or conducting litigation. Consult a local lawyer in your jurisdiction if legal advice is needed.**

---

## Introduction

This paper considers the challenges that exist for the design of software that allows pseudonymous and non-pseudonymous parties to form contracts and licence agreements. It first outlines the requirements for formal provisions; that is, the aspects of an agreement that are not dependent on the content. It then explores the various substantive provisions that parties may choose to incorporate, which, in simple terms, is the actions the parties are agreeing to perform.

A modular approach has been adopted, consisting of a number of mandatory global provisions, and provisions which may become mandatory based on user input. It should be possible for such software (a contract and licence 'wizard') to include a set number of provisions which can be combined as required by its users, rather than allowing users to choose from umpteen different agreements, which would reduce flexibility and become burdensome to maintain.

## Formal provisions

The formal provisions of a contract can be contrasted with the substantive provisions. Formal provisions are those elements that relate to form, and which are largely independent of the primary obligations that the parties have assumed. These generally include definitions of terms used, the identification of the parties, a governing law clause, a forum selection clause, the signatures or other marks of the parties, and the date the agreement was executed.

While there is flexibility in how formal provisions are drafted (and it may not matter whether they are included, depending on the nature of the contract), it is best drafting practice to include them as, if drafted properly, they establish with reasonable certainty where, how and between whom a contract is to be enforced, as well as when it came into existence.

### Parties

It is essential to the enforceability of a contract that its parties are identified with precision and certainty. Without a high degree of certainty, the parties will find it difficult to know who can enforce the contract against them, and against whom they can enforce the contract.

In standard practice, incorporated or otherwise registered entities will be identified by their full legal name, legal form, registered address, registration number, and jurisdiction of incorporation or registration. Individuals and sole traders are normally identified by their full name, trading name and business number (if either are applicable), and full address (for additional certainty, a personally-identifying number such as a driver's licence or passport number may be included, though this raises privacy concerns).

An example of how an incorporated entity would be identified: 'Squiggle Limited, registered office 1 Paper Mews, 330 High Street, Dorking, Surrey, United Kingdom RH4 2TU, UK company number 05823082.' An example of how a sole trader would be identified: 'Justin Stenning, trading as D.E.R.P., Australian business number 73 197 084 806, 1 Fictional Street, Eaglehawk, Victoria, Australia 3556.'

A challenge is presented when parties to an agreement wish to conceal their identities. While each party may be able to prove their 'ownership' of a pseudonym, a well-designed system that protects the pseudonymity of its users will not allow users to obtain sufficiently identifying information of other users. In such an arrangement, a person will at best be able to prove their entitlement to enforce the contract: they will not be able to prove against whom they are entitled to enforce it.

Of course, such information might be obtained by a subpoena, under which a court orders that the identity of a user be revealed. However, this assumes a centralised database of users containing that information which is under the control of an identifiable individual or corporation. A decentralised system that does not store that information is too robust for a traditional approach.

A possible solution to the problem of pseudonymous parties is to mandate the use of escrow and arbitration where one or both parties is pseudonymous. Escrow and arbitration will be discussed further below, for some remarks are appropriate now. Mandating the use of an escrow agent places control over the subjects of the transaction in the hands of a third party, allowing for its enforcement without the need to reveal the identities of the parties. Combined with escrow, an arbitrator (who may be the escrow agent if willing) could resolve a dispute without the formal identification required by a court.

---

- **Select:** `PSEUDONYMOUS` or `NON-PSEUDONYMOUS`
  - **If** `PSEUDONYMOUS`:
    - `ESCROW` (mandatory) and `ARBITRATION` (mandatory)
   - **If** `NON-PSEUDONYMOUS`:
    - **Select:** `INDIVIDUAL` or `REGISTERED COMPANY`
      - **If** `INDIVIDUAL`:
        - **Inputs:**
          - `FULL NAME` (mandatory)
          - `TRADING NAME` (optional)
          - `BUSINESS NUMBER` (optional)
          - `FULL ADDRESS` (mandatory)
      - **If** `REGISTERED COMPANY`:
        - **Inputs:**
          - `FULL NAME AND FORM` (mandatory)
          - `REGISTERED OFFICE` (mandatory)
          - `REGISTRATION NUMBER` (mandatory)

---

### Definitions

The terms of an agreement will generally be interpreted using their ordinary meaning unless the context indicates otherwise. This may be implicit (inferred from the way a word is used) or explicit (specifically stated). A definitions section is helpful for removing ambiguity by explicitly stating the meaning of a word that has multiple ordinary meanings, and allows a word to be used any number of times with a consistent meaning throughout the agreement.

Because the function of the software is to assist persons with limited legal knowledge form sound and enforceable agreements, definitions should be fixed. The length of the definitions section _may_ be variable depending on the options that the user selects, but there should be no scope for users to define terms themselves. Preventing users from defining terms avoids poor drafting and potentially conflicting definitions.

Care must be taken to ensure that the software does not itself produce conflicting definitions, although it may be necessary to define the same word differently based on a user's selections (though this is not ideal and is likely avoidable). Careful and concise drafting of all clauses should eliminate the need for a lengthy definitions section.

### Governing law

A governing law clause specifies the jurisdiction under which a contract is made: that is, which law applies when enforcing and interpreting the agreement. In the absence of a governing law clause, the laws of a relevant jurisdiction will typically apply: 'relevant' may be the jurisdiction in which the contract was made, or in which either of the parties is ordinarily resident, or in which the contract is to be performed.

It is important to note here that a governing law clause does not specify _where_ an agreement is to be enforced, but rather _which law is to apply_. The former is dealt with a forum selection clause (see below). While it is typical for the governing law and the forum to be connected (a contract could specify Californian law as the governing law, and California or a specific court in California as the forum), this is not strictly necessary, especially in the case of arbitration.

There are about 210 sovereign states. Some thirty of those are federations (eg, Australia, Canada, Germany, Russia and the United States) and many also have devolved legislatures or separate regional legal systems (eg, Belgium, France, Spain and the United Kingdom). The possible number of jurisdictions under which a contract could be made is likely to be greater than 700.

Despite some convergence and the promulgation of model laws, differences in contract law naturally exist between jurisdictions. Sometimes these differences can be so minor (often as a result of harmonisation or shared legal ancestry) that the same contract could be enforced in one jurisdiction as much as another: for example, a simple contract drafted according to the laws of New South Wales is likely to be enforceable in any other Australian state, and probably also in any Canadian province (except Quebec), England, or a state of the United States (except Louisiana).

In other circumstances the differences can be quite major. One prominent area where contract law differs significantly between jurisdictions is the issue of _consideration_. Consideration is the 'price' of a contract: it is what each party exchanges. In a simple sale of goods contract, the seller's consideration is the goods (or the promise to supply goods), and the buyer's consideration is the agreed sum (or the promise to that sum). Consideration is an _essential_ element of a contract in common law jurisdictions (those with legal systems descended primarily from English law); if a party does not provide consideration they are not entitled to enforce the contract. However, In civil law jurisdictions (those with legal systems derived from continental European law) a contract _can_ be enforced even if one party has not given or promised anything. England, as a common law jurisdiction, requires consideration, but Scotland, which follows the civil law tradition, does not!

Allowing contracting parties to choose a jurisdiction would provide flexibility at the cost of a significant increase in the administrative and financial burdens of the system. Firstly, each provision of the form agreements would need to be translated by a professional translator twhoch specialises in documents of a legal nature. Secondly, legal advice would need to be sought in the relevant jurisdictions to advise on and confirm the enforceability of the form agreements. Thirdly, it would be necessary to monitor and stay abreast of legal developments in all relevant jurisdictions and periodically review provisions to ensure the continued validity of the form agreements. These challenges are amplified in the case of an open-source project with limited commercial or financial backing.

It is posited that in the case of the relatively simple contracts and licence agreements that the software would provide, the parties would be concerned less with whether the agreement is enforceable under the laws of a particular jurisdiction, but more with whether the agreement could be enforced at all from both a theoretical and practical perspective. The fact that a contract _is_ reasonably enforceable is likely to be sufficient to encourage the parties to uphold their ends of the bargain.

Consequently, a simpler approach, at least initially, would be to include a mandatory governing law clause specifying a single jurisdiction. English contract law is advantageous because the language is widely spoken in terms of geographic spread, and the law is stable and well-understood. It should pose no unusual difficulties for creating enforceable agreements.

### Forum selection

A forum selection clause designates the tribunal or tribunals in which a dispute arising under an agreement can be enforced. Whereas a governing law clause determines the applicable law, a forum selection clause determines the venue. It is important to differentiate between the two and ensure an agreement has provisions dealing with both because a forum selection clause may be broader or narrower than the governing law clause.

For example, a contract formed under New York law will be subject to the state law of New York and the federal law of the United States, but this does not expressly indicate which courts or tribunals may determine the dispute. It perhaps suggests that courts in New York ought to have jurisdiction, but it wouldn't necessarily preclude a court or tribunal in another jurisdiction from applying New York law to determine the dispute, and perhaps a court in New York would decline jurisdiction if neither party was resident or headquartered in New York. Hence, both the law and forum in which it is to be applied should be specified clearly.

Sometimes the parties may wish to designate a more specific court. In the example in the preceding paragraph, even if it was specified that the contract must be enforced in New York, it is conceivable that a number of courts could claim jurisdiction over the dispute by virtue of their having jurisdiction over certain disputes in New York. It is common for businesses to designate a court close to their main offices or headquarters as having exclusive jurisdiction over form contracts they offer to consumers, such as a county court or equivalent. Again, this should be appropriately specified in a forum selection clause.

Still further, forum selection may be more than a mere matter of geographical convenience. The venue chosen may have expertise in disputes of a particular nature such as maritime disputes, or may involve reduced costs and a simpler procedure: for example, in New South Wales contracting parties may prefer to resolve disputes in the NSW Civil and Administrative Tribunal or Small Claims Court where possible to benefit from lower fees and faster dispute resolution. 

Arbitration, as opposed to litigation, has many of these advantages. Arbitration clauses are now standard features of commercial and consumer agreements. Arbitration is attractive for a number of reasons. First, it is much faster than litigation, and disputes can be resolved in a matter of weeks rather than months or years. Second, it is less formal in terms of procedure and admissibility of evidence, making it more accessible to laypersons. Third, the less formal nature of proceedings means that parties will not necessarily require legal representation which, combined with the faster process and limited fees, makes arbitration cheaper than litigation. Fourth, parties who, despite their dispute, wish to maintain an otherwise amicable commercial relationship may find it easier to do so if they choose arbitration because the dispute is resolved quickly and allows the relationship to resume expeditiously.

### Signature

### Date

## Substantive provisions

### Subject

### Completion date

### Exchange

### Assignment, licence, or neither

#### Assignment

#### Licence

- Exclusive licence or non-exclusive licence
  - Portfolio exception
  - Copyleft licences
- Limited licence or unlimited licence
  - Limited by duration
  - Limited by territory
  - Limited by use

#### Assignment and licence

#### No authorship

#### Confidentiality

#### No competition

