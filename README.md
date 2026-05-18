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

<img width="708" height="900" alt="template" src="https://github.com/user-attachments/assets/a4fe5e2d-0e54-4751-a1b0-39c38ac2bb43" />
<img width="1369" height="865" alt="fluxo_aprovacao" src="https://github.com/user-attachments/assets/f0eefe71-d38c-45ba-8ccb-8bf473898228" />
<img width="502" height="891" alt="formulario" src="https://github.com/user-attachments/assets/e9d52caa-e582-45aa-857e-c0fdfb083c80" />
<img width="500" height="886" alt="tela_inicial" src="https://github.com/user-attachments/assets/b2c60b62-8790-4e27-a65d-cfdf4ca26c5e" />



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

