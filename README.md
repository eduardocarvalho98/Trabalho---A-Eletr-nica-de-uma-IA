# Projeto de Sensores com ESP32


## Objetivo do Projeto

Este projeto tem como objetivo integrar e controlar múltiplos sensores utilizando um ESP32, com o intuito de monitorar a distância, a temperatura, a umidade, a intensidade da luz e detectar movimentos. O sistema foi desenvolvido para ser facilmente configurado e testado no Wokwi (simulador de circuitos) e também pode ser executado diretamente no hardware com um ESP32.

O projeto utiliza:
- **Sensor Ultrassônico HC-SR04** para medir distâncias.
- **Sensor DHT22** para medir temperatura e umidade.
- **Sensor de Luz** (LDR ou sensor de fototransistor) para detectar a intensidade da luz ambiente.
- **Sensor PIR** para detecção de movimento.
- **LED** para sinalizar o estado do sensor PIR (ligado/desligado).
## Integrantes

Eduardo Carvalho Santos - RM559438
Gustavo Rocha De Castro - RM5608318
Jhonatan Salles - RM554190

## Desenho do Circuito Completo

![Diagrama do Circuito]([https://via.placeholder.com/600x400.png](https://prnt.sc/_0E81f6cMz4O))  
*Substitua a URL da imagem com o link do diagrama do seu circuito.*

## Descrição do Papel de Cada Sensor no Sistema

1. **Sensor Ultrassônico HC-SR04**: 
   - O HC-SR04 é responsável por medir a distância do objeto mais próximo. Ele emite um sinal de ultrassom e calcula o tempo que o sinal leva para retornar ao sensor, permitindo calcular a distância em centímetros ou polegadas.

2. **Sensor DHT22**: 
   - O DHT22 mede a temperatura e a umidade do ambiente. Ele envia esses dados ao ESP32, que os exibe no monitor serial.

3. **Sensor de Luz (LDR)**: 
   - O LDR detecta a intensidade da luz ambiente. Seu valor é lido como um valor analógico e classificado em diferentes níveis de luminosidade (escuro, baixo, médio, brilhante e muito brilhante).

4. **Sensor PIR**:
   - O sensor PIR detecta movimento no ambiente. Quando o movimento é detectado, ele aciona o LED e envia uma mensagem ao monitor serial indicando que o movimento foi detectado ou encerrado.

5. **LED**:
   - O LED é usado como um indicador visual para a detecção de movimento. Ele acende quando o sensor PIR detecta movimento e apaga quando o movimento é interrompido.

## Como Configurar e Rodar o Projeto no Wokwi e ESP32

### No Wokwi:
1. Acesse [Wokwi](https://wokwi.com/projects/413990387359571969)
2. Execute a simulação
### No Hardware com ESP32:
1. Conecte os sensores e o LED aos pinos conforme descrito acima.
2. Conecte o ESP32 ao seu computador e abra a IDE do Arduino.
3. Selecione o modelo correto da placa (ESP32) e a porta serial.
4. Carregue o código no ESP32.
5. Abra o Monitor Serial na IDE do Arduino para visualizar os dados dos sensores em tempo real.

## Instruções de Instalação e Dependências

Este projeto requer a instalação da biblioteca **DHTesp** para o sensor DHT22.

### Instalar a Biblioteca DHTesp:
1. Abra a IDE do Arduino.
2. Vá para **Sketch** > **Incluir Biblioteca** > **Gerenciar Bibliotecas**.
3. Pesquise por **DHTesp** e instale a biblioteca.

O código está pronto para ser compilado e carregado na placa ESP32 com a IDE do Arduino.

## Testes Realizados

### Testes de Funcionalidade:
1. **Sensor Ultrassônico HC-SR04**:
   - O sensor foi testado para medir distâncias de objetos à frente.
   - **Exemplo de saída**:
     ```
     Distância (cm): 30.75
     Distância (inch): 12.09
     ```
     O sensor foi capaz de medir distâncias de 10 a 400 cm com precisão.

2. **Sensor DHT22**:
   - O sensor foi testado para medir temperatura e umidade em diferentes condições ambientais.
   - **Exemplo de saída**:
     ```
     Temperatura: 22.50°C
     Umidade: 65.2%
     ```
     O DHT22 forneceu leituras precisas de temperatura entre 0 a 50°C e umidade de 0 a 100%.

3. **Sensor de Luz (LDR)**:
   - O sensor foi testado para detectar mudanças na intensidade da luz ambiente e classificar em diferentes níveis.
   - **Exemplo de saída**:
     ```
     Analog Value = 712 => Dim
     ```
     A intensidade de luz foi classificada como "Dim" com valor analógico de 712. A leitura foi realizada com uma lâmpada de baixa intensidade.

4. **Sensor PIR**:
   - O sensor foi testado para detectar movimento no ambiente e acionar o LED correspondente.
   - **Exemplo de saída**:
     ```
     Motion detected!
     ```
     Após o movimento ser interrompido:
     ```
     Motion ended!
     ```

## Conclusão

Este projeto oferece uma forma simples de integrar vários sensores com o ESP32 para monitoramento ambiental. Ele pode ser expandido para outras aplicações, como sistemas de alarme, automação residencial ou monitoramento remoto. Durante os testes, os sensores mostraram funcionar de maneira confiável, com leituras precisas de distância, temperatura, umidade e luz, além de um comportamento eficaz na detecção de movimento. A integração entre sensores permite um sistema eficiente para monitoramento e controle.

Sinta-se à vontade para modificar e melhorar este projeto de acordo com suas necessidades.
