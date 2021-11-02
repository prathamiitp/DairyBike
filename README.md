# e-Yantra 2021 - DairyBike
## Task - 1
  #### Task [1.1] <**Main_File.m**>
    
    1) 1;
    2) Function_File;
    3) pkg load symbolic                  # Load the octave symbolic library
    4) syms x1 x2                         # Define symbolic variables x1 and x1
    5) x1_dot = -x1 + 2*x1^3 + x2;        # Write the expressions for x1_dot and x2_dot
    6) x2_dot = -x1 - x2;                 # YOU CAN MODIFY THESE 2 LINES TO TEST OUT OTHER EQUATIONS
    7) [x_1 x_2  jacobians  eigen_values  stability] = main_function (x1_dot, x2_dot);
  
    Line 3   - It loads the symbolic library for Octave. When we want to define equations containing variables like x, y, z etc, we need to use the symbolic library.
    Line 4   - Declares 2 symbolic variables x1 and x2 (to denote x₁ and x₂ )
    Line 5-6 - Defines a coupled set of non-linear equations using x1 and x2 (x1_dot and x2_dot are used to denote ẋ₁ and ẋ₂).
    Line 7   - It is a function call to a function named main_function(). main_function() is defined in Function_File.m and takes 2 arguments (x1_dot and x2_dot). We will explain this function later.
    
    Main_File can be used to test your code for different sets of equations on your side. You can change the x1_dot and x2_dot values to specify different equations for your code to test. Please do not modify any other line in this script.
    
  #### Task [1.1] <**Function_File.m**>
    
    find_equilibrium_points()

    1) function [x_1, x_2] = find_equilibrium_points(x1_dot, x2_dot)
    2) x1_dot == 0;
    3) x2_dot == 0;

    ######################ADD YOUR CODE HERE##########################

    ##################################################################
    
    4) x_1=double(x_1);
    5) x_2=double(x_2);
    6) endfunction

    This function is pretty straightforward
    
    find_equilibrium_points() takes x1_dot and x2_dot as arguments.
    Line 2 and 3 equate the expressions specified by x1_dot and x2_dot equal to zero.
    The function returns the set of equilibrium points for x1_dot = 0 and x2_dot = 0. This set is stored in the array [x_1, x_2].
    Please complete the code in this function so that it calculates the equilibrium points for the set of equations and stores it in the variable [x_1, x_2].
    
    When you display [x_1, x_2] (using disp() function in octave), the structure should be as shown:
    
   ![image](https://user-images.githubusercontent.com/78234306/139842544-62eac2ff-e673-42ab-8901-5663b1e97380.png)
   
    find_jacobian_matrices()
    1) function jacobian_matrices = find_jacobian_matrices(x_1, x_2, x1_dot, x2_dot)
    2) syms x1 x2;
    3) solutions = [x_1, x_2];
    4) jacobian_matrices = {};

    #####################   ADD YOUR CODE HERE  #####################

    #################################################################

    5) endfunction

    This function takes the equilibrium points (x_1, x_2) and x1_dot and x2_dot as arguments.
    It computes the jacobian matrix for x1_dot and x2_dot (It should be a 2x2 symbolic array).
    It then substitutes calculated values of x1 and x2 for each of the equilibrium points. This function returns a variable called jacobian_matrices. It is a cell array in which     each element is a 2x2 J matrix calculated for each of the corresponding equilibrium points.

    You are not allowed to change any code already written in this function. You are required to add your own code in the space provided.

    Line 3 - solution x_1 & x_2 are combined in one array solutions
    Line 4 - empty cell array jacobian_matrices is initialized.

    You are required to add code which does the following:
        Computes the jacobian of x1_dot and x2_dot.
        For each of the equilibrium points, substitute the calculated values of x1 and x2 in the jacobian and form a 2x2 matrix.
        Store that jacobian matrix as an element of the cell array jacobian_matrices.
        
    When you display the jacobian matrices cell array (using disp() function in octave), the cell array structure should be similar to the following:
    
   ![image](https://user-images.githubusercontent.com/78234306/139843280-c62ae789-5e8c-4cd0-accd-222f05979730.png)

    check_eigen_values()
    1) function [eigen_values stability] =  check_eigen_values(x_1, x_2, jacobian_matrices)
    2) stability = {};
    3) eigen_values = {};
    4) for k = 1:length(jacobian_matrices)
    5)    matrix = jacobian_matrices{k};
    6)    flag = 1;

    #####################   ADD YOUR CODE HERE  #####################

    #################################################################

    7)    if flag == 1
    8)      fprintf("The system is stable for equilibrium point(%d, %d)\n",double(eqbm_pts{k}.x1),double(eqbm_pts{k}.x2));
    9)      stability{k} = "Stable";
    10)   else
    11)     fprintf("The system is unstable for equilibrium point (%d, %d) \n",double(eqbm_pts{k}.x1),double(eqbm_pts{k}.x2));
    12)     stability{k} = "Unstable";
    13)   endif
    14) endfor
    15) endfunction	

    This function takes the x_1, x_2 and jacobian_matrices as input. For each jacobian matrix stored in jacobian_matrices, the eigenvalues of matrix are calculated and stored in the cell array eigen_values. Subsequently the eigenvalues are checked in this function. If for any jacobian matrix the eigenvalues have positive real part, the system is unstable at the corresponding equilibrium point. If all eigenvalues have negative real part, the system is stable at the corresponding equilibrium point.
    
    Two empty cell arrays stability and eigen_values are defined. A for-loop is iterated through the length of jacobian_matrices. Within the for-loop, flag = 1 is initialized. You are required to write code which does the following:
        Find out the eigenvalues for the current jacobian matrix (value stored in matrix)
        Check real part of all eigenvalues of the matrix. If all eigenvalues have negative real part, then flag is set equal to 1.
        If even one eigenvalue is positive (greater than zero), the flag is set to 0.
        Store the eigenvalues calculated in the cell array eigen_values.
        Based on value of flag, the stability of system is reported in the if-else statement.
        
    When you display the eigen_values and stability cell arrays (using disp() in octave) the output should be similar to the following:
    
   ![image](https://user-images.githubusercontent.com/78234306/139844197-70f98ffe-17f2-4f96-9898-aa97f54ca809.png)
   
    main_function()
    1. function [x_1 x_2 jacobians eigen_values stability] = main_function(x1_dot, x2_dot)
    2. 			pkg load symbolic;
    3. 			syms x1 x2;
    4.			[x_1, x_2] = find_equilibrium_points(x1_dot, x2_dot);
    5.			jacobians = find_jacobian_matrices(x_1, x_2, x1_dot, x2_dot);
    6.			[eigen_values stability] = check_eigen_values (x_1, x_2, jacobians);
    7. endfunction
    
    This function puts together all the pieces.

    It takes x1_dot and x2_dot as argument. First the equilibrium points are calculated. For each equilibrium point, the jacobian matrix is calculated. Then the stability for each equilibrium point is determined by computing the eigen_values and checking the real parts of eigen values.

    This equation returns x_1, x_2, jacobians, eigen_values, stability.
    You are not allowed to make any changes to this function. You need to run it as it is.
    After you have modified the functions explained above as instructed. You need to test your solution.
    
    To test your script, you need to run Main_File.m in octave. If your solution is correct you will see the following octave prompt:
    
   ![image](https://user-images.githubusercontent.com/78234306/139845033-32338db0-dd47-4288-bc12-e182d177615b.png)

  #### Task [1.1] <**Test_Suite.m**> (Testing Solution)
  
    Test_Suite.m is used for testing your solution. You are not allowed to make any changes in this script.
    
    The Test_Suite script has a set of non-linear equations. If your code runs successfully for the given equations then the output should be as follows:
    
   ![image](https://user-images.githubusercontent.com/78234306/139845377-a47ac1b8-7bde-4fb5-a2b5-ef5a78e542de.png)
   
    If your Test_Suite runs successfully, your Function_File.m file is ready to be submitted
        For successful completion of Task 1_1, upload the Function_File.m file on the portal.
        Now, open the portal and go to Task 1. In the Task 1 Upload section select Task 1A.
        Now select Choose file button to upload the file. From the dialogue box, select the file and click Open.
        You shall see the file name Function_File.m in text-box besides the Choose file button. Click on Upload Task button to submit the file.
