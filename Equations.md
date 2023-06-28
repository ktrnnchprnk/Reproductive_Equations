

## MePD system

To model the interplay between GABA and glutamate within the MePD we employ the Wilson-Cowan framework (Wilson et al., 1972). We extended it by including a second inhibitory variable with no external input, which constitutes the activity in the population of GABA efferents.

A key component of the Wilson-Cowan framework is a sigmoid stimulus-response function $\phi(a, F, \theta)$, which controls the mean level of activity generated in a populations at time $t$:

$\phi(a, F, \theta) = \dfrac{1}{1+\exp(-a(F-\theta))}  - \dfrac{1}{1+\exp(a\theta)},$

where $F$ indicates the input current to the given population and parameters $a$ and $\theta$ define maximal slope and its location respectively, respectively.

The input current $F$ is given by the linear sum of excitatory and inhibitory currents as follows: 

$F_{l} = c_{ll}G_l-c_{il}G_i-c_{el}G_e+\alpha K_p,$ 
$F_{i} = c_{li}G_l-c_{ii}G_i- c_{ei}G_e+(1-\alpha)K_p,$
$F_{e} = c_{le}G_l-c_{ie}G_i-c_{ee}G_e,$ 

where the parameters $c_{\text{subscript}}$ are the coupling constants, representing the strength of the communication from one population to another. The parameter $K_p$ depicts the overall level of kisspeptin input, which is then distributed to glutamate and GABA interneurons in accordance with the ratio constant $\alpha \in [0,1]$ representing the proportion of kisspeptin input to glutamate.

Using the stimulus-response function and the proposed interactions between the populations we can formulate the GABA-glutamate MePD model as follows:

$\dfrac{dG_l}{dt} =d_{l}\big(-G_l+(1- r_{l}G_l)\phi(a_{l}, F_{l}, \theta_{l})\big),$ 
$\dfrac{dG_i}{dt} = d_{i}\big(-G_i+(1-r_{i}G_i)\phi(a_{i}, F_{i}, \theta_{i})\big),$
$\dfrac{dG_e}{dt} =d_{e}\big(-G_e+(1-r_{e}G_e) \phi(a_{e}, F_{e}, \theta_{e})\big),$


where the dependent variables $G_l$, $G_i$, $G_e$ represent the non-dimensional fractions of active neurons in the populations of glutamate, GABA interneurons and GABA projection neurons at time $t$, respectively. 
The parameters $d_{l}$, $d_{i}$, $d_{e}$ control the time-scale of each corresponding variable, enabling the adjustment to the signal's transmission on different time-scales.
The model also includes refractory dynamics via the term $(1-rG)$, which detects the time period during which the populations are unable to produce a signal following an activation.
Specifically, the parameter $r$ represents the refractory period for the corresponding population and its primary effect is decreasing the maximum firing rate. 

