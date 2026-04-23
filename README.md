# Sprint-1-Projeto-Sustentavel-em-Arquitetura-de-Computadores

# Projeto RAIOS 
Sistema Inteligente de Recarga com Baixo Consumo Computacional 
 
## Integrantes 
- Vinicius Sanches Chiarle - 568846 
- Mateus Felipe Curtale Serafim - 571129 
- Rafaella Ferreira De Moraes  -  571030 
- Aneliza Rondina Bonafé - 572977 
- Jeferson dos Santos Oliveira - 572594 

## 🚨 Problema 
Eletropostos utilizam software de alto nível e hardware genérico, resultando em alto consumo energético e baixa eficiência computacional. 
 
## 📌 Justificativa 
Com o crescimento da mobilidade elétrica, otimizar o consumo energético dos sistemas de recarga é essencial para sustentabilidade. 
 
## Proposta de Solução 
Desenvolver um módulo em Assembly para controlar: 
- Autenticação 
- Monitoramento de energia 
- Controle de carga 
 
##️ Arquitetura Utilizada 
- RISC-V 
- Pipeline 
- Execução otimizada 
 
## Exemplo de Código - Módulo de Controle
```assembly 
# Registradores:
# t0 = A (autenticado)
# t1 = B (carro conectado)
# t2 = C (bateria cheia)
# t3 = S (liberar recarga)
# t4 = corrente
# t5 = potencia PWM
main:
# Leitura de sensores
lw t4, 0x40000000
lw t1, 0x40000010
lw t2, 0x40000020
lw t0, 0x40000030
# Lógica: S = A AND B AND NOT C
xori t6, t2, 1
and  t7, t0, t1
and  t3, t7, t6
# Decisão
beq t3, x0, desligar
# Subida suave
addi t5, t5, 5
li   t6, 100
blt  t5, t6, aplicar
li   t5, 100
j aplicar
desligar:
addi t5, t5, -5
bge  t5, x0, aplicar
li   t5, 0
# Segurança
li   t6, 32
bgt  t4, t6, emergencia
j aplicar
emergencia:
li t5, 0
aplicar:
sw t5, 0x40000040
# Economia de energia
wfi
j main
´´´

## Relação com Eficiência e Sustentabilidade 
A solução impacta diretamente: 
Eficiência Energética 
● menos ciclos de CPU → menor consumo elétrico 
● menor dissipação de calor 
# Sustentabilidade 
● redução da pegada energética dos sistemas 
● maior eficiência em larga escala 
# Integração com Energias Renováveis 
● melhor aproveitamento de energia solar ou outras fontes 
● menor desperdício computacional em sistemas inteligentes
