# 🚀 Sistema de Gestão e Automação de Solicitações de Transporte

Este repositório contém a documentação técnica e a arquitetura da solução desenvolvida para otimizar e automatizar o fluxo de requisições de transporte corporativo utilizando o ecossistema Microsoft Power Platform.

---

## 📊 Impacto de Negócio Registrado
* **Eficiência Operacional:** Redução de mais de **4 horas diárias de trabalho manual** da equipe administrativa.
* **Integridade de Dados:** Eliminação de 100% dos erros de concorrência e perda de dados causados pelo uso compartilhado de planilhas.
* **Padronização:** Transformação de requisições textuais livres em um fluxo de dados 100% estruturado e controlado.

---

## 📄 O Desafio (Cenário Antigo)
O processo operava de forma descentralizada e manual, gerando gargalos operacionais e vulnerabilidade na segurança dos dados:
1. **Falta de Padronização:** Usuários enviavam e-mails com textos livres, resultando na ausência de dados cruciais para o agendamento.
2. **Concorrência de Dados:** A equipe administrativa transcrevia os e-mails para um Excel Online. Com mais de 7 pessoas editando o arquivo simultaneamente, fórmulas eram apagadas e dados eram perdidos frequentemente.
3. **Sobrecarga Administrativa:** Após definir o motorista, a equipe redigia e respondia manualmente os e-mails para cada solicitante.

---

## 🛠️ A Solução Desenvolvida (Cenário Atual)

### 📱 Front-end: Power Apps (Canvas App)
Desenvolvimento de uma interface intuitiva, segura e responsiva para a entrada de dados.
* **Entrada Controlada:** Substituição do e-mail livre por um formulário com regras de validação rigorosas.
* **Módulo Administrativo:** Visão restrita para gestores avaliarem pendências, permitindo o deferimento rápido e atribuição do motorista.

### ⚙️ Back-end e Automação: Power Automate
Implementação de um fluxo de trabalho inteligente que eliminou a necessidade de intervenção humana nas notificações:
* **Comunicação Visual Premium:** Envio de e-mails automatizados formatados em **HTML e CSS** personalizados, garantindo uma identidade visual limpa e profissional.

---

## 📸 Demonstração Visual


<img width="365" height="611" alt="inicio" src="https://github.com/user-attachments/assets/241f032d-31ed-46cc-831e-ba7934e12a4a" />
<img width="502" height="891" alt="formulario" src="https://github.com/user-attachments/assets/5f13b8e3-f9e5-48db-b637-cc4cc3dd9c5e" />
<img width="1369" height="865" alt="fluxo_aprovacao" src="https://github.com/user-attachments/assets/6241c233-1979-4c95-9125-52b0efa39f2f" />
<img width="708" height="900" alt="template" src="https://github.com/user-attachments/assets/fa9549c5-43f3-45b4-80d5-b9cea3782c7d" />
<img width="696" height="527" alt="negativa" src="https://github.com/user-attachments/assets/a8d2e34f-998f-4d24-b8b8-751ccc0321ce" />



---

## ⚡ Diferenciais Técnicos & Código (Power FX)

Abaixo está um exemplo da lógica aplicada no botão de submissão do formulário, garantindo a validação dos campos obrigatórios e a persistência correta dos dados:

```powerfx
// Exemplo de validação e submissão utilizando ponto e vírgula como separador
If(
    IsBlank(DataInício.SelectedDate) ; 
    Notify("A data de início é obrigatória." ; NotificationType.Error) ;
    SubmitForm(FormularioTransporte)
)

