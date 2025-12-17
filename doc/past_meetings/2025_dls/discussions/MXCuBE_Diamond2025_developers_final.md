1.  MXCuBE meeting, Diamond, November 19, 2025

    Developers' meeting minutes

# 

# Developers meeting

## Participants

Ezequiel Panepucci (MAX IV)

Annie Heroux (ex-Elettra)

Andrey Gruzinov (DESY)

Pawel Mocko (S2 Innovation)

Martin Savko (SOLEIL)

Yan Walesch, Antonia Beteva, Alex de Maria, Marcus Oscarsson (ESRF)

Clemens Vonrhein, Rasmus Fogh, Peter Keller (Global Phasing)

Alessandro Olivo (Elettra)

Michel Hellmig (HZB)

Pedro Benetton (LNLS)

Michal Gucwa (Solaris)

## 

## Abstract Diffractometer

The new abstract diffractometer hardware object has been cleaned up, and
non-diffractometer functionality has been put into SampleView. The
latter still needs refactoring. There is now a standard coordinate
system for specifying axes, fixed motor names, fixed phase names, and a
separation between existing and movable motors. **ACTION PK** check if
there is a standard coordinate definition (e.g. McSTAS) that we should
consider adopting instead of the current ESRF-standard one. The current
PR should be checked quickly, as the plan is to finish testing and merge
the AbstractDiffractometer ASAP; preferably Jan/Feb 2026

## Cybersecurity

The ESRF report summary on their cybersecurity inspection has been
received. There are no major weaknesses to fix. One outstanding change
proposal is to replace the XMLRPC module (which is not used outside the
ESRF). Replacement could be a different RPC system; GPhL would be
interested in having a messaging system like e.g. ActiveMQ, since
messaging is anyway needed for the GPhL workflow. A REST-based system
was also proposed, which would fill the need but came with some
technical problems.

## Configuration repository

It was agreed to have a separate location for configuring tests -- this
is already in place in the code. It was also agreed to move to having
the demo/mock configuration in the mxcube_configuration repository, the
main argument being that this avoided having to maintain separate mock
configuration repos for the web and qt branches. It is necessary to make
some changes in the Web version deployment to support this change
(**ACTION: MO**), after which the move will be made.

## Pydantic models for configuration

It was agreed that this should be introduced soon, after the change to
the new configuration repo, and that it would be a good topic for the
code camp.

Under this heading it was further agreed that it should be possible to
specify that a given configuration parameter should be read from an
environment variable (even though this could be seen as a duplicate
configuration mechanism). The clinching argument was that certain
configuration parameters having to do with access control could not, for
security reasons, live in

a configuration file. PB would make a PR to start the discussion
(**ACTION PB**). One proposal was to have env-read parameters start with
\'*.env://*\')

## Code camp

It was agreed to have a day and a half for the code camp, and to prefer
it at the start of the meeting.

Potential topics were Pydantic configuration and X-ray
centring/processing. There was no enthusiasm for taking up linting as a
topic.

An important topic proposed was to give an introduction for newcomers to
MXCuBE, with detailed description and probably flow diagrams of key
processes like acquisition, the workings fo the queue, centring, ...
This would be particularly useful for recent newcomers (e.g. at MAX IV),
and new members from the US, Korea, and Poland. **ACTION PB**, to make
an issue showcasing the work he has already done on flow diagrams.
