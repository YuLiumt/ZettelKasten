## GW170817 and GW190814: tension on the maximum mass

- **Author**: Nathanail A, [[Elias Roland Most]], Rezzolla L.
- **Summary**:
	- The detection of the binary events GW170817 and GW190814 has provided invaluable constraints on the maximum mass of nonrotating configurations of neutron stars, $M_{TOV}$. 
		- However, the large differences in the neutron-star masses measured in GW170817 and GW190814 has also lead to a significant tension between the predictions for such maximum masses, with GW170817 suggesting that $M_{TOV} \lesssim 2.3 M_{\odot}$, and GW190814 requiring $M_{TOV} \gtrsim 2.5 M_{\odot}$ if the secondary was a (non- or slowly rotating) neutron star at merger.
			- When assigning a NS nature to the secondary in GW190814, a massive (rapidly) rotating NS with a mass $>2.5 M_{\odot}$ is perfectly consistent with a maximum mass $M_{TOV} \simeq 2.3 M_{\odot}$ inferred from the GW170817 event.
			- Given the difficulty of sustaining rapid rotation over the very long timescales associated with the inspiral of the binary, the secondary must have collapsed at one point before merger, so that in this second scenario GW190814 should effectively be considered a BH-BH merger
		- Hence, the tension can be released by assuming that the secondary in GW190814 was a black hole at merger.
	- We have employed a genetic algorithm to refine in a probabilistic manner the previous estimates of the maximum mass, obtaining that $M_{\mathrm{TOV}}=2.210_{-0.123}^{+0.117} M_{\odot}$ within a $2\sigma$ confidence level.
- **Link**: [[GW170817]], [[GW190814]], [[NS - Mass]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2021arXiv210101735N/abstract) Nathanail A, Most E R, Rezzolla L. GW170817 and GW190814: tension on the maximum mass. arXiv:2101.01735.

___

## Highlight


- The median of the distribution is  $M_{\mathrm{TOV}}=2.210_{-0.123}^{+0.117} M_{\odot}$, where the errors reported here are for $2\sigma$ level, and thus in good agreement with massive-pulsar measurements.
	![[Pasted image 20210107222214.png]]
	- As a consistency check, we can use set of parameters that yield the maximum-mass distribution in Fig. 1, to estimate the GW energy lost both in the inspiral and in the post-merger.
		![[Pasted image 20210108104159.png]]
		- The ejected-mass distribution is in perfect agreement with observational bounds when the maximum mass is below $2.326 M_{\odot}$.
- Does anything break down when larger maximum masses are considered?
	- Consider two specific values of the maximum mass, namely, $M_{\text {TOV}}=2.4 M_{\odot}$ and $M_{\text {TOV}}=2.5 M_{\odot}$.
		![[Pasted image 20210108104534.png]]
		- Considering maximum masses with $M_{\mathrm{TOV}} \gtrsim 2.4-2.5 M_{\odot}$ requires efficiencies in the GW emission well above the NR estimates and leads to a significant under-production of the ejected mass, well below the values expected from the observations.
			-  This behaviour is due to the fact that remnants with a given $\chi$ will radiate more GWs if they are more massive.
			- Considering large-mass stars inevitably reduces the portion of the budget available for the ejecta.
		

## Algorithm

Quasi-universal relations exist between the masses of uniformly rotating stellar models along the stability line to BH formation and the corresponding dimensionless angular momentum $j_{coll}$ normalised to the maximum (Keplerian) one $j_{Kep}$. We here express this relation as

$$
\chi\left(j_{\text {coll}} / j_{\text {Kep}}\right):=\frac{M_{\text {crit}}}{M_{\text {TOV}}}=1+\alpha_{2}\left(\frac{j_{\text {coll}}}{j_{\text {Kep}}}\right)^{2}+\alpha_{4}\left(\frac{j_{\text {coll}}}{j_{\text {Kep}}}\right)^{4} \tag{1}
$$
where $\alpha_{2}=1.316 \times 10^{-1}$ and $\alpha_{4}=7.111 \times 10^{-2}$, and the value of the Keplerian specific angular momentum is approximately given by $j_{\text {Кер}} \sim 0.68$. In the case of nonrotating models, $j_{\text {coll}}=0$ and $\chi(0)=1$, while for maximally rotating models $j_{\text {coll }}=j_{\text {Kep }}$ and $\chi(1):=M_{\max } / M_{\mathrm{TOV}} \approx 1.20_{-0.05}^{+0.02}$, where $M_{\max }$ is the maximum mass that can be sustained through uniform rotation. Note that range $\chi(1)$ is based on a specific set of hadronic equations of state (EOSs).
 
 Because Eq. (1) expresses a relation between gravitational masses, while the electromagnetic emission from GW170817 informs us about the ejected baryonic mass, we need a relation between gravitational and baryonic mass $M_{b}$ for uniformly rotating NSs at the mass-shedding limit. This relation obeys a quasi-universal relation near the values of the maximum mass that, with a $2\sigma$ uncertainty, is given by $\eta:=M_{b, \max } / M_{\max } \approx 1.171 \pm 0.014$ at the maximum-mass limit. $\eta$ is almost constant in the neighbourhood of $M_{\max }$ so that hereafter we simply write the conversion between the two masses as $M_{b}=\eta M$.
 
 The total gravitational mass of GW170817 as inferred from the GW signal is $M_{g}=2.73_{-0.01}^{+0.04}$, whose corresponding baryonic mass $M_{b}$ soon after the merger can be thought of as being given by the combination of the baryonic mass in the HMNS $M_{b, \mathrm{HMNS}}$ - itself composed of the mass in the core and in a Keplerian disk - and of the mass ejected dynamically, i.e.,
 
 $$
M_{b}=M_{b, \mathrm{core}}+M_{b, \mathrm{disk}}+M_{\mathrm{ej}}^{\mathrm{dyn}}=\eta M_{g}^{*} \tag{2}
$$
where $M_{g}^{*}:=M_{g}-M_{\mathrm{GW}}^{\mathrm{insp}}$ and $M_{\mathrm{GW}}^{\mathrm{insp}}$ is the energy lost to GWs in the inspiral. Here, the last equality relates the baryonic and gravitational mass of the merger remnant.

Defining now $\xi$ as the fraction of the HMNS baryonic mass in the core, the two components of the HMNS shortly after merger can be written as

$$
M_{b, \text { core }}:=\xi\left(M_{b}-M_{\mathrm{ej}}^{\mathrm{dyn}}\right)=\xi\left(\eta M_{g}^{*}-M_{\mathrm{ej}}^{\mathrm{dyn}}\right) \tag{3}
$$
The fraction $\xi$ is in principle unknown, but numerical simulations have shown that this ratio is actually weakly dependent on the EOS and given by $\xi \approx 0.95_{-0.05}^{+0.04}$. As time goes by, the merger remnant will loose part of its baryonic mass via the emission of magnetically driven or viscous-driven winds, so that at collapse it will have a baryonic mass

$$
M_{b}=M_{b, \text { core }}^{\text {coll }}+M_{b, \text { disk }}^{\text {coll }}+M_{\mathrm{ej}}^{\mathrm{dyn}}+M_{\mathrm{ej}}^{\text {blue }}+M_{\mathrm{ej}}^{\mathrm{red}} \tag{4}
$$
where the last equality follows from rest mass conservation and $M_{b, \text { core }}^{\text {coll }}$ and $M_{b, \text { disk }}^{\text {coll }}$ are the respective values of the core and the disk at the time when BH formation of the core is triggered, while $M_{\mathrm{ej}}^{\mathrm{blue}}$ ($M_{\mathrm{ej}}^{\mathrm{red}}$) is the part of the ejected matter leading to the blue (red) emission in the kilonova and differs from the dynamical ejecta from the timescale over which the material is lost.

Numerical simulations of remnant disks indicate that most of the red ejecta originate from the disk, whereas most of the blue ejecta will come from the hot surface of the HMNS. Hence, for simplicity we will assume that the blue ejecta originate from the HMNS only, while the red ejecta exclusively represent unbound material of the disk. We classify the latter via a parameter

$$
f_{\text {disk }}:=M_{\mathrm{ej}}^{\mathrm{red}} / M_{b, \mathrm{disk}} \simeq 0.2-0.5 \tag{5}
$$

BH formation is triggered when the gravitational mass is reduced by the emission of GWs and the remnant hits the stability line for uniformly rotating models with a massive core $M_{b, \text { core }}^{\text {coll }}$

$$
M_{b, \text { core }}^{\text {coll }}=\eta M_{g}^{*}-M_{b, \text { disk }}-M_{\text {ej }}^{\text {dyn }}-M_{\text {ej }}^{\text {blue }}=\eta \chi M_{\text {TOV }} \tag{6}
$$
where the last equality relates the baryon mass of the remnant core to the maximum mass $M_{\text {TOV }}$ of nonrotating NS via Eq. (1). Eq. (6) can also be written

$$
\eta \chi M_{\mathrm{TOV}}=\xi\left(\eta M_{g}^{*}-M_{\mathrm{ej}}^{\mathrm{dyn}}\right)-M_{\mathrm{ej}}^{\mathrm{blue}} \tag{7}
$$

Two more equations can be used for consistency

$$
M_{\mathrm{ej}}^{\mathrm{red}}=f_{\mathrm{disk}}(1-\xi)\left(\eta M_{g}^{*}-M_{\mathrm{ej}}^{\mathrm{dyn}}\right) \tag{8}
$$ 

$$
\chi M_{\mathrm{TOV}}=M_{g}^{*}-\eta^{-1}\left(M_{b, \mathrm{disk}}^{\mathrm{coll}}+M_{\mathrm{ej}}^{\mathrm{dyn}}+M_{\mathrm{ej}}^{\mathrm{blue}}+M_{\mathrm{ej}}^{\mathrm{red}}\right)-M_{\mathrm{GW}}^{\mathrm{post}} \tag{9}
$$

where the first one expresses the conservation of rest-mass leading to the kilonova emission and the second one the conservation of gravitational mass since $M_{\mathrm{GW}}^{\mathrm{post}}$ is the mass lost to GWs after the merger. Expression (9) does not constraint post $M_{\mathrm{GW}}^{\mathrm{post}}$, which thus remains undetermined. As a way around, we use an approximate quasi-universal relation between the total mass lost to GWs $M_{\mathrm{GW}}^{\text {tot }}$ and the specific angular momentum of the remnant after the merger

$$
m_{\mathrm{GW}}^{\mathrm{tot}} \sim c_{0}+c_{1} j_{\mathrm{rem}, 20}+c_{2}\left(j_{\mathrm{rem}, 20}\right)^{2} \tag{10}
$$
where $m_{\mathrm{GW}}^{\mathrm{tot}}:=M_{\mathrm{GW}}^{\mathrm{tot}} /\left(M_{g} v\right)$, $j_{\mathrm{rem}, 20}:=J_{\mathrm{rem}, 20} /\left(M_{g}^{2} v\right)$ is the specific angular momentum of the remnant within $\sim$ 20 ms from the merger, and $v:=m_{1} m_{2} /\left(m_{1}+m_{2}\right)^{2}$ is the symmetric mass ratio.

By splitting total mass lost to GWs into the two components relative to the inspiral and post-merger, i.e., $M_{\mathrm{GW}}^{\mathrm{tot}}=M_{\mathrm{GW}}^{\mathrm{insp}}+M_{\mathrm{GW}}^{\mathrm{post}}$, Eq. (10) allows us to introduce an additional constraint between $j_{\mathrm{coll}}$ and $M_{\mathrm{GW}}^{\mathrm{post}}$.

Not all of the merger remnant’s angular momentum will end up in the collapsed object. A number of physical processes will move part of the angular momentum outwards, placing it on stable orbits relative to the newly formed BH. Because the efficiency of this process depends on microphysics that is poorly understood, we account for this by introducing a fudge factor $f_{B}$ defined as $j_{\text {coll }}=:\left(1-f_{B}\right) j_{\text {rem }, 20}$, so that the specific angular momentum of the disk is $j_{\text {disk }}:=f_{B} j_{\text {rem }, 20}$

Since in Eqs. (7), (8) and (9) the function $\chi$ always appears together with $M_{\mathrm{TOV}}$, it is difficult to set reasonable ranges for $\chi$. However, numerical simulations have revealed that the dimensionless spin of the BH produced by the merger $j_{\mathrm{BH}}$ (and hence $j_{\text {coll }} \lesssim j_{\mathrm{BH}}$) is actually constrained in a rather limited range, i.e., $0.7 \lesssim j_{\mathrm{BH}} \lesssim 0.9$. Exploiting this information, and assuming conservatively that $80 \%$ of the specific angular momentum at collapse is inherited by the BH, i.e., $j_{\text {coll }}=0.8 j_{\text {BH}}$, we can effectively constrain 𝜒 to be in the range $1.11 \leq \chi \lesssim 1.22$.

In summary, we need to solve a multidimensional parametric problem as expressed by Eqs. (7), (8) and (9) after varying in the appropriate ranges the (ten) free parameters in the system: $\chi, \xi, \eta, M_{\mathrm{GW}}^{\mathrm{insp}}, M_{\mathrm{ej}}^{\mathrm{blue}}, M_{\mathrm{ej}}^{\mathrm{dyn}}, M_{\mathrm{TOV}}, v, f_{\mathrm{disk}}$ and $f_{B}$. 