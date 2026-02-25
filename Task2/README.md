Each group member should provide feedback on the other group members’ work. Be detailed and specific where possible. The quality of this feedback can play a part in your grade.

You can provide feedback to your group members in many different ways (live in a meeting, offline, or however else you devise) but the feedback must be documented here! 

Please replace “Feedback giver #x” with a group member’s name below and add feedback as a bulleted list below. Note: There is a pencil icon on the top right of the README file (when you are viewing the README.md file) that allows you to edit.

- Feedback giver - Yujin Kim
  - The metadata organization is clear and well structured.
  - Although missing values needed to be removed for my task-specific calculations, replacing -200 with NaN during the EDA stage is more appropriate for preserving data integrity. The inclusion of a missing rate summary further strengthens the data quality assessment.
  - The missing value handling procedure is generalizable and could be modularized into a function for improved code clarity and reusability.
  - For the correlation analysis, examining time- or season-specific correlations, as well as relationships among additional variables, may provide further insight into potential drift patterns and underlying structure in the dataset.


- Feedback giver - Hannah Shaw
  + A few typos:
  +   "The manufacturer specifies less than 2% drift per 6 months (DeVito, 2008)" missing a period at the end of the sentence
  +   "Finally, we conduct temporal analysis from two perspectives: benzene variation over time (line plots across the full collection period) and benzene relationships ignoring time" another missing period at the end of the sentence
  +   "Note No additional timing variables" (under the header Date and Time Transformation) missing a : after Note
  +   "Unique key / Index variable:" (under the header Data Subsetting) text was left unbolded when the other requirements were bolded
  +   "Exclude the other ground truth columns (CO(GT), NMHC(GT), NOx(GT), NO2(GT)) per requirements" missing a period at the end of the sentence
  +   "A little bit of housecleaning since the variables are challenging to type We will create a named variable grouping for easy reference in subsequent DataFrame manipulations." Need a period or comma after "type"
  + "Action: Replacing -200 values with NaN in features_clean_df DataFrame" <- Is this markdown statement necessary? You already said that was what you were going to do in the text right before the relevant code box.
  + You have your bar plots labeled as "Boxplots of Benzene values by time categories" - should fix that by properly labelling as Bar Plots. Also, while your plots look good as-is, I wonder if you can adjust the y-axis on the "Distribution of hour" and "Distribution of day_of_week" to make the differences between the bars more obvious.
