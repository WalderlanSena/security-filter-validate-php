<h1 align="center">Exemplos dos Filtros de dados nativos do php</h1>
<h3 align="center">Desenvolvendo aplicações seguras com PHP <br />
  <br />
  <img src="https://seeklogo.com/images/P/php-logo-ADE513E748-seeklogo.com.png">
  <br />
  <img src="https://github.com/WalderlanSena/tagsGit/blob/master/mvsSecurity.svg">
</h3>
<p align="center">Exemplos de utilização dos métodos de filtragem de dados nativos da linguagem PHP</p>

<h2>O que é segurança da Informação ?</h2>
<p align="center">
  <img src="http://www.starti.com.br/blog/wp-content/uploads/2015/08/blogstarti_post_63.png"><br>
  "A segurança da informação está diretamente relacionada com proteção de um conjunto de informações, no sentido de preservar o valor que possuem para um indivíduo, produto ou uma organização."
</p>
<p align="justify"></p>

<h2>Vamos aos filtros do PHP</h2>

No <strong>php</strong> nativamente utilizamos a função <a href="https://secure.php.net/manual/pt_BR/function.filter-var.php">FILTER_VAR</a> para validar ou filtrar as nossas informações:

```php
mixed filter_var ( mixed $variable [, int $filter [, mixed $options ]] )

filter_var($valor, CONSTANTE_FILTRO)
```
<h3>Parâmetros:</h3>

<strong>Variável:</strong><br/>
<i>Valor para filtrar.</i>
<br/>

<strong>Filtro</strong><br />
<i>ID do filtro. O padrão é FILTER_SANITIZE_STRING.</i> <br />

<strong>Opções</strong><br />
<i>Array associativo de opções ou disjunção binário de flags. Se o filtro aceita opções, flags podem ser providas no campo "flags" do array. Para o "callback" do filtro, o tipo callback pode ser passado.</i>

<br />
<p align="justify">A dois tipos de possibilidades nas constantes: <strong>FILTER_SANITIZE_:</strong> Limpa o valor passando, e o <strong>FILTER_VALIDATE_:</strong> Valida se o valo está correto.</p>

<h2>Exemplo:</h2>

```php
var_dump(filter_var('walderlan@example.com', FILTER_VALIDATE_EMAIL));
var_dump(filter_var('12312', FILTER_VALIDATE_EMAIL));

// O exemplo acima irá imprimir
// string(19) "walderlan@email.com"
// bool(false)

if (filter_var('walderlan@example.com', FILTER_VALIDATE_EMAIL)) { 
    echo 'E-mail válido'; 
} else {
    echo 'E-mail não é válido';
}
```

<h4>Valor Retornado</h4>
<p>Retorna o dado filtrado, ou FALSE se o filtro falhar.</p>

<h5>Alguns dos filtros disponíveis:<h5>
<table>
  <thead>
    <th>Tipo</th>
    <th>Função</th>
  </thead>
  <tbody>
    <tr>
      <td>FILTER_VALIDATE_EMAIL</td>
      <td>Validando endereço de E-mail</td>
    </tr>
    <tr>
      <td>FILTER_VALIDATE_IP</td>
      <td>Validando endereço de IP</td>
    </tr>
    <tr>
      <td>FILTER_VALIDATE_URL</td>
      <td>Validando URL</td>
    </tr>
    <tr>
      <td>FILTER_VALIDATE_INT</td>
      <td>Validando se o valor é inteiro</td>
    </tr>
    <tr>
      <td>FILTER_VALIDATE_FLOAT</td>
      <td>Validando se o valor é float</td>
    </tr>
  </tbody>
</table>
