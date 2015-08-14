# Created by KcaJP
#
# This Program makes life a lot easier by automatically
# retriving lingot data from the internet to update the LINGOT HALL OF FAME
#
# Note:
#     miyavmjaupurr and TheCapitalist must have changed their accounts.
#     I removed them from the list.  If you can find their new usernames,
#     you can add them back onto the list.
#
#     It is normal for this program to take a long time to execute.
#     It takes me about a minute to run it.
#
#     If you have any questions, just ask!
# 
# Tested and works for python 3.4.2

import urllib.request
import json

class User(object):
    # This is the class that retrives the data from the internet.
    def __init__(self, user):
        self.user = user

        url = 'https://www.duolingo.com/users/' + str(self.user)
        response = urllib.request.urlopen(url)
        content = response.read()

        self.data = json.loads(content.decode('utf8'))

    def lingots(self):
        return self.data['rupees']

# This is a list that stores all of the users.  To add users, just add more items
# to the list.  Make sure the users are in quotes and seperated by commas.
people = ['KcaJP', 'Professor01', 'TromBennyBone' , 'davidcwalls', 'Anorak13',
          'nekonekokoneko', 'Soolrak', 'Sarah-Cheung', 's-g-miller', 'GregHullender',
          'm.tastic', 'QQJoy', 'northernguy', 'KevanSF', 'jairapetyan',
          'nhanderson', 'sheldolina', 'LongHenry', 'M4rt4a', 'suesieb',
          'panagiotists13', 'G2DIPI_true', 'Erven.R', 'Linguist001', 'XD29',
          'adamyoung97', 'Deodwyn', 'Don_Cristian', 'Valoja', 'Xephers',
          'rubiagm', 'JonnySmooth', 'GC1998', 'Orsowski', 'Lorel90',
          'xeno78', 'ChicoGenio', 'StrapsOption', 'parked91', 'Hectoglot',
          'KinanHabbal', 'Alastair17', 'BrookeLorren', 'only_human', 'Teenage_Polyglot', 
          'Tamuna10', 'KimberleyAsh', 'deguo', 'Bryan.EDU', 'BLAZERUNNER', 
          'Maurice314', 'asawp']

PersonalLingots = {}

# Displays the loading bar
print ('Retriving data . . .')
print ('')
print ('___Loading Bar___')

loading = 0

for i in people:
    # Assigns the lingots to people.
    try:
        user = User(i)
        PersonalLingots[i] = user.lingots()

    except ValueError:
        print ('The accout, ' + i + ', appears to be deactivated')
        people.remove(i)

    # The Loading Bar calculation
    loading += 1/len(people)
    
    if loading > 0.04:
        print ('-', end='')
        loading = 0

print ('\n\n')       

def sort():
    # Sorts all of the data from high to low
    for i in range(len(people)-1):
        if PersonalLingots[people[i]] < PersonalLingots[people[i+1]]:
            person = people[i]
            people[i] = people[i+1]
            people[i+1] = person
            sort()

sort()

for k in people:
    # Prints all of the data
    print (k + ': ' + str(PersonalLingots[k]))
