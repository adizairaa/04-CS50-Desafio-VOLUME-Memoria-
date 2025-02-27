# Projeto: Manipulação de Arquivos WAV

## Descrição
Este projeto implementa um programa em C que altera o volume de arquivos de áudio no formato WAV. A manipulação é feita escalando cada amostra de áudio por um fator determinado pelo usuário. O programa recebe três argumentos: o nome do arquivo de entrada (input), o nome do arquivo de saída (output) e o fator de escalonamento do volume.

## Conceitos Utilizados
- Manipulação de arquivos em C com `fopen`, `fread` e `fwrite`
- Uso de tipos de dados da biblioteca `stdint.h` (`uint8_t` para cabeçalhos e `int16_t` para amostras de áudio)
- Processamento de dados binários
- Operações matemáticas para ajuste de volume
- Boas práticas de alocação de memória

## Como Configurar o Ambiente
1. Faça login no ambiente [CS50 IDE](https://ide.cs50.io) usando sua conta do GitHub.
2. No terminal, crie um diretório para o exercício:
   ```sh
   mkdir pset4
   ```
3. Acesse o diretório criado:
   ```sh
   cd pset4
   ```
4. Baixe os arquivos do exercício:
   ```sh
   wget https://cdn.cs50.net/2023/fall/psets/4/volume.zip
   ```
5. Extraia os arquivos:
   ```sh
   unzip volume.zip
   ```
6. Remova o arquivo ZIP para economizar espaço:
   ```sh
   rm volume.zip
   ```
7. Acesse o diretório do projeto:
   ```sh
   cd volume
   ```

## Implementação
O programa modifica o volume de um arquivo WAV seguindo os seguintes passos:
1. Lê o cabeçalho do arquivo WAV (44 bytes) e o copia para o arquivo de saída.
2. Processa cada amostra de áudio (16 bits), multiplicando-a pelo fator fornecido.
3. Salva as novas amostras no arquivo de saída.

### Estrutura do Código
- O programa define `HEADER_SIZE = 44` para indicar o tamanho do cabeçalho.
- Utiliza `uint8_t` para armazenar o cabeçalho e `int16_t` para armazenar as amostras de áudio.
- Lê os dados de entrada, aplica a modificação e grava no arquivo de saída.

### Exemplo de Uso
```sh
./volume input.wav output.wav 2.0
```
Este comando criará um novo arquivo WAV com o dobro do volume do original.

```sh
./volume input.wav output.wav 0.5
```
Este comando criará um novo arquivo WAV com metade do volume do original.

## Testando o Código
Para verificar a precisão da implementação, use o `check50`:
```sh
check50 cs50/problems/2024/x/volume
```
Para verificar a formatação do código, use o `style50`:
```sh
style50 volume.c
```

## Contribuição
Sinta-se à vontade para contribuir com melhorias! Você pode abrir issues ou enviar pull requests.

## Licença
Este projeto segue a licença MIT. Sinta-se livre para usá-lo e modificá-lo.

