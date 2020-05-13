# foobar-ion-flux-relabeling
Google foobar Ion Flux Relabeling 

def solution(h, q):
    p=list()
    root_node=(2**h)-1
    flag=0
    flag2=0
    ht=h-1
    temp=root_node
    for i in q:
        while flag != 1:
           if i== root_node:
              p.append("-1")
              flag +=1
           else:

              if i == (temp-1)/2:
                    p.append(int(temp))
                    flag+=1


              elif i == temp-1 :
                   p.append(int(temp))
                   flag+=1


              else:
                    if flag2 != 1:
                      if i < (temp-1)/2:
                          temp = (temp-1)/2
                      else :
                        temp=temp-1
                        flag2=1
                        ht=ht-1
                    else :
                        if i == (temp-(2**ht)):
                            p.append(int(temp))
                            flag = 1


                        elif i == temp-1 :
                            p.append(int(temp))
                            flag+=1
                        elif i <(temp-(2**ht)):
                            temp = temp-(2**ht)

                        else:
                            temp -= 1

                        ht -= 1
        flag = 0
        temp=root_node
        flag2=0
    return p
print(solution(5,[19,14,28]))
