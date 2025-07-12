---
title: "Simplified Language for Specifying Interoperability"
category: info

docname: draft-thomson-balsamic-latest
submissiontype: IETF  # also: "independent", "editorial", "IAB", or "IRTF"
number:
obsoletes: 2119, 8714
date:
consensus: true
v: 3
# area: AREA
# workgroup: WG Working Group
keyword:
 - next generation
 - unicorn
 - sparkling distributed ledger
venue:
#  group: WG
#  type: Working Group
#  mail: WG@example.com
#  arch: https://example.com/WG
  github: "martinthomson/balsamic"
  latest: "https://martinthomson.github.io/balsamic/draft-thomson-balsamic.html"

author:
 -
    fullname: "Martin Thomson"
    organization: Mozilla
    email: "mt@lowentropy.net"

normative:

informative:
  IESG-KW:
    title: "IESG Statement on Clarifying the Use of BCP 14 Key Words"
    target: "https://datatracker.ietf.org/doc/statement-iesg-statement-on-clarifying-the-use-of-bcp-14-key-words/"
    date: 2025-03-17
    author:
      - name: IESG

...

--- abstract

The key words used to establish interoperability requirements,
can be reduced to a single key word, "MUST".
All others are either redundant
or cover for latent interoperability issues
and can be discouraged.

--- middle

# Introduction

The most cited RFC ever, RFC 2119 {{!BCP14}},
defines 10 key words -- phrases really --
for use in specifications.
THese key words have formed the backbone of interoperable specifications
in many fields,
not just the IETF.

These words and phrases represent part of the identity of the IETF.
The list is also unnecessarily long.

This note argues that a single key word suffices: "MUST".

The remainder of this document provides arguments
for why all other key words are unnecessary.


# Redundant Key Words

Most of the set of 10 key words or phrases used are strictly redundant
with the term "MUST".


## SHALL and REQUIRED

The terms "SHALL" and "REQUIRED" are defined to have the same definition as "MUST".

Neither term has ever been favoured relative to "MUST".

Of the 803 documents published after RFC 9000,
644 of these cite BCP 14.
Of these 644 documents,
the word "MUST" appears 17,327 times,
not including the quote from BCP 14.
The word "SHALL" appears just 810 times.

This ratio (~21.4) is lower than for the RFCs between 2501 and 3000 (~8),
which suggests a decline in the popularity of "SHALL".

As a perfect synonym of "MUST",
it would be easy to stop using "SHALL" entirely.

The term "REQUIRED" has become even less popular than "SHALL".
Though frequency of usage in RFCs 2501 through 3000
is close to that of "SHALL",
it appears just 490 times in recent documents.

This word lends itself more to the use of passive voice,
which has gradually fallen out of favour in technical writing.
This would be easier to retire than "SHALL".


## MAY and OPTIONAL

A "MAY" or "OPTIONAL" define optional behaviour.

On the face of it, these might seem necessary.
In defining interoperability,
every option that one actor might exercise
requires every other actor to support that choice.
That is, every "MAY" for one is a "MUST" for others.

For instance, if a field in a message is optionally present,
every recipient of that message has to tolerate its presence or absence equally.
It is therefore more precise to define requirements in terms of the mandatory behaviour
of participants other than the one that can exercise choice.


## Negations

Negations include "MUST NOT", "SHALL NOT", and "SHOULD NOT".
The undefined and confusing "MAY NOT" appears in several RFCs as well,
more early in the series,
but also as recently as RFC 9783.

The inclusion of negations in key words is unnecessary.
Saying "MUST not do X" is equally comprehensible
to the shoutier "MUST NOT do X".

It is often better to phrase such statements positively,
avoiding the use of negation entirely.
By specifying the expected reaction of other protocol participants
to a forbidden action --
such as to mandate the generation of a fatal error --
the prohibition is both more effective and more fully defined.


# Ambiguous Language: SHOULD and RECOMMENDED

"SHOULD", its synonym "RECOMMENDED",
and its antonym "SHOULD NOT",
like the phrases from RFC 6919 {{?EXTRA=RFC6919}},
are best avoided in protocol specifications.

The use of the term "SHOULD" is one of the most hotly debated
and misused
of the key words defined in BCP 14.
The IESG statement clarifying key word usage {{IESG-KW}}
takes special effort to identify some of these inappropriate uses.

Use of "SHOULD" is almost always phrased in less ambiguous terms,
by defining the preferred behaviour,
and the conditions where it is acceptable to deviate from that practice.

In many cases,
"SHOULD" is used to cover deliberate ambiguity in specifications
where agreement on specifics could not be reached.
A commitment to stop using this language
would also lead to better specification discipline
and more interoperable specifications;
see also {{?RFC9413}}.


# Security Considerations

The security of protocols can critically depend
on the precision of the language used in specifications.


# IANA Considerations

This document has no IANA actions.


--- back

# Acknowledgments
{:numbered="false"}

Stuart Cheshire made the observation that a "MAY" for one is a "MUST" for others.
