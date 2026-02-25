Each group member should provide feedback on the other group members’ work. Be detailed and specific where possible. The quality of this feedback can play a part in your grade.

You can provide feedback to your group members in many different ways (live in a meeting, offline, or however else you devise) but the feedback must be documented here! 

Please replace “Feedback giver #x” with a group member’s name below and add feedback as a bulleted list below. Note: There is a pencil icon on the top right of the README file (when you are viewing the README.md file) that allows you to edit.

- Feedback giver - David Pressley
  + This is great work. It takes the reader through a step-wise, understandable flow that describes gradient descent in pseudo-code and then implements
  + Testing functions show good practice with test cases (e.g., squared_error_D2(y_test, x_test, b0_test, b1_test))
  + Data cleaning done correctly (or at least the same as I did it): Properly removed -200 values before analysis
  + I think the grid search results are correct (optimal c ≈ 10.28, grid search b0 ≈ -23, b1 ≈ 0.03) and comparing optimal c to the mean helps verify the algorithm works
  + Algorithm structure is correct: The gradient descent logic follows the pseudo-code correctly aside from the bug noted.
  + I did notice that `grid_search_2dim` uses 2 spaces indentation, but the rest are 4 spaces. As part of our GPP score, I suggest 4 spaces, or at least consistency throughout
  + I noticed various typos:
  +   "Constnat prediction" should be "Constant prediction"
  +   "Miminum RMSE" should be: "Minimum RMSE"
  +   there is a section header: "y and anotehr numeric variable" should be: "another"

  + If you like my introduction, please copy and use the relevant portions. We are all supposed to have a lead narrative. I think for yours, you  need to discuss the prediction task and why we're predicting benzene concentration and why gradient descent is useful here. 

    
- Concerns
  + your final gradient descent results give b1 = -0.0015 (negative), but Dr. Post's reference indicates the slope should be positive (~0.0017).
  + This caught my eye: `dist = np.linalg.norm(np.array(new_b0, new_b1) - np.array([cur_b0, cur_b1]))`. I think you need to have brackets around the first argument to `.norm`. I think it should be `dist = np.linalg.norm(np.array([new_b0, new_b1]) - np.array([cur_b0, cur_b1]))`. Maybe that's why you are getting a negative?
  + confirm you are using the correct grid in `grid_search_constant` you have `opt_c_sd = grid[opt_index_sd]`, using 'grid' instead of 'grid_sd'
  + the implementation of your `grid_search_2dim(x, y)` function seems to unpack to the same two variables: `opt_b1, opt_b1 = grid_search_2dim(x_G2, y_G2)`. I think this should be `opt_b0, opt_b1 = grid_search_2dim(x_G2, y_G2)`
  + GPP: your variable naming could be cleaner and more descriptive. I get `_sd` and `_i`, but `_D1`, `_D2`, `_D3` could use more descriptive names
  + your functions (e.g. `grid_search_constant()`, `gradient_descent_constant()`, `diff_quotient_b0()` need docstrings
  + 

- Feedback giver - Hannah Shaw
  + A few suggestions on grammar/syntax/wording:
  +   "This data is time series data (data recorded over time) for air quality measurements in Italy." - I would rewrite this as "This dataset consists of time series data (data recorded over time) for air quality measurements in an Italian city." since the website the data comes from specifically says it comes from a single Italian city, not Italy as a whole.
  +   For "Remove missing value: Exclude observation where C6H6(GT) or CO(GT) equal -200." (under the header Data Cleaning) I would explain why you are removing observations where C6H6(GT) or CO(GT) equal -200 (mainly that -200 represents NaN in this dataset). Also it should be "observations" not "observation"
  +   You keep switching between "we/our", "you/your", and "I/me/my" pronouns throughout the notebook. For the sake of consistency, just pick one set of pronouns and stick with it for the whole notebook.
  + Some typos I noticed:
  +   "we could consider the mean sqaured error" (under the header Loss Function) should be "we could consider the mean squared error"
  +   "implementing a grid search" The word "implementing" should be capitalized as "Implementing" since it's the first word in a sentence.
  +   "Pseudo cod" under the header (1) Just y - I assume you meant "Pseudo code"
  +   print("c 후보값:", grid[:5]) (2nd code box below the header (1) Just y) - I'm confused as to why that line is the only part of your notebook in Korean. And also impressed/surprised that Korean characters work in the code boxes.
