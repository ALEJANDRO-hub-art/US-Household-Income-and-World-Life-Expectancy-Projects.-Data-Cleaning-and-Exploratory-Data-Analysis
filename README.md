📊 **World Life Expectancy Data Cleaning and Exploratory Data Analysis Project**

📌 **Project Overview**

This project analyzes the World Life Expectancy dataset, which contains yearly health and socioeconomic indicators for countries around the world. The dataset includes key metrics such as life expectancy, adult mortality rates, infant deaths, GDP, disease prevalence (Measles, Polio, HIV/AIDS), nutrition indicators, and schooling levels.

The goal of the project is to:

- Clean and prepare the dataset by removing duplicates, handling missing and null values
- Explore global health trends across time
- Identify relationships between economic conditions and life expectancy
- Compare developed vs developing countries
- Uncover insights that explain differences in public health outcomes

By combining data cleaning, exploratory analysis, and SQL-based calculations, this project provides a clearer understanding of the factors that influence life expectancy worldwide.

🧩 **Business Problem**

Global organizations, governments, and healthcare policy groups struggle with:

- uneven access to healthcare resources
- rising mortality rates in developing regions
- limited understanding of what factors most strongly impact life expectancy
- data quality problems that prevent accurate reporting and decision-making

Without reliable analysis, policymakers cannot:

- Target interventions effectively
- Allocate funding efficiently
- Evaluate the impact of health programs
- Prioritize high-risk populations

This project addresses the problem by:

- Cleaning inaccurate or incomplete health records
- Identifying patterns in life expectancy and mortality
- Linking economic indicators (such as GDP and schooling) to health outcomes
- Highlighting disparities between developed and developing nations

These insights help guide data-driven public health strategies and investment decisions.

🛠️ **Tech Stack**


✅ MySQL / SQL

Used for:

- Storing the cleaned dataset
- Querying and aggregating health indicators
- Identifying missing values

calculating:

- Averages
- Rolling totals
- Country-level comparisons
- GDP-based life expectancy patterns


📈🧮 **Overview of Findings**

The SQL analysis reveals:

- Life expectancy varies significantly across countries
- Countries with higher GDP consistently show higher life expectancy
- Developed nations live ~12–13 years longer than developing nations
- BMI extremes may indicate health risks
- Adult mortality trends show long-term health improvements in some nations
- Strong socio-economic and health correlations exist globally

**Life Expectancy Change Over Time**
MAX(Life_expectancy) - MIN(Life_expectancy)

Insight:
- Many countries show noticeable increases in life expectancy
- Some nations improved 10–20+ years within the dataset range. This indicates major progress in healthcare, sanitation, and living standards

Sorting DESC reveals:
- Countries with the largest improvements often developing nations undergoing rapid health modernization

Sorting ASC reveals:
- Countries with minimal improvement suggests stagnation or already high baseline life expectancy

**Global Trend Over Time**
SELECT Year, AVG(Life_expectancy)

Insight:
- Global life expectancy steadily increases year after year
- Indicates worldwide improvement in health outcomes

**GDP vs Life Expectancy**
SELECT Country, ROUND(AVG(Life_expectancy)), ROUND(AVG(GDP))

Insight:
- Many countries with low GDP also show low life expectancy
- Wealthier nations show the highest life expectancy averages
- This reveals a strong economic-health relationship

**GDP Threshold Analysis**

CASE WHEN GDP >= 1500
Insights:
- The dataset contains: 1326 Countries with high-GDP with a High_GDP_Life_Expectancy of 74.20

CASE WHEN GDP <=1500
Insights:
- The dataset contains: 1612 countries with low-GDP records with a Low_GDP_Life_Expectancy of 64.70

Average life expectancy for:
- High GDP countries = significantly higher
- Low GDP countries = much lower

This confirms: Economic development strongly impacts population longevity

**Developed vs Developing Status**
SELECT Status, AVG(Life_expectancy)

Insight:
- Developed countries: ~79.2 years
- Developing countries: ~66.8 years

This means: People in developed countries live over a decade longer on average

**Status Count**
COUNT(DISTINCT Country)

Insight:
- ~32 developed countries
- ~162 developing countries

This explains: Why global averages are pulled downward. Most of the world is still classified as developing

**BMI vs Life Expectancy**
AVG(BMI)

Insight:
- Countries with extremely high BMI levels may have increased health risks
- Higher BMI does not always correlate positively with longer life
- Some high-BMI countries show reduced life expectancy

**Adult Mortality Trend Analysis (Window Function)**
SUM(Adult_Mortality) OVER (PARTITION BY Country ORDER BY Year)

Insights:
- Running totals reveal long-term mortality burden

Afghanistan example shows:
- Yearly mortality improving but cumulative mortality remains high. This indicates long-term health challenges

United Arab Emirates example:
- Low adult mortality year-to-year means increasing life expectancy. This reflects strong healthcare systems and living standards

📝**Conclusion**

The SQL analysis reveals:
- Strong evidence that economic development, healthcare access, and living conditions drive global differences in life expectancy, with developing nations facing significantly lower longevity and higher mortality challenges.


















--------------------------------------------------------------------------------------------------------------------------------

📊 **US Household Income Data Cleaning and Exploratory Data Analysis Project**
