# e-Yantra 2021 - DairyBike   
    
## [Equation Solving In Octave](https://github.com/prathamiitp/DairyBike/tree/master/solving%20Eq%20in%20octave)
This folder contain file written in Octave which shows the use of symbolic package and equation solving in octave, the specific code written in this finds Jacobian, Eigens value, and return whether a system is stable or unstable.
  
To run this code, first install Octave on your pc using the official documentation, get these two packages (control, symbolic) in your Octave envirnment and then just copy the above folder to your system and cd to that folder, then write the name of the main file dropping the ***.m*** from the last as shown here
```
Main_File
```
and hit enter in Octave CLI, or press the run button in Octave GUI.

## [Mathematical Real World Systems In Octave](https://github.com/prathamiitp/DairyBike/tree/master/Mathematical%20Real%20world%20systems%20in%20octave)
This folder contains octave files for 5 different real world systems that are mathematically modeled in octave and represented within the same code using 2d simulation.
These Real world systems are:
- [Mass_Spring_System](https://github.com/prathamiitp/DairyBike/blob/master/Mathematical%20Real%20world%20systems%20in%20octave/Mass_Spring_System.m)  
![image](https://user-images.githubusercontent.com/75429858/171190568-cb8195a8-9960-4c80-ab44-ccff9693101e.png)
- [Simple_Pulley](https://github.com/prathamiitp/DairyBike/blob/master/Mathematical%20Real%20world%20systems%20in%20octave/Simple_Pulley.m)   
![image](https://user-images.githubusercontent.com/75429858/171190882-359a1f6a-d489-4234-83d6-135752e94542.png)
- [Simple_Pendulum](https://github.com/prathamiitp/DairyBike/blob/master/Mathematical%20Real%20world%20systems%20in%20octave/Simple_Pendulum.m)  
![image](https://user-images.githubusercontent.com/75429858/171195099-0ec7b763-86e8-4dc2-82fb-6abec0d4bf00.png)
- [Complex_Pulley](https://github.com/prathamiitp/DairyBike/blob/master/Mathematical%20Real%20world%20systems%20in%20octave/Complex_Pulley.m)  
![image](https://user-images.githubusercontent.com/75429858/171188800-2fa8ec09-0b9d-4254-b3a5-a3c17ddbad35.png)
- [RW_Pendulum](https://github.com/prathamiitp/DairyBike/blob/master/Mathematical%20Real%20world%20systems%20in%20octave/RW_Pendulum.m) (Which is essentially reaction wheel based self balancing inverted pendulum, a active feedback control system that work on momentum conservation. Such systems are also used in space telescope to face there cameras to specific directions using three axis reaction wheel system.)   
![image](https://user-images.githubusercontent.com/75429858/171191851-0bd4e803-f053-4e4d-afb8-c510cfe6d545.png)

To run any code just write the name of the file dropping the ***.m*** from the last and hit enter in Octave CLI, or press the run button in Octave GUI.   
for example to run the Reaction Wheel Inverted Pendulum file use this command:
```
RW_pendulum
```

## [V-rep CppeliaSim simulations](https://github.com/prathamiitp/DairyBike/tree/master/V-rep%20CppeliaSim%20simulations)
This folder contains the V-rep simulations of [Inverted Reaction Wheel Pendulum](https://github.com/prathamiitp/DairyBike/blob/master/V-rep%20CppeliaSim%20simulations/RW_pendulum.ttt), and [Self Balancing Bike](https://github.com/prathamiitp/DairyBike/blob/master/V-rep%20CppeliaSim%20simulations/Self_Balancing_Bike.ttt), a [base model](https://github.com/prathamiitp/DairyBike/blob/master/V-rep%20CppeliaSim%20simulations/Bike_Base.ttt) of this self balancing bike is also present to show the behavious without the active feedback reaction wheel control system.  
To run these, just install CoppeliaSim EDU in your pc and start the simulation.
