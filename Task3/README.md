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


- Feedback giver #2
  + item
