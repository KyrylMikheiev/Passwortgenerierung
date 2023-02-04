import random
import time

def information():
    chars = []
    amount = int(input('Wie viel Passwörter brauchst du?(Nummer): '))
    length = int(input('Wie lang sollte das Passwort sein?(Nummer): '))
    numbers = input('Soll ich Zahlen aufnehmen?(ja oder nein): ')
    big = input('Soll ich Großbuchstaben verwenden?(ja oder nein): ')
    small = input('Kleinbuchstaben?(ja oder nein): ')
    symbol = input('Brauchst du diese symbole:  (  !#$%&*+-=?@^_  ) ?(ja oder nein): ')
    info = [numbers, big, small, symbol]
    for i in range(len(info)):
        info[i] = info[i].strip()
        info[i] = info[i].lower()
    if info[0] == 'ja':
        chars.extend('0123456789')
    if info[1] == 'ja':
        chars.extend('ABCDEFGHIJKLMNOPQRSTUVWXYZ')
    if info[2] == 'ja':
        chars.extend('abcdefghijklmnopqrstuvwxyz')
    if info[3] == 'ja':
        chars.extend('!#$%&*+-=?@^_')
    data = [amount, length, chars]
    return data

def password_generate(data):
    amount = data[0]
    length = data[1]
    chars = data[2]
    for i in range(amount):
        print(*random.sample(chars, length), sep='')
        time.sleep(0.2)
print()
print('Moin, du brauchst Passwörter generieren? Dann bist du bei uns genau richtig!')
time.sleep(3.7)
print('Es müssen jedoch einige Fragen beantwortet werden...')

password_generate(information())
