# SimpleTuringMachine
A simple C/C++, singletape turing machine.

SAMPLE PROGRAM - ADD ONE TO A BIN-NUMBER:
* const char* turing_add_one_program = "tape_size,32\n"
* "start_head_pos,3\n"
* "start_rule,0\n"
* "tape_conf,1,1,2,3\n" //zelle 1,2,3 auf 1 setzten//RULESET 1 df
* "rule_set,0,0,1,-1,1,1\n" //<- START RULE
* "rule_set,0,1,0,-1,0,0\n"
* "rule_set,0,-1,1,0,2,-1\n"//RULESET 2
* "rule_set,1,0,0,-1,0,1\n"
* "rule_set,1,1,1,-1,0,1\n"
* "rule_set,1,-1,-1,1,2,0\n";//eig kommt noch ein zweites aber durch die 2 wird direkt abgebrochen 
