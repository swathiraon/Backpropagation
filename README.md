# Backpropagation

Backpropagation is an algorithm that is designed to test for errors working back from output nodes to input nodes.

Consider the following model as an example,

<img width="756" alt="Screen Shot 2024-03-02 at 12 21 23 AM" src="https://github.com/swathiraon/Backpropagation/assets/37450502/5b7eedd9-a885-444a-9052-9292de5e1fd7">
## Parameter Description

 i1,i2 -input
 
 w1,w2,w3,w4,w5,w6,w7,w8 -weights
 
 a_o1,a_02 -output
 
 t1,t2-expected output
 
 a_h1,a_h2 -activation function(sigmoid)
 
 a_o1,a_o2 -activation function(sigmoid)
 
 E1,E2 -squared error
 
 Etotal-Total error

  ## Relationship amongst parameters
 
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

## Backpropagation calculation

Once we calculate the Etotal,in order to change weights we should know the relationship between weights and the Etotal. It is  calculated from right to left.

In our case w5,w6,w7 and w8 are outermost weights closer to the output layer.Let us calculate how  Etotal value is dependented on w5.<br/>
<img width="207" alt="Screen Shot 2024-03-02 at 12 46 32 AM" src="https://github.com/swathiraon/Backpropagation/assets/37450502/ecf23283-841d-458d-9817-7d9f1a29e8ec">

But based on the above picture,w5 doesn't contribute to E2 hence, Etotal=E1


<img width="159" alt="Screen Shot 2024-03-02 at 12 46 49 AM" src="https://github.com/swathiraon/Backpropagation/assets/37450502/6839286a-92af-46c1-9e9d-c36981b14bae">

This partital derivative can further be defined using activation function output a_o1

<img width="152" alt="Screen Shot 2024-03-02 at 12 49 34 AM" src="https://github.com/swathiraon/Backpropagation/assets/37450502/56efa355-e88c-452b-8466-91514b7b2a5b">

<br/>

<img width="326" alt="Screen Shot 2024-03-02 at 12 51 33 AM" src="https://github.com/swathiraon/Backpropagation/assets/37450502/42967634-0163-43bf-ad1a-33a25308cb12">

<br/>

<img width="359" alt="Screen Shot 2024-03-02 at 12 52 03 AM" src="https://github.com/swathiraon/Backpropagation/assets/37450502/2314201b-0097-4ad9-80a5-a2225bc94501">
<br/>
Similarly,
<br/>
<img width="385" alt="Screen Shot 2024-03-02 at 12 52 37 AM" src="https://github.com/swathiraon/Backpropagation/assets/37450502/55c8d4b7-78db-4dde-b8b9-4bcafd08e775">
<br/>
<img width="354" alt="Screen Shot 2024-03-02 at 12 52 56 AM" src="https://github.com/swathiraon/Backpropagation/assets/37450502/d6db8c3f-743c-4878-886e-25b3a814b191">
<br/>

Now moving on the first NN layer,we get the following partial derviatives,

<img width="359" alt="Screen Shot 2024-03-02 at 12 54 20 AM" src="https://github.com/swathiraon/Backpropagation/assets/37450502/03aacb29-5a24-4dec-81f6-8aad38294531"><br/>
<img width="593" alt="Screen Shot 2024-03-02 at 12 54 31 AM" src="https://github.com/swathiraon/Backpropagation/assets/37450502/f99e3b04-f2bd-48cc-8d7f-482318452046"><br/>

Using the above partial dervivates we can calculate the partial dervivative of Etotal w.r.t w1,w2,w3 and w4

<img width="277" alt="Screen Shot 2024-03-02 at 12 55 45 AM" src="https://github.com/swathiraon/Backpropagation/assets/37450502/21360b73-f671-4bd4-bdad-53128d06a292"><br/>
<img width="738" alt="Screen Shot 2024-03-02 at 12 56 05 AM" src="https://github.com/swathiraon/Backpropagation/assets/37450502/9c7b7115-cad0-4a4a-b6cf-037062e56319"><br/>

The calculation for the image is as follows
<img width="1408" alt="Screen Shot 2024-03-02 at 1 00 26 AM" src="https://github.com/swathiraon/Backpropagation/assets/37450502/f5bced16-7a73-45d9-8947-3228ba926a57"><br/>

<img width="1402" alt="Screen Shot 2024-03-02 at 1 01 58 AM" src="https://github.com/swathiraon/Backpropagation/assets/37450502/30dae1a5-b8a2-475d-93e8-fb5ddbce457d"><br/>

For learning rate of 0.1 this is how the loss graph looks like

<img width="761" alt="Screen Shot 2024-03-02 at 1 02 37 AM" src="https://github.com/swathiraon/Backpropagation/assets/37450502/ebdbc94e-6362-498c-95c8-54a04bdcf87c"><br/>

For learning rate of 0.2 this is how the loss graph looks like



<img width="664" alt="Screen Shot 2024-03-02 at 1 04 54 AM" src="https://github.com/swathiraon/Backpropagation/assets/37450502/739b0263-23ae-4dee-ae76-10fa934707ba"><br/>

For leaerning rate of 0.5,

<img width="679" alt="Screen Shot 2024-03-02 at 1 05 47 AM" src="https://github.com/swathiraon/Backpropagation/assets/37450502/17ebd3fe-b3a5-4cc5-a8ea-d16f7e821749"><br/>

For learning rate of 0.8,
<img width="680" alt="Screen Shot 2024-03-02 at 1 06 45 AM" src="https://github.com/swathiraon/Backpropagation/assets/37450502/fe194c8e-78e1-4ca0-970d-5f5ce230d27c"><br/>

For learning rate of 1





<img width="658" alt="Screen Shot 2024-03-02 at 1 07 08 AM" src="https://github.com/swathiraon/Backpropagation/assets/37450502/1b9b121c-c452-421e-a4ad-2b52d5372252">


