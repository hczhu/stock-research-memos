- tags:: [[AI infrastructure]], [[data-center]], [[capex]], [[opex]], [[power]], [[networking]], [[hyperscalers]]

- ## One-Gigawatt AI Data Center Annual Costs
	- **Source**:
		- user-provided screenshot from `Epoch AI | CC-BY`
		- chart title: `One-gigawatt AI data center annual costs`
	- **Context**:
		- the chart is based on a stylized model of a U.S. hyperscaler AI data center with `1 GW` of nameplate capacity for IT equipment
		- `CapEx` is converted to annual costs over each asset's lifespan, using cost of capital as the discount rate
		- `Facility` includes building shell, mechanical systems, and electrical equipment
		- values below are annualized cost categories, not upfront construction costs
	- **Caveat**:
		- the screenshot provides labeled values but does not include the full underlying model assumptions
		- totals below are derived from the labeled chart values

- ## Extracted Annual Cost Table
	| Cost category | Cost type | Annual cost | Share of total annual cost | Context |
	| --- | --- | ---: | ---: | --- |
	| `Servers` | `CapEx` | `$5.00B` | `58.6%` | Largest cost bucket; represents AI compute servers as annualized capital cost. |
	| `Facility` | `CapEx` | `$1.40B` | `16.4%` | Building shell, mechanical systems, and electrical equipment. |
	| `Network infrastructure` | `CapEx` | `$1.20B` | `14.1%` | Networking is the third-largest bucket and a major part of scaled AI cluster cost. |
	| `Energy` | `OpEx` | `$590M` | `6.9%` | Largest operating-cost item; direct power consumption cost. |
	| `Taxes` | `OpEx` | `$140M` | `1.6%` | Recurring tax burden in the stylized model. |
	| `Maintenance` | `OpEx` | `$120M` | `1.4%` | Recurring maintenance cost for facility and infrastructure. |
	| `Labor` | `OpEx` | `$40M` | `0.5%` | Small relative to power and capitalized infrastructure. |
	| `Utility works` | `CapEx` | `$20M` | `0.2%` | Grid / utility-related works shown as annualized CapEx. |
	| `Land` | `CapEx` | `$13M` | `0.2%` | Very small annualized cost versus servers, facility, and networking. |
	| `Water` | `OpEx` | `$6M` | `0.1%` | Smallest labeled operating-cost bucket. |

- ## Cost Split Summary
	| Metric | Value | Context |
	| --- | ---: | --- |
	| Total annual cost | `$8.53B` | Sum of all labeled annualized cost categories. |
	| Annualized CapEx cost | `$7.63B` | Servers, facility, network infrastructure, utility works, and land. |
	| Annual OpEx cost | `$896M` | Energy, taxes, maintenance, labor, and water. |
	| CapEx share of annual cost | `89.5%` | The model is overwhelmingly capital-cost driven. |
	| OpEx share of annual cost | `10.5%` | Operating costs are meaningful but much smaller than annualized infrastructure cost. |
	| Servers + network infrastructure | `$6.20B` | Compute and networking together account for about `72.7%` of total annual cost. |
	| Servers + facility + network infrastructure | `$7.60B` | The top three buckets account for about `89.1%` of total annual cost. |
	| Energy as share of OpEx | `65.8%` | Power dominates recurring operating cost. |

- ## Stock Implications
	- The cost stack is primarily a compute and capital-equipment story: servers alone are nearly `59%` of annualized cost.
	- Networking is large enough at `$1.2B` annually to matter as a separate AI infrastructure investment theme, not just an attachment to server spend.
	- Facility cost at `$1.4B` shows that power delivery, cooling, building shell, and electrical systems are major beneficiaries of AI data-center expansion.
	- Energy is much smaller than servers on an annualized basis, but it dominates OpEx and becomes strategically important as clusters scale to multi-gigawatt footprints.
	- Labor, land, water, and utility works are visible constraints but not the major dollar pools in this stylized annual-cost model.

- ## Memo Takeaway
	- A `1 GW` AI data center is modeled as roughly an `$8.5B` annual-cost machine, with nearly `90%` of annualized cost tied to CapEx categories.
	- For stock work, this supports prioritizing the infrastructure value chain around AI servers, networking, facility electrical / cooling systems, and power availability.
