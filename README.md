# Cifras de Substituição e Transposição

Este projeto implementa duas técnicas de criptografia: **Cifra de César** (substituição) e **Cifra de Transposição Colunar** (transposição). Ambas as cifras incluem capacidades de criptografia, decriptografia e criptoanálise.

## Funcionalidades

### Cifra de César (substitution.py)
- **Criptografia**: Criptografa texto usando cifra de César com valor de deslocamento (chave) especificado
- **Descriptografia**: Descriptografa texto da cifra de César com chave conhecida
- **Análise de Frequência**: Encontra automaticamente a chave mais provável analisando frequências de letras em português
- **Ataque de Força Bruta**: Testa todas as chaves possíveis (0-25) para quebrar a cifra

### Cifra de Transposição Colunar (permutation.py)
- **Criptografia**: Criptografa texto usando transposição colunar com chave alfabética
- **Descriptografia**: Descriptografa texto da cifra de transposição com chave conhecida
- **Análise de Frequência**: Usa análise de frequência de dígrafos e trígrafos para encontrar a chave mais provável
- **Ataque de Força Bruta**: Testa todas as permutações possíveis de uma chave de 4 letras

#### Funcionamento da Análise de Frequência na Transposição

Diferentemente da cifra de substituição, onde cada letra é substituída por outra, na transposição apenas a ordem das letras muda. Por isso, não é possível aplicar análise de frequência diretamente. 

A solução implementada combina força bruta com análise de frequência: o algoritmo testa todas as permutações possíveis de chaves de 4 letras e, para cada resultado, analisa a frequência de dígrafos e trígrafos em português. A chave que gera o texto com maior pontuação de frequência (mais "legível") é considerada a mais provável.

## Como Executar
#### Cifra de César
1. Abra um terminal/prompt de comando
2. Navegue até o diretório do projeto
3. Execute o programa da cifra de César:
   ```bash
   python substitution.py
   ```
4. Siga o menu interativo:
   - **Opção 1**: Criptografar uma mensagem (requer texto claro e chave de deslocamento 0-25)
   - **Opção 2**: Descriptografar uma mensagem (requer texto cifrado e chave de deslocamento)
   - **Opção 3**: Quebrar cifra usando análise de frequência (requer apenas texto cifrado)
   - **Opção 4**: Quebrar cifra usando força bruta (requer apenas texto cifrado)
   - **Opção 5**: Sair do programa

#### Cifra de Transposição Colunar
1. Abra um terminal/prompt de comando
2. Navegue até o diretório do projeto
3. Execute o programa da cifra de transposição:
   ```bash
   python permutation.py
   ```
4. Siga o menu interativo:
   - **Opção 1**: Criptografar uma mensagem (requer texto claro e chave alfabética sem letras repetidas)
   - **Opção 2**: Descriptografar uma mensagem (requer texto cifrado e a chave correta)
   - **Opção 3**: Quebrar cifra usando análise de frequência (requer apenas texto cifrado)
   - **Opção 4**: Quebrar cifra usando força bruta (requer apenas texto cifrado, limitado a chaves de 4 letras)
   - **Opção 5**: Sair do programa


## Observações
- Os métodos de análise de frequência funcionam melhor com textos mais longos 
- Ataques de força bruta mostrarão todas as descriptografias possíveis - inspeção manual é necessária para identificar o texto claro correto
- Ambas as técnicas de criptoanálise funcionam apenas para textos criptogrados de um texto em português