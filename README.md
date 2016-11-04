# SimpleTuringMachine
This is a simple Turing-Machine implemented in C/C++.
Its a simple singletape design so you can run simple programs.
Each step will be printed in the console.
The programming synta is easy and you can define further settings like:
* Tapesize
* Start-Rule
* End-Rule
* Tape default state
* Tape startup state
* Head start position

# SYNTAX
* tape_size,_SIZE_
* start_rule,_RULE_ID_
* tape_conf,_STATE_TO_SET,_POS_1_(,_POS_2_,...)\n

A rule is a set of IF STATE THEN WRITE statements = rule_set_entry
Every rule_set_entry with the same id belongs to a ruleset.
So for example :
* IF HEAD READS 0 -> WRITE 1 ((optional) MOVE HEAD)
* IF HEAD READS 1 -> WRITE 2 ((optional) MOVE HEAD)
For this example, the rule_set has 2 entries.

These will look like this:
* rule_set,0,0,1,0,0
* rule_set,0,1,0,0,0

with head movement (move +1):
* rule_set,0,0,1,0,1
* rule_set,0,1,0,0,1

So the general syntax of a rule_set_entry look like this:
* rule_set,_RULE_ID_,_IF_STATE_,_WRITE_THAT_,_MOVE_HEAD(-1,0,+1)_,_NEXT_RULE_

# SAMPLE PROGRAM - ADD ONE TO A BIN-NUMBER
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
