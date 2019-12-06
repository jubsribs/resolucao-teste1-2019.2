# resolucao-teste1-2019.2

#include <stdio.h>

typedef struct alu{
	int idAluno; // id da aluno
	char nome[100]; // nome do aluno
	char sexo; // sexo do aluno
} Aluno;

typedef struct disc{
	int idDisciplina; // id da disicplina
	int idProfessor; // id do professor responsável
	char nome[100]; // nome da disciplina
	int vagas = 40; // total de vagas da disciplina
	int qtdAlunos = 0; //guarda a quantidade de alunos matriculados
	int idAlunosMatriculados[vagas]; /* guarda o id dos alunos matriculados. */
} Disciplina;


int main(){

	Aluno listaAluno[100];
	Disciplina listaDisciplinas[100];
	int ret;

	/* suponha que todas os idAlunosMatriculados de todas as disciplinas são inicializados com menos -1 */

	/* chamar a seguir a funcao excluirAlunoDeDisciplina e a depender do retorno informar se foi excluido ou não */

       ret = excluirAlunoDeDisciplina(20,30,listaDisciplinas);
       
       if(ret==1) printf(" Não achou o Aluno");
       if(ret==2) printf(" Não achou a Disciplina");
       if(ret==3) printf(" Aluno Excluido com Sucesso");


}

int excluirAlunoDeDisciplina( int idDisc , int idAlu , int listaDisc[]){
	int i;
	int achouDisciplina=0;
	int j;
	int achouAluno=0;
	
	for(i=0;i<100;i++){
		
		if(listaDisc[i].idDisciplina == idDisc){
			achouDisciplina = 1;
			for(j=0;j<listaDisc[i].qtdAlunos;j++){
				if(listaDisc[i].idAlunosMatriculados[j] == idAlu]){
					achouAluno=1;
	            	listaDisc[i].idAlunosMatriculados[j]=
					listaDisc[i].idAlunosMatriculados[qtdAlunos - 1];
					listaDisc[i].idAlunosMatriculados[qtdAlunos - 1]= -1;
					listaDisc[i].qtdAlunos --;
					
					return 3;
				}
			}
			if(!achouAluno) return 1;
		}
	}
	if(!achouDisciplina) return 2;
}
