<H1 align="center"> Igor Suzuki Kira </H1>
 
 # Sumário 
 [1. INTRODUÇÃO](#introdução)
 
[2. PROJETOS DESENVOLVIDOS](#projetos-desenvolvidos)   
   - [Projeto 1](#projeto1)
   - [Projeto 2](#projeto2)
   - [Projeto 3](#projeto3)
   - [Projeto 4](#projeto4)
   - [Projeto 5](#projeto5)
   - [Projeto 6](#projeto6)
   
   
    
 

# Introdução

Olá, sou Igor Suzuki, tenho 24 anos e sou aluno de Banco de Dados da FATEC de São José dos Campos. <br>
<br>
Meu conhecimento na programação iniciou-se em 2016 quando cursei meu técnico de Automação Industrial e aprendi a programar arduínos em C. Após terminar o curso, trabalhei como técnico de TI, me aproximando ainda mais da área da tecnologia. Em 2021, ingressei na FATEC para me especializar e dedicar-me à área de desenvolvimento, e obtive grandes ganhos de conhecimento, desenvolvendo hard e soft skills primordiais para minha migração profissional para a área de desenvolvimento de software. <br><br>
Atualmente, trabalho como Analista Programador na empresa IACIT e tenho maior domínio de tecnologias como <b>Java, Banco de Dados Relacional e ReactJS</b>.
<div align = center>
<img src="https://github.com/igorsuzuki99/Portfolio/blob/982f68b68765893dc2b732b8c773252340fbb3d0/IMG_4773%20(1).jpg" alt="eu" width="203" height="213">
</div>
<div align = center>
 <a href="https://www.linkedin.com/in/igor-suzuki/" target="_blank"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a>
 <a href="mailto:igorsuzuki.dev@gmail.com"><img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" target="_blank"></a>
</div>
 <br><br>
 
# Projetos desenvolvidos
<div id='projeto1' />
 
## Projeto 1: 2º Semestre de 2021
***Visualizador de dados COVID-19***
<p align="center">
 <b> Carcará Analysis </b>
  <br>
 Interno - FATEC
</p>

### Descrição do Projeto
O desafio foi desenvolver um projeto com o objetivo de analisar os dados oficiais da COVID-19 no Estado de São Paulo e entregá-los ao usuário de forma clara e contextualizada, através de visualizações gráficas ou não-gráficas.
<br><br>
A solução foi um sistema web em Python através do Flask, que a partir dos CSVs disponilizados pelo governo contendo dados estatísticos da COVID, mostrava para o usuário gráficos de diferentes tipos, como barras e setores, que continham estatísticas sobre o vírus e também demais insights relevantes que eram calculados através dos dados já existentes.
<br><br>

## Tecnologias Utilizadas &nbsp;&nbsp;&nbsp;<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/python/python-original.svg" width="40" height="40"/> &nbsp; <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/pandas/pandas-original-wordmark.svg" width="40" height="40"/> &nbsp; <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/plotly/plotly-original.svg" width="40" height="40"/>
        

### Python 
A aplicação foi desenvolvida predominantemente em Python devido à sua sintaxe clara e simplificada, além de uma vasta quantidade de bibliotecas e frameworks que suportam diversas áreas de desenvolvimento, incluindo análise de dados, que facilitou o processo de criação do primeiro projeto.
<br><br>

### Pandas
Para ajudar com a manipulação dos dados foi utilizado o Pandas, que é uma biblioteca que oferece estruturas de dados de alto desempenho, além de ferramentas de análise de dados. Ela foi usada para a leitura dos dados que eram obtidos através de CSVs. O Pandas também possui integração com a biblioteca NumPy, o que proporcionou um desempenho eficiente para as operações numéricas.
<br><br>

### Plotly
Para facilitar a visualização dos dados estatísticos, foi utilizado Plotly, uma biblioteca gráfica interativa para Python. Ela é usada para criar visualizações de dados interativas e dinâmicas, além de oferecer suporte a uma variedade de tipos de gráficos, desde gráficos simples até visualizações mais complexas e personalizadas. No caso desse projeto, ela foi utilizada para criar gráficos de barra e setores, para demonstrar os dados da COVID.
<br><br><br>
### Contribuições Individuais
<details>
  <summary><b>Cálculos estatísticos para plotagem de gráficos</b></summary>
  <br>
  <p>Nesse projeto, realizei o desenvolvimento dos cálculos para plotagem de gráficos com as estatísticas personalizadas de diferentes dados. Através dos cálculos, foi possível extrair informações complementares além das que os dados forneciam originalmente</p>
  
  ```python
  
    # GRÁFICO TOTAL DE CASOS (Taxa de Incidência)
    pop = 44000000 #população do estado de SP
    casos = covidsp[covidsp['Data'] == data]['Casos por dia'].values[0]
    
    inc = casos / (pop-casos) * 100000
    print('Incidência de casos: %.f' %inc, 'a cada 100 mil habitantes')
    
    # GRÁFICO TOTAL DE ÓBITOS (Taxa de Letalidade)
    obtotal = covidsp[covidsp['Data'] == data]['Total de óbitos'].values[0]
    casostotal = covidsp[covidsp['Data'] == data]['Total de casos'].values[0]
    
    let = (obtotal/casostotal) * 100
    print('Taxa de letalidade no Estado: %.1f' %let, '%')
  
  ```
  
  <p><i>No exemplo de código acima, eu utilizei os dados de casos por dia e a população do estado de SP para calcular a incidência de casos a cada 100 mil habitantes. No segundo cálculo, através do número de óbitos total e de casos total, realizei o cálculo para mostrar a porcentagem de letalidade da doença.</i></p>
  <br>
</details>
<details>
  <summary><b>Cálculos estatísticos para comparação de informações</b></summary>
  <br>
  <p>Realizei também o desenvolvimento dos cálculos para amostragem de informações de comparação. Através dos cálculos, foi possível comparar os dados de diferentes períodos e ter noção da evolução da COVID.</p>
  
  ```python
  
    # OCUPAÇÃO DOS LEITOS DE UTI E ENFERMARIA NO ESTADO (%) (Variação nos últimos 7 dias)
    ocup = leitos[leitos['Data'] == data]['Ocupação dos leitos de UTI e Enfermaria (%)'].values[0]
    ocup7 = leitos[leitos['Data'] == (data - dt.timedelta(days=7))]['Ocupação dos leitos de UTI e Enfermaria (%)'].values[0]
    
    x = (ocup*100) / ocup7-100
    print('Ocupação de leitos {0}%. Comparação com 7 dias atrás: {1:.2f}'.format(ocup, x), '%')

    # NOVAS INTERNAÇÕES POR DIA NO ESTADO (Variação nos últimos 7 dias)
    inter = leitos[leitos['Data'] == data]['Novos casos de internações (UTI e Enfermaria)'].values[0]
    inter7 = leitos[leitos['Data'] == (data - dt.timedelta(days=7))]['Novos casos de internações (UTI e Enfermaria)'].values[0]
    
    x = (inter*100) / inter7-100
    print('Novas internações: {0}. Comparação com 7 dias atrás: {1:.2f}'.format(inter, x), '%')
  ```
  
  <p><i>No trecho de código acima, utilizei os números de ocupação de leitos e de novas internações em determinada data, para realizar o cálculo da diferença em porcentagem com os números dos mesmos dados de 7 dias atrás.</i></p>
  <br>
</details> <br>

### Aprendizados Efetivos

#### HARD SKILLS

<details>
  <summary>Linguagem Python</summary>
  <br>
    <ul>
      <li>Lógica, variáveis e tipos de dados: sei fazer com autonomia</li>
      <li>Funções: sei fazer com autonomia</li>
      <li>Listas e dicionários: sei fazer com ajuda</li>
      <li>Manipulação de entrada e saída de arquivos: sei fazer com ajuda</li>
    </ul>
  <br>
</details>
<details>
  <summary>Plotagem de gráficos</summary>
  <br>
    <ul>
      <li>Popular e construir gráficos: sei fazer com ajuda</li>
      <li>Plotagem de diferentes estilos de gráficos: sei fazer com ajuda</li>
      <li>Manipulação e personalização de dados estatísticos: sei fazer com ajuda</li>
    </ul>
  <br>
</details><br>

#### SOFT SKILLS 

<ul>
 <li>Comunicação eficaz: Com as aulas em sua totalidade no regime online, precisei evoluir minha comunicação com os integrantes do grupo para melhor o entendimento e compreensão entre a equipe. </li>
 <br>
 <li>Aprendizado contínuo: A partir da necessidade do aprendizado sobre desenvolvimento de software, sendo o meu primeiro semestre, precisei estudar bastante para entender a base necessária para programar em Python. </li>
</ul>
<br>

[Projeto no GitHub](https://github.com/igorsuzuki99/Carcara)

<br><br>

<div id='projeto2' />


## Projeto 2: 1º Semestre de 2022
***Sistema de cadastro de clientes***

<H3 align="center">Parceiro Acadêmico</H3>

<p align="center">
<img src="https://github.com/igorsuzuki99/bertoti/blob/e945b5938ce30752e0848b95343dda228c0cff3f/Metodologia/domrock.png" alt="domrock" width="230" height="70">
</p>

### Descrição do Projeto
O desafio foi criar uma plataforma para criação e ativação de clientes para posterior uso da empresa. O projeto devia contar com telas de cadastro que inserem informações no banco de dados para posterior exibição na tela de consulta dos clientes.<br><br>
A solução foi um aplicativo desktop em Java através de interface GUI, na qual eram dispostos componentes swing para formar etapas de um cadastro, os dados preenchidos nesses componentes eram salvos no banco de dados conforme o usuário avançava nas etapas do formulário.
<br><br>

## Tecnologias Utilizadas &nbsp;&nbsp;&nbsp; <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/java/java-original.svg" width="40" height="40"/> &nbsp; <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/postgresql/postgresql-original.svg" width="40" height="40"/> 

### Java e Swing 
A aplicação foi desenvolvida em Java, linguagem orientada a objetos, a qual juntamente com o framework Swing foi possível criar elementos visuais para utilização em um aplicativo desktop.
O Swing fornece componentes gráficos, como botões, caixas de texto, tabelas, entre outros, que podem ser usados para construir interfaces de usuário interativas. Essa característica foi útil nesse projeto pois facilitou o desenvolvimento da parte visual da aplicação.
<br><br>

### PostgreSQL
Para armazenamento das informações, foi utilizado o PostgreSQL, um banco relacional no qual guardamos os dados de usuários e clientes. Foi escolhido o Postgres por conta de sua interface dedutiva, e funcionalidades expostas de forma facilitada, que contribuíram na conexão, manuseio e gerenciamento do banco de dados.
<br><br><br>

### Contribuições Individuais
<details>
  <summary><b>Visualização de clientes cadastrados</b></summary>
  <br>
  <p>Neste projeto realizei o desenvolvimento dos métodos de crud dos clientes. Dentre eles, realizei o método de listagem dos clientes para visualizar quais empresas estão cadastradas no banco de dados da plataforma. </p>
  
  ```java
  
  public void mostrarCliente(String cnpj) {
        try {
            Connection conexion = conectar();
            st = conexion.createStatement();
            String sql ="select * from cliente where cnpj_cliente='" + cnpj+ "';";
            rs = st.executeQuery(sql);
            variables empresa = new variables();       
            if (rs.next()) {
                empresa.setCnpj(rs.getString("cnpj_cliente"));
                empresa.setNome_empresa(rs.getString("nome_empresa"));
                empresa.setObjetivo_neg(rs.getString("objetivo_negocio"));
                var.add(empresa);
            }
            else {
                JOptionPane.showMessageDialog(null, "Registro não encontrado", "Sem registro", JOptionPane.INFORMATION_MESSAGE);
            }
            st.close();
            conexion.close(); 
        } catch (Exception e) {
            JOptionPane.showMessageDialog(null, "Erro no Programa " + e, "Erro no sistema", JOptionPane.ERROR_MESSAGE);
        }
  
  ```
  
  <p><i>No exemplo de código acima, é realizada uma conexão com o banco e realizada uma query de consulta dos clientes, procurando pelo CNPJ. Com base nos dados obtidos pela consulta, são setados nos campos de informação da empresa as informações referentes ao CNPJ pesquisado. Caso não seja encontrado um registro, mostra uma mensagem de "Registro não encontrado" em uma janela JOptionPanel</i></p>
  <br>
</details>
<details>
  <summary><b>Cadastro de clientes</b></summary>
  <br>
  <p>Desenvolvi o método para cadastrar as informações da empresa que é cadastrada na plataforma, com seus respectivo armazenamento no banco de dados.</p>
  
  ```java
  
  public void inserir(String cnpj, String nome_empresa, String objetivo_neg, String entregavel_min, String entregaveis_possi,
                       String solucao, String produto, String funcionalidade, String core) {
        try {
            Connection conexion = conectar();
            st = conexion.createStatement();
            String sql = "insert into escopo(cnpj,nome_empresa,objetivo_neg,entregavel_min,entregaveis_possi,
            solucao,produto,funcionalidade,core) values('" + cnpj + "','" + nome_empresa + "','"+entregavel_min+"',
            '"+entregaveis_possi+"','"+solucao+"','"+produto+"','"+funcionalidade+"','"+core+"');";
            st.execute(sql);
            st.close();
            conexion.close();
            JOptionPane.showMessageDialog(null, "Salvo com sucesso", "Mensagem", JOptionPane.INFORMATION_MESSAGE);
        } catch (Exception e) {
            JOptionPane.showMessageDialog(null, "Erro ao Salvar " + e, "Mensagem", JOptionPane.ERROR_MESSAGE);
        }
    }
  ```
  
  <p><i>No trecho de código acima, é aberta uma conexão com o banco, realizada uma query de inserção no banco de dados, a qual recebe os dados da empresa, itera na query de inserção e executa para armazenar as informações no banco. Após esse processo é encerrada a conexão com o banco e se ocorrer algum erro é mostrado uma janela com a mensagem de erro para o usuário.</i></p>
  <br>
</details><br>


### Aprendizados Efetivos

#### HARD SKILLS

<details>
  <summary>Linguagem Java</summary>
  <br>
    <ul>
      <li>Orientação a objetos: sei fazer com ajuda</li>
      <li>Funções em Java: sei fazer com ajuda</li>
      <li>Integração com banco de dados: sei fazer com ajuda</li>
      <li>Tratamento de erros: sei fazer com ajuda</li>
    </ul>
  <br>
</details>
<details>
  <summary>Banco de dados</summary>
  <br>
    <ul>
      <li>Consultas personalizadas com SQL: sei fazer com ajuda</li>
      <li>Gerenciamento de conexões: sei fazer com ajuda</li>
    </ul>
  <br>
</details>
<details>
  <summary>Swing Framework</summary>
  <br>
    <ul>
      <li>Desenvolvimento através de componentes Swing: sei fazer com autonomia</li>
      <li>Gerenciamento de componentes GUI: sei fazer com ajuda</li>
      <li>Desenvolvimento de aplicação desktop: sei fazer com ajuda</li>
    </ul>
  <br>
</details><br>

#### SOFT SKILLS

<ul>
      <li>Criatividade: Com o primeiro contato com uma empresa real, precisei de criatividade para conseguir desenvolver uma solução que cumprisse com os requisitos impostos.</li><br>
      <li>Aprendizado contínuo: A partir do requisito de desenvolver em Java e ter o primeiro contato com a linguagem no semestre em questão, precisei estudar para aprender sobre os princípios de orientação à objetos.</li>
</ul>
<br>

[Projeto no GitHub](https://github.com/igorsuzuki99/Dom-Rock)

<br><br>


<div id='projeto3' />


## Projeto 3: 2º Semestre de 2022
***Visualizador de dados meteorológicos***

<H3 align="center"> Parceiro Acadêmico </H3>

<p align="center">
<img src="https://github.com/igorsuzuki99/Portfolio/blob/fa2a1c999b7e4fdbebf9a13c8cc4b927e5264772/iacit.jpg" alt="iacit" width="200" height="106">
</p>

### Descrição do Projeto
O desafio consistia no desenvolvimento de um sistema no qual seja possível importar, pesquisar e gerar relatórios de dados meteorológicos. Além disso, alocação dos dados disponibilizados no site do Instituto Nacional de Meteorologia (INMET) para um banco de dados, para integrar com o sistema desenvolvido.<br><br>
A solução foi uma aplicação com interface web, que dispõe de um mecanismo de filtro no qual é possível filtrar os registros por datas, regiões, estados, localidades e tipo de dado, para posteriormente expor as informações em formato de gráficos e com a possibilidade de exportar um relatório com base na consulta realizada.
<br><br>

## Tecnologias Utilizadas &nbsp;&nbsp;&nbsp; <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/java/java-original.svg" width="40" height="40"/> &nbsp; <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/spring/spring-original.svg" width="40" height="40"/> &nbsp; <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/postgresql/postgresql-original.svg" width="40" height="40"/> &nbsp; <img src="https://asset.brandfetch.io/idFdo8ulhr/idg4l58CuH.svg" width="40" height="40"/> 

### Java e Spring 
O back-end da aplicação foi desenvolvido predominantemente em Java, uma linguagem orientada a objetos, na qual juntamente com a tecnologia de Spring foi possível criar endpoints para interfaces web.
O Spring é um framework que dispõe de recursos para criação de aplicações web escritas em Java e que traz mais agilidade para o desenvolvimento, visto que facilita as configurações iniciais do projeto com a injeção de dependências, as quais servem tanto para preparar o ambiente, quanto para otimizar a utilização de ferramentas e bibliotecas durante o desenvolvimento do projeto.
<br><br>

### PostgreSQL
O banco de dados utilizado foi o PostgreSQL, um banco relacional no qual alocamos todos os dados meteorológicos, dados de estações e regiões. A escolha do Postgres se deu por conta de sua versatilidade, interface simplificada, e funcionalidades expostas de forma dedutiva, que facilitaram a usabilidade e gerenciamento do banco de dados. A sua alta eficiência e desempenho contribuiram para armazenar com tranquilidade os milhões de dados meteorológicos importados.
<br><br>

### Chart.js
Chart.js é uma biblioteca do JavaScript que possibilita a exposição de dados em forma de gráficos em páginas web, ela foi essencial para a interface do projeto. Com ela, pudemos mostrar de forma interativa os dados meteorológicos devidamente filtrados e escolhidos pelo usuário da aplicação. Nela também é possível personalizar as propriedades de design, o que possibilitou a exposição de gráficos personalizados de acordo com cada tipo de dado.
<br><br><br>
### Contribuições Individuais
<details>
  <summary><b>Criação e personalização dos endpoints back-end</b></summary>
  <br>
  <p>Nesse projeto realizei o desenvolvimento dos métodos em back-end que realizavam as consultas dos dados meteorológicos no banco de dados. Criei os endpoints principais de consultas gerais, e também os endpoints personalizados baseados nos filtros. De acordo com os filtros selecionados, eu validava os parâmetros recebidos e adaptava os endpoints com consultas personalizadas no banco de dados para retornar os resultados pretendidos.</p>
  
  ```java
  
  @GetMapping(value = "/precipitacao/range/{estacao}/{data1}/{data2}")
    public List<Precipitacao> listarRangePrecipitacao(@PathVariable("estacao") String codigo, @PathVariable("data1") String precData, @PathVariable("data2") String precData1){
        Query query = entityManager.createNativeQuery("select * from precipitacao where prec_data between '"+precData+"' and '"+precData1+"' and fk_estacao_cod_wmo = '"+codigo+"'");
        List<Object[]> rows = query.getResultList();
        List<Precipitacao> list = new ArrayList<>();
        for (Object[] obj : rows) {
            list.add(new Precipitacao(
                    (Integer) obj[0],
                    (Date) obj[1],
                    (Date)obj[2],
                    (BigDecimal) obj[3],
                    (String) obj[4])
            );
        }
        return list;
    }
  
  ```
  
  <p><i>No exemplo de código acima, o endpoint de precipitação recebe os parâmetros personalizados de acordo com a estação e datas escolhidas pelo usuário, realiza a pesquisa no banco de dados com as variáveis e coloca o resultado dentro de uma lista de arrays de objetos. Através de um laço, cada objeto do tipo precipitação retornado pela consulta na query é adicionado na lista.</i></p>
  <br>
</details>
<details>
  <summary><b>Desenvolvimento do dashboard</b></summary>
  <br>
  <p>Contribuí no desenvolvimento da interface do front-end, onde implementei a utilização da biblioteca chart.js para construir os gráficos baseados nos dados meteorológicos requisitados. Realizei métodos em JavaScript, que consultavam os JSON's dos endpoints do back-end, e gerava os gráficos a partir dos dados captados. Também implementei inputs na página web para receber os critérios de filtragem e passar os parâmetros para o back-end realizar as consultas.</p>
  
  ```javascript
  
  if(dado[0]=="temperatura"){
    $(document).ready(function(){
        $.getJSON("/temperatura/range/"+dado[1]+"/"+dado[2]+"/"+dado[3],function(data){
          if(dado[1]!=null){
              document.getElementById("selectRegiao").innerHTML = "";
              $("#selectRegiao").append(inventory.find(procurarEstacao).nome_estacao+" - |"+dado[1]+"|");
              document.getElementById("selectEstado").innerHTML = "";
              $("#selectEstado").append(inventory.find(procurarEstacao).estado);
              $(document).ready(function(){
                  $.getJSON("/estados",function(regiao){
                     function procurarEstado(estado) {
                       return estado.nome_estado === inventory.find(procurarEstacao).estado;
                     }
                     document.getElementById("selectRegiao").innerHTML = "";
                     $("#selectRegiao").append(regiao.find(procurarEstado).regiao);
                  });
              });
          }
  ...
  ```
  
  <p><i>No trecho de código acima se o usuário busca pelo dado de temperatura, é realizado uma busca do JSON do endpoint formado pela URL personalizada de acordo com os parâmetros passados de região, estado e estação.</i></p>
  <br>
</details>
<details>
  <summary><b>Geração de relatório</b></summary>
  <br>
  <p>Implementei a função de gerar um PDF do gráfico gerado, contendo as informações meteorológicas filtradas de acordo com a pesquisa do usuário. O pdf gerado contém os dados pesquisados e o gráfico equivalente</p>
</details><br>


### Aprendizados Efetivos

#### HARD SKILLS

<details>
  <summary>Spring Framework</summary>
  <br>
    <ul>
      <li>Desenvolvimento de aplicações web: sei fazer com ajuda</li>
      <li>Arquitetura REST: sei fazer com autonomia</li>
      <li>Integração com banco de dados: sei fazer com autonomia</li>
      <li>Injeção de dependências: sei fazer com autonomia</li>
      <li>Desenvolvimento de código através de interfaces: sei fazer com ajuda</li>
    </ul>
  <br>
</details>
<details>
  <summary>Banco de dados</summary>
  <br>
    <ul>
      <li>Consultas personalizadas com SQL: sei fazer com autonomia</li>
      <li>Geração de scripts: sei fazer com autonomia</li>
      <li>Export e import de backup: sei fazer com autonomia</li>
    </ul>
  <br>
</details>
<details>
  <summary>Programação</summary>
  <br>
    <ul>
      <li>Funções em JavaScript: sei fazer com ajuda</li>
      <li>Manipulação de variáveis com JavaScript: sei fazer com autonomia</li>
      <li>Programação orientada a objetos: sei fazer com autonomia</li>
      <li>Consumo de API Rest: sei fazer com autonomia</li>
      <li>Gerenciamento de usuários: sei fazer com ajuda</li>
      <li>Consumo de recursos de bootstrap: sei fazer com ajuda</li>
    </ul>
  <br>
</details><br>

#### SOFT SKILLS

<ul>
      <li>Resolução de problemas: A partir da proposta de solução do projeto, necessitei de habilidades na resolução de problemas para contornar obstáculos durante o desenvolvimento.</li><br>
      <li>Flexibilidade: Como desenvolvi no front-end e também no back-end desse projeto, precisei desenvolver minha flexibilidade para conseguir conciliar o desenvolvimento em ambas as stacks.</li><br>
      <li>Autoconhecimento: Neste projeto necessitei me conhecer melhor, reconhecer meus limites e entender que existem coisas ao meu alcance, e coisas que não dependem somente de mim, entender que a pressa não adianta de nada se não houver qualidade no que se está fazendo. Me conhecer melhor foi um aprendizado essencial para a minha vida.</li>
</ul>
<br>

[Projeto no GitHub](https://github.com/igorsuzuki99/IACIT)

<br><br>

<div id='projeto4' />


## Projeto 4: 1º Semestre de 2023
***Aircraft Configuration Control: Gerenciador de componentes instalados em aeronaves***

<H3 align="center">Parceiro Acadêmico</H3>
<br>
<p align="center">
<img src="https://github.com/igorsuzuki99/Portfolio/blob/fa2a1c999b7e4fdbebf9a13c8cc4b927e5264772/Embraer_logo.png" alt="embraer" width="350" height="64">
</p>
<br>

### Descrição do Projeto
O desafio era a criação de uma plataforma em que o usuário consulte itens instalados nas aeronaves. O sistema inclui a verificação e edição de itens instalados ou aplicáveis a determinados "chassis" conforme base de dados fornecida.<br><br>
A solução foi um sistema que possuía todas as lógicas de formação de todos os itens armazenadas no banco de dados, dessa forma, a partir do chassi consultado, a lógica de composição dos itens era consultada no banco e os itens que eram compatíveis com o chassi em questão eram mostrados na tela para o usuário. Para melhor usabilidade do sistema, foi utilizada hospedagem em nuvem, que permitiu o acesso do sistema tanto pelo computador, como pelo celular ou qualquer outro dispositivo com acesso ao navegador com internet.
<br><br><br>

## Tecnologias Utilizadas &nbsp;&nbsp;&nbsp; <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/java/java-original.svg" width="40" height="40"/> &nbsp; <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/spring/spring-original.svg" width="40" height="40"/> &nbsp; <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/oracle/oracle-original.svg" width="40" height="40"/> &nbsp; <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vuejs/vuejs-original.svg" width="40" height="40"/> &nbsp; <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/amazonwebservices/amazonwebservices-original-wordmark.svg" width="40" height="40"/>
          
### Java e Spring 
O back-end da aplicação foi desenvolvido em Java juntamente com o framework Spring, onde foi realizada a lógica das regras de negócio para determinação de quais itens eram considerados instalados, instaláveis ou não instaláveis de acordo com os chassis que fossem pesquisados. Através do Spring Data foi possível realizar consultas de forma mais eficiente no banco de dados para tratamento das lógicas e condições no back-end.
<br><br>

### Oracle Autonomous Database
Para armazenamento dos dados, foi utilizado o Oracle Autonomous Database, um banco relacional em nuvem. Foi escolhido devido a possibilidade de consultar o banco através da internet, proporcionando uma melhor acessibilidade, praticidade e flexibilidade. Além do mais, também proporcionou maior segurança, tanto no controle de acesso ao banco, quanto na consistência dos dados, pois eram gerados backups automáticos que protegiam contra a perda de dados e facilitavam a recuperação em caso de falhas de operação.
<br><br>

### Vue.js
O front-end do sistema foi desenvolvido em Vue.js, um framework JavaScript que conta com uma arquitetura estruturada por meio da criação de componentes reusáveis. Isso facilitou o desenvolvimento da plataforma, tendo em vista que certas partes visuais da interface tinham certa semelhança.
<br><br>

### AWS
Para hospedar a aplicação em um servidor, foi utilizada uma instância da AWS, que é uma das principais plataformas provedora de serviços de infraestrutura para aplicações online baseado em Cloud. Com ela foi possível hospedar a aplicação em nuvem, que permitiu o acesso ao sistema pelo endereço do servidor AWS, possibilitando o acesso por outros dispositivos, como celulares, tablets e outros dispositivos com acesso à internet.
<br><br><br>

### Contribuições Individuais
<details>
  <summary><b>Gerenciamento de permissões de usuários</b></summary>
  <br>
  <p>Realizei o gerenciamento de permissões dos usuários de acordo com as roles que forem definidas na criação dos mesmos. Essas permissões diferenciam quais conteúdos do sistema cada nível de usuário terá acesso.</p>
  
  ```java
  
  @Service
public class CreateRoleUserService {
    @Autowired
    UsuarioRepository userRepository;
    public User execute(CreateUserRoleDTO createUserRoleDTO) {
        Optional<User> userExists = userRepository.findById(createUserRoleDTO.getIdUser());
        List<Role> roles = new ArrayList<>();
        if (userExists.isEmpty()) {
            throw new Error("User does not exists!");
        }
        roles = createUserRoleDTO.getIdsRoles().stream().map(role -> {
            return new Role(role);
        }).collect(Collectors.toList());

        User user = userExists.get();
        user.setRoles(roles);
        userRepository.save(user);
        return user;
    }
}
  
  ```
  
  <p><i>No exemplo de código acima, na criação de permissões de um usuário, é passado uma DTO (Data Transfer Object) contendo as roles definidas para aquele perfil. Para cada role informada é realizada a atribuição e cadastro no usuário, através do setRole e save do mesmo.</i></p>
  <br>
</details>
<details>
  <summary><b>Geração de relatório PDF</b></summary>
  <br>
  <p>Contribuí no desenvolvimento da interface do front-end, onde implementei a utilização da biblioteca pdfMake para construir um relatório contendo os itens instalados no chassi pesquisado.</p>
  
  ```javascript
  
const gerarPDF = () => {
    const docDefinition = {
      header: {
        text: `Chassi: ${chassi.value} - Embraer`,
        style: 'header',
      },
      content: [
        {
          style: 'table',
          table: {
            headerRows: 1,
            widths: ['*', '*'],
            body: [
              [
                { text: 'Item', style: 'tableHeader' },
                { text: 'Installed', style: 'tableHeader' },
              ],
              ...itens.value.map((item) => [
                item.nome,
                {
                  text: item.status === '✔' ? 'Aplicable' : 'Not Aplicable',
                  style: item.status === '✔' ? 'aplicable' : 'notAplicable',
                }
            [...]
    pdfMake.createPdf(docDefinition).download('Embraer.pdf');
  };
  ```
  
  <p><i>No trecho de código acima foi utilizada a biblioteca do pdfMake, biblioteca para gerar e exportar documentos PDF. No corpo do docoumento foram atribuídas as informações que serão expostas: o item, e se ele está instalado. E no final é chamado o método de createPdf para exportar o documento.</i></p>
  <br>
</details>
<details>
  <summary><b>Hospedagem da aplicação em nuvem</b></summary>
  <br>
  <p>Realizei a instanciação e configuração de um servidor em nuvem na AWS para disponibilizar a aplicação de forma pública. Configurei as aplicações back-end e front-end para realizarem a comunicação através do servidor, habilitei as portas necessárias e configurei o ambiente para rodar ambas as aplicações publicamente.</p>
</details> <br>


### Aprendizados Efetivos

#### HARD SKILLS

<details>
  <summary>Spring Framework</summary>
  <br>
    <ul>
      <li>Integração do banco com Spring Data: sei fazer com autonomia</li>
      <li>Arquitetura REST: sei fazer com autonomia</li>
      <li>Implementação de Spring Security: sei fazer com ajuda</li>
    </ul>
  <br>
</details>
<details>
  <summary>Banco de dados</summary>
  <br>
    <ul>
      <li>Segurança do banco de dados: sei fazer com autonomia</li>
      <li>Hospedagem de banco em nuvem: sei fazer com ajuda</li>
      <li>Gerenciamento de usuários do banco: sei fazer com ajuda</li>
    </ul>
  <br>
</details>
<details>
  <summary>Hospedagem em nuvem</summary>
  <br>
    <ul>
      <li>Configuração de Windows Server: sei fazer com ajuda</li>
      <li>Permissionamento de portas do servidor: sei fazer com autonomia</li>
      <li>Gerenciamento de firewall: sei fazer com ajuda</li>
      <li>Gerenciamento de recursos: sei fazer com ajuda</li>
    </ul>
  <br>
</details> 
<br>

#### SOFT SKILLS
<ul>
      <li>Pensamento crítico: Com a complexidade do projeto, necessitei desenvolver meu pensamento crítico para saber qual melhor caminho seguir e priorizar o que era mais importante para desenvolver uma solução para a regra de negócio mais complexa do projeto.</li><br>
      <li>Adaptabilidade: A partir da decisão de hospedar o sistema em nuvem e um dos requisitos ser a utilização do framework Vue.js, precisei me adaptar com novos ambientes e tecnologias com as quais nunca tive contato, o próprio Vue, e o sistema operacional Linux.</li><br>
      <li>Trabalho em equipe: Nesse projeto foi essencial a harmonia entre a equipe, pois com as novas tecnologias foi necessário que todos aprendessem algo novo, de forma a conseguir repassar para os colegas de que forma seria implementado no projeto. Através da boa comunicação e trabalho em equipe conseguimos conciliar o desenvolvimento de maneira mais eficiente.</li>
</ul>
<br>

[Projeto no GitHub](https://github.com/igorsuzuki99/Embraer)

<br><br>

<div id='projeto5' />


## Projeto 5: 2º Semestre de 2023
***Cloud Kitchen: Gerenciador de restaurante***
<H3 align="center"> Parceiro Acadêmico </H3>

<p align="center">
<img src="https://github.com/igorsuzuki99/bertoti/blob/4eb1813907df5839051e2f270cdef8abbdbd2187/Projeto%20Trabalho%20de%20Gradua%C3%A7%C3%A3o%20em%20BD%20I/oracle.png" alt="oracle" width="170" height="102">
</p>

### Descrição do Projeto
O desafio abrangia o desenvolvimento de um sistema web para gerência de um restaurante, com controle de estoque e fornecedores, visualização do desempenho de funcionários e pratos, além de gráficos para facilitar a visualização dos insights relevantes para o dono do estabelecimento. <br><br>
A solução foi uma plataforma web, separada em diferentes seções, contendo insights em formas de gráficos, tabelas e cards para visualização de informações sobre estoque, vendas, pratos e funcionários.
<br><br>

## Tecnologias Utilizadas &nbsp;&nbsp;&nbsp; <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/java/java-original.svg" width="40" height="40"/> &nbsp; <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/spring/spring-original.svg" width="40" height="40"/> &nbsp; <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/oracle/oracle-original.svg" width="40" height="40"/> &nbsp; <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vuejs/vuejs-original.svg" width="40" height="40"/>

### Java e Spring 
O back-end foi desenvolvido em Java com framework Spring para disponibilizar uma API com arquitetura REST contendo o mapeamento das rotas. Foram desenvolvidos endpoints CRUD que interagem com dados de pratos, funcionários e estoque para consumo do frontend.
<br><br>

### Oracle Autonomous Database
O banco de dados foi alocado em nuvem com o Autonomous Database da Oracle, que permitiu o consumo dos dados de qualquer ambiente com internet. Seu acesso restrito por wallet e backups automáticos foi um fator relevante para a escolha desse banco de dados.
<br><br>

### Vue.js
Com o framework do Vue.js foi possível componentizar os elementos do frontend para reutilizá-los em locais diferentes. Suas propriedades de condicional com v-if e looping com v-for proporcionaram uma maior facilidade na exibição dos dados utilizando condições e iterações em componentes.
<br><br>

### Contribuições Individuais
<details>
  <summary><b>Cadastro de alertas de estoque</b></summary>
  <br>
  <p>Realizei o consumo da API do backend para cadastrar alertas para avisos de estoque baixo ou validade próxima.</p>
  
  ```javascript
  
  <script>
import axios from 'axios';

export default {
    name: 'alerta',
    data() {
        return {
            formData: {
                nomeAlerta: "",
                descricao: "",
                entidade: "",
                condicaoDisparo: "",
                valorParametro: "",
                acao: "",
                destinatarios: ""
            },
        };
    },
    methods: {
        submitForm() {
            const jsonData = JSON.stringify(this.formData);
            axios.post('http://localhost:8081/alerta', jsonData, {
                headers: {
                    'Content-Type': 'application/json'
                }
            })
                .then(response => {
                    console.log('Resposta do servidor:', response.data);
                    this.formSubmitted = true;
                    alert("Alerta criado");
                })
                .catch(error => {
                    console.error('Erro na solicitação:', error);
                    alert("Erro ao criar alerta");
                });
        }
    }
};
</script>
  
  ```
  
  <p><i>No exemplo de código acima, é enviado um conteúdo de formulário em formato de JSON em uma requisição HTTP do tipo POST para o endpoint da API que cadastra alertas no banco de dados. Após isso, é retornado se o cadastro do alerta obteve sucesso ou não.</i></p>
  <br>
</details>

<details>
  <summary><b>Exibição de quadro de funcionários</b></summary>
  <br>
  <p>Realizei a exibição dos funcionários escalados em determinado dia conforme dados consumidos da API do backend.</p>
  
  ```javascript
  
  <template>
  <div>
    <p class="funcio">{{ title }}</p>
    <table class="tabela">
      <thead>
        <tr>
          <th>COLABORADORES ESCALADOS</th>
          <th>FUNÇÃO</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(funcao, nome) in funcionarios" :key="nome">
          <td>{{ nome }}</td>
          <td>{{ funcao }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import { ref, onMounted } from 'vue';
import axios from 'axios';

export default {
  ...
  methods: {
    async fetchData(date) {
        const formattedDate = this.formatDate(this.date);
      try {
        const response = await axios.get(`http://localhost:8081/diario/${formattedDate}`);
        this.funcionarios = response.data.funcionarios || {};
      } catch (error) {
        console.error('Erro ao buscar dados:', error);
      }
    }
  ...
  ```
  
  <p><i>No exemplo de código acima, uma tabela com nome e função dos funcionários é montada com um v-for de uma lista, que contém dados de resposta obtidos de uma requisição HTTP, do tipo GET, para um endpoint de obter os funcionários escalados em um determinado dia, que é passado como parâmetro.</i></p>
  <br>
</details>

<details>
  <summary><b>Plotagem de gráficos de desempenho de pratos</b></summary>
  <br>
  <p>Realizei a plotagem de gráficos com os pratos, sobremesas e bebidas mais e menos vendidos de acordo com os dados do banco de dados.</p>
  
  ```javascript
  
  <template>
  <div class="container">
    <div class="component-title2">Mais Vendidos</div>
    <div class="row">
      <div class="column">
        <P class="desc-grafico">Principais mais vendidos</P>
        <bar-chart :data="maisVendidos.principal"></bar-chart>
      </div>
      <div class="column">
        <P class="desc-grafico">Sobremesas mais vendidas</P>
        <bar-chart :data="maisVendidos.sobremesa"></bar-chart>
      </div>
      <div class="column">
        <P class="desc-grafico">Bebidas mais vendidas</P>
        <bar-chart :data="maisVendidos.bebida"></bar-chart>
      </div>
    </div>

    <div class="component-title3">Menos Vendidos</div>
    <div class="row">
      <div class="column">
        <P class="desc-grafico">Principais menos vendidos</P>
        <bar-chart :data="menosVendidos.principal"></bar-chart>
      </div>
      <div class="column">
        <P class="desc-grafico">Sobremesas menos vendidas</P>
        <bar-chart :data="menosVendidos.sobremesa"></bar-chart>
      </div>
      <div class="column">
        <P class="desc-grafico">Bebidas menos vendidas</P>
        <bar-chart :data="menosVendidos.bebida"></bar-chart>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import BarChart from './BarChart.vue';

export default {
  name: 'pratos',
  components: {
    'bar-chart': BarChart,
  },
  data() {
    return {
      maisVendidos: { principal: [], sobremesa: [], bebida: [] },
      menosVendidos: { principal: [], sobremesa: [], bebida: [] }
    };
  },
  mounted() {
    this.fetchData();
  },
  methods: {
    fetchData() {
      axios.get('http://localhost:8081/pratos/mais-vendidos')
        .then(response => {
          this.maisVendidos = response.data;
        })
        .catch(error => {
          console.error('Erro ao buscar pratos mais vendidos: ', error);
        });

      axios.get('http://localhost:8081/pratos/menos-vendidos')
        .then(response => {
          this.menosVendidos = response.data;
        })
        .catch(error => {
          console.error('Erro ao buscar pratos menos vendidos: ', error);
        });
    }
  ```
  
  <p><i>No exemplo de código acima, são plotados 6 gráficos de barra, com os pratos principais, sobremesas e bebidas mais e menos vendidos. Cada gráfico recebia seus dados de acordo com as listas resgatadas do banco de dados, em endpoints do tipo GET para consultar os pratos com melhores e piores desempenhos.</i></p>
  <br>
</details><br>

### Aprendizados Efetivos

#### HARD SKILLS

<details>
  <summary>Vue.js</summary>
  <br>
    <ul>
      <li>Condicionais com v-if: sei fazer com ajuda</li>
      <li>Looping com v-for: sei fazer com ajuda</li>
      <li>Desenvolvimento com componentes: sei fazer com autonomia</li>
    </ul>
  <br>
</details>
<details>
  <summary>DevOps</summary>
  <br>
    <ul>
      <li>Gitflow Workflow: sei fazer com autonomia</li>
      <li>Deploy com Github Actions: sei fazer com ajuda</li>
      <li>Testes automatizados: sei fazer com autonomia</li>
    </ul>
  <br>
</details>
<br>

#### SOFT SKILLS
<ul>
      <li>Gestão de tempo: Sendo o responsável pelo frontend da aplicação, precisei gerir bem meu próprio tempo pois as telas dependiam exclusivamente de mim, então uma boa gestão de tempo foi essencial para não gerar atrasos nem pendências nas entregas.</li><br>
      <li>Criatividade: Para desenvolver telas exclusivas do zero, necessitei de criatividade para criar o layout dos painéis e decidir o que seria mostrado, e onde seria exibido.</li><br>
      <li>Responsabilidade: Como único desenvolvedor alocado no frontend, necessitei assumir a responsabilidade pelo meu próprio trabalho, cumprir prazos e entregar resultados com valor. Responsabilidade foi essencial para cumprir com minhas devidas atribuições.</li>
</ul>
<br>

[Projeto no GitHub](https://github.com/CarcaraTec/Cloud-Kitchen-Oracle)

<br><br>

<div id='projeto6' />


## Projeto 6: 1º Semestre de 2024
***Sistema de análise de sentimentos***
<H3 align="center"> Parceiro Acadêmico </H3>

<p align="center">
<img src="https://github.com/igorsuzuki99/Portfolio/blob/a83d652f36101c75c59c755d9951869008b37b4f/imagem_esri.png" alt="imagem" width="180" height="90">
</p>

### Descrição do Projeto
O desafio consistia em desenvolver um sistema capaz de compreender os sentimentos de clientes através de avaliações online obtidas pelo consumo de um produto ou serviço, para interpretar, em diferentes contextos, as necessidades de seus clientes. <br><br>
A solução foi uma plataforma web que, com dados obtidos de avaliações de hotéis, analisava e previa os sentimentos dos clientes através de modelos de machine learning, separando em diferentes categorias e segmentos, possibilitando uma visão mais clara e abrangente do desempenho dos hotéis através de visualização geográfica, e insights de diferentes contextos, com filtros por cidades, datas, hotéis e características específicas dos hóspedes.
<br><br>

## Tecnologias Utilizadas &nbsp;&nbsp;&nbsp; <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/python/python-original.svg" width="40" height="40"/> &nbsp; <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/scikitlearn/scikitlearn-original.svg" width="40" height="40"/> &nbsp; <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/java/java-original.svg" width="40" height="40"/> &nbsp; <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/spring/spring-original.svg" width="40" height="40"/> &nbsp; <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/mongodb/mongodb-original-wordmark.svg"  width="40" height="40"/> &nbsp; <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/mysql/mysql-original.svg" width="40" height="40"/> &nbsp; <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vuejs/vuejs-original.svg" width="40" height="40"/>

### Python a SKLearn
O Python, além de ser usado para o desenvolvimento da API back-end, também foi utilizado em conjunto com a biblioteca scikit-learn para o treinamento dos modelos de machine learning. Essa biblioteca contém uma série de modelos e ferramentas para auxiliar tanto na preparação de dados, quanto no treinamento dos modelos de aprendizado de máquina, e foi fundamental para o desenvolvimento e aperfeiçoamento do nosso modelo de classificação de sentimentos.
<br><br>

### Java e Spring 
Para o gerenciamento de usuários e outras funcionalidades que envolviam os conceitos de LGPD, foi utilizado Spring Boot para o desenvolvimento de um módulo específico para tratar a parte de gerenciamento de acesso. O fácil manuseio e familiaridade com o Java foi decisivo na escolha dessas ferramentas para tratar e implementar os conceitos da LGPD no projeto.
<br><br>

### MongoDB
O banco de dados não relacional MongoDB foi escolhido para armazenar os dados que passaram pelo nosso modelo de classificação de sentimentos. Como o MongoDB possui um schema flexível, foi a escolha ideal para armazenar os registros como "documentos", pois os dados não vinham somente com a classificação, mas também com outras informações contidas na base de dados original.
<br><br>

### MySQL
Para armazenar os dados referentes ao gerenciamento de acesso, foi utilizado o banco MySQL, por ser um banco relacional de fácil manuseio, para garantir a integridade e relacionamento dos dados dos usuários com os termos aceitos, informações de assinatura e demais logs que eram necessários.
<br><br>

### Vue.js
Para o front-end foi utilizado o Vue.js pela familiaridade com o framework, que permitiu desenvolver com maior facilidade os dashboards e gráficos. Como as telas do sistema continham muitos elementos de insights com o mesmo modelo visual, mudando somente o conteúdo dos dados, a componentização fornecida pelo Vue facilitou o desenvolvimento.
<br><br>

### Contribuições Individuais
<details>
  <summary><b>Tratamento da base de dados</b></summary>
  <br>
  <p>Realizei o tratamento da base de dados de avaliações de hotéis, para otimizar tanto o manuseio quanto o treinamento com ML posteriormente.</p>
  
  ```python
  
data = pd.read_csv(r'C:\Hotel_Reviews.csv', low_memory=False,delimiter=',', encoding='iso-8859-1', decimal='.')

df.loc[:, 'Positive_Review'] = data.Positive_Review.apply(lambda x: x.replace('No Positive', ''))
df.loc[:, 'Negative_Review'] = data.Negative_Review.apply(lambda x: x.replace('No Negative', ''))
df.sample(5)

def calculate_total_review(row):
    if row['Reviewer_Score'] < 6:
        return row['Negative_Review']
    else:
        return row['Positive_Review']

df.loc[:,'Total_Review'] = df.apply(calculate_total_review, axis=1)

df.loc[:,'review_type'] = df["Reviewer_Score"].apply(
    lambda x: "negative" if x < 6 else "positive"
)

positive_reviews = df_reviews[df_reviews.review_type == "positive"]
negative_reviews = df_reviews[df_reviews.review_type == "negative"]

min_reviews = min(len(positive_reviews), len(negative_reviews))

positive_df = positive_reviews.sample(n=min_reviews, random_state=42)
negative_df = negative_reviews.sample(n=min_reviews, random_state=42)

df_review_resampled = pd.concat([positive_df, negative_df], ignore_index=True)

  ```
  
  <p><i>No exemplo de código acima, é realizada a importação de um arquivo CSV contendo as avaliações de hotéis, no qual eu realizei alguns tratamentos como: replace de dados redundantes, uma condição para identificar o tipo de avaliação de acordo com a nota fornecida pelo avaliador (se foi uma avaliação negativa eu considero o que tem no campo de comentários negativos, e se for uma avaliação positiva, considero o que tem no campo de comentários positivos), e também faço um equilíbrio na quantidade de dados para o treinamento não ficar desbalanceado.</i></p>
  <br>
</details>

<details>
  <summary><b>Treinamento de modelos de Machine Learning</b></summary>
  <br>
  <p>Realizei o treinamento com diferentes modelos de Machine Learning, buscando uma classificação de sentimentos cada vez mais assertiva.</p>
  
  ```python
  
y = df['review_type']
y = y.map({'positive': 1, 'negative': 0})

X_train_count, X_test_count, y_train, y_test = train_test_split(text_vect_count, y, test_size=0.2, random_state=42)
X_train_tfidf, X_test_tfidf, _, _ = train_test_split(text_vect_tfidf, y, test_size=0.2, random_state=42)

def train_and_evaluate_model(model, X_train, X_test, y_train, y_test, model_name):
    model.fit(X_train, y_train)
    y_pred = model.predict(X_test)
    
    print(f"### {model_name} ###")
    print(f"Accuracy: {accuracy_score(y_test, y_pred)}")
    
    cm = confusion_matrix(y_test, y_pred)
    disp = ConfusionMatrixDisplay(confusion_matrix=cm)
    disp.plot()
    plt.title(f"Confusion Matrix - {model_name}")
    plt.show()
    
    print(classification_report(y_test, y_pred))
    
    with open(f'{model_name.lower()}_model.pkl', 'wb') as f:
        pickle.dump(model, f)

gbc = GradientBoostingClassifier(n_estimators=200, learning_rate=0.1, max_depth=5, random_state=42)
train_and_evaluate_model(gbc, X_train_count, X_test_count, y_train, y_test, "Gradient Boosting")

lgbm = lgb.LGBMClassifier(n_estimators=1000, learning_rate=0.05, num_leaves=31, max_depth=7, random_state=42)
train_and_evaluate_model(lgbm, X_train_tfidf, X_test_tfidf, y_train, y_test, "LightGBM")

catboost = CatBoostClassifier(iterations=1000, learning_rate=0.05, depth=6, verbose=100, random_seed=42)
train_and_evaluate_model(catboost, X_train_tfidf, X_test_tfidf, y_train, y_test, "CatBoost")

xgb = XGBClassifier(n_estimators=600, objective='binary:logistic', learning_rate=0.05, max_depth=5, min_child_weight=3, random_state=42)
train_and_evaluate_model(xgb, X_train_hash, X_test_hash, y_train, y_test, "XGBoost")

  ```
  
  <p><i>No exemplo de código acima, após a importação de um dataframe, os dados foram divididos entre treino e teste e foi declarada uma função para auxiliar no treinamento de diferentes modelos de Machine Learning, realizando o treinamento, teste, exibição de resultados e salvamento do modelo. Neste código foram treinados os modelos GradientBoosting, LightGMB, CatBoost e XGBoost, que são somente alguns modelos entre os vários testados durante o desenvolvimento.</i></p>
  <br>
</details>

<details>
  <summary><b>Classificação de diferentes idiomas e detecção de sarcasmo</b></summary>
  <br>
  <p>Implementei as funcionalidades de classificação de diferentes idiomas através de uma biblioteca de tradução, e detecção de sarcarmos com um modelo BERT pré treinado.</p>
  
  ```python

def translate_to_english(text):
   translator = GoogleTranslator(source='auto', target='en')
   return translator.translate(text)

tokenizer = AutoTokenizer.from_pretrained('nikesh66/Sarcasm-Detection-using-BERT')
sarcasm_model = AutoModelForSequenceClassification.from_pretrained('nikesh66/Sarcasm-Detection-using-BERT')

def detect_sarcasm(text):
    inputs = tokenizer(text, return_tensors='pt', truncation=True, padding=True, max_length=512)
    outputs = sarcasm_model(**inputs)
    logits = outputs.logits
    probabilities = torch.softmax(logits, dim=-1).tolist()[0]
    sarcasm_probability = probabilities[1]
    return sarcasm_probability

def predict_text(input_text):
    translated_text = translate_to_english(input_text)
    sarcasm_probability = detect_sarcasm(translated_text)
    if sarcasm_probability > 0.6:
        sentiment = {
            'sentiment': f'Sarcastic ({sarcasm_probability * 100:.2f}%)'
        }
    else:
        predicted_sentiment = predict_sentiment(input_text)
        sentiment = {
            'sentiment': predicted_sentiment
        }
    return sentiment

  ```
  
  <p><i>No código acima, é declarada uma função para traduzir textos, que recebe um texto e detecta de forma automática qual seu idioma e traduz para inglês. Também há uma função que detecta sarcasmos utilizando um modelo BERT pré treinado especificamente para detectar sarcasmos, e as duas funções são utilizadas para o tratamento do texto na função de classificação, a qual traduz o texto de entrada para inglês, verifica a probabilidade de sarcasmo e depois realiza a classificação normalmente com o modelo desenvolvido por mim.</i></p>
  <br>
</details><br>

### Aprendizados Efetivos

#### HARD SKILLS

<details>
  <summary>Python</summary>
  <br>
    <ul>
      <li>Tratamento de dados: sei fazer com autonomia</li>
      <li>Criação de endpoints com flask: sei fazer com autonomia</li>
      <li>Desenvolvimento com Jupyter Notebook: sei fazer com autonomia</li>
    </ul>
  <br>
</details>
<details>
  <summary>Aprendizado de Máquina</summary>
  <br>
    <ul>
      <li>Preparação de dados para treinamento: sei fazer com autonomia</li>
      <li>Treino e teste de diferentes modelos de machine learning: sei fazer com ajuda</li>
      <li>Interpretação de resultados e matriz de confusão: sei fazer com autonomia</li>
      <li>Uso de algoritmos para classificação de sentimentos: sei fazer com ajuda</li>
    </ul>
  <br>
</details>
<details>
  <summary>Banco de Dados Não-Relacional</summary>
  <br>
    <ul>
      <li>Criação e uso do MongoDB: sei fazer com autonomia</li>
      <li>Conexão do MongoDB com Python: sei fazer com autonomia</li>
      <li>Salvamento e busca de documentos: sei fazer com autonomia</li>
    </ul>
  <br>
</details>
<br>

#### SOFT SKILLS
<ul>
      <li>Adaptabilidade: Com novas tecnologias necessárias (machine learning e banco de dados não relacional), necessitei me adaptar com uma linguagem que não tinha familiaridade e também aprender a utilizar novas bibliotecas, ferramentas e frameworks.</li><br>
      <li>Aprendizado contínuo: Pelo fato de ser meu primeiro contato com aprendizado de máquina, necessitei aprender do zero como era o processo para a criação de um modelo. Inicialmente consegui desenvolver um modelo básico, porém para evoluir cada vez mais, necessitei de um aprendizado contínuo de novos modelos, novas bibliotecas e novos conceitos para melhoria da performance do classificador.</li><br>
      <li>Resolução de problemas: Durante o desenvolvimento do classificador de sentimentos, me deparei com muitos problemas que não reconhecia o motivo nem a solução, devido à falta de familiaridade com a área de machine learning. Com isso, foram necessárias intensas pesquisas e testes de diferentes cenários para conseguir contornar ou solucionar os problemas no decorrer do projeto.</li>
</ul>
<br>

[Projeto no GitHub](https://github.com/CarcaraTec/Imagem-api6sem)
<br><br><br>
