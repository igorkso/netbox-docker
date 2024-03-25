# Netbox-Ansible LSD-UFCG

Este projeto automatiza o deployment do Netbox, uma ferramenta de gestão de infraestrutura, utilizando Docker e Ansible.

## Sobre o Netbox

O Netbox é uma aplicação de código aberto desenvolvida pela Network to Code, LLC, que oferece recursos abrangentes para a gestão de ativos de rede, endereços IP e documentação de infraestrutura.

## Pré-requisitos

- Ansible instalado no ambiente onde será executado o deployment.
- Credenciais do usuário 'suporte' para acessar os arquivos encriptados com ansible-vault.

## Como Usar

1. Clone este repositório.
2. Configure o arquivo de inventário em `inventory/inventory.ini`.
3. Execute o playbook `init.yaml` para iniciar o deployment:

```bash
ansible-playbook init.yaml --ask-vault-password -K
```

## Executando apenas uma das roles:

Para executar apenas uma das roles, você deve usar uma das tags abaixo e seguir o exemplo abaixo:

- `netbox-install`
- `docker-install`

E executar com o comando:

```bash
ansible-playbook init.yaml --tags netbox-install --ask-ansible-vault -K
```

Certifique-se de fornecer a senha do ansible-vault com --ask-vault-password e a opção -K para solicitar a senha do super user no host de destino.

Para mais informações, consulte a documentação do Netbox em netbox.readthedocs.io
