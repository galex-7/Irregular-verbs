//# Irregular-verbs
//Ayuda para estudiar cualquiera de los 103 verbos establecidos

#include <stdlib.h>
#include <time.h>
#include <iostream>
#include <fstream>

using namespace std;

int main(){
  ifstream fin("ingles.txt");
  int i=0, c=0, num=0, num1=0, num2=0, resp=0;
  string simple, past, participle, compara[103], compara1[103], compara2[103],texto, opcion1, opcion2;

  for(i=0;i<=102;i++){
    compara[i]=simple;
    compara[i]=past;
    compara[i]=participle;
  }

  do{
  cout<<endl<<"Ingresa la opcion que quieres consultar: "<<endl<<endl;
  cout<<" 1-Lista de verbos"<<endl;
  cout<<" 2-Consulta de verbo espesifico"<<endl;
  cout<<" 3-Adivina el verbo"<<endl;
  cin>>num;

if(num==1){
  for(i=0;i<=102;i++){
    cout<<i<<" Base form: "<<compara[i]<<endl;
    cout<<"Simple past: "<<compara1[i]<<endl;
    cout<<"Past Participle: "<<compara2[i]<<endl<<endl;
  }
}

if(num==2){
  cout<<"Ingresa el verbo que quieres buscar :";
  cin>>texto;
  for(i=0;compara[i]!=texto;++i){
  }
  cout<<endl<<"Simple past: "<<compara1[i]<<endl;
  cout<<"Past Participle: "<<compara2[i]<<endl<<endl;
}

if(num==3){
  cout<<"¿Cuantos verbos quieres adivinar? "<<endl;
  cin>>num2;
  srand(time(NULL));
  for(c=1;c<=num2;c++){
    num1=rand() % (103);

    cout<<"Escribe los tiempos faltantes de: "<<compara[num1]<<endl<<"Simple past: ";
    cin>>opcion1;
    if(opcion1==compara1[num1]){
      cout<<" Bien"<<endl;
    }
    else{
      cout<<" La respuesta es: "<<compara1[num1]<<endl;
    }
    cout<<"Past participle: ";
    cin>>opcion2;
    if(opcion2==compara2[num1]){
      cout<<" Bien"<<endl<<endl;
    }
    else{
      cout<<" La respuesta es: "<<compara2[num1]<<endl<<endl;
    }
  }
}

cout<<endl<<"¿Quieres terminar el programa? escribe 1=Si/2=No"<<endl;
cin>>resp;
}while(resp==2);
return 0;
}
