# Trabalho Engenharia Software 2026
Trabalho de clínica veterinária do Técnico em Informática, segundo semestre de 2026.
https://www.figma.com/design/tfM8Nz7j2IhWiDiP5KNTXz/Sem-t%C3%ADtulo?node-id=0-1&m=dev&t=8ET3fFTOcIBfyKrZ-1

##Diagramas UML
###Diagrama de caso de uso
```mermaid
flowchart LR
    cliente(["Cliente"])
    pet(["Pet"])
    atendente(["Atendente"])
    veterinario(["Veterinário"])
    
    consulta["Consulta"]
    exame["Exame Veterinário"]
    formulario["Formulário da Consulta"]

    cliente -- "tem" --> pet
    cliente --> atendente
    atendente -- "marca / remarca" --> consulta
    consulta -- "é realizada por" --> veterinario
    veterinario -- "realiza" --> exame
    exame -- "examina" --> pet
    veterinario -- "preenche" --> formulario
    formulario -- "é entregue ao" --> cliente
```
###Diagrama de classe
```mermaid
classDiagram
    class Cliente {
        -cpf: String
        -nome: String
        -telefone: String
        -email: String
        +cadastrar()
        +agendarConsulta()
        +receberFormulario()
    }

    class Pet {
        -nome: String
        -especie: String
        -raca: String
        -idade: int
        -dono: Cliente
        +atualizarDados()
    }

    class Atendente {
        -matricula: String
        -nome: String
        +marcarConsulta()
        +remarcarConsulta()
        +cadastrarCliente()
    }

    class Veterinario {
        -crmv: String
        -nome: String
        -especialidade: String
        +realizarConsulta()
        +realizarExame()
        +preencherFormulario()
        +emitirReceita()
    }

    class Consulta {
        -data: Date
        -horario: String
        -status: String
        +agendar()
        +cancelar()
        +realizar()
    }

    class ExameVeterinario {
        -tipo: String
        -resultado: String
        -data: Date
        +realizar()
        +registrarResultado()
    }

    class FormularioConsulta {
        -diagnostico: String
        -observacoes: String
        -receita: String
        +preencher()
        +entregarCliente()
    }

    %% Relacionamentos
    Cliente "1" --> "*" Pet : possui
    Cliente --> Atendente : solicita
    Atendente --> Consulta : marca/remarca
    Consulta --> Veterinario : é realizada por
    Veterinario --> ExameVeterinario : realiza
    ExameVeterinario --> Pet : examina
    Veterinario --> FormularioConsulta : preenche
    FormularioConsulta --> Cliente : é entregue a
```
