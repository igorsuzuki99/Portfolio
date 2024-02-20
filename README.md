# Igor Suzuki Kira

## Projeto 1: 2º Semestre de 2021
#### Carcará Analysis
### Descrição do Projeto
Desenvolver um projeto com o objetivo de analisar os dados oficiais da COVID-19 no Estado de São Paulo e entregá-los ao usuário de forma clara e contextualizada, através de visualizações gráficas ou não-gráficas.
<br><br>
### Tecnologias Utilizadas

<img src="https://github.com/igorsuzuki99/bertoti/blob/c282e732369eac9c6747be43ef7537406b0eecbe/Metodologia/python.png" alt="python" width="100" height="100">

#### Python
A aplicação foi desenvolvida predominantemente em Python devido à sua sintaxe clara e simplificada, além de uma vasta quantidade de bibliotecas e frameworks que suportam diversas áreas de desenvolvimento, incluindo análise de dados, que facilitou o processo de criação do primeiro projeto.
<br><br><br>

<img src="https://github.com/igorsuzuki99/bertoti/blob/bb03798c11a5ba06031f163a6aefdea19bfc9a25/Metodologia/pandas.png" alt="pandas" width="200" height="80">

#### Pandas
Para ajudar com a manipulação dos dados foi utilizado o Pandas, que é uma biblioteca que oferece estruturas de dados de alto desempenho, além de ferramentas de análise de dados. Ela foi usada para a leitura dos dados que eram obtidos através de CSVs. O Pandas também possui integração com a biblioteca NumPy, o que proporcionou um desempenho eficiente para as operações numéricas.
<br><br><br>

<img src="https://github.com/igorsuzuki99/bertoti/blob/311ec11072ab295d94f6687b7a1923c1402b5a53/Metodologia/plotly.png" alt="plotly" width="200" height="70">

#### Plotly
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
<details>
  <summary>Linguagem Python</summary>
  <br>
    <ul>
      <li>Lógica, variáveis e tipos de dados</li>
      <li>Funções</li>
      <li>Listas e dicionários</li>
      <li>Manipulação de entrada e saída de arquivos</li>
    </ul>
  <br>
</details>
<details>
  <summary>Plotagem de gráficos</summary>
  <br>
    <ul>
      <li>Popular e construir gráficos</li>
      <li>Plotagem de diferentes estilos de gráficos</li>
      <li>Manipulação e personalização de dados estatísticos</li>
    </ul>
  <br>
</details><br><br>



## Projeto 2: 1º Semestre de 2022
### Parceiro Acadêmico
#### Dom Rock

<img src="https://github.com/igorsuzuki99/bertoti/blob/e945b5938ce30752e0848b95343dda228c0cff3f/Metodologia/domrock.png" alt="domrock" width="230" height="70">
<br>

### Descrição do Projeto
Desenvolvimento de uma plataforma para criação e ativação de clientes para posterior uso da empresa. O projeto conta com telas de cadastro que inserem informações no banco de dados para posterior exibição na tela de consulta dos clientes.
<br><br><br>

### Tecnologias Utilizadas

<img src="https://github.com/igorsuzuki99/bertoti/blob/8ca25ab9891af0ebeea315388c33a7f40670bef4/Metodologia/swing.png" alt="swing" width="120" height="70">

#### Java e Swing 
A aplicação foi desenvolvida em Java, linguagem orientada a objetos, a qual juntamente com o framework Swing foi possível criar elementos visuais para utilização em um aplicativo desktop.
O Swing fornece componentes gráficos, como botões, caixas de texto, tabelas, entre outros, que podem ser usados para construir interfaces de usuário interativas. Essa característica foi útil nesse projeto pois facilitou o desenvolvimento da parte visual da aplicação.
<br><br><br>

<img src="https://github.com/igorsuzuki99/bertoti/blob/15e9c5d7351a579e2e31344f6e97498082a493ca/Metodologia/postgre.jpg" alt="postgres" width="100" height="100">

#### PostgreSQL
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
<details>
  <summary>Linguagem Java</summary>
  <br>
    <ul>
      <li>Orientação a objetos</li>
      <li>Funções em Java</li>
      <li>Integração com banco de dados</li>
      <li>Tratamento de erros</li>
    </ul>
  <br>
</details>
<details>
  <summary>Banco de dados</summary>
  <br>
    <ul>
      <li>Consultas personalizadas com SQL</li>
      <li>Gerenciamento de conexões</li>
    </ul>
  <br>
</details>
<details>
  <summary>Swing Framework</summary>
  <br>
    <ul>
      <li>Desenvolvimento através de componentes Swing</li>
      <li>Gerencimento de componentes GUI</li>
      <li>Desenvolvimento de aplicação desktop</li>
    </ul>
  <br>
</details><br><br>




## Projeto 3: 2º Semestre de 2022
### Parceiro Acadêmico
#### IACIT

<img src="https://github.com/igorsuzuki99/bertoti/blob/e476dee40e6b64e6f22ca2866eb7b950dc834383/Metodologia/download.png" alt="iacit" width="150" height="90">

### Descrição do Projeto
Desenvolvimento de um sistema no qual seja possível importar, pesquisar e gerar relatórios de dados meteorológicos. Além disso, alocação dos dados disponibilizados no site do Instituto Nacional de Meteorologia (INMET) para um banco de dados, para integrar com o sistema desenvolvido. Aplicação com interface web, que dispõe de um mecanismo de filtro no qual é possível filtrar os registros por datas, regiões, estados, localidades e tipo de dado, para posteriormente expor as informações em formato de gráficos e com a possibilidade de exportar um relatório com base na consulta realizada.

### Tecnologias Utilizadas

<img src="https://github.com/igorsuzuki99/bertoti/blob/3bdf06bd363c4a90096a16e0491ab4f8ca127638/Metodologia/javaspring.jpg" alt="spring" width="120" height="90">

#### Java e Spring 
O back-end da aplicação foi desenvolvido predominantemente em Java, uma linguagem orientada a objetos, na qual juntamente com a tecnologia de Spring foi possível criar endpoints para interfaces web.
O Spring é um framework que dispõe de recursos para criação de aplicações web escritas em Java e que traz mais agilidade para o desenvolvimento, visto que facilita as configurações iniciais do projeto com a injeção de dependências, as quais servem tanto para preparar o ambiente, quanto para otimizar a utilização de ferramentas e bibliotecas durante o desenvolvimento do projeto.
<br><br><br>

<img src="https://github.com/igorsuzuki99/bertoti/blob/15e9c5d7351a579e2e31344f6e97498082a493ca/Metodologia/postgre.jpg" alt="postgres" width="100" height="100">

#### PostgreSQL
O banco de dados utilizado foi o PostgreSQL, um banco relacional no qual alocamos todos os dados meteorológicos, dados de estações e regiões. A escolha do Postgres se deu por conta de sua versatilidade, interface simplificada, e funcionalidades expostas de forma dedutiva, que facilitaram a usabilidade e gerenciamento do banco de dados. A sua alta eficiência e desempenho contribuiram para armazenar com tranquilidade os milhões de dados meteorológicos importados.
<br><br><br>

<img src="https://github.com/igorsuzuki99/bertoti/blob/f15061508c05dbba8a39773679a2937d07c6a00c/Metodologia/chart%20(3).jfif" alt="spring" width="100" height="100">

#### Chart.js
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
<details>
  <summary>Spring Framework</summary>
  <br>
    <ul>
      <li>Desenvolvimento de aplicações web</li>
      <li>Arquitetura REST</li>
      <li>Integração com banco de dados</li>
      <li>Injeção de dependências</li>
      <li>Desenvolvimento de código através de interfaces</li>
    </ul>
  <br>
</details>
<details>
  <summary>Banco de dados</summary>
  <br>
    <ul>
      <li>Consultas personalizadas com SQL</li>
      <li>Geração de scripts</li>
      <li>Export e import de backup</li>
    </ul>
  <br>
</details>
<details>
  <summary>Programação</summary>
  <br>
    <ul>
      <li>Funções em JavaScript</li>
      <li>Manipulação de variáveis com JavaScript</li>
      <li>Programação orientada a objetos</li>
      <li>Consumo de API Rest</li>
      <li>Gerenciamento de usuários</li>
      <li>Consumo de recursos de bootstrap</li>
    </ul>
  <br>
</details><br><br>


## Projeto 4: 1º Semestre de 2023
### Parceiro Acadêmico
#### Embraer

<img src="https://github.com/igorsuzuki99/bertoti/blob/792ed4d524602bbda8b81e40500d30b0a93fa57a/Metodologia/embraer.png" alt="embraer" width="300" height="70">
<br>

### Descrição do Projeto
Desenvolvimento de uma plataforma em que o usuário consulte itens instalados nas aeronaves. O sistema inclui a verificação e edição de itens instalados ou aplicáveis a determinados "chassis" conforme base de dados fornecida.
<br><br><br>

### Tecnologias Utilizadas

<img src="https://github.com/igorsuzuki99/bertoti/blob/3bdf06bd363c4a90096a16e0491ab4f8ca127638/Metodologia/javaspring.jpg" alt="spring" width="120" height="90">

#### Java e Spring 
O back-end da aplicação foi desenvolvido em Java juntamente com o framework Spring, onde foi realizada a lógica das regras de negócio para determinação de quais itens eram considerados instalados, instaláveis ou não instaláveis de acordo com os chassis que fossem pesquisados. Através do Spring Data foi possível realizar consultas de forma mais eficiente no banco de dados para tratamento das lógicas e condições no back-end.
<br><br><br>

<img src="https://github.com/igorsuzuki99/bertoti/blob/e018c7c6990ba7bf256cd85a755669c315326d8c/Metodologia/autonomousdatabase.png" alt="databaseoracle" width="120" height="80">

#### Oracle Autonomous Database
Para armazenamento dos dados, foi utilizado o Oracle Autonomous Database, um banco relacional em nuvem. Foi escolhido devido a possibilidade de consultar o banco através da internet, proporcionando uma melhor acessibilidade, praticidade e flexibilidade. Além do mais, também proporcionou maior segurança, tanto no controle de acesso ao banco, quanto na consistência dos dados, pois eram gerados backups automáticos que protegiam contra a perda de dados e facilitavam a recuperação em caso de falhas de operação.
<br><br><br>

<img src="https://github.com/igorsuzuki99/bertoti/blob/cae68c8f73db8c544a69cf0f9965b5db786d8c41/Metodologia/vue.png" alt="vue" width="240" height="60">

#### Vue.js
O front-end do sistema foi desenvolvido em Vue.js, um framework JavaScript que conta com uma arquitetura estruturada por meio da criação de componentes reusáveis. Isso facilitou o desenvolvimento da plataforma, tendo em vista que certas partes visuais da interface tinham certa semelhança.
<br><br><br>

<img src="https://github.com/igorsuzuki99/bertoti/blob/d6b27b079fb959effbfb4c9f25e4cc39be24f57d/Metodologia/aws.png" alt="aws" width="110" height="80">

#### AWS
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
  <p>Contribuí no desenvolvimento da interface do front-end, onde implementei a utilização da biblioteca chart.js para construir os gráficos baseados nos dados meteorológicos requisitados. Realizei métodos em JavaScript, que consultavam os JSON's dos endpoints do back-end, e gerava os gráficos a partir dos dados captados. Também implementei inputs na página web para receber os critérios de filtragem e passar os parâmetros para o back-end realizar as consultas.</p>
  
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
  
  <p><i>No trecho de código acima foi utilizada a biblioteca do pdfMake, biblioteca para gerar e exportar documentos PDF. No corpo do dcoumento foram atribuídas as informações que serão expostas: o item, e se ele está instalado. E no final é chamado o método de createPdf para exportar o documento.</i></p>
  <br>
</details><br>


### Aprendizados Efetivos
<details>
  <summary>Spring Framework</summary>
  <br>
    <ul>
      <li>Integração do banco com Spring Data</li>
      <li>Arquitetura REST</li>
      <li>Implementação de Spring Security</li>
    </ul>
  <br>
</details>
<details>
  <summary>Banco de dados</summary>
  <br>
    <ul>
      <li>Segurança do banco de dados</li>
      <li>Hospedagem de banco em nuvem</li>
      <li>Gerenciamento de usuários do banco</li>
    </ul>
  <br>
</details>
<details>
  <summary>Hospedagem em nuvem</summary>
  <br>
    <ul>
      <li>Configuração de Windows Server</li>
      <li>Permissionamento de portas do servidor</li>
      <li>Gerenciamento de firewall</li>
      <li>Gerenciamento de recursos</li>
    </ul>
  <br>
</details><br><br>
