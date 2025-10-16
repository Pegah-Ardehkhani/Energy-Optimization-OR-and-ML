# Energy Optimization with OR and ML ️‍🔥⚡ ![license](https://img.shields.io/github/license/Pegah-Ardehkhani/Energy-Optimization-OR-and-ML.svg) <a href="https://colab.research.google.com/github/Pegah-Ardehkhani/Energy-Optimization-OR-and-ML/blob/main/Energy%20Optimization%20with%20OR%20and%20ML.ipynb" target="_parent\"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a> [![nbviewer](https://img.shields.io/badge/render-nbviewer-orange.svg)](https://nbviewer.org/github/Pegah-Ardehkhani/Energy-Optimization-OR-and-ML/blob/main/Energy%20Optimization%20with%20OR%20and%20ML.ipynb)

This project explores the optimization of power generation from multiple sources, aiming to maximize profit while adhering to various operational constraints. It leverages both Operations Research (OR) techniques, specifically Linear Programming, and Machine Learning (ML) to address the complexities of energy management, including sensitivity analysis, parametric analysis, stochastic programming, and predictive modeling.

## Project Overview

The core objective of this project is to determine the optimal electricity generation plan for a system comprising three power generators. The optimization considers factors such as profit per megawatt-hour (MWh), gas consumption per MWh, total available gas units, minimum electricity demand, and individual generator capacities. The project demonstrates how to derive an optimal generation strategy under deterministic conditions and then extends this analysis to incorporate uncertainty and predictive capabilities.

## Methodologies and Analyses

#### 🔹 1. Linear Programming (LP) for Optimal Power Generation

What was done:

The initial phase involved formulating the power generation problem as a Linear Program. This mathematical model was designed to maximize the total profit from the three generators subject to constraints on gas availability, minimum electricity demand, and the maximum capacity of each generator. The Gurobi optimizer was used to solve this LP model, identifying the precise MWh output for each generator that yields the highest profit.

What was analyzed:

The analysis of the LP solution revealed the optimal power generation plan, specifying the exact output for each generator. It highlighted which generators were utilized to their full capacity, which were partially used, and which were not used at all, providing a clear, profit-maximizing strategy under the given deterministic conditions. Key insights were drawn regarding the efficiency and profitability of each generator.

#### 🔹 2. Sensitivity Analysis

What was done:

Following the initial LP solution, a comprehensive sensitivity analysis was performed. This involved examining how changes in key parameters—such as generator profits and constraint right-hand sides (e.g., gas availability, minimum demand)—would impact the optimal solution and total profit. This analysis provided ranges within which these parameters could vary without altering the fundamental optimal generation strategy.

What was analyzed:

Sensitivity analysis yielded critical insights into the robustness of the optimal solution. It identified binding and non-binding constraints, revealing which resources or demands were bottlenecks (e.g., gas availability) and which had slack (e.g., minimum demand). The analysis quantified the allowable increases and decreases in generator profits and constraint values, indicating the stability of the current optimal plan. Furthermore, shadow prices (dual values) were calculated to understand the marginal value of relaxing each constraint, providing economic insights into the scarcity and value of resources. Reduced costs were also analyzed to determine the profitability threshold for currently unused generators or those operating at their bounds.

#### 🔹 3. Parametric Analysis

What was done:

Parametric analysis was conducted to observe the dynamic changes in the optimal generation plan and total profit as a specific parameter was varied systematically. Specifically, the profit of Generator 3 was gradually increased to determine at what point it would become economically viable to include it in the optimal generation mix, and how its inclusion would affect the output of other generators and the overall profit.

What was analyzed:

This analysis provided a visual and quantitative understanding of the trade-offs involved when a key economic factor changes. It showed how the optimal MWh output for each generator shifted in response to the varying profit of Generator 3, illustrating the breakpoints where the optimal strategy would change. The total profit curve demonstrated the non-linear impact of such changes, offering insights into the sensitivity of the overall system to individual generator profitability.

#### 🔹 4. Robust Optimization

Got it! Here's a **concise, consistent version** written in the same style and length as your previous sections (LP, Sensitivity, Stochastic, etc.):

---

#### 🔹 6. Robust Optimization

What was done:

The project extended the deterministic LP to a **robust optimization model** using the Bertsimas–Sim approach. This accounts for uncertainties in gas consumption for each generator by introducing a **budget of uncertainty (Γ)**, which limits how many generators can deviate simultaneously. The objective remained maximizing total profit while ensuring feasibility under worst-case gas usage scenarios.

What was analyzed:

The analysis examined how generator outputs and total profit change as Γ increases. High gas-consuming generators reduce output to prevent exceeding the gas limit, illustrating the **trade-off between profit and robustness**. Shadow prices and gas usage decomposition were analyzed to quantify the economic impact of uncertainty and identify which generators are most sensitive. Visualizations highlighted the **price of robustness**, generator adjustments, and worst-case gas usage under different uncertainty budgets.

#### 🔹 5. Stochastic Programming

What was done:

To address real-world uncertainties, the project extended the optimization problem to include stochastic elements. This involved defining multiple scenarios for uncertain parameters, such as the profit of Generator 3 or gas availability, each with an associated probability. The objective was to maximize the expected total profit across these scenarios, leading to a more robust and resilient generation plan that accounts for variability.

What was analyzed:

Stochastic programming revealed an optimal generation plan that performs well on average, rather than being tailored to a single deterministic outcome. The analysis demonstrated how the model balances potential profits and risks across different scenarios, leading to a decision that is robust against future uncertainties. It highlighted the expected total profit and the profit contribution from each scenario, providing a comprehensive view of the system's performance under probabilistic conditions. This approach underscored the value of proactive planning in volatile environments.

#### 🔹 6. Machine Learning for Predictive Modeling and Pattern Discovery

What was done:

Leveraging the power of Machine Learning, a dataset was generated by solving numerous LP instances under varying input conditions (gas availability, demand, and generator profits). This dataset was then used to train a Random Forest Regressor model. The ML model was tasked with predicting the optimal generator outputs and total profit for new, unseen scenarios. Additionally, clustering techniques (K-Means) were applied to the generated LP solutions to identify distinct operational patterns or regimes.

What was analyzed:

The trained Random Forest model demonstrated its ability to accurately predict optimal generation plans and profits, providing a fast and efficient alternative to solving complex LPs for every new scenario. The analysis included evaluating the model's performance using metrics like Mean Squared Error and identifying feature importances, which revealed which input parameters had the most significant impact on the optimal outputs. This provided valuable insights into the drivers of the optimal solution. Furthermore, the clustering analysis uncovered natural groupings within the optimal solutions, indicating different operational strategies that emerge under varying conditions. This pattern discovery can help in developing simplified decision-making rules or understanding the underlying structure of the optimal solution space.

## Conclusion

This project successfully integrates Operations Research and Machine Learning to provide a holistic framework for energy optimization. By combining the precision of linear programming with the predictive power of machine learning and the robustness of stochastic analysis, it offers a comprehensive approach to managing power generation in dynamic and uncertain environments. The analyses performed provide deep insights into optimal resource allocation, sensitivity to changing conditions, and the identification of key operational patterns, enabling more informed and resilient decision-making in the energy sector.

