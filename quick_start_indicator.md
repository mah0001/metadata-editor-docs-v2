# Quick-start: Indicator

In this example, we will document an indicator produced by the World Bank, and published in the Bank's Poverty and Inequality Platform (PIP) and World Development Indicators (WDI): the *Poverty headcount ratio at $2.15 a day (2017 PPP) (% of population)*.

The only file you need to reproduce this Quick-Start example is the image file of the that will be used as (optional) thumbnail: *poverty_thumbnail.jpg*.
The metadata we will enter in the Metadata Editor is the metadata provided by the World Bank at https://data.worldbank.org/indicator/SI.POV.DDAY?locations=US (downloaded on 12 February 2025). We will complement this metadata with information extracted from the data itself, e.g., to obtain the geographic and time coverage. We will also doument the fact that this indicator is one of the Sustainable Development Goals.


**Step 1: Create a new project and add a thumbnail**

To begin, open the Metadata Editor link and log in with your username and password. The "My projects" page will be displayed, showing all projects you have previously created and those that have been shared with you by others, if any. If you are using the application for the first time and no project has been shared with you by other users of the Metadata Editor, the project list will be empty. 

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_indicator_project_list.png)

Click on "CREATE NEW PROJECT" and select "Indicator" when prompted to indicate the type of resource you will be documenting.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_document_create_project_types.png)
  
A new project page will open in a new tab.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_indicator_new_project_home.png)

We will use the image *poverty_thumbnail.jpg* as a thumbnail (or feel free to select your own JPG or PNG file). It will be displayed in the Metadata Editor and in the NADA catalog if the metadata is published in NADA. Click on the edit button in the screenshot image, and select the image file when prompted. 

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_indicator_edit_thumbnail.png)

We will use the default metadata template provided, so there is no need to switch template. 


**Step 2: Enter metadata**

On the left navigation tree, select "Metadata information / Information on metadata" to enter optional elements used to capture information on who documented the indicator and when. Enter your name in *Metadata producers* and the date in ISO format (YYYY-MM-DD) in *Production date*. Then click on SAVE.

You can now start entering the metadata related to the indicator itself in the "Indicator description" section. In the navigation tree, first select "Title statement" and enter the required **primary ID** (a unique identifier of your choice, e.g., JD_IND_001; if you want to publish the document in a NADA catalog, make sure that this same identifier is not used by another user or for another document). Also enter the (optional) **other identifiers** for the document (enter the WDI indicator: ). Then enter the **title** of the indicator, which is also a required element. Then click SAVE.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_indicator_title_statement.png)

Then proceed with the other sections in the navigation tree and fill out the relevant metadata elements using the following information copied from the World Bank website:
- ***ID***: SI.POV.DDAY
- ***Name***: Poverty headcount ratio at $2.15 a day (2017 PPP) (% of population)
- ***Source***: World Bank, Poverty and Inequality Platform. Data are based on primary household survey data obtained from government statistical agencies and World Bank country departments. Data for high-income economies are mostly from the Luxembourg Income Study database. For more information and methodology, please see pip.worldbank.org.
- ***License***:  CC BY-4.0 
- ***Development Relevance***: The World Bank Group is committed to reducing extreme poverty to 3 percent or less, globally, by 2030. Monitoring poverty is important on the global development agenda as well as on the national development agenda of many countries. The World Bank produced its first global poverty estimates for developing countries for World Development Report 1990: Poverty (World Bank 1990) using household survey data for 22 countries (Ravallion, Datt, and van de Walle 1991). Since then there has been considerable expansion in the number of countries that field household income and expenditure surveys.
- ***General Comments***: The World Bank’s internationally comparable poverty monitoring database now draws on income or detailed consumption data from more than 2000 household surveys across 169 countries. See the Poverty and Inequality Platform (PIP) for details (pip.worldbank.org).
- ***Limitations and Exceptions***: Despite progress in the last decade, the challenges of measuring poverty remain. The timeliness, frequency, quality, and comparability of household surveys need to increase substantially, particularly in the poorest countries. The availability and quality of poverty monitoring data remains low in small states, countries with fragile situations, and low-income countries and even some middle-income countries. The low frequency and lack of comparability of the data available in some countries create uncertainty over the magnitude of poverty reduction. Besides the frequency and timeliness of survey data, other data quality issues arise in measuring household living standards. The surveys ask detailed questions on sources of income and how it was spent, which must be carefully recorded by trained personnel. Income is generally more difficult to measure accurately, and consumption comes closer to the notion of living standards. And income can vary over time even if living standards do not. But consumption data are not always available: the latest estimates reported here use consumption data for about two-thirds of countries. However, even similar surveys may not be strictly comparable because of differences in timing or in the quality and training of enumerators. Comparisons of countries at different levels of development also pose a potential problem because of differences in the relative importance of the consumption of nonmarket goods. The local market value of all consumption in kind (including own production, particularly important in underdeveloped rural economies) should be included in total consumption expenditure but may not be. Most survey data now include valuations for consumption or income from own production, but valuation methods vary.
- ***Long Definition***: Poverty headcount ratio at $2.15 a day is the percentage of the population living on less than $2.15 a day at 2017 purchasing power adjusted prices. As a result of revisions in PPP exchange rates, poverty rates for individual countries cannot be compared with poverty rates reported in earlier editions.
- ***Periodicity***: Annual
- ***Related source links***: World Bank, Poverty and Inequality Platform: pip.worldbank.org
- ***Short definition***: Poverty headcount ratio at $2.15 a day is the percentage of the population living on less than $2.15 a day at 2017 international prices.
- ***Statistical Concept and Methodology***: International comparisons of poverty estimates entail both conceptual and practical problems. Countries have different definitions of poverty, and consistent comparisons across countries can be difficult. Local poverty lines tend to have higher purchasing power in rich countries, where more generous standards are used, than in poor countries. Since World Development Report 1990, the World Bank has aimed to apply a common standard in measuring extreme poverty, anchored to what poverty means in the world's poorest countries. The welfare of people living in different countries can be measured on a common scale by adjusting for differences in the purchasing power of currencies. The commonly used $1 a day standard, measured in 1985 international prices and adjusted to local currency using purchasing power parities (PPPs), was chosen for World Development Report 1990 because it was typical of the poverty lines in low-income countries at the time. As differences in the cost of living across the world evolve, the international poverty line has to be periodically updated using new PPP price data to reflect these changes. The last change was in September 2022, when we adopted $2.15 as the international poverty line using the 2017 PPP. Poverty measures based on international poverty lines attempt to hold the real value of the poverty line constant across countries, as is done when making comparisons over time. The $3.65 poverty line is derived from typical national poverty lines in countries classified as Lower Middle Income. The $6.85 poverty line is derived from typical national poverty lines in countries classified as Upper Middle Income. Early editions of World Development Indicators used PPPs from the Penn World Tables to convert values in local currency to equivalent purchasing power measured in U.S dollars. Later editions used 1993, 2005, and 2017 consumption PPP estimates produced by the World Bank. The current extreme poverty line is set at $2.15 a day in 2017 PPP terms, which represents the mean of the poverty lines found in 15 of the poorest countries ranked by per capita consumption. The new poverty line maintains the same standard for extreme poverty - the poverty line typical of the poorest countries in the world - but updates it using the latest information on the cost of living in developing countries. As a result of revisions in PPP exchange rates, poverty rates for individual countries cannot be compared with poverty rates reported in earlier editions. The statistics reported here are based on consumption data or, when unavailable, on income surveys.
- ***Topic***: Poverty: Poverty rates
- ***Unit of measure***: %

**Additional useful information**
- ***Database ID***: WDI
- ***URL of CC BY-4.0 license***: https://creativecommons.org/licenses/by/4.0/
- ***SDG Goal, target corresopnding to the indicator***:
   - *Framework*: Sustainable Development Goals (SDG)
   - *Custodian*: United Nations
   - *Goal 1*: No poverty (End poverty in all forms by 2030) 
   - *Target 1.1*: By 2030, eradicate extreme poverty for all people everywhere, currently measured as people living on less than $1.25 a day
   - *Indicator 1.1.1*: Proportion of the population living below the international poverty line by sex, age, employment status and geographical location (urban/rural)    
- ***Time coverage***: 1963 to 2023 (as of February 2025)
- ***Geographic coverage***: 266 countries and regions; the list (names and codes) can be cop[y/pasted from an Excel file available from the World Bank website at https://api.worldbank.org/v2/en/indicator/SI.POV.DDAY?downloadformat=excel
  
With this information in hand, you can now start documenting the indicator. 

The metadata elements in the template maps to the content of the Excel file as follows: 
| From World Bank           | In the metadata template                        | 
| ------------------------- | ----------------------------------------------- | 
| ID                        |                                                 |
| Title                     |                                                 |
|                      |                           | 
|                      |                           |
|                      |                           | 
|                      |                           |
|                      |                           | 
|                      |                           |
|                      |                           | 
|                      |                           |
|                      |                           | 
|                      |                           |
|                      |                           | 
|                      |                           |
|                      |                           | 
|                      |                           |


**Step 3: Add information on related resources**


**Step 4: Export and publish metadata**

In the project page, a menu of options will be available to you.


