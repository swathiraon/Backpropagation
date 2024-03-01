# Backpropagation

Backpropagation is an algorithm that is designed to test for errors working back from output nodes to input nodes.

Consider the following model as an example,

<img width="756" alt="Screen Shot 2024-03-02 at 12 21 23 AM" src="https://github.com/swathiraon/Backpropagation/assets/37450502/5b7eedd9-a885-444a-9052-9292de5e1fd7">

 i1,i2 -input
 
 w1,w2,w3,w4,w5,w6,w7,w8 -weights
 
 a_o1,a_02 -output
 
 t1,t2-expected output
 
 a_h1,a_h2 -activation function(sigmoid)
 
 a_o1,a_o2 -activation function(sigmoid)
 
 E1,E2 -squared error
 
 Etotal-Total error
 
 All the parameters in the above image are calculated below,
- h1=w1*i1+w2*i2
- h2=w3*i1+w4*i2
- a_h1=(1/1+exp(-h1))
- a_h2=(1/1+exp(-h2)
- o1=a_h1*w5+a_h2*w6
- o2=a_h1*w7+a_h2*w8
- a_o1=(1/1+exp(-o1))
- a_o2=(1/1+exp(-o2))
- Etotal=E1+E2
- E1=1/2*(t1-a_o1)2
- E2=1/2*(t2-a_o2)2
