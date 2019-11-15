# Kitty-Excursion
adventure game
# Statements    Have to spell the whole word. If more than one word put in a underline in the space.
# For example the_wilds.Or use the numbers 1,2,3,4,5,6 if that exit is available it will take you to that area

locations = {0: "Kitty sits in the hall waiting for the door to open",
             1: "Kitty sits on the porch waiting for door to open",
             2: "Kitty climbs tree to see what he can see",
             3: "Kitty launches across the fence to The Wilds",
             4: "Kitty plays with his girlfriend",
             5: "Kitty dives underground through the drainage slot",
             6: "Kitty fights the local toms at the rebel rouse "}

exits = {0: {"Q": 0},  # quit
         1: {"N": 2, "W": 4, "S": 5, "Q": 0},  # p-tc, p-pg, p-u, quit
         2: {"N": 3, "W": 4, "S": 1, "Q": 0},  # tc-tw, tc-pg,tc-p,  quit
         3: {"S": 2, "E": 6, "Q": 0},  # tw-tc, tw-rr,quit
         4: {"N": 2, "W": 1, "S": 5, "Q": 0},  # pg-tc, pg-p, pg-u, quit
         5: {"N": 1, "W": 4, "E": 6, "Q": 0},  # u-p, u-pg, u-rr, quit
         6: {"N": 3, "S": 5, "Q": 0}}  # rr-tw, rr-u, quit

namedExits = {1: {"2": 2, "5": 5, "4": 4},  # p-tc, p-u, p-pg
              2: {"3": 3, "4": 4, "1": 1},  # tc-tw, tc-pg, tc-p
              3: {"2": 2, "6": 6},  # tw-tc, tw-rr
              4: {"1": 1, "2": 2, "5": 5},  # pg-p, pg-tc, pg-u
              5: {"1": 1, "4": 4, "6": 6},  # u-p, u-pg, u-rr
              6: {"3": 3, "5": 5}}  # rr-tw, rr-u

vocabulary = {"QUIT": "Q",
              "NORTH": "N",
              "SOUTH": "S",
              "EAST": "E",
              "WEST": "W",
              "PORCH": "1",
              "TREE_CLIMBING": "2",
              "THE_WILDS": "3",
              "PLAY_WITH_GIRLFRIEND": "4",
              "UNDERGROUND": "5",
              "REBEL_ROUSING": "6"}

loc = 1
while True:
    availableExits = ", ".join(exits[loc].keys())

    print(locations[loc])
    if loc == 0:
        break
    else:
        allExits = exits[loc].copy()
        allExits.update(namedExits[loc])

    direction = input("Available exits are " + availableExits + " ").upper()
    print()
    # #Parse the user input, using our vocabulary dictionary if necessary

    if len(direction) > 1:  # more that one letter, so check vocabulary
        words = direction.split()
        for word in words:
            if word in vocabulary:
                direction = vocabulary[word]
                break

    if direction in allExits:
        loc = allExits[direction]
    else:
        print("You cannot go in that direction")









"C:\Users\Mary Page\venv3\Scripts\python.exe" "C:/Users/Mary Page/Desktop/Python Programs/More Dictionary/Kitty Excursion Game.py"
Kitty sits on the porch waiting for door to open
Available exits are N, W, S, Q 4

Kitty plays with his girlfriend
Available exits are N, W, S, Q 2

Kitty climbs tree to see what he can see
Available exits are N, W, S, Q 1

Kitty sits on the porch waiting for door to open
Available exits are N, W, S, Q 4

Kitty plays with his girlfriend
Available exits are N, W, S, Q 5

Kitty dives underground through the drainage slot
Available exits are N, W, E, Q 6

Kitty fights the local toms at the rebel rouse 
Available exits are N, S, Q 3

Kitty launches across the fence to The Wilds
Available exits are S, E, Q 2

Kitty climbs tree to see what he can see
Available exits are N, W, S, Q 1

Kitty sits on the porch waiting for door to open
Available exits are N, W, S, Q 2

Kitty climbs tree to see what he can see
Available exits are N, W, S, Q 1

Kitty sits on the porch waiting for door to open
Available exits are N, W, S, Q underground

Kitty dives underground through the drainage slot
Available exits are N, W, E, Q rebel_rousing

Kitty fights the local toms at the rebel rouse 
Available exits are N, S, Q the_wilds

Kitty launches across the fence to The Wilds
Available exits are S, E, Q tree_climbing

Kitty climbs tree to see what he can see
Available exits are N, W, S, Q porch

Kitty sits on the porch waiting for door to open
Available exits are N, W, S, Q play_with_girlfriend

Kitty plays with his girlfriend
Available exits are N, W, S, Q porch

Kitty sits on the porch waiting for door to open
Available exits are N, W, S, Q underground

Kitty dives underground through the drainage slot
Available exits are N, W, E, Q play_with_girlfriend

Kitty plays with his girlfriend
Available exits are N, W, S, Q tree_climbing

Kitty climbs tree to see what he can see
Available exits are N, W, S, Q the_wilds

Kitty launches across the fence to The Wilds
Available exits are S, E, Q tree_climbing

Kitty climbs tree to see what he can see
Available exits are N, W, S, Q porch

Kitty sits on the porch waiting for door to open
Available exits are N, W, S, Q quit

Kitty sits in the hall waiting for the door to open

Process finished with exit code 0


