# Afwrm5

Hello World simples para deploy em VPS via Ansible.

## Estrutura

- `index.html`: página estática de exemplo.

## Exemplo de tarefa Ansible

Use a tarefa abaixo para copiar o arquivo para um servidor com Nginx/Apache:

```yaml
- name: Deploy Hello World
	hosts: vps
	become: true
	tasks:
		- name: Copiar index.html para web root
			copy:
				src: index.html
				dest: /var/www/html/index.html
				owner: www-data
				group: www-data
				mode: '0644'
```