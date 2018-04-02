# XOR 문제 딥러닝으로 풀기

#### XOR

|  X1  |  X2  | XOR  |
| :--: | :--: | :--: |
|  0   |  0   |  0   |
|  0   |  1   |  1   |
|  1   |  0   |  1   |
|  1   |  1   |  0   |

#### Neural Net (Sigmoid 사용)

w1 = [5,	    b1 = -8	w2 = [-7,     b2 = 3		w3 = [-11,   b3 = 6

​	  5]					   -7]				-11] 

| X1    X2 | Y1    Y2 |  Y'  | XOR  |
| :------: | :------: | :--: | :--: |
|  0   0   |  0   1   |  0   |  0   |
|  0   1   |  0   0   |  1   |  1   |
|  1   0   |  0   0   |  1   |  1   |
|   1  1   |  1   0   |  0   |  0   |

> 예) [0 0][5 5]  - 8 = 0 - 8 = - 8 , sigmoid(-8) = 0



#### NN

W1 = [5, -7    b1 = [8, 3]	w2 = [-11  b2 = 6

​	  [5, -7]				          -11]

K(X) = sigmoid(XW1 + b1)

Y' = H(X) = sigmoid(K(X)W2 + b2)

~~~
K = tf.sigmoid(tf.matmul(X, W1) + b1)
hypothesis = tf.sigmoid(tf.matmul(K, W2) + b2)
~~~

---

# Backpropagation

Training data 에서 어떻게 W1, W2, b1, b2를 학습할 수 있을까?



#### Chain Rule

f = wx + b, g = wx, f = g + b

=> w가 / x가 / b가 **f**에 미치는 영향을 구하자! (by *미분*)

