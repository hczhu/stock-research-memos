- tags:: [[DRAM]], [[HBM]], [[NAND]], [[Samsung]], [[SK Hynix]], [[Micron]], [[semiconductor]], [[AI infrastructure]], [[supply]]

- ## Memory Market Size and Big 3 Financials — Data Compilation
	- **Source**: Synthesized from memos in this repo; primary sources include Morgan Stanley, Epoch AI, UBS, Goldman Sachs, Gartner
	- **Note**: Dollar market size figures for individual server DRAM and HBM segments are not fully broken out in current memos; gaps are marked below. Big 3 quarterly segment revenue breakdowns are not captured in current memos — only margin, capex, and pricing data are available

- ## Table 1: Server Memory Market Size ($ Billion)

	| Segment | 2024 | 2025 | 2026E | 2027E | 2028E |
	|---|---:|---:|---:|---:|---:|
	| HBM | $12.1B | $31.5B | ~$60–75B† | ~$110–130B† | n/a |
	| Server DRAM (non-HBM) | n/a | n/a | n/a | n/a | n/a |
	| **Total server memory** | n/a | n/a | n/a | n/a | n/a |
	| **Total memory (all)** | n/a | **$220B** | **$890B** | n/a | n/a |

	- **HBM 2024/2025**: Epoch AI; tracks HBM spend across NVIDIA, AMD, Google, Amazon chips (all major HBM buyers — effectively total HBM market). Q4 2025 alone = $11.0B, implying ~$44B+ annualized run rate entering 2026
	- **HBM 2026E/2027E (†)**: Derived from UBS volume model (+88% YoY in 2026E, +76% in 2027E) applied to 2025 base, with modest ASP compression assumed. Not directly sourced from a memo dollar figure
	- **Total memory $220B/$890B**: Morgan Stanley Chipflation report (June 2, 2026); $890B reflects a +71% upward revision in just 3 months from a prior $520B estimate; includes all memory types globally
	- **Server DRAM dollar market**: Not available in current memos. Volume data available: commodity DRAM demand 316,640 mn Gb (2025) → 469,675 mn Gb (2026E) → 619,970 mn Gb (2027E) per Morgan Stanley, of which server's share of DRAM bit demand rises from 37% (2023) → 59% (2028E)

- ## HBM Volume Demand (mn Gb) — Morgan Stanley / UBS

	| Source | 2023 | 2024 | 2025 | 2026E | 2027E |
	|---|---:|---:|---:|---:|---:|
	| Morgan Stanley (demand) | 1,866 | 9,059 | 19,516 | 34,205 | 56,085 |
	| Morgan Stanley (supply) | 3,150 | 11,436 | 22,765 | 34,997 | 53,837 |
	| UBS (demand, bn GB) | — | — | 17.5 | 32.9 | 58.0 |
	| UBS YoY growth | — | — | — | +88% | +76% |

	- MS and UBS figures broadly consistent; slight differences reflect model vintage and methodology
	- HBM supply and demand converge in 2026E and reverse (demand > supply) by 2027E per MS model

- ## Table 2: Big 3 Latest Quarter Revenue by Segment

	**Most recent comparable data available in memos. Full segment revenue breakdowns are not captured — these require earnings reports not yet in this repo.**

	### SK Hynix — Q1 2026 (most recent with data)

	| Metric | Value | Source |
	|---|---|---|
	| Overall memory revenue | n/a in memos | — |
	| HBM revenue | n/a in memos | — |
	| Server DRAM revenue | n/a in memos | — |
	| Consumer DRAM revenue | n/a in memos | — |
	| NAND revenue | n/a in memos | — |
	| **Operating margin** | **72%** | MS / super-cycle memo |
	| Operating profit vs. prior year | More in Q1 alone than all of prior year | super-cycle memo |
	| FY27E operating margin (DRAM) | 82.8% | Goldman Sachs estimate |
	| FY27E operating profit revision | +21% vs. prior GS estimate | Goldman Sachs |
	| FY28E operating profit revision | +24% vs. prior GS estimate | Goldman Sachs |

	### Samsung — Latest Available Data

	| Metric | Value | Source |
	|---|---|---|
	| Overall memory revenue | n/a in memos | — |
	| HBM revenue | n/a in memos | — |
	| Server DRAM revenue | n/a in memos | — |
	| Consumer DRAM revenue | n/a in memos | — |
	| NAND revenue | n/a in memos | — |
	| DRAM contract price, Q1 2026 | ~KRW 20,000 (+100% QoQ) | pricing memo |
	| DRAM contract price, Q2 2026 | ~KRW 26,000 (+30% QoQ) | pricing memo |
	| HBM yield rate, 2025 | 60% | MS Exhibit 30 |
	| HBM yield rate, 2026E | 55% (declining — execution risk) | MS Exhibit 30 |
	| HBM UTR, 2025 | 60% (vs. 100% for peers) | MS Exhibit 30 |
	| Memory capex 2026E | $40.0B (+20% YoY) | semi capex memo |
	| Samsung MX operating profit FY2026E | KRW ~5T (>60% decline) | DRAM pricing memo |

	### Micron — Latest Available Data

	| Metric | Value | Source |
	|---|---|---|
	| Overall memory revenue | n/a in memos | — |
	| HBM revenue | n/a in memos | — |
	| Server DRAM revenue | n/a in memos | — |
	| Consumer DRAM revenue | n/a in memos | — |
	| NAND revenue | n/a in memos | — |
	| **Gross margin** | **~74%** (characterized as all-time high) | Michael Burry bear-case memo |
	| Memory capex FY2026E (FYE Sep) | $20.0B (+45% YoY) | semi capex memo |
	| HBM yield rate, 2025 | 70% | MS Exhibit 30 |
	| HBM UTR, 2025 | 100% | MS Exhibit 30 |

- ## Big 3 Capital Expenditure ($ Billion)

	| Vendor | 2024 | 2025 | 2026E | 2025 Growth | 2026E Growth |
	|---|---:|---:|---:|---:|---:|
	| Samsung | $33.0B | $33.4B | $40.0B | +1% | +20% |
	| SK Hynix | $11.7B | $19.4B | $27.4B | +66% | +42% |
	| Micron (FYE Sep) | $8.1B | $13.8B | $20.0B | +70% | +45% |
	| **Total** | **$54.9B** | **$69.1B** | **$90.3B** | **+26%** | **+31%** |

	- **Source**: SC-IQ estimates via Morgan Stanley semiconductor capex memo

- ## HBM Production Share by Vendor (Implied from MS Exhibit 30)

	| Vendor | 2025 Production (mn Gb) | Share | 2027E Production (mn Gb) | Share |
	|---|---:|---:|---:|---:|
	| SK Hynix | 12,830 | 56% | 22,226 | 41% |
	| Samsung | 6,387 | 28% | 21,239 | 40% |
	| Micron | 3,548 | 16% | 10,372 | 19% |
	| **Total** | **22,765** | 100% | **53,837** | 100% |

	- SK Hynix leads in 2025 on volume share, driven by superior yield (75%) and UTR (100%)
	- Samsung and SK Hynix converge by 2027E as Samsung recovers UTR to 100% and yield to 70%
	- Micron grows fastest proportionally but remains smallest in absolute volume

- ## Data Gaps — What to Add
	- **Earnings memos needed**: Add SK Hynix Q1 2026, Samsung Q1 2026, Micron FQ2 2026 earnings call notes to `earnings/` to fill in segment revenue breakdowns
	- **Server DRAM dollar TAM**: Requires a Gartner / IDC / IHS Markit market sizing report — not currently in memos
	- **2028 HBM forecast**: Not available in current memos; MS and UBS models end at 2027E
