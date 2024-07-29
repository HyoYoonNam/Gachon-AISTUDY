* input node의 수 = features 수
* output node의 수 = class의 수
# What is Perceptron
In machine learning, the perceptron is an **algorithm for supervised learning of binary classfiers**.  
* 1943, 개념 고안 Warren McCulloch and Walter Pitts.
* 1957, Mark I machine 개발 at the Cornell Aeronautical Laboratory by Frank Rosenblatt.

## Single-layer Perceptron
input layer와 output layer만으로 구성된다.  
이 경우에는 AND, OR gate에 대해서는 linear하게 표현하여 학습할 수 있다.  
하지만 XOR gate의 경우에는 non-linear하기 때문에 학습할 수 없다.

## Multi-layer Perceptron
input layer와 output layer 사이에 one or more hidden layer를 배치하여 non-linear classified data에 대해서도 학습할 수 있도록 했다.

# Neural Network; 신경망
perceptron을 여러 개 연결한 것 즉, 2개 이상의 input node와 2개 이상의 output node가 존재한다.  
> 굳이 분류를 하자면, NN은 ML이고 DNN부터 DL이라고 할 수 있겠다.

## Deep Neural Network; DNN; 심층 신경망
multi-layer perceptron을 여러 개 연결한 것 즉, 2개 이상의 input node, 2개 이상의 out node, 2개 이상의 hidden layer가 존재한다.



# References
[책정보, 딥러닝 파이토치 교과서 : 길벗, 이지톡](https://www.gilbut.co.kr/book/view?bookcode=BN003345)  
[Neural network (machine learning)](https://en.wikipedia.org/wiki/Neural_network_(machine_learning))  
[Perceptron](https://en.wikipedia.org/wiki/Perceptron)
