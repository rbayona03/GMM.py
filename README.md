# GMM.py
#The purpose of this Project is to Showcase a entry level of python understanding
#By: Roberto Bayona
#This is a Standard two choice game which steers you in a win/lose path

print('Welcome to Good Morning Miami')

def gamepath():

        health = 9
        if health <= 0:
            print('You have 0 lives youve lost the game')

        name = input('what is your characters name? \n')
        age = int(input('what is your age? \n'))

        if age >= 18:
            print('Lets go!\n')

            want_to_play = input('Do you want to play? \n' ).lower()
            if want_to_play =='yes':
                print('\nWelcome', name, 'to the City of Miami')
                print('You have', health, 'lives')
                print('Good luck!\n')

                cafe = input('\nYou go for the morning coffee where do you go? \n(Starbucks/Carreta):').lower()
                if cafe == 'carreta':
                    ans = input('Great choice! now lets get to work. Take 95 or backroads? \n (95/Backroads): ').lower()
                    if ans == 'backroads':
                        print('Small delay but still faster than 95.')
                        road = input('Construction ahead make next left or go straight? \n (left/straight): ').lower()

                        if road == 'straight':
                            print('small delay but youre good. -1 life')
                            print('the office is right there but theres free doughtnuts from a dunkin truck? ')
                            donut = int(input('How many do you get? \n'))
                            health -= 1

                            if donut >= 12:
                                print('Great excuse for being late, YOU WIN!')
                            elif donut <=11:
                                print('You\'re late and no donuts for the boss... you lose')
                            else:
                                print('invalid selection', 'Choose(cones\stay):')


                        else:
                            print('School zone')
                            spd = input('Do you fly through or speedlimit? \n (fly\speedlimit): ').lower()

                            if spd == 'speedlimit':
                                print('Congrats you made it to work barely on time, YOU WIN!!!')

                            elif spd == 'fly':
                                print('You just got pulled over and lost all lives, you lose')
                                health -= 6
                                return mainmenu()
                            else:
                                print('invalid selection', 'Choose(cones\stay)')

                                

                    else:
                        print('3 lanes blocked and no exit in sight -3 lives')
                        health -= 3
                        trf = input('What do you do.. Cut over Express lane cones or stay in lane? \n (cones\stay):').lower

                        if trf == 'stay':
                                print('All this mess for a broken down cae')
                                print('Congestion opens up and you fly to work. ')
                                print('You WIN!!')
                        elif trf == 'cones':
                                print('State Trooper was waiting for someone like you.')
                                print('You get pulled over, YOU LOSE!!')
                                return mainmenu()
                        else:
                            print('invalid selection', 'Choose(cones\stay)')

                                
                    
                elif cafe == 'starbucks':
                    print('You got caught in the line and youre late for work... AGAIN')
                    print('Youre FIRED, you lose')
                    return mainmenu()
                else:
                    print('invalid selection', 'Choose(cones\stay)')


            elif want_to_play =='no':
                mainmenu()
        else:
            print('Come back in a few young one')
            return mainmenu()

        
def rules():
        print('\nThe Rules are Simple.')
        print('__' * 35)
        print('\t1) You will be given 9 lives at the start of the game.')
        print("""\t2) Every round you will have 2 paths to choose from.
\t\tA) Choose correct and move on to the next round safely.
\t\tB) Choose wrong and lose lives.""")
        print('\t3) Lose all your lives and you lose the game.')
        print('\t4) Finish the game with lifes remaining and you win!')




def mainmenu():
        print('Welcome to Good Morning Miami')
        print('1) See Rules')
        print('2) Play Game')
        print('3) Exit game')
        while True:
            try:
                selection = int(input('\nSelect option\n'))
                if selection ==1:
                    rules()
                elif selection ==2:
                    gamepath()
                elif selection ==3:
                    print('See you soon!!')
                    exit()
                        
                else:
                    print('invalid selection', 'Choose 1, 2 or 3')
            except ValueError:
                    print('invalid selection', 'Choose 1, 2 or 3')

                
mainmenu()

