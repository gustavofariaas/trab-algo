Algoritmo_trabmatrizes

inteiro: l,c,sanduba=0,jar=0,sky=0,bauru=0,lucrototal=0

real:matriz [200][4],precomatriz[200],precofilial1[100],precofilial2[50],filial1[100][4],filial2[50][4], 
lucromatriz=0,lucrofilial1=0,lucrofilial2=0,maisvendido1=0,maisvendido2=0,maisvendido3=0,maisvendido4=0,maior=0,menor=0,diferenca=0

inicio

	escreva("Bem vindo ao Burguer Lord")
	escreva("Cardapio 1-SandubaDeLuz = 15,00,2-JarJarBurguer = 28,00,3-SkywalkerBuerguer = 30,00,
		4-BauruYoda = 25,00)
	
	
	escreva("Hamburgueria Matriz")
	para l de 0 ate 199
		para c de 0 ate 3
			

		escreva("Cliente X ,Informe a quantidade de hamburguers de numero X:",l+1,c+1)
                leia(matriz[l][c])

		se(matriz[l][c]>5){
                    escreva("Apenas 5 hamburguers para cada tipo.")
	                    c--
		
		se(matriz[l][0] + matriz[l][1] + matriz[l][2] + matriz[l][3] == 0){
                    escreva("O cliente x nao pediu nada.",l+1)
                    l--

	fim_para


		para l de 0 ate 199
           		para c de 0 ate 3
           			se(matriz[l][0] || matriz[l][1] || matriz[l][2] || matriz[l][3])
            sanduba=15*matriz[l][0]

            jar=28*matriz[l][1]

            sky=30*matriz[l][2]

           bauru=25*matriz[l][3]

           precomatriz[l]=sanduba+jar+sky+bauru

		lucromatriz+=precomatriz[l]
		

		fim_para
		
		escreva("o Lucro da matriz eh x",lucromatriz)

		escreva("HAMBURGUERIA FILIAL 1")

            para l de 0 ate 99	
		para c de 0 ate 3

                escreva("Cliente x,Informe a quantidade de hamburguers de numero y:",l+1,c+1)
                leia(filial1[l][c])

                se(filial1[l][c]>5)
                    escreva("Apenas 5 hamburguers para cada tipo.")
                    c--
                
                se(filial1[l][0] + filial1[l][1] + filial1[l][2] + filial1[l][3] == 0)
                    escreva("O cliente x nao pediu nada.",l+1)
                    l--
		
		fim_para

		para l de 0 ate 99	
		para c de 0 ate 3
	
        	   	se(filial1[l][0] || filial1[l][1] || filial1[l][2] || filial1[l][3]){
            	   sanduba=15*filial1[l][0]

	           jar=28*filial1[l][1]

	           sky=30*filial1[l][2]

	           bauru=25*filial1[l][3]

	           precofilial1[l]=sanduba+jar+sky+bauru                
           		
	           lucromatriz+=precofilial1[l]

			fim_para

		escreva("O lucro da filia 1 eh :x",lucormatriz)

		escreva("HAMBURGUERIA FILIAL 2.")
            para l de 0 ate 49	
		para c de 0 ate 3

                escreva("Cliente x,Informe a quantidade de hamburguers de numero y:",l+1,c+1)
                leia(filial2[l][c])

                se(filial2[l][c]>5)
                    escreva("Apenas 5 hamburguers para cada tipo.")
                    c--
                
                se(filial2[l][0] + filial2[l][1] + filial2[l][2] + filial2[l][3] == 0)
                    escreva("\nO cliente %d nao pediu nada.\n\n",l+1)
                    l--

                fim_para


           
            para l de 0 ate 49	
		para c de 0 ate 3
           
		se(filial2[l][0] || filial2[l][1] || filial2[l][2] || filial2[l][3])

            sanduba=15*filial2[l][0]

            jar=28*filial2[l][1]

            sky=30*filial2[l][2]

           bauru=25*filial2[l][3]

           precofilial2[l]=sanduba+jar+sky+bauru

           lucrofilial2=precofilial2

            fim_para
		
		escreva("Lucro da filial 2: x",lucrofilial2)

		lucrototal=lucrofilial1+lucrofilial2+lucromatriz
            	escreva("LUCRO TOTAL DA BURGUER LORD:x",lucrototal)


		para l de 0 ate 199
            maisvendido1+=matriz[l][0]
            maisvendido2+=matriz[l][1]
            maisvendido3+=matriz[l][2]
            maisvendido4+=matriz[l][3]
            fim_para
            para l de 0 ate 99
            maisvendido1+=filial1[l][0]
            maisvendido2+=filial1[l][1]
            maisvendido3+=filial1[l][2]
            maisvendido4+=filial1[l][3]
            fim_para
            para l de 0 ate 49
            maisvendido1+=filial2[l][0]
            maisvendido2+=filial2[l][1]
            maisvendido3+=filial2[l][2]
            maisvendido4+=filial2[l][3]
            fim_para

	//MAIS VENDIDOS
            se(maisvendido1>maisvendido2 && maisvendido1>maisvendido3 && maisvendido1>maisvendido4)
                escreva("O hamburguer mais vendido eh o Sanduba de Luz")
                maisvendido1=maior

            senao se(maisvendido2>maisvendido1 && maisvendido2>maisvendido3 && maisvendido2>maisvendido4)
                escreva("O hamburguer mais vendido eh o JarJar Burguer")
                maisvendido2=maior;
            senao se(maisvendido3>maisvendido1 && maisvendido3>maisvendido2 && maisvendido3>maisvendido4)
                escreva("O hamburguer mais vendido eh o Skywalker Burguer")
                maisvendido3=maior;
            senao se(maisvendido4>maisvendido1 && maisvendido4>maisvendido2 && maisvendido4>maisvendido3)
                escreva("O hamburguer mais vendido eh o Bauru yoda")
                maisvendido4=maior
            
//MENOS VENDIDOS

            se(maisvendido1<maisvendido2 && maisvendido1<maisvendido3 && maisvendido1<maisvendido4)
                escreva("O hamburguer menos vendido eh Sanduba de Luz")
                maisvendido1=menor
            senao se(maisvendido2<maisvendido1 && maisvendido2<maisvendido3 && maisvendido2<maisvendido4)
                escreva("O hamburguer menos vendido eh o JarJar Burguer")
                maisvendido2=menor
            senao se(maisvendido3<maisvendido1 && maisvendido3<maisvendido2 && maisvendido3<maisvendido4)
                escreva("O hamburguer menos vendido eh o Skywalker Burguer")
                maisvendido3=menor
            senao se(maisvendido4<maisvendido1 && maisvendido4<maisvendido2 && maisvendido4<maisvendido3)
                escreva("O hamburguer menos vendido eh o Bauru yoda\n")
                maisvendido4=menor
            
            diferenca=maior-menor
            
            escreva("a diferenca do mais vendido pelo menos vendido :x",diferenca)

	FIM
            






