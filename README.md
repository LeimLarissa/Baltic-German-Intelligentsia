# Baltic-German Intelligentsia

Here I collect everything for a possible future database of Baltic(-German) educated people from the turn of the 19th century.  
This is more or less my sandbox to test and improve my skills.  
The idea for this project developed during my Master Studies, but now this is just a side project on a topic I'm interested in. 

## Goals
Goal 1:   
I'm interested in people with higher education from the Baltic Governorates of the Russian Empire and their activities in Baltic-German learned societies. My main sources are self-published meeting minutes of different learned societies and the membership-lists within them.  
These source materials do put the focus on more of the German speaking popultation of the Baltic Governorates, but whereever possible I'm interested in identifying people with higher education regardless of ethnic identity.   

The tasks I set for myself are: 
- Task 1: Clean errors generated through OCR to improve data quality. [Detailed Explanation.](https://github.com/LeimLarissa/Baltic-German-Intelligentsia/blob/main/T1_detailled_explanation.md)
- Task 2: Extract information from membership-lists.
- Task 3: Clean and homogenise data from extracted lists. 
- Task 4: Disambiguate persons using authority files like Wikidata and GND.  
- Task 5: Analyse overlap in membership and social-economic composition of the learned societies. 

## Contents
### Scripts 
[G1T1CleaningOCRErrors.ipynb](https://github.com/LeimLarissa/Baltic-German-Intelligentsia/blob/main/G1T1CleaningOCRErrors.ipynb)  
Task 1: Clean errors generated through OCR to improve data quality.  Status = **finished** 
- [x] I'm working on a Jupyter notebook to identify the OCR generated error of spaces inbetween individual letters of a line.  
- [x] I also want to track how common the error is across my sources.   
- [x] I want to remove the additional spaces and create better source materials.   
- [x] I want to create an overview for the errors detected and removed for each document.  

Side Quests: 
- [x] Run NVR 1873 and NVR 1874 through error pipeline
- [x] Renew error statistics 

[G1T2ExtractMembership.ipynb](https://github.com/LeimLarissa/Baltic-German-Intelligentsia/blob/main/G1T2ExtractMembership.ipynb)  
Task 2: Extract names from membership-lists. Status = **in progress**  
- [ ] I need to identify the part within the text that includes the membership list. I will tag all sections of the text to make future work easier. 
  - [X] GEG
  - [x] GGuA
  - [ ] NVR
- [ ] I need to make sure that information is not lost by a line break. Therefore, I want all information about one person in one line as well as membership status information taged. 
  - [x] GEG
  - [x] GGuA
  - [ ] NVR
- [ ] I want to extract the following metadata (if available): Year, Society, Membership Status (1st, 2nd, 3rd Level + No.), Text (Fullname, Profession, Location)  
  - [x] GEG
  - [x] GGuA
  - [ ] NVR
   
 Task 3: Clean and homogenise data from extracted lists. Status = **in progress**  
- [ ] I will use OpenRefine to clean the membership lists. I want to 
    - separate the "Text" field into Title, Name, Occupation, Location and Entry Year (if available) 
    - remove additional spaces as well as OCR transcription errors outside of the Text field (probably manually) 
    - homogenise especially Location and Profession information (e.g. clean writing differences or versions)   

[G1T3HomogeniseData.ipynb](https://github.com/LeimLarissa/Baltic-German-Intelligentsia/blob/main/G1T3HomogeniseData.ipynb)
- [ ] I want to generalise some aspects for statistical analysis and visualisations: 
    - create profession fields that group certain professions together (possibly using a given ontology)
    - add location IDs that would allow mapping by longitude and latitude (most difficult for smaller Baltic towns and "Gutshöfe" that were renamed or no longer exist) 

Task 4: Disambiguate persons using authority files like Wikidata and GND. Status = **in preparation**
- [ ] I want to keep a list of membership instances as well as a list of individual people (see [first DB draft](https://github.com/LeimLarissa/Baltic-German-Intelligentsia/blob/main/Balt_Ger_Intelligentsia-dbdesigner.pdf) ) 
    - [ ] I want to compare the text line of one membership list with those of all the other lists to identify the individual persons that were members.
    - [ ] I will create a separate list with these identified people that has fixed information about the person (e.g. most common name variant). These link to the membership instances through the ID of the person within the instance. This list of people is not connected to any specific society, but overarching all of them.
    - [ ] I want to enrich the inmutuable information about the individual persons (e.g. birth date, death date) through exisiting authority files (GND, VIAF, Wikidata) as well as disambiguate them through those external IDs. 

### Sources
Abbr.   | Learned Society   | Title of Publication | Location| Timespan     | Database | Rights 
--------|-------------------|----------------------|---------|--------------|----------|-------
GEG | Gelehrte Estnische Gesellschaft zu Dorpat | Sitzungsberichte der Gelehrten Estnischen Gesellschaft | Tartu (Estonia) | 1873-1914 | [University Tartu Dspace](http://dspace.ut.ee/handle/10062/20828) | free to use 
GGuA | Gesellschaft für Geschichte und Alterhumskunde der Ostseeprovinzen | Sitzungsberichte der Gesellschaft für Geschichte und Alterthumskunde der Ostseeprovinzen Russlands | Riga (Latvia) | 1873-1914 | [University Tartu Dspace](http://dspace.ut.ee/handle/10062/17734) | free to use 
NVR | Der Naturforschende Verein zu Riga | Correspondenzblatt des Naturforschenden Vereins zur Riga | Riga (Latvia) | 1870-1924 | [University Tartu Dspace](http://dspace.ut.ee/handle/10062/45701) | free to use 
