---
layout: post
title: Notes on "Measurement-Device-Independent Quantum Key Distribution"
date: 2017-05-20
categories: Research
tags: [Quantum Physics, MDI, QKD]
description: A short note on MDI QKD.
---


### The big gap between the theory and practice of QKD.
- Real-life implementations of QKD rarely conform to the assumptions in idealized models used in security proofs.

- DI-QKD is highly impractical because it needs near unity detection efficiency.

### A simple example of MDI QKD is as follows.

- Both Alice and Bob prepare phase randomized weak coherent pulses (WCPs) in the four possible BB84 polarization states [12].
 
- Send them to an untrusted relay Charlie (or Eve) located in the middle, who performs a Bell state measurement that projects the incoming signals into a Bell state [13].

- Alice and Bob apply decoy-state techniques [14] to estimate the gain (i.e., the probability that the relay outputs a successful result) and quantum bit error rate (QBER) for various input photon numbers.
 
- Alice and Bob keep the data that correspond to the successful Bell measurement instances and discard the rest. A click in $D_{1H}$ and $D_{2V}$, or in $D_{1V}$ and $D_{2H}$, indicates a projection into the Bell state $\ket{\psi^{-}}=1/\sqrt{2}(\ket{HV}-\ket{VH})$, while a click in $D_{1H}$ and $D_{1V}$, or in $D_{2H}$ and $D_{2V}$, reveals a projection into the Bell state $\ket{\psi^{+}}=1/\sqrt{2}(\ket{HV}+\ket{VH})$.

![@Fig. 1 Basic setup of a MDI-QKD protocol.|center|0](./1488369826699.png)


### Let us now evaluate the performance of the protocol above in detail.

- (A) Rectilinear basis.

	- We obtain then that $e_{rect}^{n,m}$ is zero for all $n, m$. This means that no error correction is needed for the sifted key.

	- It implies that the usage of WCP sources (rather than single-photon sources) does not substantially lower the key generation rate of the QKD protocol (in the error correction part).

- (B) Diagonal basis.

	-  Assuming again the ideal scenario discussed in the previous paragraph, we find that $e_{diag}^{1,1}=0$.

	-  It means that the usage of WCP sources does not substantially lower the key generation rate (in also the privacy amplification part).

- (C)Key generation rate.

 $$R=Q_{rect}^{1,1}[1-H(e_{diag}^{1,1})]-Q_{rect}f(E_{rect})H(E_{rect})$$

### Security Analysis

- Our security proof is inspired by that of a time reversed EPR-based QKD protocol [1] and the decoy state method [2].

- Alice and Bob post-select only those transmission events where Charles has received some specific Bell state.

- Using decoy states, Alice and Bob can now obtain the gain and QBER of those events where both of them send to Charlie single-photon states.

- In such virtual qubits setting, the protocol is directly equivalent to an entanglement based protocol [6–8]. Alice and Bob share a pair of qubits in their quantum memories and they simply compute the QBER on their virtual qubits in the XX and ZZ bases.

### Some remarks about security proof

-  Indeed, in security proofs such as [6] and [7], losses do not affect security.

- Furthermore, with the above virtual qubit picture in mind, one sees that what Alice and Bob actually send out is unimportant for security proofs as long as their single-photon signals are basis-independent.

-  In the event that there are some basis-dependent flaws in their preparation, Alice and Bob can take care of them by using a quantum coin idea [5, 9].

- Furthermore, our protocol can tolerate very high channel loss and very low success probability of a Bell measurement without compromising its security.

### Some remarks
-  MDI-QKD requires the additional assumption that Alice and Bob have almost perfect state preparation.

-  How to generate indistinguishable photons from two independent laser sources and observe stable HOM interference [17]. 

-  It has a key advantage of removing all detector side channels, and it can double the transmission distance covered with conventional QKD schemes using WCPs. 

## Reference
[Lo2012]: H.-K. Lo, M. Curty and B. Qi, Measurement-Device-Independent Quantum Key Distribution, *Phys. Rev. Lett.* **108**, 130503 (2012).
