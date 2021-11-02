# e- Yantra 2021 - DairyBike
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

