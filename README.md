### PASSO A PASSO
Instalar as dependências

### `npm install`

Rodar o projeto

### `npm start`

Instalar o módulo para manipular rotas

### `npm install --save react-router-dom`


### BREVE EXPLICAÇÃO
Cria o diretório pages  dentro do SRC.
Dentro de Pages crie os diretórios que representam cada página do site como por exemplo: .src/Contato/index.js. Neste arquivo index crie o componente com nome da página e exporte conforme o modelo abaixo:

import React from 'react';
function Contato(){
    return(
        <h1>Página de contato</h1>
    );
}
export default Contato;

  ### ARQUIVO DE ROTAS
No diretório SRC crie o arquivo que concentra todas as rotas: src/rotas.js
Importe o  react-router-dom.
Importe as páginas criadas.
Crie um componente Routes e exporte para o arquivo App.js:

import React from 'react';
import { BrowserRouter, Switch, Route} from 'react-router-dom';

import Home from './pages/Home';
import Empresa from './pages/Empresa';
import Contato from './pages/Contato';

function Routes(){
    return(
        <BrowserRouter>
            <Switch>
                <Route path="/" exact component={Home} />
                <Route path="/sobre-empresa" component={Empresa} />
                <Route path="/contato" component={Contato} />
            </Switch>
        </BrowserRouter>
    );
}

export default Routes;

  ### IMPORTANDO O ARQUIVO DE ROTAS EM APP.JS
  
import React from 'react';
import Routes from './routes';

function App() {    
    return (
        <Routes />
    )
}
export default App;

Este App será renderizado na página public/index.html em <div id="root"></div> e as rotas já podem ser utilizadas.   
