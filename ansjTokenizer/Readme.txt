Please use the following command to run this program:
>> java -jar ansjTokenizer.jar input_file_name output_file_name

example:
>> java -jar ansjTokenizer.jar chinese chinese.tok
The program will output the result in the "chinese.tok" file.

**Note: 
1. ANSJ parser support Simplified Chinese only, it make poor performance when using Traditional Chinese.
2. The program will reference the ambiguity information from , it can improve the performance if you provide this file.

Library setting:
library/ambiguity.dic: add the definition to tell ANSJ how to separate word
library/default.dic: define a list of Chinese words with their word type and count.

Example for ambiguity.dic:
李民工作	李民	nr	工作	vn
This rule tell the ANSJ that, if you find "李民工作", separate as "李民	nr" and "工作	vn". 
Note: 
1. The space in the rules are separated by Tab.
2. All rules in this file will consider as first priority!
3. "nr" and "vn" is word type for that Chinese word.

Example for default.dic:
先进	a	13966
先	d	25558
进	vf	25668
Note: 
1. The space in the rules are separated by Tab.
2. "a", "d" and "vf" is word type for that Chinese word.
3. The number in last column is the word count, which will take as one parameter to score the separation by ANSJ.