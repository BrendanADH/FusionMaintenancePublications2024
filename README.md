# FusionMaintenancePublications2024
A dataset containing categorised papers pertaining to nuclear fusion maintenance.

This repository is a contribution of my PhD at University of York (CFAA), in which I survey current practises in fusion maintenace.

# Methodology

A survey of fusion maintenance literature was undertaken to ascertain progress in the field as of September 2024. The following `advanced query' was executed on the Scope online database:

    
    TITLE("remote maintenance" OR "maintenance" OR "remote handling" AND ("nuclear fusion" OR "nuclear maintenance" OR "tokamak devices" OR "tokamak" OR "ITER" OR "JET" OR "DEMO" OR "CFETR" OR "JT60" OR "JT-60" OR "EAST" OR "ST-E1" OR "ARC" OR "SPARC" OR "GP-FPP" OR "DTT" OR "T-15" OR "PST))
    AND SUBJAREA(COMP OR ENER OR ENGI OR PHYS)
    AND NOT TITLE-ABS-KEY("sensor fusion" OR "image fusion")
    AND KEY("tokamak" OR "nuclear fusion" OR "fusion energy" OR "nuclear reactors" OR "tokamak devices")


In plain English, the query matches documents which:


- Have titles including both at least one of the strings "remote maintenance", "maintenance", or "remote handling" and at least one of the strings "nuclear fusion", "nuclear maintenance", "tokamak devices", "tokamak", and various strings chosen to correspond to all tokamaks identified previously within the thesis.
- Are within the subject areas of computer science, energy, engineering, and physics
- Do *not* include "sensor fusion" or "image fusion" in their titles, abstracts, or keywords.
- Include at least one of "tokamak", "nuclear fusion", "fusion energy", "nuclear reactors" or "tokamak devices" in their keywords.
- 
The result was a set of 545 publications. These publications were then manually sorted eliminate irrelevant entries, leaving 382 entries. The valid entries were again manually sorted according to their titles and abstracts to establish their themes, the projects they pertained to, and the plant systems they addressed. The themes and systems were defined as such: 

## Themes

An effort was made to classify each publication by only its most relevant theme, but in cases where the content had an undeniable connection to multiple themes, they were all recorded.

- HARD (hardware) - primarily relates to maintenance hardware e.g. presenting new hardware, analysing existing hardware, comparing various hardware options.
- SOFT (software) - primarily related to software, e.g. simulation packages, control software for robotics, implementation of computer vision. 
- STRAT (strategy) - concerning strategy and operations, which in turn may range from low-level approaches to specific maintenance scenarios like pipe cutting or divertor cassette transport, or high-level approaches to things like information management. 
- OVER (overview) - overview papers which present knowledge that is generally already available elsewhere, e.g. overviews of the progress on ITER maintenance hardware. 
- ASSESS (assessment) - any sort of miscellaneous assessment related to maintenance but not primarily related to software or hardware, e.g. assessments of radioactivity or seismic activity, quality and safety assessments, estimations of maintenance duration.
- SYS (systems) - publications which approach maintenance from a systems-first point-of-view. These are primarily concerned with engineering systems so that maintenance can be easily performed.
- FAC (facilities) - publications regarding facilities that are usually test-beds for maintenance activities.
- EXP (experience) - records of experience from maintenance activities. 
- AUTO (automation) - publications regarding automated maintenance.
    
## Systems

Many publications made mention of more than one system and all were recorded. The terms were chosen to provide a suitably level of granularity for discussion.

- IN-VESSEL - This was used as a generic name for most unspecified work on the vacuum vessel, including the ports. Most publications regarding arm-type robots such as MASCOT (JET) or EAMA (CFETR) performing unspecified tasks were classified in to this category.
- BLANKET - the breeding blanket.
- DIVERTOR - the divertor.
- TRANSPORT - anything related to the transport of maintenance components or waste materials (i.e. blanket and divertor parts) outside the tokamak.
- NBI - neutral beam injection.
- RF-HCD - radio frequency heating and current drive, mostly concerning the maintenance of the antennae inside the vessel. 
- REMOTE - maintenance on the maintenance systems (i.e. remote handling systems) themselves. Usually involved rescue protocols for stranded maintenance equipment.
- CRYO - any cryogenics equipment.
- COILS - the magnetic coils.

The data is available in .csv form (fusion_maintenance_dataset.csv). Also included is a python script used for visualisation.
