# Profile-of-students
u_input = None
result = dict()
n = 0
round = 1
keys = ('first name', 'last name', 'age', 'location city')
while u_input!='0':
    if round==1:
        def round1():
            global u_input
            global n
            global result
            u_input = input('1. Add a student information | 0. End this process.\n\n\t')
            print()
            if u_input=='1':
                info = {'first name': input("Enter student's first-name: "),
                        'last name': input("Enter student's last-name: "),
                        'age': input("Enter student's age: "),
                        'location city': input("Enter the name of the city he/she lives in: ")}
                print()
                while info['age'].isdigit()==False:
                    age = str()
                    for i in range(len(info['age'])):
                        if info['age'][i].isdigit()==True:
                            age += info['age'][i]
                    if len(age)==0:
                        print('You entered a wrong age! You shoud enter a "number"...\n')
                        info['age'] = input("Enter student's age again please: ")
                        print()
                    else:
                        info['age'] = age
                result[n] = info
                n += 1
            elif u_input=='0':
                pass
            else:
                print('\nYou entered a wrong answer... Please try again.\n')
                round1()
        round1()
    elif round>1:
        u_input = input('1. Add a student information | 0. Getting final list and end this process.\n\n\t')
        print()
        if u_input=='1':
            info = {'first name': input("Enter student's first-name: "),
                    'last name': input("Enter student's last-name: "),
                    'age': input("Enter student's age: "),
                    'location city': input("Enter the name of the city he/she lives in: ")}
            print()
            while info['age'].isdigit()==False:
                age = str()
                for i in range(len(info['age'])):
                    if info['age'][i].isdigit()==True:
                        age += info['age'][i]
                if len(age)==0:
                    print('You entered a wrong age! You shoud enter a "number"...\n')
                    info['age'] = input("Enter student's age again please: ")
                    print()
                else:
                    info['age'] = age
            result[n] = info
            n += 1
        elif u_input=='0':
            for i in range(max(result.keys())+1):
                if max(result.keys())>0:
                    print(f'{i+1})')
                k = 0
                while k<4:
                    print(f'\t{keys[k]}: {dict(result.items())[i][keys[k]].capitalize()}')
                    k += 1
                print()
        else:
            print('You entered a wrong answer... Please try again.\n')
    round += 1
