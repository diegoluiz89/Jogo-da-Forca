# Jogo-da-Forca

#include <iostream>
#include <stdlib.h>

using namespace std;

int main (){

    char palavra [30], letra [1], secreta [30];
    int tam,ind,chances,acertos;
    bool acerto = false;

    chances = 6;
    tam = 0;
    ind = 0;
    acerto = false;
    acertos = 0;

    cout << "Fale para seu amigo tampar os olhos e digite a palavra secreta: ";
    cin >> palavra;
    system("cls");

    while (palavra[ind] != '\0'){
        ind++;
        tam++;
    }

    for (ind=0; ind<30; ind++){
        secreta[ind] = '-';
    }

    while ((chances > 0)and(acertos < tam)){
        cout << "Chances Restantes: " << chances << "\n\n";
        cout << "Palavra Secreta: ";
        for (ind=0; ind<tam; ind++){
            cout << secreta[ind];
        }
        cout << "\n\nDigite uma letra: ";
        cin >> letra [0];
        for(ind=0; ind<tam; ind++){
            if(palavra[ind]==letra[0]){
                acerto=true;
                secreta[ind] = palavra [ind];
                acertos++;
            }
        }
        if(!acerto){
            chances--;
        }
        acerto=false;
        system("cls");
    }

    if(acertos==tam){
        cout << "Voce Venceu";
    }
    else{
        cout << "Voce Perdeu";
    }

    return 0;
}
