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
