# Hooks 
Hooks são uma feature do react que permitem interagir com um componente sem necessariamente a necessidade de criar uma classe pra ele.

Observações:
- Hooks só podem ser chamados na camada mais externa da aplicação.
- No modo estrito, os inicializadores serão chamados duas vezes para reduzir a ocorrência de erros.

## Built-in Hooks
### useState
Declaração: const [ |variável de estado| , |função de alteração| ] = useState( |valor inicial| )

A variável irá armazenar o valor dado.

A função de alteração irá mudar o valor da variável de estado, e pode ser usada de dois jeitos:
- Passando um valor literal.
- Passando uma função que irá receber como argumento o último valor armazenado e retornar o próximo valor.

Observações:
- A variável de estado funciona apenas pra leitura, por isso não é possível alterá-la.
- Se uma função for passada para useState, ela será executada apenas na inicialização.
- A mudança da variável de estado só ocorrerá depois do código responsável pela sua alteração for finalizado.
Ex:
```
const [age, setAge] = useState(12);

function birthday(){
    setAge(age + 1)
    console.log(age)
}

birthday() // Vai printar 12
```
- Se eu chamar a função de alteração mais de uma vez passando um valor literal, o valor só será alterado uma vez, algo que não acontecerá se for passada uma função.
- Caso a variável de estado seja um tipo de dado composto, é necessário criar elemento diferente toda vez que ele for alterado.
- É possível resetar um componente alterando uma variável de estado atrelado a ele no atributo key.

### useEffect
Serve para lidar com efeito colateral de algumas funções, por exemplo funções que fazem requisições e demoram um pouco para serem executadas, e garantir que os valores que estão na função só sejam usados quando receberem um valor válido.

Declaração: useEffect( |função|, |variáveis "instáveis"| )

# Eventos
Eventos são características de cada tag, como por exemplo clicar num botão ou alterar o texto de um input, geralmente seguindo essa estrutura:

\<|tag|  |atributo|={ |função| }\>

E é possível atribuir uma função que receberá um objeto de evento, que conterá informações do objeto quando o evento ocorreu.
