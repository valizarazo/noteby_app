copy of project tracking sheet: https://docs.google.com/spreadsheets/d/1xrJs_eHiRdPWIWyC8kW-vX6U-cyy2TVo0Pp1-4N5Dfg/edit?usp=sharing


# import shelve

import shelve
s = shelve.open("test")
s['account_user'] = []
# s['songs_owned'] = []
# s['note_balance'] = []

accounts = {
   }

songs = {
  1: ["Abbey Road","Beatles","Pop", 5],
  2: ['Do Me A Favour','Artic Monkeys',"Indie Rock", 5],
  3: ["Despues De La Playa","Bad Bunny","Reggeton", 7],
  4: ['Sculptures of Anything Goes','Artic Monkeys','Indie Rock', 2],
  5: ['Vivir Mi Vida', 'Marc Anthony', 'Pop', 3],
  6: ['The Best Of The Best','Artic Monkeys','Indie Rock', 2],
  7: ['Aguacero', 'Bad Bunny', 'Reggeton', 5],
  8: ['I Know The End', 'Pheobe Bridgers', 'Indie Rock', 2]
  9: ['Fils de joie', 'Stromae', 'French Pop', 4]
  10:['Fine Line', 'Harry Styles', 'Pop', 4]
}

def buy_songs(self, title, notes_price,notes_balance):
  if notes_balance >= notes_price:
    Account.my_songs.append(title)
    Account.notes_balance -= notes_price
    return True
  else:
    print("Not enough Notes to get By!")


class Account:
  def __init__(self, username, password, notes_balance=10):
    self.username = username
    self.password = password 
    self.notes_balance = 10
    self.my_songs = []
    
class Song:
  def __init__(self, key, notes_price, title, artist, genre):
    self.key = key
    self.title = title
    self.artist = artist
    self.genre = genre


def menu():
  while True:
    print("What would you like to do today")
    print("1.Login to Account")  
    print("2.Create account ")
    print('3.View All Songs')
    print("4.Buy Songs")
    print("5.View Your Songs")
    print("6.Buy Notes")
    choice = input()
# login
    global user
    if choice == "1":
      userIn = input('Enter username: ')
      passIn = input('Enter password: ')
      if userIn in accounts:
        if accounts[userIn].password == passIn:    
          print('Welcome to your Account')
          user = accounts[userIn]
          print('Your balance is:', user.notes_balance)
          menu()
          break
      print('Account not found')
      break
# create account
    if choice == "2":
      # global userIn
      username = input('Username: ')
      password = input('Password: ')
      user = Account(username,password)
      # accounts = 'user'
      accounts[username] = user
      # print(accounts)
      print('Account Created')
      s.close()

    if choice == '3':
      print([songs])
      print(user.my_songs)

    if choice == '4':
      select = int(input("What song would you like to buy? Please choose a number: "))
      print(songs[select])
      song_choice = input("Are you sure you want to buy this song?")
      if song_choice == 'yes':
        if user.notes_balance >= songs[select][3]:
          user.my_songs.append(songs[select][0])
          user.notes_balance -= int(songs[select][3])
          menu()
          break
        else:
          print("Not enough Notes to get By!")
      
    if choice == '5':
      # song_list = 
      print(user.my_songs)
      # print(Account.my_songs)

    if choice == '6':
      print(user.notes_balance)
      notes_choice = int(input('How many notes would you like to buy? Please enter a number: '))
      total = user.notes_balance + notes_choice
      print('Your now have', total, 'notes')
  # function to buy songs with notes
  
menu()
