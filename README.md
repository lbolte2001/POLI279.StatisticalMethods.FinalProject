This analysis is recreated from an article titled “The effect of self-esteem on depressive symptoms among adolescents: the mediating roles of hope and anxiety” (Gu et al., 2024). The study was conducted on 431 adolescents in a Chinese public middle school, with all students ranging between 13 and 18 years old and 52% being female. The dataset itself contains responses from a psychological survey containing questions based on constructs of anxiety, hope, depression, and self-esteem. Students were presented with a questionnaire and informed that participation would not impact their academic standing. Each construct was represented by self-reporting scales containing 6 to 20 items per variable. These measures are represented in previous literature and include the Rosenberg Self-Esteem Scale, The Center for Epidemiologic Studies Depression Scale, The Children’s Hope Scale, and the Self-rating Anxiety Scale. Internal consistency for each scale was confirmed with acceptable Cronbach’s alpha scores, which can be seen in the correlation analysis. 

The overall analysis conducted in this paper aims to understand how hope and anxiety play a role in the relationship between self-esteem and depressive symptoms. This relationship is also impacted by gender, which is considered in the research. Through correlation analysis, multiple mediation modeling, and bootstrapping methods, they found that hope and anxiety mediated the association between self-esteem and depression in female adolescents. However, only anxiety mediated this relationship in male adolescents. Since multiple mediation modeling had not yet been covered in our course, I attempted to use linear and multiple regressions to recreate the statistical patterns the original paper discovered. I was able to successfully recreate the correlation analysis despite some discrepancies in the data that may be from the lack of information on the original researchers’ data cleaning process. 

The data contained 431 observations with NA values remaining in the public dataset. Every item in each psychological construct scale had its own column, with the participants self-reported score as the individual observation. Depressive symptoms had 20 columns, self-esteem had 10 columns, hope had 6 columns, and anxiety had 10 columns. All constructs were measured on a 4-point scale except for hope, which had 6. Due to the variance in measure, I standardized the total scores for each construct to compare them directly. The z-standardized variable scores can be seen below:

 
 <img width="468" height="294" alt="image" src="https://github.com/user-attachments/assets/370a9e41-48ee-442a-9c84-ad51d14f3c36" />


We can see that anxiety and depressive symptoms have several high outliers, but all variables have similar distributions. Self-esteem has several low outliers which shows there is a handful of participants that have unusually low self-esteem relative to the sample. All variables have median z-scores around 0, so the typical participant scores near the sample average. 

It is important to note that this dataset included NA values, which were left in for the bulk of analysis but removed for calculating variable means. If NAs were left in the data for this calculation, the mean would return NA. The data cleaning process may not match the original study due to a lack of information on the researchers’ process in the published paper.  It is unknown if the sum or mean of variable items were used for analysis. Based on the finalized numbers in the original paper, I used total mean to analyze the descriptive statistics of the data and sum to analyze correlations between variables and for regressions. 

<img width="464" height="309" alt="image" src="https://github.com/user-attachments/assets/6a6673fb-acc8-4f68-b7ed-4b09e9e22394" />

<img width="468" height="288" alt="image" src="https://github.com/user-attachments/assets/193e2f8a-e473-4182-963f-53684daeecd6" />

 
The linear regression between self-esteem and depressive symptoms in both genders shows a strong negative linear relationship. Both the intercept and coefficient are highly significant, and the R-squared score is strong for psychological data at 0.395. If self-esteem is 0, then the depression is 54.13 (intercept). Depressive symptoms decrease by 1.25 units with every 1 unit increase in self-esteem. 


<img width="468" height="106" alt="image" src="https://github.com/user-attachments/assets/67905917-9ff5-4c50-92a3-9524e589200c" />

 
The correlation analysis published in the original paper was reproducible based on what topics we had covered in class. The results above are my recreation of the researchers’ analysis. On the diagonal we can see the Cronbach alphas for each construct scale. Based on these results, we can conclude that self-esteem is a strong predictor of mental health (depressive symptoms). High self-esteem is strongly associated with high hope and therefore associated with lower levels of depression, which is consistent with the original study’s conclusion. 

As an attempt to evaluate the relationship between gender and the proposed psychological constructs within the paper without using multiple mediation models, I created a series of linear and multiple regressions. Overall, female adolescents show higher baseline rates of depressive symptoms that are more positively impacted by hope and less positively impacted by self-esteem. Male adolescents show higher self-esteem. The regression visualizations and model outputs are shown below, broken up by predictor and gender:

 <img width="288" height="179" alt="image" src="https://github.com/user-attachments/assets/f8ebe012-ee9b-4fb9-b164-bcd10867dd71" />
<img width="271" height="185" alt="image" src="https://github.com/user-attachments/assets/6272411e-c4cc-4674-ba22-ddeb3013326d" />

  
Self-esteem and depression have a negative linear relationship, with depressive symptoms decreasing by 1.24 units with every 1 unit increase in self-esteem.

 <img width="294" height="184" alt="image" src="https://github.com/user-attachments/assets/c2484e73-2a2c-400a-86dc-930806351427" />
<img width="273" height="193" alt="image" src="https://github.com/user-attachments/assets/cfb44041-39f1-4b7f-80b8-ff35be314cd8" />

 
The linear relationship between self-esteem and depression in male adolescents is almost identical to that of female adolescents, but females show a higher baseline rate of depressive symptoms (53.59 vs 54.19 intercept). The linear model for males is stronger with an R-squared of 0.48. 
 
 <img width="269" height="164" alt="image" src="https://github.com/user-attachments/assets/61b4742e-56ed-4009-8787-f4cd8a770f63" />
<img width="265" height="179" alt="image" src="https://github.com/user-attachments/assets/3677a549-78bb-44b4-b8d3-a8ffc44d6530" />
<img width="306" height="189" alt="image" src="https://github.com/user-attachments/assets/41dabe94-1078-4af3-b04a-8934c289ba38" />
<img width="301" height="200" alt="image" src="https://github.com/user-attachments/assets/9be84589-1f85-4fb4-bca6-16d900953e46" />


 
 
In the relationships between hope and depressive symptoms for both genders, females still show an overall higher rate of baseline depressive symptoms. The linear model for females is stronger, and they are overall more positively impacted by feelings of hope. In order to look at the interactions between all predictors and depressive symptoms for each gender, I ran multiple linear regressions. 
 
<img width="271" height="194" alt="image" src="https://github.com/user-attachments/assets/b25180f0-efad-420b-bf50-503f3da7b8a4" />

The model above shows the multiple linear regression for female adolescents. There is no multicollinearity issue with a VIF < 5. A high R-squared represents a strong model, and anxiety is the strongest predictor in the model. All coefficients are statistically significant. 
 

<img width="302" height="220" alt="image" src="https://github.com/user-attachments/assets/1f49cb80-9294-4585-9576-3907f54b51cb" />

The model above shows the multiple linear regression for male adolescents. This model has an even higher R-squared, shows not multicollinearity issue (VIF < 5), and anxiety is still a strong predictor of depressive symptoms. The coefficient for hope is not statistically significant, meaning that hope does not strongly predict depressive symptoms when anxiety and self-esteem are included in the model. 

The main limitation to my approach was not being able to recreate the multiple mediation model shown in the original paper since we had not yet covered the topic in class. I attempted to show similar patterns in the data through linear regressions but was able to recreate the correlation analysis. Discrepancies in the anxiety construct in the correlation analysis show that there may have been some data cleaning or collection steps that were not discussed in the paper. All other values were successfully matched to the paper’s outcomes. The models that I used in my analysis show additive relationships instead of mediative. Although I was able to show similar interactions between the variables, it is not an exact replication of the original analysis done on this data set. 

My analysis was successful in showing that hope is a much weaker predictor of depressive symptoms in male adolescents than female adolescents. This conclusion varies from the original study because it does not account for the mediative effects of hope and anxiety on self-esteem and depression. Instead, it looks at direct effects of the predictors on depressive symptoms. I was still able to see a statistically significant difference between genders in the study. 


Link to original study: https://www.nature.com/articles/s41599-024-03249-1#Sec2 

