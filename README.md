import random
n=int(input("please select number of players "))  #number of players
a=[]
ladder=[4,13,33,42,50,62,74]
e=[]
snake=[27,40,43,54,66,76,89,99]
x=0
for i in range(n):
    a.append('p'+str(i+1))
    e.append(0)
while(1):
    for i in range(len(a)):
        b=random.randint(1,6)
        print("For player"+str(i+1)+" dice rolls on: ",b)
        print("player"+str(i+1)+": starting position="+str(e[i]))
        c=e[i]
        e[i]=e[i]+b
        if(e[i] in ladder): #if dice rolls on ladder
            print("climb the ladder")
            if(e[i]==4 or e[i]==42):
                e[i]=e[i]+21
            elif(e[i]==50 or e[i]==62):
                e[i]=e[i]+19
            elif(e[i]==13):
                e[i]+=33
            elif(e[i]==33):
                e[i]+=16
            elif(e[i]==74):
                e[i]+=18
        if(e[i] in snake): #if dice rolls on snake
            print("you have bitten by a snake")
            if(e[i]==27):
                e[i]=e[i]-22
            elif(e[i]==40):
                e[i]=e[i]-37
            elif(e[i]==43):
                e[i]=e[i]-25
            elif(e[i]==54):
                e[i]=e[i]-23
            elif(e[i]==66):
                e[i]=e[i]-21
            elif(e[i]==76):
                e[i]=e[i]-18
            elif(e[i]==89):
                e[i]=e[i]-36
            elif(e[i]==99):
                e[i]=e[i]-58
        if(e[i]>100):
            e[i]=c
        if(e[i]==100):
            print("player"+str(i+1)+": final position=",e[i])
            print("player"+str(i+1)+": is WINNER")
            x=1
            break
        print("player"+str(i+1)+": final position=",e[i])
        f=0
        while(b==6): #when dice rolls on 6
            print("you have got another chance to roll the dice")
            f=f+1
            b=random.randint(1,6)
            print("For player"+str(i+1)+" dice rolls on: ",b)
            print("player"+str(i+1)+": starting position="+str(e[i]))
            if(f==3):
                e[i]=c
                print("dice rolled continuesly three times on 6\n"+"final position of player"+str(i+1)+" is",e[i])
                break
            e[i]=e[i]+b
            if(e[i] in ladder): #if dice rolls on ladder
                print("climb the ladder")
                if(e[i]==4 or e[i]==42):
                    e[i]=e[i]+21
                elif(e[i]==50 or e[i]==62):
                    e[i]=e[i]+19
                elif(e[i]==13):
                    e[i]+=33
                elif(e[i]==33):
                    e[i]+=16
                elif(e[i]==74):
                    e[i]+=18
            if(e[i] in snake): #if dice rolls on snake
                print("you have bitten by a snake")
                if(e[i]==27):
                    e[i]=e[i]-22
                elif(e[i]==40):
                    e[i]=e[i]-37
                elif(e[i]==43):
                    e[i]=e[i]-25
                elif(e[i]==54):
                    e[i]=e[i]-23
                elif(e[i]==66):
                    e[i]=e[i]-21
                elif(e[i]==76):
                    e[i]=e[i]-18
                elif(e[i]==89):
                    e[i]=e[i]-36
                elif(e[i]==99):
                    e[i]=e[i]-58
            if(e[i]>100):
                e[i]=c
            if(e[i]==100):
                print("player"+str(i+1)+": final position=",e[i])
                print("player"+str(i+1)+": is WINNER")
                x=1
                break
            print("player"+str(i+1)+": final position=",e[i])
    if(x==1):
        break
