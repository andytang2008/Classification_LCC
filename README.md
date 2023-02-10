# Classification_LCC
In old Primo, we had the “Classification LCC” facet which looks like below.
https://github.com/andytang2008/Classification_LCC/issues/1#issue-1580093238
However, during the migration process from the Primo to Primo VE, we found there was no choices to select and activate Classification LCC. The Primo VE merely provided the “Classification NDC” facet which is a Nippon classification number system.

Intending to make this Classification LCC available in the facet, a local field named “local_field_02” was created by clicking Discovery->Manage display and local fields->Add field->Add local field. The “Enable field for search” and “Enable field for facet” boxes were checked.

The “MARC21 normalization rule for search and facet” was edited. The customized normalization rule is very long and I put it in github. The part of demo is like as follows.
 
After you copy and paste the customized rule into the box, please click the Save button and don’t forget to click “Apply rules” button. Then, add the local facet named ”LC Call Number” (You could name whatever you want) into “Brief results” in “View configuration”. The last step, you need to submit a ticket to the Ex Libris Primo customer service team asking them stepping in to re-index. After the re-index was completed, your Classification LCC facet is up. 

This is the temporary way to solve this problem. We still expect Ex Libris could create this “Classification LCC” facet choice in “brief views” within “View Configuration” of Primo VE in future, so that we could activate it by clicking a button.
The rules will get the first letter from the field 050 subfield a and add corresponding suffix (like “General works”, etc.) as facets. The reason we didn’t include 090 and 099 field, because many libraries created their own customized call number system and put into 090 and 099 field. For the reason of the special characteristics of normalization rules, it was very difficult to judge whether the variable (like TEMP “1”) has some special value. So, we had to create the 21 rules to accommodate the LCC numbers. If someone has any better idea to shrink the code, please let me know.


