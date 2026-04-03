Pra quem quer fazer colaboração pelo mobile, recomendo essa dica aqui e os dois vídeos do Zee gamedev pra usar pelo termux.

Claude dicas:
O problema
O aviso warning: unable to access '.gitignore': Permission denied acontece porque o Termux não tem permissão para acessar arquivos no armazenamento interno do Android (/storage/emulated/0/).
Solução
1. Dê permissão de armazenamento ao Termux:
termux-setup-storage
Vai aparecer um popup pedindo permissão — aceite.
2. Tente o git add novamente:
git add .
Se ainda der erro, o problema é que o Git não confia no diretório (você já tentou o safe.directory). Tente também:
3. Corrija o ownership do repositório:
git config --global --add safe.directory '*'
Isso libera todos os diretórios de uma vez.
Dica importante
Trabalhar com Git em pastas do armazenamento interno (/storage/emulated/0/) no Termux sempre dá problema de permissão. O ideal é mover o projeto para dentro do diretório home do próprio Termux:
cp -r /storage/emulated/0/Documents/the-greg-returns-asym ~/
cd ~/the-greg-returns-asym
git add .
Assim o Git funciona sem nenhum erro de permissão.


Videos que eu assisti pra aprender o básico do termux com Github.

Video 1.
https://youtu.be/UbtomQj7lxk?si=1EQVKLkghEKQ0Ind

Video 2.
https://youtu.be/cRgq355nlL0?si=TJ2b7iQlRpZiBKdE

ignora o nome do Repositorio pq eu so coloquei pra testar, mas ja que funcionou, só tô com preguiça de ajeitar o nome e pra não da erro eu so não quis mudar depois ok.
