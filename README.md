# 📦 Solicitação de Materiais — ServiceNow

Solução desenvolvida no ServiceNow para digitalizar e automatizar o processo de solicitação de materiais em uma organização, eliminando solicitações informais por e-mail ou WhatsApp e centralizando tudo em um portal com rastreabilidade completa.

Projeto prático desenvolvido durante mentoria com [Renan Amorim Cavalcante](https://www.linkedin.com/in/renan-acavalcante/), simulando uma demanda real de negócio em formato de backlog.

---

## 🛠️ Tecnologias utilizadas

- **ServiceNow App Engine Studio**
- **Flow Designer**
- **Service Catalog (Record Producer)**
- **Business Rules**
- **Catalog UI Policies**
- **Source Control (GitHub)**

---

## 📋 O que foi construído

### STS0001 — Tabela e Formulário
Criação da tabela customizada para armazenar as solicitações com todos os campos necessários: solicitante, e-mail, departamento, categoria, material, quantidade, prioridade, status, justificativa e observações de atendimento.

### STS0002 — Item de Catálogo no Portal
Publicação de um **Record Producer** no Service Catalog para que o colaborador consiga abrir a solicitação pelo portal. O envio gera registro diretamente na tabela customizada.

### STS0003 — Status Inicial Automático
**Business Rule** configurada para garantir que toda nova solicitação inicie automaticamente com status **Aberto**, independente do canal de criação.

### STS0004 — Fluxo de Automação
Fluxo criado no **Flow Designer** disparado na criação de cada solicitação. Realiza o envio automático de e-mail de confirmação com os dados da solicitação preenchidos dinamicamente.

### STS0005 — Lista de Acompanhamento
Lista customizada para o time de atendimento acompanhar todas as solicitações com os campos mais relevantes visíveis: número de protocolo, solicitante, material, quantidade, prioridade, status e data.

---

## 💡 Decisões técnicas

**Record Producer em vez de Standard Catalog Item**
O Standard Catalog Item gera registros nas tabelas nativas do ServiceNow (`sc_request`, `sc_req_item`). O Record Producer foi escolhido para gerar os registros diretamente na tabela customizada da aplicação, mantendo a solução organizada em escopo próprio.

**Business Rule para status inicial**
Poderia ter sido resolvido com valor default no campo, mas a Business Rule garante o comportamento mesmo em criações via API ou integrações futuras, não apenas pelo formulário — solução mais robusta para um ambiente real.

**Catalog UI Policy para campo condicional**
Quando o usuário seleciona "Outro" no campo Material solicitado, um campo de texto adicional é exibido dinamicamente via UI Policy, melhorando a experiência do usuário sem poluir o formulário com campos desnecessários.

**Escopo customizado**
A aplicação foi desenvolvida em escopo próprio (não Global), seguindo a boa prática de isolamento de customizações em ambientes reais de produção.

---

## 📸 Demonstração

### Portal — Item de Catálogo
<img width="480" height="548" alt="catalog" src="https://github.com/user-attachments/assets/c5d31339-fee9-441d-8a61-236e4b088a9f" />


### E-mail de Confirmação
<img width="550" height="499" alt="email" src="https://github.com/user-attachments/assets/ae4f578d-5f0c-4ce6-a179-b8f47f78bca1" />


### Lista de Acompanhamento
<img width="800" height="375" alt="lista" src="https://github.com/user-attachments/assets/41017dcf-6493-4af3-b4bc-2d460e530d3a" />


---

## 🔗 Links

- [Post no LinkedIn — Projeto](https://www.linkedin.com/feed/update/urn:li:activity:7463556307170746368/)
- [Post no LinkedIn — ATF](https://www.linkedin.com/feed/update/urn:li:activity:7467029015468457984/)

---

## 👨‍💻 Autor

**Amaury Lobo**  
Estudante de Engenharia de Software | ServiceNow Developer  
[LinkedIn](https://www.linkedin.com/in/amaury-lobo-4b8988304) · [GitHub](https://github.com/AmauryLobo)
