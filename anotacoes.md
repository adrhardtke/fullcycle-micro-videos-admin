
## anotações
<!-- Rodar o comando para permissão de leitura e o docker conseguir ter acesso -->
`chmod +x .docker/start.sh`

<!-- não é interessante usar anemica -->
`anemica - ORM`

`mix - entidades misturadas com ORM (ricas)`
<!-- trabalharemos com a forma purista -->
`Puristas - entidades - mais possível de libs e frameworks`

# Entidades
É algo que queremos manipular, que seja único através de uma identificação, que vai se diferenciar dos demais por justamente ter essa identificação.

Ex:
*Pessoa, o identificador poderia ser um próprio ID do banco de dados, mas o mais real seria o CPF, afinal, uma pessoa só pode ter um único CPF, pra sempre.*

`Pessoa - cpf(unique) (id) chave primária.`


# Value Objects
- livres de efeitos colaterais
- imutáveis
- a ideia é sempre criar um novo VO para qualquer update que ele precise sofrer, não é mudar o mesmo, mas sim criar um novo e reatribuir aquele VO.

ex:
`class BirthDate {`
    `constructor(private readonly value: {prop1, prop2}){}`

    getValue(): string {
        return this.value
    }

    update(prop2){
        return new BirthDate({prop1: this.prop1, prop2 })
    }
`}`