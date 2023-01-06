# noteby_app
 
<!-- link for project tracking spreadsheet -->


# all_songs = []
# my_songs = []
# saved_songs = []

class Account:
  def __init__(self,name,notes_balance=10,song_amount=0):
    self.name = name
    self.song_amount = song_amount
    self.notes_balance = notes_balance

  def buy(self,notes_price,all_songs,song_amount):
    # once you buy songs, you also lose the amount of notes you had
    if self.notes_balance >= notes_price:
      # this is to say "if the notes balance is greater or equal to the note price"
      # self.all_songs.append(saved_songs)
      self.notes_balance += notes_price
    else:
      return False
  def upload(self,notes_price,all_songs,my_songs):
    if self.my_songs.append(all_songs):
      self.notes_balance += 10
      pass

def menu():
  created_accounts = []
  current = None
  while True:
    print("Welcome to Noteby! What would you like to do today")
    print("1.Access Account")
    print("2.Create account ")
    print("3.Buy Songs")
    print("4.View Your Songs")
    print("5.Buy Notes")
    print("6.View Note Balance")
    choice = input()
    if choice == "1":
      userIn = input('Enter username: ')
      for i in range(len(created_accounts)):
        if created_accounts[i].name==userIn:
          current=created_accounts[i]
          print("Account Created")
        else:
          print('Account not found')
          break
    if choice == "2":
      current = input('Username: ')
      a = Account(current)
      created_accounts.append(a)
      print("Welcome to your account")
menu()

def main():
  a = Account('me','user','123', 'all songs 1,2,3','my songs 1,2,3', 'saved songs 1,2,3')
  # savings.accountType()
  a.notes_balance += 30
  print(a.notes_balance)
  a.buy(int(5),'song1','song2')
  # this is supposed to move 1 song from all songs to saved somgs
  print(a.saved_songs)
   # if self.my_songs (I want this to basically say if a song moved from all_songs is uploaded to saved_songs, the user gets 10 more notes)

  pass
# menu()
main()
