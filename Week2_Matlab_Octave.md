# practice and explain!
1~=2  
disp(sprintf('%.2f',3.14159))  
format long/short  
v = 1:0.2:2  
ones(3,3)  
zeros(3,3)  
rand(2,3)  
randn(2,3)  
hist(rand(100,100),100)  
eye(10)  
help help/randn/eye...  


# Basic Operation
* bool value return 0/1; e.g: 1 && 0  >> ans = 0
* not equal is ~= not !=  
* put ';' at the end if a semi-colon is put at the end:  
a=3; dont print the result;  
* logical operator: &&, || (xor function)  
* display something: disp(sprintf('2 decimals: %.2f',3.14159)) >> 2 decimals: 3.14  
disp(),  sfprintf('c string template')  
* change output number decimal place. >> format long/short
* matrix A = [1 2;3 4;5 6]  
* vector V = [1 2 3 4 5 6] -- 1 by 6 matrix
* V= [1;2;3;4;5;6] -- 6 by 1 matrix  
* v = 1:0.2:3 --> Start from 1, increased by 0.2 until 3
* ones(2,3) generate a matrix 2 by 3 with only ones...
* zeros(1,3) is basically the same
* rand(1,3) generate 1 by 3 matrix of random numbers(from 0 to 1)
* randn(1,3) --> from Gaussian distribution(normal distribution), generate 1 by 3 vector
* sqrt() --> square root
* hist(matrix,number of bins) --> print histogram of a matrix with bins  
* eye(4) --> 4 by 4 identity matrix  
* help command --> help eye, help doc of eye function

# Moving Data
* size(matrix) --> return 1 by 2 matrix: row, column
* length(v) --> length of the longest dimension  
*　load data:  load features.dat  
* who shows the variables in memory
* clear variable --> delete variable from memory
* v= priceY(1:10) --> slice to get v including 1 and 10
* save file_name.mat variable  --> load file_name.mat  then you can use v
* save hello.txt v -ascii %will save as ascii text  
* A(3,2) means element at row 3 column 2
* A(2,:) %':' means everything at that row/column
* A(:,2) everything at the second column
* A([1 3],:) [1 3] means 1 or 3, : means every element at that row  
* A(:,2) = [1 22 33] reassign the second column
* A=[A,[101;102;103]] % append the new column to the right
* A(:)  --> put all elements in A to one vector
* C = [ A B ]  --> concate B to the right of A
* C = [A ; B] --> put B below of A

# Computing Data
* A * B --> matrix multiply  
* A .* B --> element wise multiplication
* A .^ 2 --> element wise square  
* 1 ./ A --> element wise inverse
* log(maxtrix) --> log for each element
* exp(matrix) -->  e to the element base
* abs(matrix) --> absolute value
* A + ones(size(A)) == A + 1
* A' = A<sup>T</sup>
* [val, ind] = max(a) --> return the value and index of max element
* A < 3 --> compare each element and replace with 0 or 1 
* find(A < 3) --> tell you which element is less than 3
* A = magic(3) --> return 3by3 matrix that all columns and rows and diagonal sum to the same value 
* [r,c] = find(A>5) --> return row, column index of elements that is true
* sum(), prod() --> sum or product column wise  
* floor(), ceil() --> floor or ceil each element
* max(rand(3),rand(3)) --> compare the element at the same position in two matrix and return the maxiumum value
* max(A,[],1) --> get the max of the first dimension (column-wise) of A
* max(A,[],2) --> the second dimension(row-wise) of A
* max(max(A)) == max(A(:))
* sum(A,1) --> sum of first dimension(column-wise)  
* sum(A,2) --> sum of the second dimension(row-wise)
* A .* eye(9) 
* flipud(matrix) --> flip up down
* pinv() --> psudo inverse

# Plot Data
* plot(x_array,y_array,'color') 
* hold on; --> generate plot on the same current diagram
* figure(1); --> create new empty figures
* plot(x,y) --> plot on the new created figure
* subplot(1,2,1); %divides plot a 1x2 grid, and access the first element
* plot(t,y2) --> plot t-y2 on the newly created left subplot 
* axis([0.5 1 -1 1]) --> set the x and y range, x: 0.5~1, y:-1~1
* clf --> clear figure
* imagesc(A), colorbar, colormap grey  --> create a pic to divided by A matrix, use color to display A's values
* a=1,b=2,c=3 --> command chaining of function calls, same as a=1;b=2;c=3 but do not print the result

# Flow contro
* for i=1:10, v(i)=2^i;end;
* break/continue also can be used
* i=1; while i<=5, v(i)=100;i=i+1;end;
* if condition; elseif condition; else; end;
* function y=squareThisNumber(5), y=x^2;
* addpaht('path') to be able to execute the func in this path

# Vectorization
* h(x) = sum(theta j  * x j) = theta<sup>T</sup> * x   
  prediction = theta' * x
* using vector rather than loops as much as possible, it is:  1. more efficient. 2. more easy to understand.  
3. less error-prone
