# Workshop 3 - Strategic Scenarios [draft] - Part 2

# 4. Threat Evaluation of Each Actor

The threat level of each stakeholder is calculated from the two factors evaluated in the previous section:

**Threat level = Exposure / Cyber Reliability**

- A ratio of **1** means the access the stakeholder has matches the trust the company can give them.
- A ratio **above 1** means the stakeholder has more access than the company can trust them with.
- The higher the ratio, the higher the threat.

The classification used:

| Threat level (ratio) | Zone | Meaning |
| --- | --- | --- |
| >= 2 | Critical | Exposure is at least double the reliability. The stakeholder is a critical stakeholder (PPC). |
| > 1 and < 2 | Watch | Exposure is higher than reliability. The stakeholder is monitored. |
| <= 1 | Acceptable | Reliability matches or exceeds exposure. |

| Stakeholder | Exposure | Cyber Reliability | Threat level | Zone | Main threat |
| --- | --- | --- | --- | --- | --- |
| Suppliers | 4 | 1 | 4.00 | Critical | Falsified or wrong data (stocks, prices, delays) misleads the AI decisions. A compromised supplier account can be used as an entry point. |
| Cleaning service provider | 3 | 1 | 3.00 | Critical | Physical access to servers, network equipment and workstations: theft, corruption, rogue USB device, accidental unplugging. |
| Warehouse service | 2 | 1 | 2.00 | Critical | Wrong data entry, unintentional leak of warehouse information, misuse of IoT devices. |
| Carrier Drivers | 2 | 1 | 2.00 | Critical | Falsified delivery data, lost or stolen mobile devices and IoT trackers. |
| Clients | 2 | 1 | 2.00 | Critical | Fraudulent orders, account takeover, attacks through the sales website used as an entry point. |
| Sales Service | 4 | 3 | 1.33 | Watch | Leak of client data, loss of clients, phishing. |
| Information system Admin (DSI) | 6 | 5 | 1.20 | Watch | Compromise of a privileged account gives full control of the system. |
| Technical Service (Engineers) | 6 | 5 | 1.20 | Watch | Design errors, tampering with the AI layer, insecure deployment. |
| Software providers | 6 | 5 | 1.20 | Watch | Supply chain attack through malicious updates or vulnerable ERP / WMS components. |
| Administration | 5 | 5 | 1.00 | Acceptable | Targeted phishing of managers, leak of sensitive information. |
| Finance & accountants service | 3 | 3 | 1.00 | Acceptable | Financial fraud, theft of financial data. |
| Website management service | 5 | 5 | 1.00 | Acceptable | Wrong configuration exposing sensitive information to the public. |
| Hosting service provider | 5 | 5 | 1.00 | Acceptable | Provider outage or breach leading to data exposure and website unavailability. |
| Other competitor spare parts companies | 1 | 1 | 1.00 | Special case | Espionage, intrusion, alteration of information. |

**Note on competitors:** competitors are not a normal stakeholder. They have no legitimate access to the system but they have the intention to harm the company, so the ratio does not reflect their threat. They are treated as a **risk source** (a high source of threat, as mentioned in the stakeholders evaluation), not rated by the ratio.

**Note on external API providers:** the external API providers (weather, traffic and road conditions, suppliers) mentioned in the ecosystem definition are not in the stakeholders table. They provide data to the AI layer, so they carry a data integrity risk similar to the suppliers, and should be considered with them.

# 5. PPC - Parties Prenantes Critiques (Critical Stakeholders)

The PPCs are the stakeholders in the **Critical zone** (threat level >= 2).

| PPC | Threat level | Why it is critical | Possible security measures |
| --- | --- | --- | --- |
| Suppliers | 4.00 | They have a significant access to the system (4/6) with a very low cyber reliability (1/6). Wrong or falsified data directly falsifies the decisions of the AI. | Validation and anomaly detection of supplier data, authenticated APIs, security clauses in contracts. |
| Cleaning service provider | 3.00 | They have physical access to the IT infrastructure with no cybersecurity awareness. | Locked server room, supervised or scheduled access, access logs, disabled USB ports. |
| Warehouse service | 2.00 | They manage goods, stocks and orders data without cybersecurity awareness, so errors and leaks are likely. | Awareness training, input controls, least privilege access. |
| Carrier Drivers | 2.00 | They provide delivery data and may falsify it, and they use mobile devices outside the company. | Strong authentication on mobile apps, cross-checking with IoT / GPS data, remote wipe of lost devices. |
| Clients | 2.00 | They use the internet-facing website, which can be used for fraud or as an entry point to the system. | Web application firewall, rate limiting, strong authentication, separation of the website from the internal network. |

**Stakeholders to monitor (not PPC by the ratio):** the **DSI, Technical Service (Engineers) and Software providers** are in the watch zone. Their ratio is low only because they are reliable, but their exposure is the maximum (6/6), so any compromise of them would have a huge impact on the whole system. They should be kept in mind when building the strategic scenarios.

**Competitors** are kept as a **risk source** and not as a PPC.

# 6. Summary

- **5 PPCs:** Suppliers, Cleaning service provider, Warehouse service, Carrier Drivers, Clients.
- **3 stakeholders to monitor for their high impact:** DSI, Technical Service (Engineers), Software providers.
- **1 risk source:** Competitor spare parts companies.
