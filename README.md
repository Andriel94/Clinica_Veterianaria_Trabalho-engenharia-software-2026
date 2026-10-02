# trabalho-engenharia-software-2026
Trabalho de clínica veterinária do Técnico em Informática, segundo semestre de 2026.
https://www.figma.com/design/tfM8Nz7j2IhWiDiP5KNTXz/Sem-t%C3%ADtulo?node-id=0-1&m=dev&t=8ET3fFTOcIBfyKrZ-1

##Diagrama UML
```mermaid
flowchart TD

    cliente["cliente"]
    pet["pet"]
    atendete["atendete"]
    veterinario["veterinario"]

    consulta["consulta"]
    exame_veteinario["exame_veteinario"]
    furmulario_da_culsulta["furmalrio_da_culsulta"]

    cliente -- tem --> pet 
    cliente --> atendente -- "marca/remarca" --> consulta
    consulta -- "chega para" --> veterinairo -- "examina" --> pet
    veterinairo -- "preenche" --> furmulario_da_culsulta
    furmulario_da_culsulta -- "vai para" --> cliente
 
```
