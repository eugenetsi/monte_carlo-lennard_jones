# monte_carlo-lennard_jones
Monte Carlo Simulations of a Lennard-Jones System

## The N-body problem

An N-body simulation approximates the motion of particles, often specifically particles that interact with one another through some type of physical forces. Using this broad definition, the types of particles that can be simulated using n-body methods are quite significant, ranging from celestial bodies to individual atoms in a gas cloud.

In this case we focus on the molecular-level n-body simulation of particles and their potential energy based on the Lennard-Jones model.

## The Lennard-Jones model

The Lennard-Jones potential (also termed the LJ potential or 12-6 potential) is an intermolecular pair potential. Among the intermolecular potentials, the Lennard-Jones potential is the potential that has been studied most extensively and most thoroughly. It is considered an archetype model for simple yet realistic intermolecular interactions.

The Lennard-Jones potential models soft repulsive and attractive interactions. Hence, the Lennard-Jones potential describes electronically neutral atoms or molecules. It is named after John Lennard-Jones.

The Lennard-Jones potential is a simplified model that yet describes the essential features of interactions between simple atoms and molecules: Two interacting particles repel each other at very close distance, attract each other at moderate distance, and do not interact at infinite distance. The Lennard-Jones potential is a pair potential, i.e. no three - or multi-body interactions are covered by the potential.

Statistical mechanics and computer simulations can be used to study the Lennard-Jones potential and to obtain thermophysical properties of the 'Lennard-Jones substance'. Both the Lennard-Jones potential and, accordingly, the Lennard-Jones substance are simplified yet realistic models, such as they accurately capture essential physical principles like the presence of a critical and a triple point, condensation and freezing. The Lennard-Jones potential is mathematically simple and is therefore extensively used in studies on matter since the early days of computer simulation. Due to its mathematical simplicity and generic modeling capabilities, the Lennard-Jones potential is probably still the most frequently studied model potential. The Lennard-Jones substance is often even referred to as 'Lennard-Jonesium', suggesting that it is viewed as a chemical element. The Lennard-Jones potential is usually the standard choice for the development of theories for matter (especially soft-matter) as well as for the development and testing of computational methods and algorithms. Upon adjusting the model parameters $\epsilon$ and $\sigma$ to real substance properties, the Lennard-Jones potential can be used to describe simple substance (like noble gases) with good accuracy. Furthermore, the Lennard-Jones potential is often used as a building block in molecular models (a.k.a. force fields) for more complex substances.

## Monte Carlo

The Monte Carlo algorithms play a fundamental role in most kind of simulations, whether they are astrophysical, molecular or financial. From these algorithms we can infer configurations and consequently conformations to hard-to-compute systems.

In this scenario, we specifically use Metropolis Monte Carlo that dictates whether to accept or reject a particle move based on some defined probability. This are based on a Markov chain whose dependence on the predecessor is split into two parts: a proposal and an acceptance of the proposal. The proposals suggest an arbitrary next step in the trajectory of the chain and the acceptance makes sure the appropriate limiting direction is maintained by rejecting unwanted moves of the chain.

Fundamentally, we propose the next step in the Markov chain (a move of a particle) and we accept or reject.

## Implementation

The implementation details are discussed in comments inside the notebook.

## Discussion

From the simulations and results we observe the following:

- Regardless of the parameters tuned, the system settles at a lower energy state.
- As can be seen by the running average plots of potential energy, while this confirms the lower energy state, we can see that the rate changes depending on the parameters. Specifically the rate the energy drops is a lot higher with T = 1, than T = 2.
- We also observe that in every simulation, the resulting particle positions are a lot more “bunched together”. This also can be seen by the final particle distance distributions.
- There was a problem in calculating the distribution of energy, that is why the 4th plot in each simulation looks like this. I could not figure out the cause of this. When printing out the array containing the values, most of them were around zero, but some were much larger, in the order of +-20.
- Another problem I faced, is that sometimes when I ran the simulation the energy remained stable. I checked the acceptance rate of the algorithm and found that it was low, around 5\%, compared to the optimal 30-40\%. I suspect that there might be a problem with my acceptance criterion but could not pinpoint the problem.

## References

- MeshGrid https://stackoverflow.com/questions/53689868/splitting-python-meshgrid-into-cells
- Lennard-Jones https://en.wikipedia.org/wiki/Lennard-Jones\_potential
