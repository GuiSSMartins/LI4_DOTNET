## || Como programar em .NET (#C)? ||

Dado por julio.duarte@algoritmi.uminho.pt (Professor Júlio Duarte - Enegnharia Biomédica - Informática Médica)

__Tecnologias__: _Microsoft Visual Studio_ e _.NET_

É um IDE (Integrated Development Environment): aplicação que fornece funcionalidades para o desenvolvimento de software (da Microsoft).

Para o nosso trabalho, vai ser feito com o méodulo _WEB Designer_ (__ASP.NET__), que inclui __C#__, __HTML__, __Javascript__...

Também será usado o módulo Data Designer para fazer a ligação da Base de Dados com a aplicação web.

Deve ser utilizado o __.NET FRAMEWORK__ para o sistema operativo Windows (não se aconselha usar Linux neste trabalho).

### -> Comandos básicos

### -> Ligação SQL Server - C#

### -> Criação de Interfaces

### -> DEMO (exemplo de aplicação)

ATENÇÃO: Não se pode usar o Oracle SQL Developer -> TEM DE SER O __SQL SERVER__.

Uso de packages para se ligar ao Oracle 
```cs
using System.Security.Cryptography;
using Oracle.ManagedDataAccess.Client;

// Preencher todos os campos que faltam (p)
string host = ;
string port = "1512"
string sid = ;
string user = ;
string password = ;

string stringCon = "Data Source=(DESCRIPTION = (ADRESS = (PROTOCOL = TCP)(HOST = " 
                    + host + ")(PORT = " + port + "))(CONNECT_DATA = (SERVER = DEDICATED)(SERVICE_NAME = "
                    + sid + ")));Password=" + password + ";User ID=" + user;

OracleConnection con = new OracleConnection(stringCon);

string sql = "select id,nome,comentario from temp_fulio";
con.Open();
OracleCommand comando = new OracleCommand(sql, con);
OracleDataReader leitor = comando.ExecuteReader();
while(leitor.Read()){
  Console.WriteLine(leitor.GetValue(1).ToString() + "-" + leitor.GetString(2));
}
con.Close();
Console.Read();
```
