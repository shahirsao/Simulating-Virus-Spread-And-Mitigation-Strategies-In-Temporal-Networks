# Overview
Despite the pandemic, the UK has been showing a downhill trend in general self-isolation, with people becoming more and more likely to go to work even when they’re unwell (CIPD, 2021). Perhaps the first bastion against the spreading of illness should be our own behaviour and workplace policies, through basic NPIs (non-pharmaceutical interventions).

This paper explores the effects of NPIs by way of simulations performed on real time-respecting contact datasets, as well as the effects of temporal structures and network topology on viral spreading and their relevance to the design and selection of viral interventions. 

The paper found that in the context of COVID-19, self-isolation upon experiencing symptoms alone is ineffective and on its own only gives a 13.6% improvement over doing nothing, assuming a 5 day asymptomatic incubation period (Zaki & Mohamed, 2021). Hybrid scheduling without any self-isolation proved to be extremely effective, decreasing total infections by up to 50.9% with just two WFH (work from home) days per week, with extended non-contact periods showing increased effectiveness over shorter, more distributed ones. Maximum effectiveness is achieved when combining the pair of these interventions, with blanket hybrid working acting as a pre-emptive measure by reducing contacts generally, and targeted self-isolation catching any stragglers with minimal extra lost contacts and achieving an additional 20-30% decrease in peak infection level.

These findings could be used to guide workplace policy on ways to minimise the human and actual cost of illness.

# Task Details
A row of simulation data is given in the format `["timestamp", "person1", "person2"]`. If we consider:
- each individual as falling into the categories of $S$, $I$ or $R$ (Susceptible, Infectious and Recovered)
- each interaction between $S$ and $I$ individuals as having an infection probability $β$
- each timestep as having a recovery probability $μ$ for each $I$ to become $R$

then we are left with a functional epidemiological model following with the SIR framework laid by Kermack and McKendrick (1927). The graph structure of this problem may not be clear at first, however if we consider each individual as a node and each interaction as a link, then the structure becomes clear that this is a network problem with temporally-evolving properties. This allows us to use network metrics such as centrality, radius and transitivity to analyse the problem.

# Data Sources
The temporal contact dataset that has been used is the [InVS15 dataset from Sociopatterns](https://sociopatterns.org/datasets.html), an organization which has been collecting such data and freely releasing much of it for public use since 2008. This data was collected at the Institut de Veille Sanitaire across 2 weeks using wearable RFID badges detecting face-to-face proximity, with a resolution of 20s. There are over 78,000 contacts in the dataset. 


# References
CIPD. (2021). CIPD | Employers urged to address high levels of people working when unwell. [online] Available at: https://www.cipd.org/uk/about/news/employers-urged-address-high-levels-presenteeism/.
Kermack, W.O. and McKendrick, A.G., 1927. A contribution to the mathematical theory of epidemics. Proceedings of the Royal Society A, 115(772), pp.700–721. https://doi.org/10.1098/rspa.1927.0118
Zaki, N. and Mohamed, E.A. (2021). The estimations of the COVID-19 incubation period: A scoping reviews of the literature. Journal of Infection and Public Health, [online] 14(5), pp.638–646. doi: https://doi.org/10.1016/j.jiph.2021.01.019
