# python-vs-Julia

# coding: utf-8

# In[86]:


import random 

teams = ["Dallas Fuel",
         "Shanghai Dragons",
         "Boston Uprising",
         "Team Envy",
         "Los Angeles Gladiators",
         "Los Angeles Valiant",
         "Immortals",
         "NRG eSports",
         "Seoul Dynasty",
         "Florida Mayhem",
         "Houston Outlaws",
         "London Spitfire",
         "Cloud9",
         "New York Excelsior",
         "Philadelphia Fusion",
         "Rogue"]
group_a = []
for team in teams:
    num = random.randint(0, len(teams)-1) 
    group_a.append(teams[num])
    teams.remove(teams[num])
    if len(group_a)==4:
        break
print(group_a)


group_b = []
for team in teams:
    num = random.randint(0, len(teams)-1) 
    group_b.append(teams[num])
    teams.remove(teams[num])
    if len(group_b)==4:
        break
print(group_b)


group_c = []
for team in teams:
    num = random.randint(0, len(teams)-1) 
    group_c.append(teams[num])
    teams.remove(teams[num])
    if len(group_c)==4:
        break
print(group_c)

group_d = teams
teams = []
print(group_d)
print(teams)

def match(group, mx = 2):
    for team in group:
        num = random.randint(0, len(group)-1)
        group.remove(group[num])
        if len(group)==mx:
            return group


play_off1=match(group_a) + match(group_b)
play_off2=match(group_c) + match(group_d)

# print(match(match(play_off1), mx = 1))
# print(match(match(play_off2), mx = 1))

final = (match(match(play_off1), mx = 1)) + (match(match(play_off2), mx = 1))
#print(final)

print(match(final, mx = 1))

