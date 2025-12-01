Aqui está um **README.md profissional, completo e pronto para usar no GitHub**, totalmente baseado no desafio que você descreveu.
Se quiser, posso personalizar com seu nome, adicionar imagens, GIFs, sumário automático ou badges.

---

# 🛡️ Projeto: Ataques de Força Bruta com Kali Linux e Medusa

Este repositório contém a implementação e documentação completa do desafio proposto na DIO, envolvendo a utilização do **Kali Linux**, da ferramenta **Medusa** e de ambientes vulneráveis como **Metasploitable 2** e **DVWA**.

O objetivo é simular cenários reais de ataques de força bruta, compreender vulnerabilidades e aplicar medidas de mitigação em um ambiente **100% controlado e educativo**.

---

## 🎯 Objetivo Geral

Demonstrar, por meio de experimentos práticos, como funcionam ataques de força bruta em serviços como **FTP**, **aplicações web** (DVWA) e **SMB**, utilizando o Kali Linux como ambiente atacante.
Toda a jornada foi documentada para reforçar o aprendizado e construir portfólio técnico no GitHub.

---

## 🧠 Objetivos de Aprendizagem

Ao longo deste projeto, foi possível:

✔️ Compreender ataques de força bruta aplicados a diferentes protocolos (FTP, HTTP/DVWA e SMB);
✔️ Utilizar o **Kali Linux** e o **Medusa** em auditorias de segurança;
✔️ Configurar máquinas virtuais de forma segura para testes;
✔️ Documentar processos técnicos de forma clara e estruturada;
✔️ Identificar vulnerabilidades comuns e propor medidas de mitigação;
✔️ Utilizar o GitHub como portfólio profissional.

---

## 🖥️ Estrutura do Ambiente

Para executar os testes, foram criadas duas VMs no **VirtualBox**:

| Máquina              | Função                   | Sistema           | Configuração de Rede      |
| -------------------- | ------------------------ | ----------------- | ------------------------- |
| **Kali Linux**       | Atacante                 | Kali 2024.x       | Host-Only                 |
| **Metasploitable 2** | Alvo Vulnerável          | Ubuntu modificado | Host-Only                 |
| **DVWA**             | Aplicação Web Vulnerável | PHP/MySQL         | Rodando no Metasploitable |

⚠️ *Todo o ambiente é isolado e não deve ser conectado a redes reais.*

---

## 🚀 Cenários Implementados

### **7.2.1 – Ataque de Força Bruta em FTP (Medusa + Wordlist)**

* Serviço atacado: `FTP` na porta 21
* Wordlist simples construída manualmente
* Comando utilizado:

```bash
medusa -h 192.168.56.101 -u msfadmin -P wordlist.txt -M ftp
```

**Resultados:**
✔ Credenciais validadas
✔ Acesso ao ambiente vulnerável

---

### **7.2.2 – Ataque a Formulário Web (DVWA – Low Security)**

* Serviço: HTTP – Formulário de login da DVWA
* Automação do brute force:

```bash
medusa -h 192.168.56.101 -u admin -P wordlist.txt -M http -m FORM:"/dvwa/login.php" -m DENY:"Login failed"
```

**Resultados:**
✔ Identificação de senha válida
✔ Análise da resposta HTTP
✔ Demonstração do impacto de validações fracas

---

### **Password Spraying em SMB com Enumeração de Usuários**

* Descoberta de usuários com enum4linux:

```bash
enum4linux -a 192.168.56.101
```

* Ataque com Medusa:

```bash
medusa -h 192.168.56.101 -U users.txt -p "123456" -M smbnt
```

**Resultados:**
✔ Identificação de contas fracas
✔ Demonstração de riscos de senhas compartilhadas

---

## 🧰 Wordlists Utilizadas

O repositório contém:

✔ `wordlist.txt` (lista simples criada manualmente)
✔ `users.txt` (usuários enumerados do SMB)
✔ Outras listas opcionais personalizadas

---

## 🛡️ Medidas de Mitigação

As recomendações levantadas incluem:

* Implementar políticas fortes de senha (complexidade + expiração);
* Bloqueio de conta após tentativas falhas consecutivas;
* Monitoramento e logs centralizados;
* Firewall restringindo acesso a serviços sensíveis;
* Uso de autenticação multifator (MFA);
* Evitar usuários padrão (root, admin, test etc.);
* Atualizações periódicas do sistema.

---

## 📁 Estrutura do Repositório

```
/
├── README.md
├── wordlist.txt
├── users.txt
├── scripts/              # opcional
├── images/               # capturas de tela e evidências
└── configs/              # arquivos de configuração
```

---

## 📸 Evidências

As capturas de tela dos experimentos (opcional) podem ser encontradas na pasta:

> `/images/`

---

## 📚 Recursos Utilizados

* **Kali Linux – Site Oficial**
* **Medusa – Documentação**
* **DVWA – Damn Vulnerable Web Application**
* **Nmap – Manual Oficial**
* **GitHub Quick Start**
* **GitHub Markdown Syntax Guide**

---

## 🚀 Como Reproduzir

1. Configure as duas máquinas no VirtualBox (Kali + Metasploitable).
2. Configure a rede host-only.
3. No Kali, instale ferramentas úteis:

```bash
sudo apt update
sudo apt install medusa enum4linux nmap
```

4. Execute cada ataque conforme documentado acima.
5. Consulte o README para entender cada etapa.

---

## 📝 Conclusão

Este desafio permitiu compreender de forma prática como ataques de força bruta funcionam, como ferramentas de auditoria podem ser utilizadas em ambiente seguro e quais medidas mitigam esses riscos no mundo real.

Toda a jornada foi documentada aqui para fins de aprendizado e portfólio técnico.

---

Se quiser, posso gerar também:

✔ versão em inglês
✔ README com emojis minimalistas
✔ README com badges, GIFS e sumário automático
✔ README mais curto ou mais longo

É só pedir!
