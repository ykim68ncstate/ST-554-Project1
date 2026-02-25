Each group member should provide feedback on the other group members’ work. Be detailed and specific where possible. The quality of this feedback can play a part in your grade.

You can provide feedback to your group members in many different ways (live in a meeting, offline, or however else you devise) but the feedback must be documented here! 

Please replace “Feedback giver #x” with a group member’s name below and add feedback as a bulleted list below. Note: There is a pencil icon on the top right of the README file (when you are viewing the README.md file) that allows you to edit.

- Feedback giver #1 - David Pressley
  + Cell: https://colab.research.google.com/drive/1nN7Vdpd8B-HCCAUJvJqDBBdrvBpjgkxf#scrollTo=GGiLTI91Udcb&line=1&uniqifier=1
      + GPP: `raw_air_quality = X` this doesn't copy the dataframe, it creates an alias. Modifications to raw_air_quality would affect X. Use .copy() if you want a separate object
      + GPP: remove unused imports (e.g. `pprint` is imported but never used in your code. No need to waste resources and cause bloat if it isn't used. Also remove: `HTML`, `Markdown`, and potentially `display` (not sure if `pd.set_option` on line 11 uses `display`, but I don't think it does.
  + Cell: https://colab.research.google.com/drive/1nN7Vdpd8B-HCCAUJvJqDBBdrvBpjgkxf#scrollTo=GGiLTI91Udcb&line=1&uniqifier=1
      + GPP: This cell just dumps your entire dataframe. Remove it.
  + Cell: https://colab.research.google.com/drive/1nN7Vdpd8B-HCCAUJvJqDBBdrvBpjgkxf#scrollTo=y-W-xbZGmVSe&line=1&uniqifier=1
      + GPP: remove the commented lines
      + BUG: looks like a copy/paste error on line 5: `(raw_air_quality["RH"] != -200) & (raw_air_quality["RH"] != -200)]`. Need to subset `AH`.
      + GPP: don't render the entire data frame, just use `.head()`
  + Cell: https://colab.research.google.com/drive/1nN7Vdpd8B-HCCAUJvJqDBBdrvBpjgkxf#scrollTo=cBhYMKzFr_YT&line=1&uniqifier=1
      +  remove the emdash and comment after the statement on line 4. Smells of AI.
  + Cell: https://colab.research.google.com/drive/1nN7Vdpd8B-HCCAUJvJqDBBdrvBpjgkxf#scrollTo=nsXu2lw4UYx1&line=1&uniqifier=1
      + CRITICAL BUG. MUST FIX: `cv_finder(raw_air_quality[['CO(GT)']], raw_air_quality[['C6H6(GT)']], 250)` uses the wrong dataframe. It should be your `average_air_quality` dataframe. (e.g. `cv_finder(average_air_quality[['CO(GT)']], average_air_quality[['C6H6(GT)']], 250)`. You create `average_air_quality` but never use it in subsequent analyses.
  + Cell: https://colab.research.google.com/drive/1nN7Vdpd8B-HCCAUJvJqDBBdrvBpjgkxf#scrollTo=0PYwLPd_NPIZ&line=4&uniqifier=1
      +   BUG: Requirements state the test set should be: "just the day + 1 row.", but `mse_finder` function includes all remaining rows, not just the next day (e.g. `X_test = X[day:]` should be: `X_test = X[day:day+1]` same for `y_test`.
  + Cell: https://colab.research.google.com/drive/1nN7Vdpd8B-HCCAUJvJqDBBdrvBpjgkxf#scrollTo=xXLhZYgEx-6t&line=2&uniqifier=1
      +  GPP: move imports to the top of the notebook and remove any unused
  + Cell: https://colab.research.google.com/drive/1nN7Vdpd8B-HCCAUJvJqDBBdrvBpjgkxf#scrollTo=0PYwLPd_NPIZ&line=1&uniqifier=1
      + GPP: add docstring to your function definition
  + Cell: https://colab.research.google.com/drive/1nN7Vdpd8B-HCCAUJvJqDBBdrvBpjgkxf#scrollTo=W2fmAmobNhcT&line=2&uniqifier=1
      + GPP: add docstring to your function definition
  + **Narrative throughout notebook**:
      + The requirements state:
          + "To be clear be sure to include markdown text describing what you are doing and your
thought process (don’t just put question prompts) A narrative (a spoken or written account of
connected events; a story) done in markdown should exist in all Notebooks for full credit."
          + "The audience you are writing for is someone that understands programming and very basic statistics,
but would need you to provide details and explanation of what you are doing to understand it."

      I think you should address the following:
          + The introduction describes the dataset but doesn't frame what Task 3 specifically does. Consider adding a couple sentences explaining why standard cross-validation doesn't work for time series data and why we're comparing SLR vs MLR for benzene prediction.
          + The model comparison after running both CV calls is pretty thin with just one sentence. Since this is the main conclusion, consider providing more. (e.g. what does the MSE difference mean? Why might adding temperature and humidity improve benzene prediction, etc).
          + After the final model equation, a brief interpretation of the coefficients would be more inclusive. CO(GT) has by far the largest coefficient, which makes sense given the relationship between combustion-related pollutants. Are the signs of the other coefficients sensible?
        


- Feedback giver - Yujin Kim
  + The assignment states, "In the end, I had 347 Dates (rows)." However, the CV is currently being run on the 7,344-row hourly dataset (`raw_air_quality`). Since you already created `average_air_quality`, it would be more appropriate to use that daily-aggregated dataset (347 days). This also affects how the training split is interpreted - right now it is using the first 250 hours, whereas the instructions specify the first 250 days out of 347.
  + In the missing-value filtering step, `RH` appears twice and `AH` is missing from the condition: `raw_air_quality = raw_air_quality[(raw_air_quality["C6H6(GT)"] != -200) & (raw_air_quality["CO(GT)"] != -200) & (raw_air_quality["T"] != -200) & (raw_air_quality["RH"] != -200) & (raw_air_quality["RH"] != -200)]` The second `RH` should be `AH`.
  + The helper CV function is not curretnly implementing a one-step-ahead prediction. The instructions specify that the test set should "just include the day + 1 row." However, the current implementation uses: `X_test = X[day:]` Which includes all rows after `day`. To follow the assignment's sequential structure, the test set should include only a single row: `X_train = X[:day]` \ `X_test = X[day:day+1]` \ 'y_train = y[:day]` \ `y_test = y[day:day+1]`
