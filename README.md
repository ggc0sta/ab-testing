# A/B Testing: Player Retention

This project analyzes a mobile game A/B test to understand whether moving a progression gate from level 30 to level 40 affects player retention.

## Project objective

The dataset comes from the Cookie Cats mobile game experiment and contains user-level results from a randomized test:

- Control group: players experience the gate at level 30
- Treatment group: players experience the gate at level 40

The business question is simple: should the game keep the gate at level 30 or move it to level 40?

## Dataset

The analysis uses the Cookie Cats dataset from Kaggle, which contains one row per player.

Columns include:

- `userid`: unique player identifier
- `version`: experiment group (`gate_30` or `gate_40`)
- `sum_gamerounds`: total game rounds played in the first 14 days
- `retention_1`: whether the player returned after 1 day
- `retention_7`: whether the player returned after 7 days

## Analysis approach

The notebook explores the experiment in several stages:

1. Importing data and validating the dataset
2. Checking group balance and basic descriptive statistics
3. Comparing 7-day retention rates between the control and treatment groups
4. Running a two-proportion z-test to evaluate statistical significance
5. Estimating a confidence interval for the effect
6. Quantifying practical impact in terms of retained users
7. Performing a power analysis to assess whether the sample size was sufficient

## Key findings

The treatment group showed a lower 7-day retention rate than the control group.

- Control retention: approximately 18.6%
- Treatment retention: approximately 17.8%
- Absolute effect: roughly -0.82 percentage points
- Relative decrease: about -4.3%

The two-proportion z-test produced a statistically significant result, suggesting that moving the gate to level 40 reduced retention.

The 95% confidence interval for the treatment effect was negative, indicating that the true effect is likely a decrease rather than an increase.

## Business interpretation

The experiment provides evidence that moving the gate from level 30 to level 40 is associated with worse long-term retention.

The estimated impact translates to around 820 fewer retained users per 100,000 players exposed to the new gate position.

Based on the evidence in the notebook, the recommendation is to keep the gate at level 30 rather than moving it to level 40.

## Repository contents

- `ab-testing-player-retention.ipynb`: the full exploratory analysis and statistical test notebook
- `README.md`: project overview and key results

## Tools and libraries used

- pandas
- kagglehub
- statsmodels

## License

This project is provided for educational and analytical purposes.
