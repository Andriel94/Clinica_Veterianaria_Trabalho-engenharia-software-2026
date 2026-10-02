# trabalho-engenharia-software-2026
Trabalho de clínica veterinária do Técnico em Informática, segundo semestre de 2026.
https://www.figma.com/design/tfM8Nz7j2IhWiDiP5KNTXz/Sem-t%C3%ADtulo?node-id=0-1&m=dev&t=8ET3fFTOcIBfyKrZ-1

##Diagramas UML
###Diagrama de caso de uso
```mermaid
flowchart LR

    cliente["cliente"]
    pet["pet"]
    atendente["atendente"]
    veterinario["veterinario"]

    consulta["consulta"]
    exame_veteinario["exame_veteinario"]
    furmulario_da_consulta["furmulario_da_consulta"]

    cliente -- tem --> pet 
    cliente --> atendente -- "marca/remarca" --> consulta
    consulta -- "chega para" --> veterinario --> exame_veteinario -- "examina" --> pet
    exame_veteinario -- "preenche" --> furmulario_da_consulta
    furmulario_da_consulta -- "vai para" --> cliente
```
###Diagrama de classe
```mermaid
classDiagram
    class pessoa{
        -CPF:String
        +darCPF() String
    }
    class atendente{

    }
     class veterinario{
        pet -- cliente   

    }
     class cliente{
        -animais: lista de animais

    }
    class pet{
        -dono: Cliente
    }
```
