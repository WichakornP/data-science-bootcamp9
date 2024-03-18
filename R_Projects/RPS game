rps_game <- function() {
  # Collect user's name and print greeting word
  flush.console() 
  user_name <- readline("What's your name: ")
  flush.console() 
  print(paste("Hi, ", user_name, "Welcome to RPS game!"))
  
  while (TRUE) {
    
    # Declare required variables
    user_score <- 0
    bot_score <- 0
    round <- 1
    moves <- c("r", "p", "s")
    
    # Game loop
    while (user_score < 3 & bot_score < 3) {
      # Player's move
      user_move <- tolower(readline("Choose your move (r/p/s): "))
      
      # User's input validation
      while (!(user_move %in% moves)) {
        print("Invalid move. Please enter 'r', 'p', or 's'.")
        user_move <- tolower(readline("Choose your move (r/p/s): "))
      }
      
      # Generate random bot move
      bot_move <- sample(moves, 1)
      
      # Determine the winner and update scores
      if (user_move == bot_move) {
        print(paste("Round:", round, "Draw!"))
      } else if ((user_move == "r" & bot_move == "s") |
                 (user_move == "p" & bot_move == "r") |
                 (user_move == "s" & bot_move == "p")) {
        print(paste("Round:", round, "Win!"))
        user_score <- user_score + 1
      } else {
        print(paste("Round:", round, "Lose!"))
        bot_score <- bot_score + 1
      }
      
      # Display scores and current round
      print(paste("Player's move is",user_move,
                  "Bot's move is",bot_move))
      print(paste("Your score:", user_score, "Bot score:", bot_score))
      round <- round + 1
      
      
      # Check if score limit reached
      if (user_score == 3) {
        print("You win the game!")
      } else if (bot_score == 3) {
        print("You lose the game!")
      }
    } # End of game loop
    
      # Ask for another round
      play_again <- tolower(readline("Do you want to play again? (yes/no): "))
      
      # User's input validation
      while (play_again != "yes" && play_again != "no") { 
        print("Invalid move. Please enter 'yes' or 'no'")
        play_again <- tolower(readline("Do you want to play again? (yes/no): "))
      }
      
      # Define actions for each result
      if (play_again == "yes"){
        TRUE                         # start game loop again
      }
      else if (play_again == "no"){
        print("Thanks for playing!") # exit message
        break                        # break out the loop
      }
  }
}


# Play the game
rps_game()
