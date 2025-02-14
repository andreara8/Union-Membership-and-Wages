# Union Membership and Wages
This is the third of a series of four projects completed for my Applied Econometrics course at UCLA's Master of Quantitative Economics. The objective is to identify the effect of labor union membership on wages across industries and time. To achieve this, we test multiple panel data models inclusive of fixed and random effects.

In this analysis, we aim to estimate the influence of union membership on wage-setting, commonly called the union wage premium. Specifically, we examine how wages vary between union and non-union workers and explore how this premium is associated with key individual characteristics.

To achieve this, we analyze data from the wage plan dataset in Wooldridge, which contains information on wages, individual characteristics, and employment details for a panel of workers. While the dataset includes many variables, we focus on a subset that captures the most relevant individual and contextual factors influencing wages and union membership. These variables include:

* Wages (`lwage`): The natural logarithm of hourly wages, the dependent variable of interest.
* Union Membership (`union`): The primary explanatory variable is a binary indicator (1 = union member, 0 = non-union member).
* Work Hours (`hours`): The total annual hours worked, reflecting labor supply and intensity.
* Experience (`exper`): The number of years of work experience, providing a proxy for skill accumulation.
* Experience Squared (`expersq`): The squared term of experience, capturing non-linear effects of experience on wages.
* Education (`educ`): The total years of schooling, representing human capital.
* Race (`black`): A binary indicator (1 = Black, 0 = otherwise), included to control for racial wage disparities.
* Rural Residency (`rur`): A binary variable indicating whether the individual resides in a rural area, accounting for regional differences in wage-setting.

Through this analysis, we aim to quantify the union wage premium while controlling for these individual characteristics, enabling us to better understand the role of unions in wage determination. By leveraging the data's panel structure, we can also account for unobserved heterogeneity across individuals and time periods, thereby improving the robustness of our estimates.

## Results
`union`, our variable of interest, is statistically significant at all levels of confidence and has the coefficient with the largest magnitude. With an estimated coefficient of 0.073, our model predicts individuals whose wages have been set through a union's contract to experience wages 7.3% higher than those of peers whose wages have not been set by unions, all else equal.

The coefficient on `rur` is not statistically significant, likely due to the fact that Entity Effects absorb much of its effect and that there is very little variation of the value of `rur` for individuals across time (few people in our dataset move from rural to non-rural areas, or vice versa, in the years from 1980 to 1987).

Finally, the coefficient on `hour` is almost exactly zero and statistically insignificant. This makes economic sense for a number of reason:
- Most people have full-time jobs and there is little variation in the number of hours worked across full-time jobs. This is also supported by the density plot of the variable, where we see a substantial spike a the mode.
- Given the little variation in hours, the "discriminating" factors in determining wages are likely to be characteristics such as education and experience, which are fully absorbed by Entity and Time Effects.
