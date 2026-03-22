Revisions are represented in two sheets: 'Old Draft' and 'New Draft', which contains the revised version of the old draft.  

Each datasheet contains the following fields:

- Sentence Index

- Sentence Content

- Aligned Index
The sentence index of the corresponding sentence in the old/new draft. 
Alignment could be one-to-many or many-to-one.

- Revision Purpose Level 0
Revision purpose of the whole sentence, which could be:
  'Claims/Ideas'
  'Rebuttal/Reservation'
  'Warrant/Reasoning/Backing'
  'Evidence'
  'General Content Development'
  'Word-Usage/Clarity'
  'Conventions/Grammar/Spelling'
  'Organization'
  'Precision'

- Revision Operation Level 0
Revision Operation at sentence-level, either:
  'ADD',
  'Delete', or
  'Modify'

- Subsentential Revision Tuple Level 0
Each subsentential revision is represented as: 
[(old_sentence_start_index,  old_sentence_end_index),  (new_sentence_start_index,  new_sentence_end_index), revision_purpose, revision_operation]

(-1,-1) in a subsentential revision indicates no phrase in new/old draft is corresponding to that (it is either added to the old sentence or deleted from the new sentence)

A sentence may contain multiple subsentential revisions

revision_purpose:
  1:  'Claims/Ideas'
  2:  'Rebuttal/Reservation'
  3:  'Warrant/Reasoning/Backing'
  4:  'Evidence'
  5:  'General Content Development'
  7:  'Word-Usage/Clarity'
  8:  'Conventions/Grammar/Spelling'
  9:  'Organization'
  10: 'Precision'
  15: 'UNANNOTATED'
	
revision_operation:
  1:  'Add'
  2:  'Delete'
  3:  'Modify'
	
Here is an example:
	
Old sentence: 
'[While]* he computers within the car are so complex that they can do such things on their own, this does not allow them to be able to identify things a human could, like if [there were]- a police officer directing traffic.'

New sentence:
'[And while]* the computers within the car are so complex that they can do such things on their own, this does not allow them to be able to identify things a human could, like if a police officer [was]+ directing traffic.'

Subsentential annotation:
[(0,5), (0,9), 7, 3],[(171,181), (-1,-1), 8, 2],[(-1,-1), (192,195), 8, 1]

[(0,5), (0,9), 7, 3]       denotes [While] --> [And while]
[(171,181), (-1,-1), 8, 2] denotes deletion of [there were]
[(-1,-1), (192,195), 8, 1] denotes addition of [was]
