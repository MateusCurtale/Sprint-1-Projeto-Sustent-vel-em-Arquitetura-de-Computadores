# Sprint-1-Projeto-Sustent-vel-em-Arquitetura-de-Computadores

# Projeto RAIOS 
Sistema Inteligente de Recarga com Baixo Consumo Computacional 
 
## Integrantes 
- Vinicius Sanches Chiarle - 568846 
- Mateus Felipe Curtale Serafim - 571129 
- Rafaella Ferreira De Moraes  -  571030 
-Aneliza Rondina Bonafé - 572977 
-Jeferson dos Santos Oliveira - 572594 

 
##🚨 Problema 
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
 
## Exemplo de Código 
```assembly 
lw $t0, 0($s0) 
beq $t0, $zero, erro
