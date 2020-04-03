# EP1---CRAPS-INSPER
#nome
print ('Craps Insper') 
#fase que esta
print ('Fase Come Out') 
#lista de apostas possiveis
print ('Tipos de apostas:') 
apostas = [0]*4
apostas[0]= '1-Pass Line Bet'
apostas[1]= '2-Field'
apostas[2]= '3-Any Craps'
apostas[3]= '4-Twelve'

print (apostas)

#fichas que o jogador começa
fichas_jogador = 100 
print ('Fichas do Jogador: ', fichas_jogador)

#qual tipo de aposta ele vai fazer
tipo_de_aposta= int(input('Qual tipo de aposta?: ')) 
#qual valor vai apostar
valor_apostado= int(input('Qual valor sera apostado?: '))

#condicional aposta 1-pass line bet
if tipo_de_aposta== 1: 
    import random  
    dado_1= random.randint(1,6) 
    dado_2= random.randint(1,6)
    soma = dado_1+dado_2
    print ('dado 1: ', dado_1)
    print ('dado 2: ',dado_2)
    print ('soma:', soma)
    
    if soma== 7 or soma==11:  #ganha
        fichas_jogador= fichas_jogador + valor_apostado
        print ('Fichas finais: ', fichas_jogador)
        
    elif soma ==2 or soma == 3 or soma == 12:
        fichas_jogador = fichas_jogador - valor_apostado
        print ('Fichas finais:', fichas_jogador)
        
    else:
        print ('Fase Point:')
        aposta_extra= input('Mais alguma aposta?:  ')
        print (aposta_extra)
        if aposta_extra == 'nao':
#consideramos que, uma vez que o jogador escolheu 'nao' ele não poderá escolher outra opção mais a frente       
            import random
            point = True
            while point:
                dado_1p= random.randint(1,6)
                dado_2p= random.randint(1,6)
                soma_p = dado_1p+dado_2p
                print('dado 1: ', dado_1p)
                print('dado 2:',dado_2p)
                print ('soma point:  ', soma_p)
                if soma_p == soma:
                    fichas_jogador= fichas_jogador + valor_apostado
                    print ('Fichas finais: ', fichas_jogador)
                    point = False
                elif soma_p == 7:
                    fichas_jogador= fichas_jogador - valor_apostado
                    print ('Fichas finais: ', fichas_jogador)
                    point = False

        if aposta_extra == 'sim' :   #se quiser fazer outra aposta
          qual_aposta_extra= int(input('Qual aposta extra?:  '))
          
          if  qual_aposta_extra== 2 :  #se pedir aposta adicional 2
              import random 
              dado_1= random.randint(1,6)
              dado_2= random.randint(1,6)
              soma = dado_1+dado_2
              print ('dado 1: ', dado_1)
              print ('dado 2: ',dado_2)
              print ('soma:', soma)
              if soma== 5 or soma==6 or soma==7 or soma==8:
                  fichas_jogador= fichas_jogador - valor_apostado
                  print ('Fichas finais: ', fichas_jogador)
              elif soma==3 or soma==4 or soma==9 or soma==10 or soma ==11 :
                  fichas_jogador= fichas_jogador + valor_apostado
                  print ('Fichas finais = {0}'.format(fichas_jogador))
              elif soma== 2:
                    fichas_jogador= fichas_jogador + 2*valor_apostado
                    print ('Fichas finais: ', fichas_jogador)
              else:
                    fichas_jogador= fichas_jogador + 3*valor_apostado
                    print ('Fichas finais: ', fichas_jogador)
                    
          if  qual_aposta_extra== 3 :#se pedir aposta aposta 3
              
              import random 
              dado_1= random.randint(1,6)
              dado_2= random.randint(1,6)
              soma = dado_1+dado_2
              print ('dado 1: ', dado_1)
              print ('dado 2: ',dado_2)
              print ('soma:', soma)
              
              if soma== 2 or soma==3 or soma==12 :
                fichas_jogador= fichas_jogador + 7* valor_apostado
                print ('Fichas finais: ', fichas_jogador)
              
              else:
                fichas_jogador= fichas_jogador - valor_apostado
                print ('Fichas finais: ', fichas_jogador)
                
          if  qual_aposta_extra== 4 :#se pedir aposta adicional 4
              import random 
              dado_1= random.randint(1,6)
              dado_2= random.randint(1,6)
              soma = dado_1+dado_2
              print ('dado 1: ', dado_1)
              print ('dado 2: ',dado_2)
              print ('soma:', soma)
              if soma== 12:
                  
                fichas_jogador= fichas_jogador + 30* valor_apostado
                print ('Fichas finais: ', fichas_jogador)
                
              else:
                  
                fichas_jogador= fichas_jogador - valor_apostado
                print ('Fichas finais: ', fichas_jogador)
                
            
if tipo_de_aposta== 2:  #se escolher aposta Field como aposta inicial
    import random 
    dado_1= random.randint(1,6)
    dado_2= random.randint(1,6)
    soma = dado_1+dado_2
    print ('dado 1: ', dado_1)
    print ('dado 2: ',dado_2)
    print ('soma:', soma)
    
    if soma== 5 or soma==6 or soma==7 or soma==8:
        fichas_jogador= fichas_jogador - valor_apostado
        print ('Fichas finais: ', fichas_jogador)
        
    elif soma==3 or soma==4 or soma==9 or soma==10 or soma ==11 :
        fichas_jogador= fichas_jogador + valor_apostado
        print ('Fichas finais: ', fichas_jogador)
        
    elif soma== 2:
        fichas_jogador= fichas_jogador + 2*valor_apostado
        print ('Fichas finais: ', fichas_jogador)
    else:
        fichas_jogador= fichas_jogador + 3*valor_apostado
        print ('Fichas finais: ', fichas_jogador)
        
if tipo_de_aposta== 3:    #se escolher aposta any craps como aposta inicial
    import random 
    dado_1= random.randint(1,6)
    dado_2= random.randint(1,6)
    soma = dado_1+dado_2
    print ('dado 1: ', dado_1)
    print ('dado 2: ',dado_2)
    print ('soma:', soma)
    
    if soma== 2 or soma==3 or soma==12 :
        fichas_jogador= fichas_jogador + 7* valor_apostado
        print ('Fichas finais: ', fichas_jogador)
        
    else:
        fichas_jogador= fichas_jogador - valor_apostado
        print ('Fichas finais: ', fichas_jogador)
        
if tipo_de_aposta== 4:     #se escolher aposta twelve como aposta inicial
    import random 
    dado_1= random.randint(1,6)
    dado_2= random.randint(1,6)
    soma = dado_1+dado_2
    print ('dado 1: ', dado_1)
    print ('dado 2: ',dado_2)
    print ('soma:', soma)
    
    if soma== 12:
        fichas_jogador= fichas_jogador + 30* valor_apostado
        print ('Fichas finais: ', fichas_jogador)
        
    else:
        fichas_jogador= fichas_jogador - valor_apostado
        print ('Fichas finais: ', fichas_jogador)
