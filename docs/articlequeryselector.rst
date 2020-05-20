Article Query Selector
========

Monok utilizes it's own query selector to express the intent of a user. 
Using this query system, you can describe accurately the type of articles you are searching for, filter out or generate.
This system can be used together with the "Funnel" or "Cluster" plugin to filter out the specific articles or cluster of 
articles you wish to list, or with the "Article Generation" or "Video Generation" plugin, describe the type of article or videos you wish to generate.
With the **AND** operand, you can express selection using boolean algebra.

===============   ==========================   ===================================================
Prefix            Value                        Description     
===============   ==========================   ===================================================
**Empty**         music                        The Default prefix is "Category", omitting a prefix 
                                               simple implies you wish to match the category of an article. 
                                               Match any article with the category "music"
category          music                        Match any article with the category "music"
title             crisis                       Match any article with the word "crisis" in its title
text              revolution                   Match with the word "revolution" in its article text
nationality       french                       Matches the word "french" when used to denote nationality
religion          catholic
ordinal           first
authors           robert
cause_of_death    illnes
ideology          socialist
person            Peter Parker
organization      who                          Matches the abbreviation of the World Health Organization (WHO)
criminal_charge   homicide
time              night
duration          hours
location          downtown
misc              COVID-19
money             $1 million
country           United Kingdom
city              London
state_or_province Florida
===============   ==========================   ===================================================

