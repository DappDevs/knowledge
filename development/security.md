# Security

Security is very important to smart contract programming, and must be considered at all stages of the process.
"Fixing" bugs is not an option to smart contracts, so the only means to provide high-reliability code is
by reducing bugs, or redefining the problem as "reducing risk".
Obviously, you can never mitigate all bugs in a software application, so a smart contract engineer
must create processes for mitigating, stopping, or migrating away from bugs when they happen.
They must also consider design mechanisms to thwart possible attacks, and to enable
the contract to scale appropiately as designed, mitigating instabilities in the platform.

A smart contract engineer should be familar with the the
[OWASP Security Model](https://www.owasp.org/index.php/OWASP_Risk_Rating_Methodology).
This framework helps standardize the identification and assignment of bug severity,
ultimately aiding the designer in making choices when tradeoffs occur in the resolution of a bug.

Smart contract engineers should also be familiar with
[known vulnerabilities](https://consensys.github.io/smart-contract-best-practices/known_attacks/).
This resource contains all of the current known attacks against Ethereum smart contracts,
and should be considered a checklist before completing design.

# Reducing risk

The best way to avoid a vulnerability from being exploited and taking down your smart contract is by
minimizing the losses possible. A contract holding large amounts of ether or other valuable quantity
for long periods of time will always be inherently more attractive than a contract that doesn't.
Part of the design process should therefore be mitigating this risk through the design of proper lifecycles,
and ensuring that valuable assets are held for the minimum amount of time necessary.

# Mitigation

Bugs will always happen, wether they are zero-day vulnerabilities or cascaded failures multiple levels deep
(it is assumed through the testing and auditing process that simple vulnerabilities have been caught).
It is therefore necessary to design a plan on what to do in case a vulnerability is present in your smart contracts.

"Circuit Breaker" (or "Emergency Stop") functionality allows you to design a boolean value that can be set by a
trusted party (or other participants in a contract) in order to halt execution of other functions.
This allows the oppurtunity to redeploy a patched smart contract with enough time to test before release.

"Rate Limiting" and adding "Speed Bumps" to your application are methods to reduce the liklihood that a significant
hack can happen without a chance to respond, reducing the ability for a malicious party to move funds quicky.
This is effective for state transitions that move large amounts of funds or allow unilateral decisions to be made.
