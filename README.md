# Model Reference Adaptive Control for a chemical process.




This project is a Matlab simulation of MRAC for a chemical process. Two types of MRAC are simulated: 

  - Gradient Method
  - Lyapunov Method

# MRAC 

The block diagram of MRAC is as follows: 

![](images/mrac_arch.PNG)



The plant to be controlled is: 

![](images/plant.PNG)

where Td and tau are unknown. 



The reference model to be tracked is: 

![](images/ref_model.PNG)


The controller is a PI controller with the following equation: 

![](images/controller.PNG)


Time delay is represented by a non-linear transfer function. However, Pade approximation estimates the delay with the following linear transfer function for the plant and the reference model, respectively.

![](images/pade_approx.PNG)


The plant model becomes: 

![](images/plant_pade.PNG)


Whereas the reference model becomes: 

![](images/ref_pade.PNG)


# Simulation

The simulation contains two redundant copies of the plant and the reference model. init.m file need to be run before running the MRAC.slx file. Many options of tau and Td could be explored to compare the performances of the two MRAC methods. 




![](images/mrac.PNG)

In this simulation tau=2 and Td=0.5, the simulation result below shows that Lyapunov converges faster and have lower overshoot than that for MIT gradient method. 

![](images/sim.PNG)


For more details please read the attached paper. 


