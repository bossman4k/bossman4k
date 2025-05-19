-- Print a line of dashes for aesthetics
local function lineBreak()
    local width, height = term.getSize()
    for i = 1, width do
      io.write("-")
    end
    io.write("\n")
end
-- Function to clear the screen
local function clearScreen()
    term.clear()
    term.setCursorPos(1, 1)
end
 
-- Set your desired password here
local password = "your_password"
 
-- Function to clear the screen
local function clearScreen()
  term.clear()
  term.setCursorPos(1, 1)
end
 
-- Function to display login prompt
local function displayLoginPrompt()
  clearScreen()
  print("Welcome to Monopoly OS by Monopoly Co.")
  lineBreak()
  print("Please enter the password to access:")
end
 
-- Main function to check password
local function checkPassword()
  displayLoginPrompt()
  local enteredPassword = read("*")
 
  if enteredPassword == password then
    clearScreen()
    print("Access granted!")
    shell.run("Greeting")
  else
    clearScreen()
    print("Incorrect password. Access denied.")
    sleep(2)
    checkPassword()
  end
end
 
-- Run the main function
checkPassword()
