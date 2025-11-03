# Comparative Global AI Regulation: EU, China, and the US

[![arXiv](https://img.shields.io/badge/arXiv-2410.21279-b31b1b.svg)](https://arxiv.org/abs/2410.21279)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**Comparative Global AI Regulation: Policy Perspectives from the EU, China, and the US**

Jon Chun¹, Christian Schroeder de Witt², Katherine Elkins¹  
¹Kenyon College | ²Oxford University

*October 2024*

---

## 🌍 Overview

As artificial intelligence rapidly advances as a powerful dual-use technology, nations worldwide are developing diverse regulatory frameworks to balance innovation with safety. This comprehensive study compares three distinct approaches to AI governance taken by the European Union, China, and the United States, including detailed analysis of California's SB 1047.

### Core Findings

- **EU AI Act**: First comprehensive AI law with risk-based framework emphasizing fundamental rights
- **China's Hybrid**: Centralized guidance + decentralized innovation + selective enforcement  
- **US Distributed**: 50+ agencies via EO 14110, market-driven, voluntary commitments
- **CA SB 1047**: Compute-based thresholds for frontier models (vetoed September 2024)
- **Geopolitics**: US-China tensions heavily influence regulatory priorities

---

## 📋 Quick Navigation

- [Repository Structure](#repository-structure)
- [Key Documents](#key-regulatory-documents)
- [Detailed Analysis](#detailed-regional-analysis)
- [Comparative Framework](#comparative-framework)
- [Usage](#installation--usage)
- [Citation](#citation)
- [Contributing](#contributing)

---

## 🗂️ Repository Structure

```
ai-regulation-comparative-study/
├── paper/comparative_ai_regulation_2024.pdf
├── regulatory_documents/
│   ├── eu/ (AI Act, GDPR, DMA)
│   ├── china/ (Cybersecurity, PIPL, GenAI Measures)
│   ├── us_federal/ (EO 14110, AI Bill of Rights)
│   └── us_california/ (SB 1047 text, veto letter)
├── analysis/
│   ├── framework_comparison_matrix.xlsx
│   ├── sb_1047_stakeholder_positions.csv
│   └── timeline_analysis.json
├── visualizations/
│   ├── decision_trees/
│   ├── comparative_charts/
│   └── maps/
├── data/ (structured regulatory data)
├── code/ (scrapers, analysis, visualization)
└── resources/ (glossary, further reading)
```

---

## 📜 Key Regulatory Documents

### EU AI Act (2024)
- **Status**: Adopted August 2024
- **Scope**: All AI on EU market
- **Risk Model**: 4-tier pyramid
- **GPAI Threshold**: 10²⁵ FLOPS
- **Penalties**: €35M or 7% revenue

### China Laws (2017-2023)
- Cybersecurity (2017)
- Data Security (2021)
- PIPL - Personal Info (2021)
- Algorithm Recommendation (2022)
- Deep Synthesis (2023)
- Generative AI Measures (2023)

### US EO 14110 (2023)
- 100+ tasks across 50+ agencies
- Safety, innovation, civil rights focus
- US AI Safety Institute (NIST)
- Deadlines met 2024

### CA SB 1047 (Vetoed 2024)
- $100M/10²⁶ FLOP threshold
- Mandatory audits, shutdown capability
- Vetoed: size ≠ risk, need context

---

## 🔍 Detailed Regional Analysis

### European Union

**Governance**: EU AI Office + Member State authorities

**Risk Pyramid**:
- 🔴 Prohibited: Social scoring, manipulation, mass surveillance
- 🟠 High-Risk: Critical infrastructure, employment, law enforcement
- 🟡 Limited: Chatbots, deepfakes (transparency required)
- 🟢 Minimal: No specific obligations

**GPAI Models**: Special category for 10²⁵+ FLOP models

**Brussels Effect**: Aims to set global standard like GDPR did

### China

**Philosophy**: CCP principles + market innovation

**3-Step Compliance**:
1. Model Registration with CAC
2. Data Management (source legitimacy, content verification)  
3. Ongoing Monitoring (security, ethics, incidents)

**Made in China 2025**: Support 10,000 "Little Giants" (SMEs)

**Enforcement Reality**: Strict on paper, lenient for small players, harsh reactive crackdowns when stability threatened

**Stats**: Only 546 models registered (vs 500K+ global)

### United States (Federal)

**EO 14110 Priorities**:
1. Federal Use (29 req, 40 entities)
2. Safety/Security (27 req, 36 entities)
3. Innovation (21 req, 10 entities)
4. Civil Rights, Consumer Protection, Privacy, International, Workers

**US AI Safety Institute**: NIST-based, multi-stakeholder, voluntary frameworks

**Philosophy**: Permissive, reactive, self-regulation, existing laws applied

**Criticisms**: Fragmented, regulatory capture risk, slow to address harms

### California (SB 1047 - Vetoed)

**Why It Mattered**: CA = 5th largest economy, home to AI leaders, history of leading US policy

**Covered Models**: >$100M cost OR >10²⁶ FLOPS training

**Requirements** (before veto):
- Immediate: Cybersecurity, safety protocol, shutdown capability
- 2026: Third-party audits, compliance statements, incident reporting
- 2027: Board of Frontier Models, annual regulations

**Coalition Splits**: 
- Pro: Bengio, Hinton, SAG-AFTRA, Musk
- Con: Pelosi, Khanna, Meta, Google, LeCun, Fei-Fei Li, VCs

**Newsom's Veto**: Size ≠ risk, need deployment-context approach

**Legacy**: Elevated debate, revealed divisions, blueprint for future

---

## 🔄 Comparative Framework

| Dimension | EU | China | US Federal | CA SB 1047 |
|-----------|----|----|-----------|------------|
| **Philosophy** | Rights-based | Harmony + Growth | Market-driven | Frontier-focused |
| **Structure** | Centralized | Hybrid | Distributed | State AG |
| **Threshold** | 10²⁵ FLOP | None | None | 10²⁶ FLOP |
| **Pre-Market** | High-risk approval | CAC registration | None | Safety protocol |
| **Penalties** | €35M or 7% revenue | Varies | Existing law | Compute-based |
| **Approach** | Ex-ante | Reactive selective | Ex-post | Ex-ante |
| **Innovation** | Concern re: burden | SME-friendly in practice | Encouraged | VC opposition |

---

## 🛠️ Installation & Usage

```bash
# Clone and install
git clone https://github.com/[user]/ai-regulation-comparative-study.git
cd ai-regulation-comparative-study
pip install -r requirements.txt
```

### Compare Frameworks

```python
from code.analysis import compare_frameworks

# Load regulations
eu = compare_frameworks.load_regulation('eu_ai_act_2024')
china = compare_frameworks.load_all_china_laws()
us = compare_frameworks.load_regulation('us_eo_14110')

# Compare
comparison = compare_frameworks.compare_all([eu, china, us])
comparison.visualize(output='comparisons/framework_compare.png')
```

### Track Legislation

```python
from code.scrapers import legislation_tracker

# Monitor US bills
tracker = legislation_tracker.USFederalTracker()
bills = tracker.get_bills(keywords=['AI'], congress=118)

# Track CA legislation  
ca = legislation_tracker.CaliforniaTracker()
ca_bills = ca.get_bills(session='2023-24', topic='AI')

# EU implementation
eu_tracker = legislation_tracker.EUImplementationTracker()
milestones = eu_tracker.get_milestones('ai_act')
```

### Analyze SB 1047 Stakeholders

```python
from code.analysis import stakeholder_network

# Load data
data = stakeholder_network.load_data('sb_1047')

# Analyze unusual coalitions
analysis = stakeholder_network.analyze_coalitions(data)
print(analysis.cross_cutting_support)

# Visualize
stakeholder_network.plot_network(
    data,
    output='visualizations/sb1047_network.png'
)
```

---

## 📈 Visualizations

**EU Compliance Flowchart**: Navigate risk classification  
**China Registration Process**: 3-step model approval  
**US Agency Delegation**: 100+ tasks across 50+ agencies  
**SB 1047 Timeline**: Phased implementation (historical)  
**Comparative Charts**: Philosophy, risk systems, enforcement  
**Global Map**: Worldwide AI regulation landscape 2024

---

## 🔮 Future Directions

**EU**: First enforcement 2025-26, GPAI registry, international cooperation  
**China**: Possible consolidated AI law, continued registrations, US tech response  
**US Federal**: Congressional bills uncertain, agency rulemaking continues, AISI expansion  
**US States**: CA alternative framework 2025, 40+ states active, preemption debates  
**Geopolitics**: Continued decoupling, export controls, alliance-building

**Open Questions**:
- Which model best balances safety + innovation?
- Global convergence or fragmentation?
- Are current evaluation methods sufficient?
- Impact on open-source AI?
- Democratic legitimacy in technical policy?

---

## 📖 Citation

```bibtex
@article{chun2024comparative,
  title={Comparative Global AI Regulation: Policy Perspectives from the EU, China, and the US},
  author={Chun, Jon and Schroeder de Witt, Christian and Elkins, Katherine},
  journal={arXiv preprint arXiv:2410.21279},
  year={2024}
}
```

**Paper**: [arXiv:2410.21279](https://arxiv.org/abs/2410.21279)

---

## 🤝 Contributing

We welcome:
- Regulatory updates and implementation tracking
- Comparative analysis and impact studies
- Structured datasets and compliance trackers
- Improved visualizations and interactive tools
- Translations of regulatory documents
- Case studies of regulatory impact

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

## 📚 Key Resources

**Official Sources**:
- [EU AI Act](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:52021PC0206)
- [CAC (China)](http://www.cac.gov.cn/)
- [White House AI](https://www.whitehouse.gov/ai/)
- [CA SB 1047](https://legiscan.com/CA/text/SB1047/2023)

**Research Orgs**:
- [OECD AI Observatory](https://oecd.ai/)
- [Stanford AI Index](https://aiindex.stanford.edu/)
- [Center for AI Safety](https://www.safe.ai/)
- [MIT AI Policy Forum](https://aipolicy.mit.edu/)

See [resources/further_reading.md](resources/further_reading.md) for comprehensive bibliography.

---

## 👥 Authors

**Jon Chun** - Kenyon College - chunj@kenyon.edu - *US & China sections*  
**Christian Schroeder de Witt** - Oxford University - *EU section*  
**Katherine Elkins** - Kenyon College - elkinsk@kenyon.edu - *US section*

---

## ⚖️ License

MIT License - See [LICENSE](LICENSE)

Free for academic/educational use. Attribution required.

---

## ⚠️ Disclaimer

**Currency**: October 2024 snapshot. AI policy evolves rapidly.  
**Legal Advice**: For informational purposes only. Consult legal counsel for compliance.  
**Views**: Authors' own, not institutions'.  
**Political Neutrality**: Multiple perspectives presented objectively.

---

**Last Updated**: October 2024  
**Status**: Active Research  
**Next Update**: Q1 2025

⭐ **Star** to follow updates | 🔄 **Share** with researchers & policymakers | 🤝 **Contribute** to expand this resource
ENDOFFILE
# global-ai-regulation-comparative-study
Comparative analysis of AI regulation in the EU, China, and the US - examining risk frameworks, enforcement approaches, and the battle between innovation and safety
