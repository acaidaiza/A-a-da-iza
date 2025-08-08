# Instalar o Git se não tiver
git clone https://github.com/SEU-USUARIO/cardapio.git
cd cardapio

# Criar um projeto React com Vite
npm create vite@latest . -- --template react
npm install

# Colar o código que te passei no arquivo src/App.jsx
git add .
git commit -m "Cardápio online"
git push origin main
