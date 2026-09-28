# K-Means Clustering: Finding Hidden Patterns

Hello! Welcome to the Unsupervised Learning section. Sometimes you don't have historical answers (labels) to train a model with. You just have a massive database of customers or logs, and you need to group them logically. That is what K-Means is designed for.

### How K-Means Works (The Algorithm):
1. **Initialization**: You decide how many groups you want (let's say K=4). The algorithm randomly drops 4 "Centroids" onto the map.
2. **Assignment**: The algorithm measures the distance from every single data point to all 4 centroids. It assigns the point to whichever centroid is closest.
3. **Update**: Once all points belong to a group, the algorithm calculates the mathematical mean (center) of the group, and moves the centroid to that exact spot.
4. **Repeat**: It repeats steps 2 and 3 over and over until the centroids stop moving. It has successfully found the center of the clusters!

### Why Beginners Fail at K-Means
K-Means relies entirely on **Euclidean Distance** (drawing a straight line with a ruler). If your dataset has "Age" (ranges from 18 to 80) and "Income" (ranges from 30,000 to 200,000), the massive numbers in Income will completely dominate the ruler. The algorithm will cluster people purely based on Income and entirely ignore Age!

### My Implementation
- **Whitening**: I explicitly implemented a mathematical `whiten()` step before clustering. This forces every feature to have a variance of 1.0. It levels the playing field so the algorithm respects all features equally!
- **System Constraints**: Because of local Windows DLL restrictions on `scikit-learn` C-extensions, I completely bypassed `sklearn` and wrote the engine using SciPy's highly optimized `scipy.cluster.vq` module.
- **Visualization**: I plotted the raw, uncolored data, and then beautifully mapped out the algorithm's final decisions, complete with giant stars denoting the final resting place of the mathematical centroids. 