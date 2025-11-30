# Sample Size Determination

This repository contains my **sample size determination** steps across a variety of epidemiological study scenarios, including continuous outcomes, proportions, and case–control studies.

---

## Steps Taken

1. **Continuous Outcome: Systolic Blood Pressure (SBP)**
   - Goal: Compare mean SBP between two groups.
   - Used pilot data: mean = 120 mmHg, SD = 15 mmHg.
   - Targeted a detectable difference of 5 mmHg, with 90% power and 5% significance.
   - Calculated **Cohen’s d** to standardize the effect size and used `pwr.t.test()` to estimate required sample size.
   - Explored alternative scenarios:
     - If SD is smaller (12 mmHg) with a fixed sample size of 150 per group.
     - Sample size needed for different power levels.

2. **Comparing Proportions**
   - Example: Smoking prevalence between two populations.
   - Baseline prevalence = 10%, clinically meaningful difference = 5%.
   - Used `pwr.2p.test()` to estimate required sample size and power for 250 participants per group.
   - Explored scenarios with absolute (40%) vs relative improvements in treatment outcomes.

3. **Single Proportion: Cross-Sectional Study**
   - Goal: Detect increase in obesity prevalence from 30% to 40%.
   - Used `pwr.p.test()` to calculate the sample size needed to detect this 10-percentage-point increase with 80% power.

4. **Case–Control Study: Tubal Ligation and Ovarian Cancer**
   - Based on real estimates from Rice et al. (2013):
     - 18.5% of controls had tubal ligation.
     - 12.8% of cases had tubal ligation.
     - Target OR = 0.82.
   - Explored how **total sample size changes with different odds ratios**.
   - Converted expected odds ratios into proportions to use in `pwr.2p.test()` for power calculations.

---

## Key Findings

- For SBP, detecting a 5 mmHg difference at 90% power required **approximately 190 participants per group**.  
- Reducing variability (SD=12) increased power for a fixed sample size.  
- Detecting a 5% difference in smoking prevalence required a moderate sample size (~250 per group) to achieve 90% power.  
- Large effect sizes (e.g., absolute 40% improvement in treatment outcomes) required smaller sample sizes, while smaller or relative improvements required much larger samples.  
- For cross-sectional studies, detecting a 10% increase in obesity prevalence required a sample size that ensures 80% power.  
- In case–control studies, required sample size grows quickly as the true odds ratio approaches 1 (no effect), highlighting how smaller effect sizes are harder to detect.

---

This workflow demonstrates how **pilot data, expected effect sizes, and variability** inform the design of epidemiological studies and how power calculations guide sample-size planning.
