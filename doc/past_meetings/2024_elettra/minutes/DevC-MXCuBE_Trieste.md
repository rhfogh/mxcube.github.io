# MXCuBE Developers Committee Minutes

### When:

Friday, November 22nd 2024

### Where:

Trieste (Elettra Synchrotron)

### Present:

P. Focia, LS\_CAT; Andrey Gruzinov, DESY; Marcus Oscarsson, Antonia Beteva, Didier Nurizzo, Yan Walesch, ESRF; Dan Costin, Martin Savko, SOLEIL; Peter Keller, Rasmus Fogh, GPhL; Annie Heroux, ex Elettra; Michael Hellmig, BESSY, Ed Daniel, Icebear; Jean Jakovic; Lais do Carmo, ESS; Alessandro Olivo, Elettra; and others

### Minutes:

* Cybersecurity

The meeting agrees to recommend the use of single sign-on, and reverse proxy, with a three-tier architecture as a longer-term goal (as presented in the talk of Jean-François Perrin).  
The meeting is in favour of having a code review done; this could cost 5-10000 Euro. It is proposed that LS-CAT might be in a position to request a review for free from the US DoE. The meeting is in favour of this, in spite of a minor worry that the acceptance criteria might differ between continents. The meeting is also generally in favour of penetration tests.  
It is requested that LS-CAT make a list of the most important pieces of documentation missing and notable points in general as part of the process of joining MXCuBE.  
The requirement that MXCuBE should run under the ID of the user who is logged in is desirable but is felt to be difficult to achieve.  
The meeting notes and approves that there will be cases where unusual access may be needed at short notice, e.g. for debugging purposes.

* Automation

Unattended data collection is a plus for MXCuBE – and a major reason for interest from LS-CAT \- but it is still not available across all facilities.  It is agreed that there is a need for a clearly defined list of capabilities that a beamline must support (first and foremost automated centering). There is also a need for a standard ‘diffraction plan’ API to define how automation jobs are specified, which keywords must be supported, what is mandatory and what is optional etc. The matter will be discussed further in the MXCuBE Automation Working Group. The group will be chaired by Didier Nurizzo, and those interested (RF and MS volunteering) should join the group on the mxcubecore github.

* YAML configuration

The yaml configuration has been fully implemented and tested at MicroMAX (with thanks to Elmir Jagudin). Testing is planned at the ESRF during the next shutdown. It is agreed to finalise the plans at the next remote developers’ meeting, and to plan a change-over to yaml configuration for the next half-yearly meeting. There is still a need to settle exactly which functions from the temporary XML/YAML implementation should be maintained and which should be purged.

* Any Other Business

\- It is agreed that Python 3.8 (already long out of support) should be dropped soonest. It is still in use at SOLEIL. Martin Savko is willing to upgrade to a newer version but needs to do some tests first. It is suggested to check if the version can be upgraded to a newer version than 3.9, to limit the number of changes required, and to gain access to some newer features.  
\- It was suggested that features like X-ray centring, reading sample resolution estimates from DOZOR, dose budget prediction, and acquisition of crystal size and shape information, could usefully be taken up for inclusion into MXCuBE. These might usefully be discussed in the first instance by the Automation Working Group.  
\- There are working groups also for cybersecurity, sample environment, and testing. Those interested should join the groups on github.
