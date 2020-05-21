Article Query Selector
========

Monok utilizes it's own query selector to express the intent of a user. 
Using this query system, you can describe accurately the type of articles you are searching for, filter out or generate.
This system can be used together with the "Funnel" or "Cluster" plugin to filter out the specific articles or cluster of 
articles you wish to list, or with the "Article Generation" or "Video Generation" plugin, describe the type of article or videos you wish to generate.
With the **AND** operand, you can express selection using boolean algebra.

====================   ==========================   ===================================================
Prefix                  Example Value                Description     
====================   ==========================   ===================================================
**Empty**               music                        The Default prefix is "Category", omitting a prefix 
                                                     simple implies you wish to match the category of an article. 
                                                     This one will match articles with the category "music"
category                music                        Match articles with the category "music"
title                   crisis                       Match articles with the word "crisis" in their title
text                    revolution                   Match articles with the word "revolution" in their article text
nationality             french                       Matches the word "french" when used to denote nationality
religion                catholic                     Matches the word "catholic" when used to refer to religion
ordinal                 first                        Matches ordinals such as "Second" or "1st", this one one matches "first"                                                      when used as an ordinal
authors                 robert                       Matches the full or part of the full name of one of the authors of an                                                        article
cause_of_death          illnes                       Matches the word "illness" when used as a cause of death
ideology                socialist                    Matches the word "socialist" when used to denote the ideologi of                                                              something or someone
person                  Peter Parker                 Matches the person name of someone, in this case "Peter Parker"
organization            who                          Matches the abbreviation of the World Health Organization (WHO)
criminal_charge         homicide                     Matches legal criminal charges such as "robbery" or in this case                                                              "homicide"
time                    night                        Matches time references in an article such as "evening" or "4:00pm",                                                          in this case "night"
duration                hours
location                downtown
misc                    COVID-19
money                   $1 million
country                 United Kingdom               Match 
city                    London
state_or_province       Florida
====================   ==========================   ===================================================

