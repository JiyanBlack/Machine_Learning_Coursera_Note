# Support Vector Machine
Change the Cost - Z from a log curve to a line vector. Similiar process, but give the computational advantage.  
Cost function is c * Cost + regularization_term , not Cost + lambda * regularization_term  
* if y=1, we want hx >=1(not just >=0), and cost =0;
* if y=0, we want hx <= -1(not just < 0), and then cost = 0;
* If C is large, the Cost term should be extremely small in order to make the total cost small. 
