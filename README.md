# HelloWord
first  repository

/*
A empresa Productivity Corporation classifica a produtividade anual de seus funcionários em quatro níveis:
(1) Excelente, (2) Bom, (3) Regular ou (4) Ruim.
De acordo com a classificação do nível de produtividade do funcionário, a empresa concede ao mesmo uma gratificação anual, proporcional ao seu salário base:
Excelente – 100%, Bom – 70%, Regular – 40% e Ruim – 10%.

/*Faça um programa para auxiliar a empresa Productivity no cálculo das gratificações de um conjunto de funcionários e na geração de relatórios, 
 * conforme especificado a seguir:

O programa deve ler, para cada funcionário o número de matrícula, o salário base e o nível de produtividade (1, 2, 3 ou 4) do mesmo.ok

 Deve-se calcular e mostrar, para cada funcionário, a matrícula e o valor da gratificação do mesmo: ok
 
Cada número de matrícula deve ser validado para valores maiores ou iguais a zero (>=0), sendo que a entrada de matrícula zero 
indica a finalização da leitura de dados dos funcionários;ok

Os salários devem ser validados para valores maiores que R$0.00 ;ok

Os níveis de produtividade devem ser validados para valores entre 1 e 4.
Deve-se calcular e mostrar para cada funcionário:
 a matrícula e o valor da sua gratificação.ok
 
Deve-se calcular e mostrar a média das gratificações pagas aos funcionários com nível de produtividade (2) Bom. ok

(OBS: Atenção para o caso de não existirem funcionários com essa classificação).ok

Deve ser computado o funcionário com a maior gratificação e mostrado sua matrícula e o valor de sua gratificação.


public class avaliacao2 {

	public static void main(String[] args) {
		//variáveis
		int produtividade, matricula, contador=0;
		Double salarioBase, gratificacao, media=0.0 , bom; 
		int i=0;
		int max=10;//numero  de funcionários
		
		//estrutura de repetição
		while(i<max) {
			
		matricula = InOut.leInt("Insira o número de  matricula");
		
		if (matricula ==0 ) {
		System.exit(0); // se o número igual a zero o programa termina 
		}
		salarioBase = InOut.leDouble("Insira o salário base");
		if (salarioBase==0) {
		System.exit(0); // se o salário = 0 o programa termina 
		}
		produtividade = InOut.leInt("Insira o nível de produtividade (1) Excelente, (2) Bom, (3) Regular ou (4) Ruim");
		if ( produtividade ==0 || produtividade >4) {
		System.exit(0); // se o salário = 0 o programa termina 
		}
		if ( produtividade ==1 ) { 
			salarioBase = ((salarioBase * 100) /100)*12; 
			InOut.MsgDeInformação("","Matricula "+matricula +" Exelente desempenho,  gratificação anual $"+ salarioBase); //Calculo de gratificação anual
		}
		if ( produtividade ==2 ) { 
			salarioBase = ((salarioBase * 70) /100)*12; 
			InOut.MsgDeInformação("","Matricula "+matricula +" Bom desempenho,  gratificação anual $"+ salarioBase); //Calculo de gratificação anual
			contador = contador+1;
			media = salarioBase;
		}		
		if ( produtividade ==3 ) { 
			salarioBase =( (salarioBase * 40) /100)*12; 
			InOut.MsgDeInformação("","Matricula "+matricula +"  desempenho regular,  gratificação anual $"+ salarioBase); //Calculo de gratificação anual
		}	
		if ( produtividade ==4 ) { 
			salarioBase = ((salarioBase * 40)) /100*12; 
			InOut.MsgDeInformação("","Matricula "+matricula +" desempenho ruim, gratificação anual $"+ salarioBase); //Calculo de gratificação anual
		}		
		}
		if(contador==1) {
		bom = (contador*media)/contador;
		InOut.MsgDeInformação(" ","média das gratificações pagas aos funcionários com nível de produtividade (2) Bom. $" +bom);
		}
	}

}
