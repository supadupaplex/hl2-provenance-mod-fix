Fix for Half-life 2 Provenance mod.

Fixed issues:
1) Crash on startup.
2) Invulnerable HECU soldiers.
3) Unavoidable death from strider.

Changes in files:

- gameinfo.txt
Applied this fix to prevent crash:
https://steamcommunity.com/app/420/discussions/0/864971765497379056/

- p_g01_l_0.lmp
Added those lines to "ai_relationship" lump:
  "Reciprocal" "1"
  "rank" "99"
This fixed invulnerability of HECU soldiers.

- p_g02_l_0.lmp
Replaced these lines:
  "OnTrigger" "boss_strider01,SetCannonTarget,boss_train01_bullseye02,0,-1"
  "OnTrigger" "boss_strider01,SetCannonTarget,boss_train01_bullseye03,0,-1"
With those:
  "OnTrigger" "boss_strider01,SetCannonTarget,!self,0,-1"
  "OnTrigger" "boss_strider01,SetCannonTarget,!self,0,-1"
This fixed unavoidable death from strider boss.
