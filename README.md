# Smooth Softmax 1D/2D

Usually the softmax function does not have a geometric constraint by definition. There are no "next" output units for individual output units.

If in continuous outputs, Multivariate Gaussian (or Beta dist.) would be a good starting point. We can intruduce the near-ness using the covairance matrix of the Gaussian.

However, in RL, we sometimes want to re@resent the continuous outputs by using binning the continious output space、and we cannot introduce the "near-ness" of next bins in the policy. 

Then. We might be interested where there is a in-between between the continuous action space and the discrete action space.

### A Solution

The key insight is that the geometric constraint can be represented by the convolution with a fixed filter before inputting into the softmax operation.

This sample code includes the example implementation to adding that constraint into the softmax.

Maybe some related architectue exists, but I'll put this insight here for future the usage.

#### Example outputs of 1D smooth-softmax
![Screen Shot 2022-02-14 at 15 26 31](https://user-images.githubusercontent.com/1684732/153815654-995628ac-0adf-4348-8965-78f040d9d10b.png)

#### Example outputs of 2D smooth-softmax
![Screen Shot 2022-02-14 at 15 26 37](https://user-images.githubusercontent.com/1684732/153815660-2d9431e0-8718-4bdf-a81b-d6034435bdcc.png)
