# Security policy

Open-BEATBox is laboratory instrumentation: a control GUI, module firmware and a static website. It is not intended to be exposed to the public internet, and it stores no personal data.

## Reporting a vulnerability

Email [eric.burguiere@cnrs.fr](mailto:eric.burguiere@cnrs.fr) rather than opening a public issue. Please include what you found, how to reproduce it, and which repository and version.

We will acknowledge the report, and will credit you when the fix is published unless you prefer otherwise.

## Scope

Worth reporting:

- Remote code execution or injection in the control software
- Firmware flaws that could damage hardware or harm an animal
- Credential or token leakage in the repositories or CI configuration
- Supply-chain problems in declared dependencies

Out of scope: the deployed website is static and has no backend, so it has no authentication, sessions or database to attack.

## Deployment advice

Run the control software on a lab network, not a public one. The system is designed for a local machine connected to the cage hardware.
