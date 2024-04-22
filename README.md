# caesar-cipher-encode-decode-game
# A program to encode secret message or information.
alphabet = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z']

def caesar(text,shift,direction):
  newtext = ""
  if direction == "decode":
    shift *= -1
  for char in text:
    if char in alphabet:
      position = alphabet.index(char)
      new_p = position + shift
      newtext += alphabet[new_p]
    else:
      newtext += char
  print(f"The {direction} text is {newtext}")

should_end = False
while not should_end:

  direction = input("Type 'encode' to encrypt, type 'decode' to decrypt:\n")
  text = input("Type your message:\n").lower()
  shift = int(input("Type the shift number:\n"))
  shift = shift % 26

  caesar(text, shift, direction)

  restart = input("Type 'yes' if you want to go again. Otherwise type 'no'.\n")
  if restart == "no":
    should_end = True
    print("Goodbye")
