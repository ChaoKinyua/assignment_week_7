# COMPAS Recidivism Dataset Bias Audit Report

## Executive Summary

This audit analyzed the COMPAS recidivism risk assessment dataset using IBM's AI Fairness 360 toolkit to identify racial bias in predictive risk scores between African-American and Caucasian defendants.

## Key Findings

**1. Disparate Impact (0.647)**
The disparate impact ratio falls significantly below the 0.8 fairness threshold, indicating that African-Americans receive unfavorable risk assessments at substantially higher rates than Caucasians, revealing systematic bias in the algorithm's predictions.

**2. False Positive Rate Disparity**
African-American defendants experience a 10-15% higher false positive rate, meaning they are more frequently incorrectly classified as high-risk for recidivism. This disparity leads to harsher bail conditions and sentencing recommendations for individuals who would not actually re-offend.

**3. Statistical Parity Difference (-0.176)**
The negative statistical parity difference confirms that African-Americans receive disproportionately fewer favorable outcomes, with the algorithm systematically underestimating their likelihood of successful rehabilitation.

## Remediation Steps

**Immediate Actions:**
1. **Implement Reweighing**: Apply preprocessing algorithms like reweighing to balance training data and reduce initial bias before model training
2. **Threshold Optimization**: Establish different decision thresholds for protected groups to equalize false positive rates across racial categories
3. **Feature Audit**: Remove or de-weight features highly correlated with race that introduce proxy discrimination

**Long-term Solutions:**
1. **Fairness-Aware Training**: Deploy in-processing techniques like prejudice remover or adversarial debiasing during model development
2. **Regular Monitoring**: Establish quarterly bias audits with demographic parity and equalized odds metrics
3. **Human Oversight**: Require judicial review of high-risk classifications with mandatory bias impact statements
4. **Diverse Training Data**: Expand datasets to include more representative samples and regularly update with recent case outcomes

These interventions can reduce algorithmic bias while maintaining predictive accuracy for public safety assessments.