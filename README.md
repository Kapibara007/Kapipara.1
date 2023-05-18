from random import randint

def create_pas():
    alphabet = 'abcdefghijklmnopqrstuvwxyz'
    numbers = '0123456789'
    n = 8
    password = ''
    for i in range(8):
        res = randint(1, 2)
        if res == 1:
            alpha = randint(0, 25)
            password += alphabet[alpha]
        else:
            num = randint(0, 9)
            password += numbers[num]
    print(password)

create_pas()
