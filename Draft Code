import sports 


all_matches = sports.all matches()
football = all_matches['football']

print(football)


from bs4 import BeautifulSoup
import requests
#pandas will need to be installed to verify data accuracy
import pandas as pd

source = requests.get('https://ksuowls.com/sports/football/schedule').text
#lxml will also need to be installed to use this code
soup = BeautifulSoup(source, 'lxml')


#Verify that data from 2019 season is being pulled (14 games)
fb_opponents = soup.find_all('div', class_='sidearm-schedule-game-opponent-text')
print("Number of opponents:",len(fb_opponents))

fb_results = soup.find_all('div', class_='sidearm-schedule-game-result text-italic')
print("Number of finished games:",len(fb_results))

fb_gamedetails = soup.find_all('div', class_='sidearm-schedule-game-opponent-date flex-item-1')
print("Number of game times:",len(fb_gamedetails))

#Lists to store the scraped information
opponents = []
results = []
game_times = []

#Add each respective result to 'Opponents' list
for opponent in fb_opponents:
    name = opponent.a.text
    opponents.append(name)
