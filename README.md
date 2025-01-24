# Requisitos de Negócio: Calculadora do Ciclo do Sono

## **Objetivo Geral**
A aplicação de calculadora do ciclo do sono tem como objetivo ajudar os usuários a identificar os melhores horários para dormir e acordar, otimizando a qualidade do sono com base em ciclos de sono de 90 minutos. A aplicação considera o tempo que o ser humano leva para adormecer (latência do sono), bem como outros fatores como idade, histórico de sono, fusos horários e hábitos pessoais.

---

## **Requisitos Funcionais**

### **1. Cadastro de Usuário**
- O sistema deve permitir que o usuário crie uma conta fornecendo nome, e-mail e senha.
- O usuário pode se registrar com credenciais tradicionais (e-mail/senha) ou com login social (Google, Facebook).
- O sistema deve validar a idade do usuário no momento do cadastro para personalizar as recomendações de sono.

### **2. Definir Horário de Acordar**
- O sistema deve permitir que o usuário informe o horário que deseja acordar.
- O sistema deve calcular e exibir os horários ideais para o usuário dormir, considerando:
  - Ciclos de sono de 90 minutos.
  - Tempo médio de latência do sono (10-20 minutos).
- O usuário deve visualizar pelo menos 3 horários sugeridos para dormir.

### **3. Personalizar Latência do Sono**
- O sistema deve permitir que o usuário personalize o tempo que leva para adormecer (latência), com valores entre 5 e 30 minutos.
- A personalização da latência deve ser refletida nos cálculos de horários ideais para dormir.
- Caso o usuário não personalize, o sistema deve usar um valor padrão de 15 minutos.

### **4. Calcular Horário Ideal com Base na Idade**
- O sistema deve ajustar a quantidade recomendada de sono de acordo com a faixa etária do usuário:
  - **Crianças (6-12 anos)**: 9-12 horas de sono.
  - **Adolescentes (13-18 anos)**: 8-10 horas de sono.
  - **Adultos (19-64 anos)**: 7-9 horas de sono.
  - **Idosos (65+ anos)**: 7-8 horas de sono.
- O sistema deve usar essas recomendações ao calcular os horários de dormir, garantindo que o usuário atinja a quantidade ideal de horas de sono.

### **5. Sugestões de Horários Baseadas em Ciclos de Sono**
- O sistema deve calcular os horários de dormir com base em múltiplos de 90 minutos (ciclos de sono completos), ajustando pela latência e hora de acordar.
- As sugestões devem ser exibidas ao usuário em uma interface amigável, permitindo que ele escolha o horário mais adequado.
- O sistema deve oferecer pelo menos três opções de horários para o usuário se deitar.

### **6. Configuração de Notificações para Dormir**
- O usuário deve poder configurar notificações para ser alertado 30 minutos antes dos horários sugeridos para dormir.
- O sistema deve permitir a configuração de dias e horários em que as notificações serão enviadas.
- As notificações devem ser ajustáveis conforme a rotina de sono do usuário.

### **7. Acompanhamento da Qualidade do Sono**
- O sistema deve permitir que o usuário registre e acompanhe a qualidade do sono após cada noite, usando critérios como:
  - Horário em que dormiu e acordou.
  - Sensação de descanso (escala de 1 a 5).
  - Número de despertares noturnos ou dificuldade para dormir.
- O sistema deve gerar gráficos de acompanhamento de qualidade do sono em intervalos diários, semanais e mensais.

### **8. Sugestões de Melhora de Hábitos de Sono**
- O sistema deve sugerir mudanças de hábitos de sono com base no histórico de sono do usuário, considerando fatores como:
  - Horários irregulares de dormir e acordar.
  - Quantidade insuficiente de horas dormidas.
  - Qualidade do sono registrada.
- As sugestões devem ser apresentadas em uma interface simples, e o usuário pode optar por seguir ou ignorar as recomendações.

### **9. Considerar Fuso Horário**
- O sistema deve identificar automaticamente o fuso horário do usuário e ajustar os horários de dormir e acordar de acordo.
- O usuário deve poder configurar manualmente o fuso horário, se necessário.
- As notificações e sugestões de sono devem ser ajustadas conforme o fuso horário configurado.

---

## **Requisitos Não Funcionais**

### **1. Performance**
- O cálculo dos ciclos de sono e as sugestões de horários devem ser exibidos ao usuário em menos de 2 segundos após a entrada do horário de despertar.
- O sistema deve ser capaz de lidar com até 10.000 usuários simultaneamente sem degradação de performance.

### **2. Escalabilidade**
- O sistema deve ser escalável horizontalmente para atender a um grande número de usuários em diferentes fusos horários e regiões.
- A aplicação deve ser desenvolvida utilizando uma arquitetura modular que permita a adição de novos recursos facilmente.

### **3. Disponibilidade**
- O sistema deve ter uma disponibilidade de 99,9%, garantindo que os usuários possam acessar as funcionalidades a qualquer momento.
- O sistema deve ser acessível em múltiplas plataformas, incluindo web e dispositivos móveis.

### **4. Usabilidade**
- A interface deve ser amigável e acessível, com foco na simplicidade de uso para pessoas de todas as idades.
- A aplicação deve ser responsiva e adaptada para diferentes tamanhos de tela, especialmente dispositivos móveis.

---

## **Regras de Negócio**

1. **Cálculo de Ciclos de Sono**:
   - Cada ciclo de sono tem 90 minutos.
   - O sistema deve calcular os horários de dormir retroativamente com base no horário de acordar, sempre incluindo o tempo de latência do sono (de 10 a 20 minutos ou personalizado pelo usuário).

2. **Idade e Recomendação de Sono**:
   - As recomendações de horas de sono são ajustadas com base na idade do usuário.
   - O sistema deve garantir que as sugestões de horários de dormir resultem na quantidade mínima recomendada de horas de sono.

3. **Latência do Sono**:
   - O sistema deve considerar que o usuário leva, em média, de 10 a 20 minutos para adormecer.
   - Esse tempo deve ser configurável pelo usuário, com valores entre 5 e 30 minutos.

4. **Histórico e Qualidade do Sono**:
   - O sistema deve armazenar o histórico de sono do usuário por no mínimo 12 meses para exibir relatórios e gráficos de desempenho.

5. **Fuso Horário**:
   - O sistema deve ajustar automaticamente os cálculos de acordo com o fuso horário do usuário, ou permitir a configuração manual.

---

## **Casos de Uso Importantes**

1. **Calcular horário ideal para dormir com base no horário de acordar.**
2. **Personalizar tempo de latência do sono.**
3. **Registrar e acompanhar a qualidade do sono.**
4. **Configurar notificações para dormir.**
5. **Gerar sugestões de melhora de hábitos de sono.**
6. **Ajustar cálculos de sono de acordo com o fuso horário.**

---

