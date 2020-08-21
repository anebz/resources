# Fundamentals of neuroscience: edX courses

* [Course 1: the Electrical Properties of the Neuron](#course-1-the-electrical-properties-of-the-neuron)
    - [Lesson 1: the resting potential](#lesson-1-the-resting-potential)
    - [Lesson 2: passive membrane properties](#lesson-2-passive-membrane-properties)
    - [Lesson 3: the action potential](#lesson-3-the-action-potential)
    - [Lesson 4: action potential propagation](#lesson-4-action-potential-propagation)
* [Course 2: Neurons and Networks](#course-2-neurons-and-networks)
    - [Lesson 1: the synapse](#lesson-1-the-synapse)
    - [Lesson 2: excitation and inhibition](#lesson-2-excitation-and-inhibition)
    - [Lesson 3: small circuits](#lesson-3-small-circuits)
    - [Lesson 4: neuromodulation](#lesson-4-neuromodulation)
    - [Lesson 5: neuronal plasticity](#lesson-5-neuronal-plasticity)
* [Course 3: The brain](#course-3-the-brain)
    - [Lesson 1: vision](#lesson-1-vision)
    - [Lesson 2: audition](#lesson-2-audition)
    - Lesson 3: smell, taste and the remaining senses
    - [Lesson 4: movement & action](#lesson-4-movement-and-action)
    - [Lesson 5: subcortical brain areas](#lesson-5-subcortical-brain-areas)

## [Course 1 the Electrical Properties of the Neuron](https://www.edx.org/course/fundamentals-of-neuroscience-part-1-the-electrical)

[Formula sheet](https://courses.edx.org/assets/courseware/v1/71475402bce93432b9b909b9180885c1/asset-v1:HarvardX+MCB80.1x+3T2019+type@asset+block/Ref_Sheet_ln_def.pdf)

### Lesson 1 The resting potential

* *Being at rest*: when a neuron doesn't send or receive signals. A cell being at rest doesn't mean it's electrically neutral. The ground is the outside of the cell, so the inside has negative voltage.
    - *Resting potential*: the membrane potential of a neuron that is specifically "at rest" is generally between -60 mV and -70 mV
* *Cell membrane*: In the dendrites, the outer surface is made of a bilayer of lipid molecules that partition the inside of the cell from the outside
* *Membrane potential*: this is a general term that describes the voltage across the membrane **at any point in time**. It always exists -90 mV to +60 mV
* Ions present in cells: Sodium, potassium, calcium and chloride

#### Diffusion and electrostatics forces

* Diffusion: the effect when particles move from places of high concentration to regions of low concentration.
* Electrostatic force: particles have a charge associated to them, positive or positive. Opposites attract, and similar forces repel

#### Potentials and equilibrium

Without channels, each side of the membrane is electroneutral, there is no net charge. For every positive charge on the inside or outside, there's a negative charge to balance it out. And no voltage, no electric field.

With channels, positive ions travel outside the neuron, leaving an excess of negative ones and an excess of positive ions at the outside. The inside will be more negative relative to the outside.

The membrane potential comes from a tiny imbalance that accumulates very close to the membrane --> creates an electric field --> electrical potential --> capacitor.

When ions start moving down the concentration gradient from in to out following **diffusion**, there's an **electrostatic** force that prevents more positive changes from diffusing out.

Only a very tiny proportion of ions move in and out of the cell and create the membrane potential, we can ignore the amount.

The electrostatic force for transporting a tiny fraction of charged particles to the other side of the membrane is enough to balance out the diffusion of a large number of particles. **Electrostatic force is much stronger than the diffusion force.**

*Equilibrium potential*: when diffusion and potential electrical forces balance each other out for a specific ion.

#### Nernst potential

The Nernst potential is the equilibrium potential for a single ion.

> E<sub>ion</sub> = (RT/zF) * ln(ion\_extracellular / ion\_intracellular).

z is the valence, the net charge of the ion. Na, K are +1. Cl is -1, Ca is +2.

*Driving force*: how hard a given ion is getting pushed across the membrane.

> E<sub>driving_force</sub> = E<sub>membrane</sub> - E<sub>ion</sub>

Calcium has a very high Nernst potential, 123mV, and the membrane potential at rest is the resting potential, -70mV. So Calcium will have a very strong driving force to move inside the cell. To bring this -70mV number closer to 123mV.

Ions will always flow in a direction that brings the current membrane potential closer to that ion’s own Nernst potential.

* *Depolarization*: positive change in the membrane potential, a change to a less negative membrane potential
* *Hyperpolarization*: negative change in the membrane potential

#### The GHK equation

The GHK equation calculates the resting potential for *a whole cell* in a more realistic way than the Nernst potential for all ions, by doing relative weighting of the major ions and taking permeability into account.

> Equilibrium != steady state

* In the Nernst potential, that ion will be at an *equilibrium*; the net flow of this ion into and out of the neuron will be equal and opposite, and there is no net flow of the ion in either direction.
* In a resting neuron, many ions are flowing across the membrane trying to reach their own equilibrium simultaneously. There are a balancing point at which the membrane potential will be *stable*. At this balancing point, no single ion will be at its own equilibrium but the total net flow of all charges into and out of the cell will be equal and opposite.

-----------------

**Permeability**: the ease with which ions can pass through the membrane and through the lipid bilayer. High --> pass easily, more channels, or permeable channels.

* Na+ has a positive Nernst potential and thus experiences a strong inward driving force, but it has low permeability at rest.
* K+ has higher permeability. The resting potential will be much closer to K+'s Nernst potential than to Na+'s Nernst potential, because K+ ions move more.

-----------------

* *Threshold voltage*: target membarne potential, -55mV, when the neuron fires an action potential to communicate with other neurons.
* To change the membrane potential fast, increase the permeability of Na+ rather than to drastically alter the concentrations of K+ ions.

#### Ion filters via selectivity filter

How does nature achieve permeability? K+ and Na+ have slightly different sizes (116pm vs. 152pm respectively).

* *Solvation shell*: Water H2O is net neutral but has polarity, the oxygen part is more negative and the hydrogen parts more positive. When soaked in water, the oxygen parts of water will be closer to Na+, thus creating a shell of water molecules surrounding the Na+.

* Different configurations: everything at a molecular level is about driving towards the lowest energy configuration. Depending on the size, ions have different configurations/spacings.

------------------

* *Selectivity filter*: the channel has a mechanism in front of its pore simulating the spacing of the solvation shell in a fixed cofiguration for its ion of interest.

The K+ can diffuse through the simulated shell, but this spacing is slightly off for the Na+ ions, making it energetically unfavorable for it to go through.

The Na+ also wants to get inside the cell, to diffuse down its concentration gradient and to move down the electrical gradient. Eventually many Na+ ions will get in, and we'll have equilibrium. But we don't want that.

* *The Na+/K+ pump uses ATP*: continually moves 3Na+ ions out of the cell, every 2K+ ions it pumps, by using ATP, a key energy carrying molecule to maintain the electrical gradient in neurons.

The transport of Na+ out and K+ in consumes up to 70% of the ATP required for overall brain function, and just to maintain an electrical gradient.

------------------

### Lesson 2 Passive membrane properties

How fast is the potential able to change given just the membrane?

#### Resistance

The opposition of the current through it.

Each channel has its own resistance. The more permeable, the lower the resistance. The more channels in the membrane, the lower the resistance. *Axial resistance*: the saltier and bigger diameter the axon, the lower resistance. Capacitors can store electrical charge, it's 2 conductors separated by an insulated region called *dialectric*. 

The capacitor charges up until the conductors are saturated, at which point the voltage across capacitor = applied voltage. Then, the capacitor slowly discharges going back to the original voltage. the capacitor slows down the charge.

Neuronal membrane ~~ capacitor. The two conductors are the intra and extracellular areas, and the insulated region is the thickness of the membrane.

* To decrease the capacitance, increase the thickness of the membrane. The charges are more separated so there's less ability to accumulate charge.
* If the material between the conductors has a high dielectric constant, more capacitance.
* Also, decreasing the diameter of the axon decreases the overall surface area. Less space over which charge can build up, less capacitance.
* To alter the capacitance of the membrane, some axons wrap more layers of membrane around the axon in a process called myelination.

More electrical concepts

* *Ohm's law*: I = V/R. The membrane acts as capacitors, and channels act like resistors. There's also a resistance in the axon itself, axial resistance.
* *Length constant*: the distance it takes for a potential change to fall of to ~36% of its initial value.
    * &lambda; = sqrt(R<sub>membrane</sub> / R<sub>axial</sub>).
* *Time constant*: how long it takes a piece of membrane to charge up to 63% of its final value in response to a step change in its input voltage.
    * Time constant &tau; = R<sub>mem</sub> * C<sub>mem</sub>
* &lambda; and &tau; are related based on R<sub>mem</sub> and linearly dependent, but there are other factors in play.

For a normal &lambda; of 1mm, it'd take 330V to send a signal through 1cm just using passive properties. We need something else.

> End voltage = Initial voltage * 0.37 ^ (length / &lambda;)

**The capacitance only begins to exert its effects when the membrane voltage changes in time**. 

* Decreasing the membrane capacitance makes the membrane snappier and more responsive to change.

A lower membrane resistance means a lower time constant and a more quickly changing membrane. Because less resistance, the current can flow more easily.

The arrangement in the RC (resistor capacitor) circuit in the axon is a low pass filter. It allows low frequencies, slow variations to pass and blocks high frequency.

### Lesson 3 The action potential

* The action potential is a rapid change of membrane voltage.
* The channels up until now are leakage channels, they have constant permeability and constant resistance. They're static.
* **Voltage gated channels** change in response to their local environment, opening/closing depending on the local membrane potential.

#### The phases of the action potential

Voltage-gated Na+ channels are more likely to be open when the membrane potential is more positive, they're closed when the cell is at its resting potential.

A neuron can be stimulated by transiently and locally raising the membrane potential. It takes a while to the membrane potential to catch up to the new current because of the capacitance.

If there's an increase in the membrane potential, there's a positive feedback loop.

1. voltage-gated Na+ channels open
2. Na+ increases its conductivity and current
3. The membrane potential gets higher
4. At ~55mV, dramatic increase in the Na+ conductance. Point of no return
5. At positive voltage, the channel gets inactivated slowly and the membrane potential goes back down. Na+ current stops
6. This is very slow, so the opening of the vg K+ channels make it go down faster.
7. Vg K+ channels also open with positive membrane potential, but much slower
8. K+ current increases
9. Membrane potential gets back to even lower voltage than the resting potential for a while
10. As they slowly close, the cell returns to resting state

Action potential shape

![ ](https://courses.edx.org/assets/courseware/v1/459829fa6ebc8ee24ab08c133f4876b4/asset-v1:HarvardX+MCB80.1x+3T2019+type@asset+block/ap_phases.png)

#### Channels and probability

* For reversible reactions, both forward and reverse reactions occur sometimes, depending on their relative probability.
* The probability of voltage-gated channels being open or close depends on the voltage.

#### Channel kinetics

Channels with fast kinetics can move fast between states. Na+ has fast kinetics for activation and deactivation, but slow for inactivation. K+ has slow for everything.

* Absolute refractory period: driven by the inactivation kinetics of the voltage-gated Na+ channels. While those channels are stuck in the inactive state, there's no way to initiate another action potential
* Relative refractory period: the vg Na+ channels are active, but the vg K+ channels are still open. With a big enough stimulus, bigger than in the beginning phase because now we're undershooting, we can start another action potential.

### Lesson 4 Action potential propagation

Some of the signal energy gets lost because of the leakage of current out of the cell through channels, and capacitive effects across the membrane.

* The neuron is close to the breakdown voltage, where the lipid bilayer stops acting as an insulator. So we can't send high amplitude signals.
* Another option is *regeneration*. Instead of moving molecules, move the state of depolarization down the axon. Without any molecule or ion movement.

An action potential in one patch of membrane depolarizes the next region, which in turn fires an action potential, creating a chain reaction.

* It's difficult to stimulate an action potential in the hyperpolarization phase, the refractory period where the vgNa+ channels are inactivated and the vgK+ channels are open. When the vgNa+ channels are inactivated, it's impossible to trigger another action potential: *absolute refractory period*.
* *Relative refractory period*: Na+ channels are active again but still fighting against the extra open K+ channels.

If instead of stimulating one end of the axon you stimulate the middle, the signal propagates in both directions. 2 action potentials.

If there are 2 action potentials coming from both sides, even if there's extra depolarization, the vgNa+ channels can't react because they're in the absolute refractory period. So action potentials collide and stop.

If you stimulate a neuron at its origin and at another location where you think the signal is going, if you receive nothing at the location, 2 propagating action potentials traveled on the same axon and collided. This way it's possible to know where signals go.

#### Speeding up the action potential

* Reducing the resistance and the capacitance of the membrane makes the signal travel faster.
* a lower membrane capacitance means the membrane voltage changes more quickly (since the time constant is smaller).

Evolution can control the axial resistance by varying the diameter/caliber of the axon. Larger diameter -> more area for current to flow through. But making the axon larger is expensive, you need more space, more energy to maintain the resting potential, more vgNa+ channels.

> How can we dramatically change the resistance and capacitance of the axon without making it much larger?

*Myelin*: an insulating segmented covering of the axon. It's a physical barrier to ion leakage, increasing membrane resistance and lowering membrane capacitance because it makes the membrane thicker. Myelin is primarily made up of lipids, giving it its characteristic white appearance and the reason why the white matter in the brain is white.

But if we have the barrier, how do ion channels still work? *Segmentation*. Myelinated axons look like a string of sausages, and in the spacing between them there's a high concentration of vgNa+ and K+ channels. These open areas are called *nodes of Ranvier*. In these nodes, the action potential gets boosted again.

There's not much to be done in the membrane capacitance in terms of its dielectric material (lipid bilayer). But its thickness can be altered, increasing the separation between the conductors and thereby lowering the capacitance.

* The length constant is increased, more current is able to flow down the axon with less of it being diverted along unproductive paths.
* And the time constant is reduced, speeding up changes in the membrane potential.
* The current does a saltatory conduction, the action potential jumps from one node to another.

If the myelin is damaged, the action potential is stopped. The length constant of the previously myelinated axion is shortened. In the multiple sclerosis disease, signals can't travel down the axons so well. The result is gradual debilitating paralysis.

---------------------------

## [Course 2 Neurons and networks](https://www.edx.org/course/fundamentals-of-neuroscience-part-2-neurons-and-ne)

### Lesson 1 The Synapse

Synapses are junctions between an axon(output) and a dendrite(input), and they allow information to pass from one neuron to another. 2 types of synapses:

* **Electrical**: pores between two cells that allow ions to pass through. Fast and with a high degree of synchronicity, allows bidirectional signaling.
* **Chemical**: the action potential through the axon causes a chemical to be released into a very small space between the two neurons called *synaptic cleft*. This chemical is taken up by the downstream neuron on the other side of the cleft. It's slower than electrical but it allows more variety of signals to be sent.

The synaptic cleft is very small, because the signaling molecules must traverse this gap by diffusion. An action potential in the chemical synapse doesn't guarantee a spike in the postsynaptic cell. Some neurons require a summation of signals across time and space to reach the threshold for the spike.

* *Neurotransmitters*: chemical signals that increase or decrease the neuron's likelihood of firing.
* *Neuromodulators*: serotonin, dopamine, adrenaline can have more complicated longer-term effects in neuronal circuits. They modulate the activity of neurons. They bind to metabotropic, G-protein coupled receptors (GPCRs) to initiate a second messenger signaling cascade that induces a broad, long-lasting signal.

Synaptic transition:

1. An action potential travels down the axon to the synapse
2. This triggers a release of pre-made neurotransmitters or neuromodulators into the synaptic cleft. These molecules are packaged into structures called **vesicles**
3. With the action potential, these vesicles fuse to the membrane and become part of it, releasing their payload into the synaptic cleft.
4. The molecules diffuse across the cleft and bind to receptors on the other side.
5. A receptor binds to a very specific molecule or class of molecules.

Some receptors are ion channels in themselves, called *ionotropic receptors*. Other receptors, *metabrotopic receptors*, set off molecular cascades within the cell.

When the depolarization arrives at the terminal (end of presynaptic neuron), it opens vgNa+ channels and the strong driving force inward of Na+ quickly increases the intracellular Na+ concentration --> the probability of neurotransmitter release is higher --> the neurotransmitters are packaged into vesicles that contain hundreds of molecules, released all at once.

#### The presynaptic terminal

Katz explored the neuromuscular junction (NMJ), which contains the end of a motor neuron and a muscle cell. The primary neurotransmitter is Acetylcholine. Different types of postsynaptic potentials:

* Excitatory, EPSP, the received signal makes the neuron more likely to fire
* Inhibitory, IPSP, the opposite

The nerves touching the muscle fibers form flat structures called *end plates*, and their potentials are end plate potentials, *EPP*s. Katz noticed that between stimuli, there were small blips/mini EPPs/minis in the postsynaptic potentials. These blips come from the cell itself. There's some chance that neurotransmitters will still be released without any stimulation. Drugs like Curare or Neostigmine can block or enhance these blips.

* Curare blocks acetylcholine receptors and prevents acetylcholine from activating the postsynaptic receptors. The EPPs disappear completely
* Neostigmine blocks the enzyme that breaks down acetylcholine. So a dose of acetylcholine has a stronger effect. The EPPs increase in amplitude and duration

Katz found out that the EPP amplitude is proportional to the calcium's concentration ^ 4. And it only has an effect exactly before the presynaptic potential.

**Calcium** is very important for cell signaling, and the intracellular concentration is tightly controlled. Under very low Ca+ concentrations, the stimulated EPPs are the same size as the minis, or double the amplitude, or 3x, or 4x. Or sometimes, no EPP.

Katz hypothesized that instead of molecules being released individually, they're released in packages of approximately fixed number. Neurotransmitter release is a quantized process, they're released in discrete quanta or groups. The minis represent just the release of just one of these putative packages, which we know now that these are *vesicles*.

> How can we visualize these vesicles?

Electron microscopes were used instead of light microscopes to see smaller objects. Scientists found *omega bodies*, named for the shape of the vesicles that formed when they fused with the membrane of the presynaptic terminal and released chemical payload into the synaptic cleft.

> How does Ca+ cause the fusion of vesicles to the presynaptic membrane?

Vesicle fusion in a synapse is catalyzed by the interaction of a vesicle associated SNARE protein, or v-SNARE, with other SNARE proteins on the membrane, target SNAREs or t-SNAREs. Calcium modulates the interactions between the SNARE proteins on the vesicle and the presynaptic membrane.

Ramón y Cajal proposed the neuron theory: each cell of the brain has its own set of branches, which means information through the brain has to jump from one neuron to the next.

### Lesson 2 excitation and inhibition

* Fast excitatory postsynaptic potentials are mediated by *cation* selective ion channels in the postsynaptic neuron.
* Fast inhibitory postsynaptic potentials are mediated by *anion* selective ion channels.

Metabolic receptors like GPCRs sense a neurotransmitter and activate specific signal transduction pathways that ultimately change ion permeability inside the cell.

Once released, a neurotransmitter molecule has 5 fates.

1. It can travel across the synaptic cleft and bind to its receptor on the other side.
    * The goal of synaptic transmission is not only to transmit info, but to transmit it exactly at and only at a specific time.
    * If a neurotransmitter stays for long in the cleft, it could bind and unbind its receptor many times and activate the postsynaptic cell many times.
    * A mechanism is needed to shut off neurotransmitter action in the synaptic cleft before simply diffusing away
2. After binding, the entire neurotransmitter and its protein can be resorbed into the post- cell
3. Neurotransmitters can be broken down by enzymes
4. Neurotransmitters might be taken up by transporter proteins from the glial cells, which surround and even sometimes invade the synaptic cleft.
5. Combinations of the above

Inhibitory synapses can:

* open chloride channels
* open potassium channels
* block calcium channels

It also depends when the synapse happens, in the dendrite or in the cell body directly. Whether a neuron fires depends on the synapses' frequency, timing and strength.

#### EPSPs

For EPSPs, because the signal is strong and fast, it needs to have a high spatial specificity. Generally, no single EPSP makes the post neuron fire. Many EPSPs have to sum up to generate an action potential.

*Desensitization*: analogous to the inactivation of vgNa+ channels, if receptor channels are open for a long time due to the repeated action of neurotransmitters binding and unbinding from the channel, individual channels will close.

In the central nervous system, excitatory postsynaptic potentials are largely due to the action of Glutamate. If there's one main neurotransmitter, how do we achieve the specifity of neural transmissions?

There are many types of postsynaptic glutamate receptors: ionotropic (ion channels) receptors, and metabotropic receptors, which change the metabolic and biochemical pathways acting indirectly through G protein coupled receptors / GPCRs.

The glutamate ionotropic receptors are divided into AMPA and NMDA receptors.

* AMPA receptors are promiscuous ion channels, permeable to all cations
* A certain cation only binds to NMDA. When at rest, NMDA has a magnesium ion blocking its central pore. The magnesium - NMDA interaction is voltage-dependent. The receptor needs an initial depolarization to have a chance to open. This is usually brought by the opening of AMPA receptors, so NMDA receptors work as "coincidence detectors"

#### IPSPs

IPSPs are slow and weak. GABA are the primary IPSP-generating receptors in the brain. Glycine receptors are the primary IPSP-generating receptors in the spinal chord. Both of them are anion-selective ion channels, causing an increase in chloride conductance. The influx of chloride forces the postsynaptic neuron to stay close to the equilibrium potential of chloride, -65mV, very close to the neuronal resting potential, -70mV.

*Shunting*: the negatively charged chloride influx can counterbalance the positively charged sodium influx or excitatory synapses, resulting in a stop signal.

### Lesson 3 small circuits

Excitatory input is thought to occur mainly on dendritic spines, while inhibitory input tends to occur on dendritic shafts, the cell body, and on the axon initial segment. There are 5 critical factors that regulate the interaction of synaptic inputs and their ability to initiate an action potential

1. Distance
2. Non-linear summation
    * Driving force of each ion. Sub-linear additivity of EPSPs
    * Dendritic action potentials
    * Action potential backpropagation
        - The action potential current from the soma also goes back to the dendritic arbor
3. Inhibitory input blocking excitatory input
    * Only in the dendrite it's in, or if the inhibitory input is in the soma, then it has a global reach and cancel all EPSPs.
4. Temporal summation
    * The second EPSP piggybacks onto the falling phase of a previous EPSP when the neuron is still depolarized
5. Inhibitory input blocking temporal summation

#### Convergence and divergence

3 principles of neuronal network organization: convergence, divergence, recurrence.

* *Convergence*: when multiple potentially disparate inputs come together to synapse on a single downstream neuron.
* *Divergence*: one neuron sends a signal to many

In the stretch/myotatic/tap reflex, when someone taps your knee, pure convergence and divergence are observed.

* *Recurrence*/feedback: a chain of connected neurons loops back onto itself
    - The central pattern generator, CPG relies on this. they can producte rythmic patterned outputs, even without sensory input. there's a delay between the activation of the neurons.

### Lesson 4 Neuromodulation

It's the process by which the synaptic transmission between 2 neurons is either enhanced or decreased through the action of a third substance, neuromodulator.

Neuromodulators are other neurotransmitters or small molecules released by a third neuron, making a synapse with per- or postsynaptic neuron. Mechanistically, most neuromodulators act through GPCRs. This is a metabotropic family, there are many types.

Synaptic transmission and neuromodulation have some similarities but they are distinct processes.

The vast majority of changes in synaptic strength aren't structural (like development in early age or degenerative disorders in late age), but induced by changing synaptic strength: *efficacy*, the structure of the synapses involved remains unchanged.

The main advantage of GPCRs over ionotropic receptors is their versatility + the fact that a few molecules of neurotransmitter binding to the receptor outside the cell, can exert a large amplified inside. GPCRs can have multiple, opposing effects on a single target. Also, it can influence many targets at once.

#### The serotonin system

This system is one of the major neuromodulatory system of our brains, it's involved in many physiological processes like hunger, sleep, and mood. Because it affects mood, serotonin is the target of most antidepressive drugs. Serotonin is released in a particular part of the brain called dorsal raphe nucleus, but its receptors can be found in many other parts.

#### Neuropeptides

Another class of neuromodulators, neuropeptides are proteins, much larger than classical neurotransmitters. Neuropeptides act exclusively through GPCRs. There are over 100 peptide varieties, like opioids, and they affect sleep, appetite, and pain sensation. The activation of opioid receptors modulate pain perception, it reduces our perception of pain.

#### The dopamine system

It's released by only a few hundred thosuand neurons, but they project over almosst the entire brain. This system modulates modalities like motor control, arousal, motivation, and reward.

Dopamine pathways die in Parkinson's desease, so the target of medicine is to try and supplement dopamine. The l-dopa drug can have dramatic effects but l-dopa becomes gradually less effective.

Cocaine blocks the reuptake of dopamine from the synacptic cleft, increasing the time this neurotransmitter spends there and increasing the likelihood of inserting a postsynaptic action. Cocaine turns up the effect of the dopaminergic system.

#### The cholinergic system

Acetylcholine is the main excitatory neurotransmitter, but also a crucial neuromodulator. This system affets muscle and motor control, learning, short-term memory, general arousal.

#### The noradrenaline system

This is released by very specialized cells in the lateral segmental field, but receptors are found in many parts of the brain and peripheral nervous system. It modulates general arousal, fight/flight response, and the activation of the reward system.

### Lesson 5 neuronal plasticity

Neuronal circuits are constantly changing and adapting to the environment. Plasticity allows us to adapt to a changing world on a faster timescale than evolution.

#### Short-term plasticity and adaptation

* short-term strengthening of synaptic connections, synaptic enhancement/facilitation. a higher probability of the presynaptic neuron releasing neurotransmitters, by an increase of EPSP.
* short-term weakening of connections, synaptic depression/fatigue. there's a depletion of readily releasable neurotransmitter.

If we want to store information in the long-term, we need mechanisms that alter synapses in a stable way and lasts for a long time.

* LTP, long-term potentiation
* LTD, long-term depression

> How does the brain choose to make synapses stronger or weaker? How do our behavior and our environment cause synaptic plasticity? 

**Hebb's rule** in 1949 said: when an axon cell A is near enough to excite a cell B and repeatedly or persistently takes part in firing it, some growth or process of metabolic change takes place in one or both cells such that A's efficacy as one of the cells firing B is increased.

* Neurons that fire together, wire together
* Neurons that fire out of sync, lose their link

#### LTP

To make LTP stronger, we either can release more neurotransmitter, increase the \#receptors on the postsynaptic neuron, or make these receptors have a bigger effect. LTP can be Hebbian (NMDA receptor-dependent LTP) or non-Hebbian. In the anti-Hebbian case, the more two neurons connect together, the more the connection is decreased.

When NMDA opens, it lets cations especially calcium get through. but it's not easy to open it all the way, it needs two ligands to open it. Both glutamate and glycine must bind to the channel to open it. The NMDA receptor is both ligand-gated and voltage-gated. To fully open it, we must fully depolarize the membrane and activate the channel with neurotransmitters. 

NMDA dependent LTP has these characteristics:

* input specificity
* associativity
* cooperativity
* persistence

#### LTD

The physiological and biochemical mechanisms of LTD vary depending upon brain regions and developmental stages, and they occur in different types of neurons releasing various neurotransmitters.

Like in LTP, the most common neurotransmitter involved in LTD is glutamate, whose receptors include NMDA, AMPA and metabotropic glutamate receptors.

* In the cerebellum, LTD results from strong synaptic stimulation
* In the hippocampus, LTD is induced by persistent weak synaptic stimulation

Mechanistically, LTD occurs due to the degradation of postsynaptic receptors, decrease in receptor density and deactivation of AMPA receptors.

#### STDP

Spie timing-dependent plasticity. Presynaptic spikes arriving just a few tens of ms before the postsynaptic spike result in potentiation, and spikes arriving just a few ms after postsynaptic spike result in depression of the synapse.

STDP exists to reinforce causal firing relationships. If the presynaptic spike arrives after the postsynaptic one, that spike couldn't have caused the postsynaptic spike. and we don't want to reinforce behaviour just because two neurons happen to fire close together in time.

#### Nonsynaptic plasticity

There are non-synaptic mechanisms of plasticity. This includes modification of the ion channel function in the dendrites, soma or axon. Homeostatic mechanisms keep the excitability of the neuron in a desirable operating range, if a neuron fires too much it could damage itself or the network. if it fires too little, it doesn't participate in the network and wastes resources.

----------------------------

## [Course 3 the brain](https://courses.edx.org/courses/course-v1:HarvardX+MCB80.3x+3T2019/)

### Lesson 1 Vision

Light comes through our retina, optic nerve, thalamus in the brain and visual cortex. The information flow in the visual cortex is both sequential and parallel.

Thre are 2 photoreceptors:

* rods: detect low light levels. The proportion to cones is 20:1
* cones: detect higher light levels, color, can see changes
    - s cones, detect blue light
    - m cones, green light
    - l cones, red light

Photoreceptors convert signals from electromagnetic, to chemical, to electrical in a sequential cascade: *phototransduction*. Rather than reacting to a chemical ligand, photoreceptors can react to electromagnetic energy in the form of photons. When it's dark, ion channels open and the photoreceptor gets depolarized. And vice versa when ther's light. Neurotransmitters are released during dark and stopped when illuminated. Because of amplification, our visual system can detect as little as a single photon.

> How does the retina generate a visual image?

The retina is organized into 3 cellular layers: photoreception (rods, cones), internal transmission(bipolar, horizontal and amacrine cells), output (retinal ganglion cells).

#### Thalamus and visual cortex

The lateral geniculate nucleus LGN is located in the dorsal lateral part of the thalamus, which is itself located between the cortex and the mid-brain. The LGN in the left hemisphere processes input from the right visual field. From the LGN, information continues via the optic radiations to the visual cortex, located at the very back of the brain in humans.

There are 2 pathways in the visual cortex, ventral pathway and dorsal pathway

* Ventral pathway: focuses on what an object is, the deeper we get into the pathway the bigger the receptive field size is and the more we can generalize to what the object is
    - If this is damaged, you can get localized blind spots (scotoma), or if the lesion is deep in the pathway you can stop recognizing faces (agnosia)
* Dorsal pathway: focuses on where and how the object is, movement direction.
    - If there are lesions here, you stop seeing motion and the world looks like a disjoint version of it.

### Lesions in the visual cortex

* Experimentally-induced lesions, done in animals. Can be permanent, where brain tissue is either suctioned out or chemically damaged, or temporary, induced by the injection of drugs, or optogenetics
* Observed lesions in humans: can arise due to
    - disease
    - stroke
    - injury: concussions, or firearms

*The binding problem*: how do we join the pathways afterwards? How to merge the parallelization? There is no answer, a solution is that synchronous firing across different areas binds or tags these different properties of an object together as one unified whole. But many neuroscientists disagree with this.

### Lesson 2 audition

Signals from the hair cells in each ear's cochlea are sent through the spiral ganglion cells and auditory nerves to a sequence of nuclei in the brainstem before eventually reaching the midbrain, thalamus and the auditory cortex.

There's a tonotopic map at the cochlear nucleus called tonotopy, it's the spatial organization of neural responses to sound according to frequency. The auditory signals from both ears are first integrated in the superior olive.

The auditory cortex is more resilient to lesions than the visual cortex due to the fact that both ears send inputs to both sides of the auditory cortex. Unilateral lesions in the auditory system have a less disruptive effect on hearing, because both ears send signals to cortical areas in both hemispheres.

> How to localize sounds

* Interaural time differences, ITDs
    - sound arrives slightly late to one ear, depending on where it's coming from
* For high frequency sounds, interaural level differences, ILDs
    - propagation distance, reflection/absorption
* But still, we wouldn't be able to tell apart sounds coming from front/back, or above/below. To overcome this symmetry, the odd shape of the outer ear helps with that. we can determine the elevation of a sound, even with just 2 ears.

### Lesson 4 movement and action

Central pattern generators CPGs are recurrent neural circuits that produce rythmic outputs without being driven by external stimuli. These circuits exist in the spinal cord, without needing any input from the brain. But external sensory cues can modulate the activity of CPGs.

### Lesson 5 subcortical brain areas

#### The hindbrain

It's at the bottom of the brain in humans, it's a collection of structures responsible for many of our anatomical functions. It consists of: medulla, pons and midbrain, and the cerebellum. It controls essential functions like breathing, coughing and heart rate.

The **medulla** connects to higher brain, controls posture, protective motor reflexes like vomiting, coughing, sneezing, swallowing. It regulates breathing, heart rate, blood pressure, digestion. The medulla can override cortical signals entirely.

The **pons** is a relay station, bridging the gap between the medulla, cortex and the cerebellum. It controls sleep, respiration, swallowing, chewing, bladder control, eye movements, facial expressions, upright posture.

These structures are so crucial that it's not simple to find disorders of the brain stem, because most injuries here result in instant death.

#### The midbrain

Located above the hindbrain, below the forebrain. It controls vision, hearing and motor control, sleep/wake cycle, alertness, temperature regulation.

#### The cerebellum

It plays a key role in motor programming but doesn't generate motor activity itself. It's a facilitator for motor learning and language. It accounts for 10% of the brain's volume but it containst 50%> of the brain's total neurons.

#### The basal ganglia

It's involved in voluntary movement, and learning and execution of actions that become automatic. It also plays a role in emotional and cognitive functions. It doesn't initiate voluntary motor movements, but it provides modulatory guidance.

#### The thalamus

It's the hub or relay station of the brain, making reciprocal connections between both higher and lower brain areas. It also does sensory processing

#### The amygdala

It's mostly involved in emotional memory, fear, pleasure, memory, making decisions based on emotions and memory.

#### The hippocampus

It's involved in declarative memory, the recall of stored facts and experiences. It consolidates short term memories into long term memories. Without the hippocampus, we can't form any new memories for facts or events, we can only remember past events. But if the basal ganglia are intact, we can still learn new procedural tasks

The hippocampus also plays a role in spatial navigation. And it's one of the few places where neurogenesis, the birth and migration of new neurons occurs in the adult brain.

#### The hypothalamus

It coordinates the body's autonomic response to information conveyed through limbic structures, like the amygdala, and higher structures like cortex. It takes in information about heart rate, plasma-sodium concentration, and temperature. It coordinates corrective behavior to restore physiological set points. If physiological aspects are too far away from the mean, it pushes you to eat, drink, sleep. If it's injured, it can lead to hypotermia, obesity.
