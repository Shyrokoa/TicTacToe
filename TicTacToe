class TicTacToe:
  combination = ['' * 9]
  winner_combination_list = []
  winner_number = 0

  def __init__(self):
    self.winner_combination_list = self.winner_combination(self.combination)
    self.winner_number = how_many_winners(self.winner_combination_list)

  def __str__(self):
    return '---------\n| {} {} {} |\n| {} {} {} |\n| {} {} {} |\n---------'.format(self.combination[0], self.combination[1], self.combination[2], self.combination[3], self.combination[4], self.combination[5], self.combination[6], self.combination[7], self.combination[8])

  def winner_combination(self, input_):
    list_ = []
    a = 0
    b = 0
    for i in range(3):
        list_.append('{}{}{}'.format(input_[a], input_[a + 1], input_[a + 2]))
        list_.append('{}{}{}'.format(input_[b], input_[b + 3], input_[b + 6]))
        a += 3
        b += 1
    # diagonal
    list_.append('{}{}{}'.format(input_[0], input_[4], input_[8]))
    list_.append('{}{}{}'.format(input_[2], input_[4], input_[6]))
    return list_
  def game(self):
    print('How many winners: {}'.format(self.winner_number))
    if self.winner_number < 1:
      # Game not finished
      if counter_(self.combination,'_') > 1:
        if abs(counter_(self.combination, 'X') - counter_(self.combination, 'O')) <= 1:
            print('Game not finished')
        elif abs(counter_(self.combination, 'X') - counter_(self.combination, 'O')) > 1:
            print('Impossible')
      # Impossible
      elif abs(counter_(self.combination, 'X') - counter_(self.combination, 'O')) > 1:
        print('Impossible')
      # Draw
      elif counter_(self.combination, '_') == 0:
        print('Draw')
    elif self.winner_number  == 1:
      print('{} wins'.format(winner(self.combination)))
    elif self.winner_number  > 1:
      print('Impossible')

  def whose_step(self):
    x = 0
    o = 0
    for a in self.combination:
      if a == 'X':
        x += 1
      elif a == 'O':
        o += 1
    if x >= o:
      #TODO
      return('X')
    else:
      return('O')
      
          
  def new_step(self):
    dictionary = (1, 2, 3)
    while True:
      step  = input('Enter the coordinates: ')
      x_step = int(step.split(' ')[0])
      y_step = int(step.split(' ')[1])
      if x_step in dictionary and y_step in dictionary :
        if 0 < x_step < 4 and 0 < y_step < 4:
          if (x_step, y_step) == (1, 1):
            if self.combination[6] == '_':
              self.combination[6] = self.whose_step()
              break
            else:
              print('This cell is occupied! Choose another one!')
          elif (x_step, y_step) == (1, 2):
            if self.combination[3] == '_':
              self.combination[3] = self.whose_step()
              break
            else:
              print('This cell is occupied! Choose another one!')
          elif (x_step, y_step) == (1, 3):
            if self.combination[0] == '_':
              self.combination[0] = self.whose_step()
              break
            else:
              print('This cell is occupied! Choose another one!')
          elif (x_step, y_step) == (2, 1):
            if self.combination[7] == '_':
              self.combination[7] = self.whose_step()
              break
            else:
              print('This cell is occupied! Choose another one!')    
          elif (x_step, y_step) == (2, 2):
            if self.combination[4] == '_':
              self.combination[4] = self.whose_step()
              break
            else:
              print('This cell is occupied! Choose another one!')
          elif (x_step, y_step) == (2, 3):
            if self.combination[1] == '_':
              self.combination[1] = self.whose_step()
              break
            else:
              print('This cell is occupied! Choose another one!')
          elif (x_step, y_step) == (3, 1):
            if self.combination[8] == '_':
              self.combination[8] = self.whose_step()
              break
            else:
              print('This cell is occupied! Choose another one!')
          elif (x_step, y_step) == (3, 2):
            if self.combination[5] == '_':
              self.combination[5] = self.whose_step()
              break
            else:
              print('This cell is occupied! Choose another one!')    
          elif (x_step, y_step) == (3, 3):
            if self.combination[2] == '_':
              self.combination[2] = self.whose_step()
              break
            else:
              print('This cell is occupied! Choose another one!')
        else:
          print('Coordinates should be from 1 to 3!')
      else:
        print('You should enter numbers!')
  def initial_board(self):
    return '---------\n|       |\n|       |\n|       |\n---------'

  def new_game(self):
    self.initial_board()
    while True:
      self.new_step()
      self.print()
      self.game()


# transform input string to literals list
def sequence_transform(input_):
    sequence = []
    for liter in range(9):   
      sequence.append(input_[liter])
    return sequence  
# check the number of winners

# who winner
def winner(potential_winner):
  for pot in potential_winner:
    if pot[0] == pot[1] == pot[2]:
      return pot[0]

# how many literals
def counter_(seq, char_):
  count = 0
  for a in seq:
    if a == char_:
      count +=1
  return count

# how many winners
def how_many_winners(potential):
  winner_counter = 0
  for a in potential:
    if a[0] == a[1] == a[2] and a[0] != '_':
      winner_counter += 1
  return winner_counter

# Test: 
game = TicTacToe()
game.new_game()
