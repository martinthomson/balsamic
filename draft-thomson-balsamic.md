---
###
# Internet-Draft Markdown Template
#
# Rename this file from draft-todo-yourname-protocol.md to get started.
# Draft name format is "draft-<yourname>-<workgroup>-<name>.md".
#
# For initial setup, you only need to edit the first block of fields.
# Only "title" needs to be changed; delete "abbrev" if your title is short.
# Any other content can be edited, but be careful not to introduce errors.
# Some fields will be set automatically during setup if they are unchanged.
#
# Don't include "-00" or "-latest" in the filename.
# Labels in the form draft-<yourname>-<workgroup>-<name>-latest are used by
# the tools to refer to the current version; see "docname" for example.
#
# This template uses kramdown-rfc: https://github.com/cabo/kramdown-rfc
# You can replace the entire file if you prefer a different format.
# Change the file extension to match the format (.xml for XML, etc...)
#
###
title: "Simplified Language for Specifying Interoperability"
category: info

docname: draft-todo-yourname-protocol-latest
submissiontype: IETF  # also: "independent", "editorial", "IAB", or "IRTF"
number:
replaces: 2119, 8714
date:
consensus: true
v: 3
area: AREA
workgroup: WG Working Group
keyword:
 - next generation
 - unicorn
 - sparkling distributed ledger
venue:
  group: WG
  type: Working Group
  mail: WG@example.com
  arch: https://example.com/WG
  github: USER/REPO
  latest: https://example.com/LATEST

author:
 -
    fullname: Your Name Here
    organization: Mozilla
    email: your.email@example.com

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

TODO Abstract


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
This note argues that a single keyword suffices: "MUST".


# Redundant Keywords

Most of the set of 10 key words or phrases used are strictly redundant
with the term "MUST".


## SHALL

The term "SHALL" is defined to have the same definition as "MUST".
This term has never been favoured relative to "MUST".
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


## REQUIRED

The term "REQUIRED" is also defined to have the same meaning as "MUST".
This word has become even less popular than "SHALL".
Though usage in RFCs 2501 through 300 is almost the same as "SHALL",
it appears just 490 times in recent documents.

This word lends itself more to the use of passive voice,
which has gradually fallen out of favour in technical writing.
This would be easier to retire than "SHALL".


## MAY and OPTIONAL

A "MAY" or "OPTIONAL" defines optional behaviour.

On the face of it, this might seem necessary.
In defining interoperability,
every "MAY" for one actor
is a "MUST" for every other actor.
For instance, if a field in a message is optionally present,
every recipient of that message MUST tolerate its presence or absence equally.
It is therefore more precise to define requirements in terms of the mandatory behaviour
of participants other than the one that can exercise choice.


## Negations

Negations include "MUST NOT", "SHALL NOT", and "SHOULD NOT".
The undefined and confusing "MAY NOT" appears in several RFCs as well,
as recently as RFC 9783.

The inclusion of negations in key words is unnecessary.
Saying "MUST not do X" is equally comprehensible
to the shoutier "MUST NOT do X".

It is often better to phrase such statements positively,
avoiding the negation entirely.
By specifying the expected reaction of other protocol participants
to a forbidden action,
which might be to generate fatal errors,
the prohibition is both more effective and more fully defined.


# Weaselly Language

"SHOULD" and its synonyms and antonyms,
like the phrases from RFC 6919 {{?EXTRA=RFC6919}},
is best avoided in protocol specifications.

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
