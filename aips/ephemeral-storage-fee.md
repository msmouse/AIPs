---
aip: 
title: Ephemeral Storage Fee and Refundable State Bytes
author: msmouse
discussions-to (*optional): 
Status: Draft
last-call-end-date (*optional):
type: Gas
created: 12/12/2023
updated (*optional): 
requires (*optional): 
---

# AIP-X - Ephemeral Storage Fee and Refundable State Bytes

## Summary

Proposed is an evolvement of the Strorage Fee charging scheme where permanent and ephemeral storage are priced respectively according to their distinct characteristics. As a result:

1. Permanent storage fee charged for state items are now refundable, in addition to the fee charged for the allocation of its slot.
2. The per slot "free bytes" quota is removed.
3. The developer can now straightforwardly decide on storage granularity according to the access (modification) pattern of things.
4. Specifically, larger state items are no longer disproportionally punished every time it's updated.


### Goals

 > What are the goals and what is in scope? Any metrics?
 > Discuss the business impact and business value this change would impact.
 > 
...

### Out of Scope

 > What are we committing to not doing and why are they scoped out?

## Motivation

 > Describe the impetus for this change. What does it accomplish?
 > What might occur if we do not accept this proposal?
>
1. Permanant storage: Items in the latest state and associated authentication data structures -- the network has to keep them around indefinitely until deleted. Such storage should be priced high and is subject to refunding once deleted.
2. Ephemeral storage: the transaction itself and it's outputs, including the write set and the events -- they are part of the "ledger history" and subject to pruning. Large transactions and transactions with large outputs can consume the disk space on nodes rapidly despite being enventally pruned, and propagating the bytes across the network is another aspact of resource consumption. Net net, ephemeral storage should be charged expensive enough to retain the network's collective abitlity to keep reasonably long ledger history and propagate them efficiently among nodes, but might be at a lower rate than the permanent storage.

[why was free quota designed]


...

## Impact

 > Which audiences are impacted by this change? What type of action does the audience need to take?


1. Permanent storage fee charged for state items are now refundable, in addition to the fee charged for the allocation of its slot.
2. The per slot "free bytes" quota is removed.
3. The developer can now straightforwardly decide on storage granularity according to the access (modification) pattern of things.
4. Specifically, larger state items are no longer disproportionally punished every time it's updated.

...

## Alternative solutions

 > Explain why you submitted this proposal specifically over alternative solutions. Why is this the best possible outcome?

...

## Specification

 > How will we solve the problem? Describe in detail precisely how this proposal should be implemented. Include proposed design principles that should be followed in implementing this feature. Make the proposal specific enough to allow others to build upon it and perhaps even derive competing implementations.

...

## Reference Implementation

 > This is an optional yet highly encouraged section where you may include an example of what you are seeking in this proposal. This can be in the form of code, diagrams, or even plain text. Ideally, we have a link to a living repository of code exemplifying the standard, or, for simpler cases, inline code.

...

## Testing (Optional)

 > - What is the testing plan? (other than load testing, all tests should be part of the implementation details and won’t need to be called out)
 > - When can we expect the results?
 > - What are the test results and are they what we expected? If not, explain the gap.

...

## Risks and Drawbacks

 > - Express here the potential negative ramifications of taking on this proposal. What are the hazards?
 > - Any backwards compatibility issues we should be aware of?
 > - If there are issues, how can we mitigate or resolve them?

...

## Future Potential

 > Think through the evolution of this proposal well into the future. How do you see this playing out? What would this proposal result in in one year? In five years?

...

## Timeline

### Suggested implementation timeline

 > Describe how long you expect the implementation effort to take, perhaps splitting it up into stages or milestones.

...

### Suggested developer platform support timeline

 > Describe the plan to have SDK, API, CLI, Indexer support for this feature is applicable. 

...

### Suggested deployment timeline

 > Indicate a future release version as a *rough* estimate for when the community should expect to see this deployed on our three networks (e.g., release 1.7).
 > You are responsible for updating this AIP with a better estimate, if any, after the AIP passes the gatekeeper’s design review.
 >
 > - On devnet?
 > - On testnet?
 > - On mainnet?

...

## Security Considerations

 > - Does this result in a change of security assumptions or our threat model?
 > - Any potential scams? What are the mitigation strategies?
 > - Any security implications/considerations?
 > - Any security design docs or auditing materials that can be shared?

## Open Questions (Optional)

 > Q&A here, some of them can have answers some of those questions can be things we have not figured out but we should
