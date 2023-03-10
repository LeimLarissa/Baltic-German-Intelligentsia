# Baltic-German Intelligentsia

Here I collect everything for a possible future database of Baltic(-German) educated people from the turn of the 19th century.  
This is more or less my sandbox to test and improve my skills.  
The idea for this project developed during my Master Studies, but now this is just a side project on a topic I'm interested in. 

## Goals
Goal 1:   
I'm interested in people with higher education from the Baltic Governorates of the Russian Empire and their activities in Baltic-German learned societies. My main sources are self-published meeting minutes of different learned societies and the membership-lists within them.  
These source materials do put the focus on more of the German speaking popultation of the Baltic Governorates, but whereever possible I'm interested in identifying people with higher education regardless of ethnic identity.   

The tasks I set for myself are: 
- Task 1: Clean errors generated through OCR to improve data quality. [Detailed Explanation.](https://github.com/LeimLarissa/Baltic-German-Intelligentsia/blob/4acb483cfa83a40357f36008d1572f368039a2c6/T1_detailled_explanation.md)
- Task 2: Extract names from membership-lists.
- Task 3: Clean and homogenise data from extracted lists. 
- Task 4: Disambiguate persons using Authority Files like Wikidata and GND.  
- Task 5: Analyse overlap in membership and social-economic composition of the learned societies. 

## Contents
### Scripts 
[G1T1CleaningOCRErrors.ipynb](https://github.com/LeimLarissa/Baltic-German-Intelligentsia/blob/49e8f741b760ee1556d8dac41bef78aa78cff3f7/G1T1CleaningOCRErrors.ipynb)  
Task 1: Clean errors generated through OCR to improve data quality.  Status = **finished** 
- [x] I'm working on a Jupyter notebook to identify the OCR generated error of spaces inbetween individual letters of a line.  
- [x] I also want to track how common the error is across my sources.   
- [x] I want to remove the additional spaces and create better source materials.   
- [x] I want to create an overview for the errors detected and removed for each document. 

[G1T2ExtractMembership.ipynb](https://github.com/LeimLarissa/Baltic-German-Intelligentsia/blob/47b5d98d764541ccf86ac3347f9a5565b8277492/G1T2ExtractMembership.ipynb)  
Task 2: Extract names from membership-lists. Status = **in progress**  
- [ ] I need to identify the part within the text that includes the membership list. I will tag all sections of the text to make future work easier. 
  - [X] GEG
  - [ ] GGuA
  - [ ] NVR
- [ ] I need to make sure that information is not lost by a line break. Therefore I want all information about one person in one line. 
- [ ] I want to extract the following metadata if available: Year, Society, Fullname, Profession, Location, Membership Status. 
- [ ] I want all extracted membership data from all societies in one .csv-file.   

### Sources
Abbr.   | Learned Society   | Title of Publication | Location| Timespan     | Database | Rights 
--------|-------------------|----------------------|---------|--------------|----------|-------
GEG | Gelehrte Estnische Gesellschaft zu Dorpat | Sitzungsberichte der Gelehrten Estnischen Gesellschaft | Tartu (Estonia) | 1873-1914 | [University Tartu Dspace](http://dspace.ut.ee/handle/10062/20828) | free to use 
GGuA | Gesellschaft f??r Geschichte und Alterhumskunde der Ostseeprovinzen | Sitzungsberichte der Gesellschaft f??r Geschichte und Alterthumskunde der Ostseeprovinzen Russlands | Riga (Latvia) | 1873-1914 | [University Tartu Dspace](http://dspace.ut.ee/handle/10062/17734) | free to use 
NVR | Der Naturforschende Verein zu Riga | Correspondenzblatt des Naturforschenden Vereins zur Riga | Riga (Latvia) | 1870-1924 | [University Tartu Dspace](http://dspace.ut.ee/handle/10062/45701) | free to use 
