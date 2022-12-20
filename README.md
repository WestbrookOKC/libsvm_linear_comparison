# libsvm_linear_comparison

dataset: https://www.csie.ntu.edu.tw/~cjlin/libsvmtools/datasets/


1.Pre-proprocess the data by subtracting mean and scale them in [-1,1]

![image](https://user-images.githubusercontent.com/100655843/208721883-6dd49593-eddc-43ac-9799-1e27fd0c31f7.png)

Use the csr_find_scale_param function from libsvm can do that
2.
The following compare the result of SVM(primal) and SVM(dual). Basically, we change the parameters -s, then we can change the type of problem. We can know that, the accuracy of dual is a little higher than primal. Dual can provide a solution which is close to the best solution. But SVM(dual) cost more time, which is not my expected. I thought dual may cost less time, but may be it is because editor have already know some information about dataset, so second time using SVM(primal) cost less time.

![image](https://user-images.githubusercontent.com/100655843/208721907-715892a9-9f8b-40fe-855e-2f065bc2a1e5.png)

 
3.Use Libsvm, apply kernel methods, the accuracy has increased.
I believe the main reason is that the dimension is large and there are too many points inside of it. So, the normal linear classifier can not handle with that well.
But after applying kernel methods, it can be non-linear, and the distance between point to point get larger. Therefore, the accuracy has increase.

![image](https://user-images.githubusercontent.com/100655843/208721948-821afbee-26c2-46a6-8802-059629dccb78.png)



4.Visualize results in 2 dimensional space. 
The first thing I need to do is to do PCA, reducing the dimension into 2 dimensional space.
Second, we have (x,y) positions, then we plot that in the figure.

The third thing is to calculate the support vector. To be details, calculate W and b

The final plot is here:
![image](https://user-images.githubusercontent.com/100655843/208721999-d45df34a-5e9c-4b8a-90aa-e28d790c3962.png)


5.Apply PCA before classification, the accuracy has increased a little, so this is the reason why we always want to reduce dimension before classification.





