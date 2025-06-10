---
dg-publish: true
dg-home: true
dg-show-local-graph: false
dg-hide-in-graph: true
dg-pinned: true
obsidianUIMode: preview
title: Homepage
---
![[ObsidianBannercopy2.png|banner]]

# Quick Links
[[Named Characters & Beasts|Characters]] | [[The Party]] | [[Locations]] | [[History & Events]] | [[Gods & Heralds]] | [[Groups & Factions]] | [[Races]]

This is a read-only version of the Ashen Campaign Vault, designed to make finding, reading, and sharing campaign information easier without setting up Obsidian.  

> [!tip] Useful Tip - Daggers
> † denotes that this character is dead.
> 
> ‡ denotes that the circumstances around this character's death are strange or unusual.
> 
> We have made a point of never officially putting daggers on people unless we are outright told by James or in an official text. 


<iframe src="https://app.kanka.io/w/322252/maps/108114/explore" width="100%" height="800">
  <p>Your browser does not support iframes.</p>
</iframe>




### Sessions
```dataview
TABLE WITHOUT ID
  file.link AS "Session", part as "Saga", Summary
From "Session Notes"
SORT number(split(file.name, "\.")[0]) DESC
LIMIT 10
```
### Books & Documents Reading List

> [!Info] **Reading List Explained**
> **High Priority** —These documents are necessary to understand the campaign's key themes. Not reading these may cause confusion or a lack of understanding of common [[Theories & Unanswered Questions|theories]].
> 
> **Medium Priority** - These documents are pertinent to understanding the story but can help explain things that are happening in the background, which may influence the story
> 
> **Low Priority** - These are books that are still good and contain helpful information, but you don't need to read them to understand what is happening 
> 
> **Unimportant Priority** - These documents won't appear in this table below but can still be found in "Books, Documents & Artefacts" for you to read at your leisure

<br> %% break line  %%

```dataview
TABLE WITHOUT ID
  file.link AS "Book/ Document", priority as "Reading Priority", booklocal as "Location found", file.cday as "Date Found"
FROM "Books, Documents & Artefacts" and !#Artefact and !#Unimportant
SORT priority
```

%% break line  %%
### Recently Modified
```dataview
list
from ""
sort file.mtime DESC
limit 5

```

### Recently Created
```dataview
list
from ""
sort file.ctime DESC
limit 5

```
%% break line  %%
%% break line  %%
%% break line  %%

### Tagged as Having Incomplete Or Out-of-Date Information
```dataview
TABLE WITHOUT ID
  file.link AS "Note", file.mday as "Date of Tagging"
FROM #INFORMATION_MISSING_OR_OUT-OF-DATE and !"Admin"
```

### Other Information 
Most tables are actually database query searches and will automatically update when new information is added. DM [[Sam Gallon]] if you have any suggestions on possible searches.

As always, you should talk to [[James Absolom]] if you have any ideas or thoughts relating to the campaign. **NEVER** keep secrets from the DM. This is a collaborative storytelling game, and it only works well if the storyteller knows what's happening. They might even be able to make it happen better than you expected. 