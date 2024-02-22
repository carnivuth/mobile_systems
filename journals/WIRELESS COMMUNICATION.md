# WIRELESS COMMUNICATIONS

## LAYER 1

Propagation formulas

- free-space loss: $P_{r}\simeq P_{t}G_{t}G_{r}(\frac{\lambda }{4\pi d})^2$ 
- plane earth loss: $P_{r}\simeq P_{t}G_{t}G_{r}(\frac{h_{t}h_{r}}{d^2})^2$ 

In this type of communications there are problems due to distance of the device and signal propagation physical laws. a mobile system with performance constraint need to account that

At a certain distance signal are to weak to be distinguished by noise, the signal is lost

from the previous formulas the signal power decreases alongside the square of distance

This models are not useful in real scenarios that are far more complicated so the focus shifts more towards empirical models

![](Pasted%20image%2020240222162731.png)

in Real world scenarios the power received from a device can be a lot more strange than what equations predict
This strange behavior is due to a phenomenon called **shadowing**, this is modeled by a probabilistic function of the power received

![](Pasted%20image%2020240222163341.png)

With this model there is no certain that the signal is always be comprehensible, so this implies that there will be always the need of re-transmission and so no bandwidth is guaranteed 

## REFLECTIONS

![](Pasted%20image%2020240222163915.png)

no model is suitable to compute this situations

## DOPPLER EFFECT 

Due to the fact that nodes can move relative to each others

## SCATTERING AND ATMOSPHERIC ABSORPTION

![](Pasted%20image%2020240222164510.png)
![](Pasted%20image%2020240222164529.png)

### WIRELESS COMMUNICATION CAN BE AFFECTED BY A MULTITUDE OF FACTORS BUT THE MEAN BEHAVIOR IS TO DECREASE ALONG WITH THE SQUARE OF **DISTANCE***

Layer 2 technologies must account for this nature of the medium