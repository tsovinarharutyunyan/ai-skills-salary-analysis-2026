# AI Skills and Advertised Salaries: 2026 Job Market Study

**Python · Pandas · SciPy · Statsmodels · Seaborn · Correlation · Regression · Data Quality**

## Business question
Are AI-related skills associated with higher advertised salaries in a 2026 snapshot of tech job postings? How robust is the relationship to basic job characteristics and different AI-skill definitions?

## Verified results from the executed base notebook
| Metric | Result |
|---|---:|
| Original rows, configuration S | 35,417 |
| Unique postings after ATS + job ID deduplication | 31,676 |
| Postings with usable annualized USD salary ranges | 12,482 (39.4%) |
| Broad AI-skill tag share | 38.1% |
| Non-AI median advertised salary midpoint | $171,500 |
| AI median advertised salary midpoint | $198,500 |
| Raw median gap | +15.7% |
| Point-biserial correlation with salary | 0.211 |
| Adjusted log-OLS association | +15.0% (95% CI +13.6% to +16.4%) |
| Regression observations and R² | 12,482; 0.159 |

The adjusted model includes country, department and remote-status controls with HC3 robust standard errors. A 1–99% trimmed-salary check yielded +13.8%; the US-only check yielded +15.1%. These are **associations**, not causal effects.

## Additional executed sensitivity analyses
| Check | Result |
|---|---:|
| Narrow GenAI tag prevalence | 21.3% of deduplicated postings |
| Narrow GenAI adjusted association | +10.5% (95% CI +8.9% to +12.1%) |
| Within-title adjusted association | +2.5% (95% CI −0.5% to +5.7%); p=0.105 |
| Within-title sample | 1,136 salary postings across 46 eligible titles |

**Key insight:** The within-title estimate is smaller and not statistically significant at the 5% level. This suggests that job-title composition may explain part of the broader observed pay difference. These models use different subsets and controls; they do not establish causation.

## Important limitations
- This is the **S** configuration, not the full dataset or a representative sample of all jobs.
- The data is a **snapshot**: it does not establish that salaries or opportunities *changed* due to AI.
- About 60% of original records lack salary information; the final USD salary sample is selective.
- Hourly salaries are annualized assuming 2,080 hours, and monthly/weekly rates using fixed factors.
- AI tags include ML and related frameworks; a separate narrow GenAI sensitivity test is reported above.
- Employer, detailed experience/seniority, role, geography, and skill-tag errors may confound results.
- Source dataset license is **CC BY-NC 4.0**; follow its attribution and non-commercial restrictions.

## Run locally
1. Download this repository and open `AI_Job_Market_Portfolio_FINAL.ipynb` in Jupyter.
2. Run `%pip install -r requirements.txt` in a temporary cell (or `pip install -r requirements.txt` in a terminal).
3. Restart the kernel, then **Run All**. The first run downloads the dataset from Hugging Face.
4. Review charts and summaries in the notebook; the notebook may also write generated outputs to `outputs/`.

## Repository contents
- `AI_Job_Market_Portfolio_FINAL.ipynb` — executed analysis and stored results, including both sensitivity checks
- `requirements.txt` — Python dependencies
- `README.md` — project overview, methodology, and verified findings

## Data attribution
[Zalize Tech Job Postings Salary Dataset](https://huggingface.co/datasets/zalizedata/tech-job-postings-salary-dataset). Dataset source is credited; no raw source data is redistributed.

## Interview takeaway
A strong observed AI salary association exists within this selected dataset. Its magnitude depends on how roles, geography, seniority and skill requirements are measured. Within-title and GenAI sensitivity checks highlight how estimates depend on role mix and skill definitions. Multi-period data would be needed to study changes over time.
