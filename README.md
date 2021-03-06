# PPA-Contatto-Tasmota

Documentação do [PPA Contatto](https://www.ppa.com.br/produtos/acessorios-e-centrais/contatto-wi-fi) para uso com Tasmota.



## Layout da placa

![Placa PPA Contatto](board.jpg)

Instalar o firmware de acordo com a [documentação oficial do Tasmota](https://tasmota.github.io/docs/Getting-Started/).



## Tasmota template

```json
{"NAME":"PPA Contatto","GPIO":[0,0,32,0,224,162,0,0,288,225,0,0,0,0],"FLAG":0,"BASE":18}
```

| GPIO   | Descrição           |
|--------|---------------------|
| GPIO2  | Button 1            |
| GPIO4  | Relay 1             |
| GPIO5  | Switch 3 (fio azul) |
| GPIO12 | Led 1               |
| GPIO13 | Relay 2             |

Também disponível no [Blakadder Devices Repository](https://templates.blakadder.com/ppa_contatto_P06809.html).



## Configuração recomendada

| Comando          | Descrição                            |
|------------------|----------------------------------------------------------------------------------------------------------------------------|
| `PulseTime2 5`   | Configura o tempo de acionamento da botoeira para 0.5s.                                                                    |
| `SetOption114 1` | Desconecta os switches dos respectivos relays ([mais informações](https://tasmota.github.io/docs/Commands/#setoption114)). |



## Fios

| Cor      | Id  | Descrição                            |
|----------|-----|--------------------------------------|
| Vermelho | VCC | 12Vdc da central                     |
| Preto    | GND | GND da central                       |
| Laranja  | BOT | Botoeira para acionar o portao       |
| Branco   | FC  | Fim de curso de fechamento           |
| Cinza    | NF  | Normalmente fechado do relé auxiliar |
| Amarelo  | CM  | Comum do relé auxiliar               |
| Verde    | NA  | Normalmente aberto do relé auxiliar  |
| Azul     |     | GPIO5                                |



## Observações

- Azul / GPIO5:
  - Normalmente fica com +3.3V (Switch: ON) 
  - Ligar em GND para desativar (Switch: OFF)
- Branco / FC
  - Normalmente fica com +1.5V?
  - Afeta o GPIO16 de alguma forma (as vezes?) mas nao conseugui identificar exatamente.
