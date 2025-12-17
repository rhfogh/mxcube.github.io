1.  MXCuBE meeting, Diamond, November 20, 2025

    Discussions

Discussions were not divided as neatly into subtopics as were the talks,
and some discussion (e.g. on MXLIMS) took place on the 17^th^, within
the ISPyB session. This is an attempt to group the discussions by topic,
showing the various points being made.

## Interoperability in Synchrotron Logistics and MXLIMS

There were numerous arguments that synchrotron logistics could be done
better. The different vocabularies at different synchrotrons require
synchrotron-specific input files for sample shipment and upload, meaning
that users have multiple parallel converters to maintain. Retrieving
data also has numerous complexities, not least the need to identify the
right files that contain the experiment or processing result(s) based on
non-standardised, generally undocumented, and potentially unstable file
naming systems and log files.

MXLIMS was proposed as a solution to the logistics problem, providing a
single, versioned exchange format and API that would enable standardised
communication to and from all synchrotrons, with conversion to local
formats at the receiving end. This would be particularly beneficial for
large-scale users, who would only have to maintain a single converter,
who could pass and retrieve detailed information, and who could rely on
synchrotrons to keep up with format versions and modify their MXLIMS
converters as their internal formats changed. One critical point raised
was the difference between industrial and large-scale users (who would
generally have their own LIMS and would be likely to welcome a powerful
system to interact with), and users with simpler problems or fewer
samples to submit (who might well shy away from the complexities of
interacting with a LIMS or directly with a complex JSON file). In order
to cater for the latter group of users, there were proposals to
establish a standardised .csv format shared between synchrotrons or a
shipping app with plug-ins from each synchrotron. Depending on your
position in the debate, these proposals could be seen either as (1) a
simple front end to MXLIMS, hiding complexities from users that did not
need them while preserving MXLIMS for use in complex cases and to feed
rich metadata back to accompany results, or (2) as an alternative
approach that would bypass the complexities (and potential gains)
associated with a more powerful exchange format like MXLIMS, but that
would still require much coordination and agreement between
synchrotrons.

The discussion raised a number of points not included in the talks:

A tough but potential use case for MXLIMS would be e.g. XFEL or SSX
shipments.

MXLIMS would be an API, model and exchange format, not an application,
and would be freely usable open source, most likely under LGPL license.

The standardised MXLIMS format for synchrotron interactions would not
imply any obligation for synchrotrons to harmonise their offerings. The
rule would be that any parameter not supported at a synchrotron could be
ignored, with the issuing of warning messages to users being at the
discretion of the synchrotron. It would be desirable if synchrotrons
could agree on a short list of standard tasks that each supports in its
own way -- so that you could specify e.g. a standard fragment screening
experiment without resorting to synchrotron-specific workflow names. But
whether or not that happened, the MXLIMS format would allow
specification of synchrotron-specific tasks and workflows in
site-specific data, where they would take precedence over non-specific
data when passed to the relevant synchrotron.

Direct interaction with synchrotrons could be standardised through the
use of common authentication protocols and a common specification for
endpoints. The OAuth protocol allows multiple access control set-ups and
already underpins many common applications.

## Data Quality Assurance Measures and metadata capture

The discussion in this section took its starting point in the recent
problems with specific XDS versions, which underscored the desire to
specify software versions as part of metadata (so that they could be
accessed when debugging problems with existing data). One more specific
proposal was for synchrotrons to acquire commercial XDS licenses, so
that they could maintain old versions as needed. There was much interest
in how XDS might be maintained in the future, but while various people
were considering the problem there was as yet no solution to present.

Another desire was for synchrotrons to track and make public not only
software versions but also hardware set-ups and regular quality control
data. There is at the moment no publicly accessible way of checking what
the set-up at any given synchrotron is, let alone what it was at an
earlier date if this is required for troubleshooting purposes, and there
were several proposals to change that. The tendency of downstream users
to rely on synchrotrons rather than to check all details themselves puts
additional weight on the need to establish and maintain confidence in
the results. Since synchrotrons clearly do run tests to maintain quality
and ensure that their internally deployed data processing pipelines keep
working, this is to some extent a communication problem, which might be
ameliorated by improved communication and reliable publication of
configuration and test data. On the specific question of synchrotron
processing there was no agreement as to how far synchrotrons could or
should be responsible for the 'merchantability and fitness for purpose'
of the output of the pipelines they run. If data quality becomes the
sole responsibility of the end user, this could lead to some quite
difficult problems, given that only the synchrotron is really in a
position to know or control how pipelines are executed.

There was a long discussion centred on the concept of 'certification' of
the suitability of a facility, which amounts to a question not so much
about useful ways of sharing data as about who took formal
responsibility for what. On one hand synchrotrons are uniquely in a
position to know the relevant parameters. On the other hand, even the
most thorough testing cannot realistically guarantee against subtle bugs
or suddenly appearing problems. Proposals ranged from explicit
certification schemes (with an open question of who could or should be
responsible for giving or withholding certification), to expecting
large-scale users to send their own test crystals and do their own
quality assurance in every shift.

The question of metadata capture to a large extent replicates the points
made for synchrotron logistics (MXLIMS) and making synchrotron status
available (software versions)

Some specific points made:

Bill Shepard (SOLEIL) notes that because of confidentiality policies it
is actually quite difficult to make even a Lysozyme test data set
public.

It is suggested to use the Dectris Cloud to run and publish test data.

Max Burian (Dectris) notes that this is not about validation but about
transparency. Software evolves, particularly in Cryo-EM, but you need to
be able to find out what was done. It is noted that at DLS, which
Cryo-EM software was used at a specific date (including version
information) is findable.

Dave Brown provided maybe the best discussion summary: "Can we do
better? DB thinks we can. Who is on board for trying?"

A meta-summary would be that existing differences of viewpoints between
industrial users of MX at synchrotrons on the one hand, and beamline
scientists and software developers at synchrotrons on the other, were
able to come to light in this unusual gathering of representatives of
both sides and to trigger discussions whose follow-up will hopefully
lead to constructive actions being taken in a collaborative manner.
