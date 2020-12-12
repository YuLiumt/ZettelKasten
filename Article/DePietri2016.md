# Modeling Equal and Unequal Mass Binary Neutron Star Mergers Using Public Codes

* **Author**: De Pietri R, Feo A, Maione F, [[Frank Löffler]]
* **Summary**:
* **Link**: [[Binary Neutron Star]]
* [ADS](https://ui.adsabs.harvard.edu/abs/2016PhRvD..93f4047D/abstract) - De Pietri R, Feo A, Maione F, Löffler F. Modeling equal and unequal mass binary neutron star mergers using public codes. PRD, 2016, 93(6): 64047.

#in-progress
___

## Accuracy in the Determination of Merger Time

To investigate the effect of different numerical methods on the errors (especially in the determination of merger time) and gain confidence in the obtained results, we simulated the same model (SLy14vs14) using different combinations of numerical methods, but keeping all other parameters the same.

* WENO reconstruction and BSSN-NOK scheme for the gravitational sector; 
* PPM reconstruction and BSSN-NOK scheme for the gravitational sector; 
* MP5 reconstruction and BSSN-NOK scheme for the gravitational sector; 
* WENO reconstruction and CCZ4 scheme for the gravitational sector.

![image-20201110123352463](https://tva1.sinaimg.cn/large/0081Kckwgy1gkjyxtpopcj30r010q7cd.jpg)

Despite all observed differences ==it is important to make sure that all tested methods lead to the same determination of the **"true" merger time**==, denoted as $t_{\text {merger }}(d x=0)$ as it is the merger time computed using an unlimited resolution, i.e., $d x=0 .$ 

If we assume the following dependence: 
$$
t_{\text {merger }}(d x)=t_{\text {merger }}^{d x=0}+A \cdot d x^{\gamma}
$$
, we obtain $t_{\text {merger }}^{d x=0} = (10.42 \pm 0.10)$ ms and $\gamma = 1.95 \pm 0.12$ for WENO-BSSN-NOK, which is consistent with the assumption of a second-order convergence for the simulation of the merger phase.

Unlike for the inspiral phase, we are not able to do a complete study of the convergence properties during the post-merger and collapse phase, e.g. for ==the neutron star life time==, without using a higher resolution (incurring a higher computational cost).

![image-20201110125121417](https://tva1.sinaimg.cn/large/0081Kckwgy1gkjzg18iogj30z40u0n47.jpg)

One can observe that the extrapolated merger time is always consistently lower than the approximation from an EOB for all models.

This differenece could be seen as an indication for the importance of **tidal effects** on the late stage of the merger, but **it could also stem from possible differences in the initial data**. We did not evolve a high enough number of orbits before the merger to draw any firm conclusion of which one is the case.

## Models Resulting in Collapse to a Black Hole

![image-20201110125812872](https://tva1.sinaimg.cn/large/0081Kckwgy1gkjzn5jfakj30qw0vw7al.jpg)

The evolution of model SLy16vs16 results in a direct collapse and the formation of a BH just after the merger. Model SLy15vs15, instead, is characterized by a delayed collapse to a BH a few milliseconds after merger.

One of the main characteristics of our results for these two models is that after the merger and subsequent collapse to a BH, the remaining matter density drops quickly below neutron drip.

> the fact that the remnant matter is below the neutron drip threshold is an indication that a noticeable emission of neutrinos should occur within the 10 ms that follows the merger.

![image-20201110130340206](https://tva1.sinaimg.cn/large/0081Kckwgy1gkjzsu1fi5j30m80xin4r.jpg)
