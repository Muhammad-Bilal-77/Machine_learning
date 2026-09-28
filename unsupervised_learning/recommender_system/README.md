# Recommender Systems: The Engine of the Internet

Welcome to Recommender Systems! If you've ever fallen down a YouTube rabbit hole, or bought something Amazon suggested, you have been influenced by algorithms exactly like this one.

### The Algorithm Explained (Collaborative Filtering)
There are two main types of recommenders: Content-Based (recommending movies with similar genres) and **Collaborative Filtering** (recommending items based on what similar people liked). I built a Collaborative Filtering system here.

The core philosophy is simple: **"If User A and User B agreed in the past, they will probably agree in the future."**

### Under the Hood: Pure Linear Algebra
A lot of tutorials just import a library and call `.fit()`. I hate that because it hides the math. I built this engine from scratch using `numpy` so you can explicitly see how the calculation happens.

1. **The Ratings Matrix**: I built a mock matrix where rows are users and columns are movies. A `0` means the user hasn't watched the movie yet. Our goal is to predict what rating they *would* give that `0`.
2. **Cosine Similarity**: I wrote a custom, vectorized function to calculate the dot product of normalized user vectors. This measures the "angle" between two users' tastes. If the cosine is `1.0`, they have identical taste!
3. **The Prediction**: To predict if User 1 will like Movie 4, the algorithm looks at how much User 1 has in common with all other users, and computes a *weighted average* of their ratings for Movie 4. 

Check out the interactive Heatmap in the notebook to visually see the "taste clusters" form before your eyes!