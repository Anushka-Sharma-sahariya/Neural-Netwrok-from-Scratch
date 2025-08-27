A simple two-layer neural network and trained it on the MNIST digit recognizer dataset. It's meant to be an instructional to understand the underlying math.


The NN will have a simple two-layer architecture. Input layer  𝑎[0]  will have 784 units corresponding to the 784 pixels in each 28x28 input image. A hidden layer 𝑎[1]  will have 10 units with ReLU activation, and finally our output layer  𝑎[2]  will have 10 units corresponding to the ten digit classes with softmax activation.

**Forward propagation**

𝑍[1]=𝑊[1]𝑋+𝑏[1]
𝐴[1]=𝑔ReLU(𝑍[1]))
𝑍[2]=𝑊[2]𝐴[1]+𝑏[2]
𝐴[2]=𝑔softmax(𝑍[2])

**Backward propagation**

𝑑𝑍[2]=𝐴[2]−𝑌
𝑑𝑊[2]=1𝑚𝑑𝑍[2]𝐴[1]𝑇
𝑑𝐵[2]=1𝑚Σ𝑑𝑍[2]
𝑑𝑍[1]=𝑊[2]𝑇𝑑𝑍[2].∗𝑔[1]′(𝑧[1])
𝑑𝑊[1]=1𝑚𝑑𝑍[1]𝐴[0]𝑇
𝑑𝐵[1]=1𝑚Σ𝑑𝑍[1]

**Parameter updates**

𝑊[2]:=𝑊[2]−𝛼𝑑𝑊[2]
𝑏[2]:=𝑏[2]−𝛼𝑑𝑏[2]
𝑊[1]:=𝑊[1]−𝛼𝑑𝑊[1]
𝑏[1]:=𝑏[1]−𝛼𝑑𝑏[1]

**Vars and shapes**

Forward prop

𝐴[0]=𝑋 : 784 x m
𝑍[1]∼𝐴[1] : 10 x m
𝑊[1] : 10 x 784 (as  𝑊[1]𝐴[0]∼𝑍[1] )
𝐵[1] : 10 x 1
𝑍[2]∼𝐴[2] : 10 x m
𝑊[1] : 10 x 10 (as  𝑊[2]𝐴[1]∼𝑍[2] )
𝐵[2] : 10 x 1

Backprop

𝑑𝑍[2] : 10 x m (  𝐴[2] )
𝑑𝑊[2] : 10 x 10
𝑑𝐵[2] : 10 x 1
𝑑𝑍[1] : 10 x m (  𝐴[1] )
𝑑𝑊[1] : 10 x 10
𝑑𝐵[1] : 10 x 1
