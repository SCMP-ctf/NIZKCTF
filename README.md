# NIZKCTF example CTF


## Registro
1. Todos os membros do time devem ter uma conta no GitHub e [configurar uma chave SSH nas suas configurações de conta](https://github.com/settings/keys).

2. Todos os membros do time devem ter um cliente git [corretamente configurado](https://git-scm.com/book/pt-br/v2/Começando-Configuração-Inicial-do-Git). Se você nunca usou git antes, execute:
   ```bash
   git config --global user.name "Fulano de Tal"
   git config --global user.email fulanodetal@exemplo.com.br
   ```

3. Todos os membros do time devem clonar o repositório e instalar as dependências:
   ```bash
   git clone git@github.com:SCMP-ctf/SCMPv9.git ou git clone https://github.com/SCMP-ctf/SCMPv9.git
   cd SCMPv9
   sudo apt-get install libsodium23 python-pip3
   sudo -H python -m pip3 install -r pip-requirements.txt
   ```
   **Note**: Se você estiver usando Ubuntu 14.04, adicione [ppa:elt/libsodium](https://launchpad.net/~elt/+archive/ubuntu/libsodium) no seu sistema para poder instalar o `libsodium18`.

4. Se as dependências estiverem corretamente instaladas, você deve conseguir ver o menu de ajuda executando:
   ```bash
   ./ctf -h
   ```

5. **O líder do time** deve executar o seguinte comando e seguir as instruções para registrar o time:
   ```bash
   ./ctf init
   ```

6. **Os demais membros** devem se logar com o github sem criar um novo time:
   ```bash
   ./ctf login
   ```

7. Após isso, **o líder** deve compartilhar o arquivo `team-secrets.json` com os demais membros. **Os demais membros** devem colocar o arquivo `team-secrets.json` na pasta `NIZKCTF` clonada.

## Challenges

Os challenges estão disponíveis em https://scmp-ctf.github.io/SCMPv9.

Se você preferir, pode consultar localmente subindo um servidor usando `./ctf serve`, ou listar os challenges na Interface de Linha de Comando:
```bash
./ctf challs
```

## Submissão de flags

Para submeter uma flag:
```bash
./ctf submit --chall chall-id 'CTF-BR{flag123}'
```

Você pode omitir o `--chall chall-id` do comando, mas vai demorar mais para submeter. Nesse caso, será tentada a flag para cada um dos challenges liberados até então.

## Placar

O placar também está disponível via linha de comando:
```bash
./ctf score --names --pull
```
