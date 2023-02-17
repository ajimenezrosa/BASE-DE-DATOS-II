![](https://kimerikal.com/wp-content/uploads/2019/07/sql-server-php-kimerikal.png)

| Alejandro Jimenez | UCSD |
|---------------------|------------------------|
|![](https://avatars.githubusercontent.com/u/7384546?v=4)|![](https://web1.ucsd.edu.do/wp-content/uploads/2022/03/cropped-Logo-UCSD-Redes-fondo-blanco-01.png)|


# BASE-DE-DATOS-II 


# UNIDAD I.- Repaso y nivelación Base de Datos I

### 1.1.	    Repaso de SQL (Structure Query Languaje)
### Bienvenido al curso de Base de datos II con servidor sql.

#### Espero que en él puedas encontrar contenido que sea útil para tu vida como profesional de la informática.

#### Antes de empezar el curso, sería bueno que hicieras un repaso a los temas tratados en nuestro curso de Base de datos 1, tal vez tomaste la materia con otro profesor o con la persona que te inscribiste.

#### Hay temas que son fundamentales para poder dominar los contenidos que trataremos.

#### Dejo en el enlace un Link que te llevará a los contenidos de la clase anterior.



#
### 1.2.	    Nivelación de Microsoft T-SQL 
#### Revisa los aspectos más relevantes de lo que es T-sql en nuestros documentos de base de datos I
  [T-sql de base de datos I](https://github.com/ajimenezrosa/Base-de-Datos-I#queessqlsql)
#

### 1.3.	    Repaso y nivelación de DML, DDL
#### En esta documentación podrás ver los aspectos más relevantes de lo que es el Lenguaje de Manipulación de Datos, desde el servidor sql.

#### Esta es la pagina oficial de microsft explorala y estudia los diferentes aspectos de este tema.
[Data manipulation language (Microsoft Access SQL)](https://learn.microsoft.com/en-us/office/client-developer/access/desktop-database-reference/data-manipulation-language)
#
### 1.4.	    Repaso y Nivelación Procedimientos Almacenados

[Creación de un procedimiento almacenado](https://github.com/ajimenezrosa/Base-de-Datos-I#procedure)


## Pagina Oficial de Microsoft
[Create a stored procedure](https://learn.microsoft.com/en-us/sql/relational-databases/stored-procedures/create-a-stored-procedure?view=sql-server-ver16)
#
[Modify a Stored Procedure](https://learn.microsoft.com/en-us/sql/relational-databases/stored-procedures/modify-a-stored-procedure?view=sql-server-ver16)
#
[Delete a stored procedure](https://learn.microsoft.com/en-us/sql/relational-databases/stored-procedures/delete-a-stored-procedure?view=sql-server-ver16)
#
[Execute a stored procedure](https://learn.microsoft.com/en-us/sql/relational-databases/stored-procedures/execute-a-stored-procedure?view=sql-server-ver16)


### 1.5.	   Clausulas SQL
#### Comandos SQL para manipulación de registros
[Manipulación de registros](https://github.com/ajimenezrosa/Base-de-Datos-I#manipulacion)


### 1.6.	   Practica # 1


## UNIDAD II.-  Operadores y Funciones

#### [2.1   Estructuras de Control](#21)
#### [2.2   Operadores aritméticos y Comparaciones](#22)
#### [2.3   Operadores Lógicos.](#23)
#### [2.4   Funciones de conversión.](#24)
#### [2.5   Transacciones.](#25)
#### [2.6   Funciones Definidas por el Usuario.](#26)
#### [2.7   Practica #2](#27) 
#







![](https://previews.123rf.com/images/stockbakery/stockbakery1710/stockbakery171001986/87835336-sql-hombre-que-trabaja-en-la-interfaz-hologr%C3%A1fica-pantalla-visual.jpg)


## Haz la siguiente práctica.
#### Cree cada una de las tablas que se muestran a continuación,
#### para cada uno de ellos debe crear cuatro procedimientos de almacenamiento,
         1 un Procedimiento de almacenamiento de selección por código (Select )
         2 un procedimiento de inserción
         3 un procedimiento de actualización
         4 a Procedimiento de borrado
#### Debe ser entregado en un archivo de formato .sql para el próximo jueves 19 de enero de 2023

## Recuerda que tarde o temprano la disciplina vencerá a la inteligencia. Sé fuerte y haz lo mejor que puedas.
#
## [Historia]

        [idHistoria] [int] 
        [fechaHistoria] [datetime]
        [observacion] [varchar](2000)
        [fechaAlta] [datetime] 

~~~sql

CREATE TABLE [dbo].[Historia](
	[idHistoria] [int] NOT NULL,
	[fechaHistoria] [datetime] NOT NULL,
	[observacion] [varchar](2000) NULL,
	[fechaAlta] [datetime] NULL,
 CONSTRAINT [PK_PacienteHistoria_1] PRIMARY KEY CLUSTERED 
(
	[idHistoria] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
~~~
# 
## [HistoriaPaciente]
        [idHistoria] [int]
        [idPaciente] [int]
        [idMedico] [int] 

~~~sql
CREATE TABLE [dbo].[HistoriaPaciente](
	[idHistoria] [int] NOT NULL,
	[idPaciente] [int] NOT NULL,
	[idMedico] [int] NOT NULL,
 CONSTRAINT [PK_HistoriaPaciente] PRIMARY KEY CLUSTERED 
(
	[idHistoria] ASC,
	[idPaciente] ASC,
	[idMedico] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
~~~
#


## [TurnoPaciente]
        [idTurno] [int] 
        [idPaciente] [int] 
        [idMedico] [smallint]
    CONSTRAINT [PK_PacienteTurno] PRIMARY KEY CLUSTERED

~~~sql
CREATE TABLE [dbo].[TurnoPaciente](
	[idTurno] [int] NOT NULL,
	[idPaciente] [int] NOT NULL,
	[idMedico] [smallint] NOT NULL,
 CONSTRAINT [PK_PacienteTurno] PRIMARY KEY CLUSTERED 
(
	[idTurno] ASC,
	[idPaciente] ASC,
	[idMedico] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
~~~

# 

## [Turno]
        [idTurno] [int]
        [fechaTurno] [datetime]
        [fechaAlta] [datetime]
        [estado] [nchar](10)
    CONSTRAINT [PK_Turno] PRIMARY KEY CLUSTERED 

~~~sql
CREATE TABLE [dbo].[Turno](
	[idTurno] [int] NOT NULL,
	[fechaTurno] [datetime] NULL,
	[fechaAlta] [datetime] NULL,
	[estado] [nchar](10) NULL,
 CONSTRAINT [PK_Turno] PRIMARY KEY CLUSTERED 
(
	[idTurno] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
~~~
# 

## [Pais]
        [idPais] [char](3)
        [pais] [varchar](30)
    CONSTRAINT [PK_Pais] PRIMARY KEY CLUSTERED 

~~~sql
CREATE TABLE [dbo].[Pais](
	[idPais] [char](3) NOT NULL,
	[pais] [varchar](30) NULL,
 CONSTRAINT [PK_Pais] PRIMARY KEY CLUSTERED 
(
	[idPais] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
~~~
# 




## [Especialidad]
        [idEspecialidad] [int] IDENTITY(1,1)
        [especialidad] [varchar](30) 
    CONSTRAINT [PK_Especialidad] PRIMARY KEY CLUSTERED 

~~~sql
CREATE TABLE [dbo].[Especialidad](
	[idEspecialidad] [int] IDENTITY(1,1) NOT NULL,
	[especialidad] [varchar](30) NULL,
 CONSTRAINT [PK_Especialidad] PRIMARY KEY CLUSTERED 
(
	[idEspecialidad] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
~~~
# 


## [Medico]
        [idMedico] [dbo].[medico] IDENTITY(1,1)
        [nombre] [varchar](50)
        [apellido] [varchar](50)
    CONSTRAINT [PK_Medico] PRIMARY KEY CLUSTERED 

~~~sql
CREATE TABLE [dbo].[Medico](
	[idMedico] [dbo].[medico] IDENTITY(1,1) NOT NULL,
	[nombre] [varchar](50) NULL,
	[apellido] [varchar](50) NULL,
 CONSTRAINT [PK_Medico] PRIMARY KEY CLUSTERED 
(
	[idMedico] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY]
GO

~~~
# 
## [MedicoEspecialidad]
        [idMedico] [int] 
        [idEspecialidad] [int]
        [descripcion] [varchar](50)
    CONSTRAINT [PK_MedicoEspecialidad] PRIMARY KEY CLUSTERED 
~~~sql
CREATE TABLE [dbo].[MedicoEspecialidad](
	[idMedico] [int] NOT NULL,
	[idEspecialidad] [int] NOT NULL,
	[descripcion] [varchar](50) NULL,
 CONSTRAINT [PK_MedicoEspecialidad] PRIMARY KEY CLUSTERED 
(
	[idMedico] ASC,
	[idEspecialidad] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
~~~


#### Cree las tablas que se muestran en el ejercicio.
#### Preste mucha atención al tipo de datos y su tamaño.

#### Debe enviar estos códigos en formato TXT o SQL. Te lo explicaremos en el aula.
#### **Recuerda que el secreto del éxito está en la perseverancia.**
#



#



## UNIDAD II.-  Operadores y Funciones
### 2.1   Estructuras de Control<a name="21"></a>
## **Estructuras de control Sql server**

## BEGIN...END
#### Incluye una serie de instrucciones Transact-SQL de forma que se pueda ejecutar un grupo de instrucciones Transact-SQL. BEGIN y END son palabras clave del lenguaje de control de flujo.

## Argumentos
#### { sql_statement | statement_block }
#### Se trata de cualquier instrucción o grupo de instrucciones Transact-SQL definidas con un bloque de instrucciones.

## Comentarios
#### Los bloques BEGIN...END pueden anidarse.

#### Aunque todas las instrucciones Transact-SQL son válidas en un bloque BEGIN...END, ciertas instrucciones Transact-SQL no deben agruparse en el mismo proceso por lotes o bloque de instrucciones.

## Ejemplos
#### En el siguiente ejemplo, BEGIN y END definen un conjunto de instrucciones Transact-SQL que se ejecutan juntas. Si el bloqueo BEGIN...END no se incluye, ambas instrucciones ROLLBACK TRANSACTION se ejecutarán y se devolverán ambos mensajes PRINT.

~~~sql
USE AdventureWorks2012
GO  
BEGIN TRANSACTION
GO  
IF @@TRANCOUNT = 0  
BEGIN  
    SELECT FirstName, MiddleName   
    FROM Person.Person WHERE LastName = 'Adams';
    ROLLBACK TRANSACTION;
    PRINT N'Rolling back the transaction two times would cause an error.';
END;
ROLLBACK TRANSACTION;
PRINT N'Rolled back the transaction.';
GO  
/*  
Rolled back the transaction.  
*/
~~~

#

## RETURN
#### RETURN (Transact-SQL)
#### Sale incondicionalmente de una consulta o procedimiento. RETURN es inmediata y completa, y se puede utilizar en cualquier punto para salir de un procedimiento, lote o bloque de instrucciones. Las instrucciones que siguen a RETURN no se ejecutan.

## Argumentos
#### integer_expression
#### Es el valor entero que se devuelve. Los procedimientos almacenados pueden devolver un valor entero al procedimiento que realiza la llamada o a una aplicación.

## Tipos de valor devueltos
#### Devuelve opcionalmente int.

## Observaciones
#### Cuando se utiliza con un procedimiento almacenado, RETURN no puede devolver un valor NULL. Si un procedimiento intenta devolver un valor NULL (por ejemplo, al utilizar RETURN @status cuando @status es NULL), se genera un mensaje de advertencia y se devuelve un valor 0.
#
#### El valor de estado devuelto se puede incluir en las siguientes instrucciones Transact-SQL del lote o procedimiento que ha ejecutado el procedimiento actual, pero se debe escribir de la forma siguiente: EXECUTE @return_status = <procedure_name>.
#
## Ejemplos
#### A. Devolver desde un procedimiento
#### En el siguiente ejemplo se muestra que si no se proporciona ningún nombre de usuario como parámetro al ejecutar findjobs, RETURN provoca la salida del procedimiento tras enviar un mensaje a la pantalla del usuario. Si se especifica un nombre de usuario, se obtienen de las tablas del sistema adecuadas los nombres de todos los objetos creados por este usuario en la base de datos actual.
#
~~~sql
CREATE PROCEDURE findjobs @nm sysname = NULL  
AS   
IF @nm IS NULL  
    BEGIN  
        PRINT 'You must give a user name'  
        RETURN  
    END  
ELSE  
    BEGIN  
        SELECT o.name, o.id, o.uid  
        FROM sysobjects o INNER JOIN master..syslogins l  
            ON o.uid = l.sid  
        WHERE l.name = @nm  
    END;
~~~


#### B. Devolver códigos de estado
#### En el siguiente ejemplo se comprueba el estado del Id. de un contacto especificado. Si el estado es Washington (WA), se devuelve un estado de 1. En caso contrario, se devuelve 2 para cualquier otra condición (un valor distinto de WA para StateProvince o ContactID que no coincida con una fila).
~~~sql
USE AdventureWorks2012;  
GO  
CREATE PROCEDURE checkstate @param VARCHAR(11)  
AS  
IF (SELECT StateProvince FROM Person.vAdditionalContactInfo WHERE ContactID = @param) = 'WA'  
    RETURN 1  
ELSE  
    RETURN 2;  
GO
~~~
#


## BREAK

#### BREAK (Transact-SQL)
#### BREAK sale del bucle WHILE actual. Si el bucle WHILE actual está anidado dentro de otro, BREAK solo sale del bucle actual y se proporciona el control a la siguiente instrucción del bucle exterior.

###### BREAK suele encontrarse dentro de una instrucción IF.


## Ejemplo para SQL Server
~~~sql
WHILE (1=1)
BEGIN
   IF EXISTS (SELECT * FROM ##MyTempTable WHERE EventCode = 'Done')
   BEGIN
      BREAK;  -- 'Done' row has finally been inserted and detected, so end this loop.
   END

   PRINT N'The other process is not yet done.';  -- Re-confirm the non-done status to the console.
   WAITFOR DELAY '00:01:30';  -- Sleep for 90 seconds.
END
~~~


## Ejemplo de un grupo de SQL exclusivo de Azure Synapse
~~~sql
declare @sleeptimesec int = 5;
declare @startingtime datetime2 = getdate();

PRINT N'Sleeping for ' + cast(@sleeptimesec as varchar(5)) + ' seconds'
WHILE (1=1)
BEGIN
  
	PRINT N'Sleeping.';  
	print datediff(s, getdate(),  @startingtime)

	if datediff(s, getdate(),  @startingtime) < -@sleeptimesec
		begin
			print 'We have finished waiting.'
			break;
		end
END
~~~


## THROW

#### THROW (Transact-SQL)
#### Genera una excepción y transfiere la ejecución a un bloque CATCH de una construcción TRY...CATCH.

#### Convenciones de sintaxis de Transact-SQL

~~~sql
THROW [ { error_number | @local_variable },  
        { message | @local_variable },  
        { state | @local_variable } ]   
[ ; ]
~~~

## Argumentos
##### error_number
#### Es una constante o una variable que representan la excepción. error_number es de tipo int y debe ser mayor o igual que 50000 y menor o igual que 2147483647.

## message
#### Es una cadena o una variable que describe la excepción. message es nvarchar (2048) .

## state
#### Es una constante o una variable comprendida entre 0 y 255 que indica el estado que se ha de asociar al mensaje. state es tinyint.

## Observaciones
#### La instrucción anterior a la instrucción THROW debe ir seguida del terminador de instrucción punto y coma (;).

#### Si una construcción TRY…CATCH no está disponible, el lote de instrucciones se finaliza. Se establecen el número de línea y el procedimiento donde se produce la excepción. La gravedad se establece en 16.

#### Si la instrucción THROW se especifica sin parámetros, debe aparecer dentro de un bloque CATCH. Esto hace que se produzca la excepción detectada. Cualquier error que se produzca en una instrucción THROW hace que el lote de instrucciones se finalice.

#### % es un carácter reservado en el texto del mensaje de una instrucción THROW y debe ser de escape. Duplique el carácter % para devolver % como parte del texto del mensaje, por ejemplo "el aumento supera un 15 %% el valor original".
#



## CONTINUE

#### Reinicia un bucle WHILE. Las instrucciones que se encuentren después de la palabra clave CONTINUE se omiten. CONTINUE se suele abrir, aunque no siempre, con una comprobación IF. Para más información, vea WHILE (Transact-SQL) y Lenguaje de control de flujo (Transact-SQL).

#

## TRY...CATCH
#### Implementa un mecanismo de control de errores para Transact-SQL que es similar al control de excepciones en los lenguajes Microsoft Visual C# y Microsoft Visual C++. Se puede incluir un grupo de instrucciones Transact-SQL en un bloque TRY. Si se produce un error en el bloque TRY, el control se suele transferir a otro grupo de instrucciones que está incluido en un bloque CATCH.

~~~sql
BEGIN TRY  
     { sql_statement | statement_block }  
END TRY  
BEGIN CATCH  
     [ { sql_statement | statement_block } ]  
END CATCH  
[ ; ]
~~~

## Argumentos
## sql_statement
#### Es cualquier instrucción Transact-SQL.

## statement_block
#### Grupo de instrucciones Transact-SQL incluidas en un lote o en un bloque BEGIN…END.

## Observaciones
#### Una construcción TRY…CATCH detecta todos los errores de ejecución que tienen una gravedad mayor de 10 y que no cierran la conexión de la base de datos.

#### Un bloque TRY debe ir seguido inmediatamente por un bloque CATCH asociado. Si se incluye cualquier otra instrucción entre las instrucciones END TRY y BEGIN CATCH se genera un error de sintaxis.

#### Una construcción TRY…CATCH no puede abarcar varios lotes. Una construcción TRY…CATCH no puede abarcar varios bloques de instrucciones Transact-SQL. Por ejemplo, una construcción TRY…CATCH no puede abarcar dos bloques BEGIN…END de instrucciones Transact-SQL, ni puede abarcar una construcción IF…ELSE.

#### Si no hay errores en el código incluido en un bloque TRY, cuando la última instrucción de este bloque ha terminado de ejecutarse, el control se transfiere a la instrucción inmediatamente posterior a la instrucción END CATCH asociada.

#### Si hay un error en el código incluido en un bloque TRY, el control se transfiere a la primera instrucción del bloque CATCH asociado. Cuando finaliza el código del bloque CATCH, el control se transfiere a la instrucción inmediatamente posterior a la instrucción END CATCH.




## Etiqueta GOTO
#### Altera el flujo de ejecución y lo dirige a una etiqueta. Las instrucciones Transact-SQL que siguen a una instrucción GOTO se pasan por alto y el procesamiento continúa en el punto que marca la etiqueta. Las instrucciones GOTO y las etiquetas se pueden utilizar en cualquier punto de un procedimiento, lote o bloque de instrucciones. Las instrucciones GOTO se pueden anidar.


## Argumentos
#### label
#### Es el punto tras el que comienza el procesamiento cuando una instrucción GOTO especifica esa etiqueta. Las etiquetas deben cumplir las reglas de los identificadores. Una etiqueta puede servir para comentar si se utiliza GOTO.

## Observaciones
#### GOTO puede aparecer dentro de las instrucciones de control de flujo condicional, en bloques de instrucciones o en procedimientos, pero no se puede dirigir a una etiqueta externa al lote. La ramificación con GOTO se puede dirigir a una etiqueta definida antes o después de la instrucción GOTO.

## Permisos
#### De forma predeterminada, cualquier usuario válido puede utilizar GOTO.

## Ejemplos
#### En el ejemplo siguiente se muestra cómo usar GOTO como mecanismo de bifurcación.


~~~sql
DECLARE @Counter int;  
SET @Counter = 1;  
WHILE @Counter < 10  
BEGIN   
    SELECT @Counter  
    SET @Counter = @Counter + 1  
    IF @Counter = 4 GOTO Branch_One --Jumps to the first branch.  
    IF @Counter = 5 GOTO Branch_Two  --This will never execute.  
END  
Branch_One:  
    SELECT 'Jumping To Branch One.'  
    GOTO Branch_Three; --This will prevent Branch_Two from executing.  
Branch_Two:  
    SELECT 'Jumping To Branch Two.'  
Branch_Three:  
    SELECT 'Jumping To Branch Three.';  
~~~
#






## WAITFOR

#### Bloquea la ejecución de un lote, un procedimiento almacenado o una transacción hasta alcanzar la hora o el intervalo de tiempo transcurrido, o hasta que una instrucción especificada modifique o devuelva al menos una fila.

~~~sql
WAITFOR   
{  
    DELAY 'time_to_pass'   
  | TIME 'time_to_execute'   
  | [ ( receive_statement ) | ( get_conversation_group_statement ) ]   
    [ , TIMEOUT timeout ]  
}
~~~

## Argumentos
## DELAY
#### Es el período de tiempo especificado (hasta un máximo de 24 horas) que debe transcurrir antes de la ejecución de un lote, un procedimiento almacenado o una transacción.

#### "tiempo_que_transcurre"
#### Es el período de tiempo que hay que esperar. time_to_pass se puede especificar en un formato de datos de datetime o como una variable local. Las fechas no se pueden especificar, por lo que la parte de la fecha del valor datetime no se permite. time_to_pass tiene el formato hh:mm[[:ss],mss].

## TIME
#### Es la hora especificada a la que se ejecuta el lote, el procedimiento almacenado o la transacción.

## "hora_de_ejecución"
#### Es la hora a la que termina la instrucción WAITFOR. time_to_execute se puede especificar en un formato de datos de datetime, o bien se puede especificar como una variable local. Las fechas no se pueden especificar, por lo que la parte de la fecha del valor datetime no se permite. time_to_execute tiene el formato hh:mm[[:ss],mss] y, opcionalmente, puede incluir la fecha de 01-01-1900.

## instrucción_receive
#### Es una instrucción RECEIVE válida.


## IF...ELSE
#### Impone condiciones en la ejecución de una instrucción Transact-SQL. La instrucción Transact-SQL que sigue a una palabra clave IF y a su condición se ejecuta si la condición se cumple: la expresión booleana devuelve TRUE. La palabra clave opcional ELSE introduce otra instrucción Transact-SQL que se ejecuta cuando la condición IF no se cumple: la expresión booleana devuelve FALSE.
#
## Argumentos
## Boolean_expression
#### Es una expresión que devuelve TRUE o FALSE. Si la expresión booleana contiene una instrucción SELECT, la instrucción SELECT debe ir entre paréntesis.

## { sql_statement| statement_block }
#### Se trata de cualquier instrucción o grupo de instrucciones Transact-SQL definidas con un bloque de instrucciones. A menos que se utilice un bloque de instrucciones, la condición IF o ELSE puede afectar al rendimiento de una sola instrucción Transact-SQL.

#### Para definir un bloque de instrucciones, utilice las palabras clave de control de flujo BEGIN y END.

## Observaciones
#### Una construcción IF...ELSE puede utilizarse en lotes, en procedimientos almacenados y en consultas ad hoc. Cuando esta construcción se utiliza en un procedimiento almacenado, se suele utilizar para probar la existencia de algún parámetro.

#### Las pruebas IF pueden estar anidadas después de otra área IF o a continuación de un área ELSE. El límite del número de niveles anidados depende de la memoria disponible.

## Ejemplo
## SQL

#
~~~sql
IF DATENAME(weekday, GETDATE()) IN (N'Saturday', N'Sunday')
       SELECT 'Weekend';
ELSE 
       SELECT 'Weekday';
~~~

#### Para más ejemplos, vea ELSE (IF...ELSE) (Transact-SQL).

## Ejemplos: Azure Synapse Analytics y Sistema de la plataforma de análisis (PDW)
#### En el ejemplo siguiente se usa IF...ELSE para determinar cuál de las dos respuestas se muestra al usuario, en función del peso de un elemento en la tabla DimProduct.
#



## WHILE
#### Establece una condición para la ejecución repetida de una instrucción o bloque de instrucciones SQL. Las instrucciones se ejecutan repetidamente siempre que la condición especificada sea verdadera. Se puede controlar la ejecución de instrucciones en el bucle WHILE con las palabras clave BREAK y CONTINUE.

## Argumentos
## Boolean_expression
#### Es una expresión que devuelve TRUE o FALSE. Si la expresión booleana contiene una instrucción SELECT, la instrucción SELECT debe ir entre paréntesis.
#
## {sql_statement | statement_block}
#### Se trata de cualquier instrucción o grupo de instrucciones Transact-SQL definidas con un bloque de instrucciones. Para definir un bloque de instrucciones, utilice las palabras clave de control de flujo BEGIN y END.

## BREAK
#### Produce la salida del bucle WHILE más interno. Se ejecutan las instrucciones que aparecen después de la palabra clave END, que marca el final del bucle.

## CONTINUE
#### Hace que se reinicie el bucle WHILE y omite las instrucciones que haya después de la palabra clave CONTINUE.

## Comentarios
#### Si dos o más bucles WHILE están anidados, la instrucción BREAK interna sale al siguiente bucle más externo. Todas las instrucciones que se encuentran después del final del bucle interno deben ejecutarse primero y después se reinicia el siguiente bucle más externo.

## Ejemplos
#### A. Utilizar BREAK y CONTINUE con IF…ELSE y WHILE anidados
#### En el ejemplo siguiente, si el precio de venta promedio de un producto es inferior a $300, el bucle WHILE dobla los precios y, a continuación, selecciona el precio máximo. Si el precio máximo es menor o igual que $500, el bucle WHILE se reinicia y vuelve a doblar los precios. Este bucle continúa doblando los precios hasta que el precio máximo es mayor que $500, después de lo cual sale del bucle WHILE e imprime un mensaje.
#
~~~sql
USE AdventureWorks2012;  
GO  
WHILE (SELECT AVG(ListPrice) FROM Production.Product) < $300  
BEGIN  
   UPDATE Production.Product  
      SET ListPrice = ListPrice * 2  
   SELECT MAX(ListPrice) FROM Production.Product  
   IF (SELECT MAX(ListPrice) FROM Production.Product) > $500  
      BREAK  
   ELSE  
      CONTINUE  
END  
PRINT 'Too much for the market to bear';
~~~
#### B. Usar WHILE en un cursor
#### En el ejemplo siguiente se usa @@FETCH_STATUS para controlar las actividades del cursor en un bucle WHILE.

~~~sql
DECLARE @EmployeeID as NVARCHAR(256)
DECLARE @Title as NVARCHAR(50)

DECLARE Employee_Cursor CURSOR FOR  
SELECT LoginID, JobTitle   
FROM AdventureWorks2012.HumanResources.Employee  
WHERE JobTitle = 'Marketing Specialist';  
OPEN Employee_Cursor;  
FETCH NEXT FROM Employee_Cursor INTO @EmployeeID, @Title;  
WHILE @@FETCH_STATUS = 0  
   BEGIN  
      Print '   ' + @EmployeeID + '      '+  @Title 
      FETCH NEXT FROM Employee_Cursor INTO @EmployeeID, @Title;  
   END;  
CLOSE Employee_Cursor;  
DEALLOCATE Employee_Cursor;  
GO
~~~


## Ejemplos: Azure Synapse Analytics y Sistema de la plataforma de análisis (PDW)

#### C: Bucle WHILE simple
#### En el ejemplo siguiente, si el precio de venta promedio de un producto es inferior a $300, el bucle WHILE dobla los precios y, a continuación, selecciona el precio máximo. Si el precio máximo es menor o igual que $500, el bucle WHILE se reinicia y vuelve a doblar los precios. Este bucle continúa doblando los precios hasta que el precio máximo es mayor que $500, después de lo cual sale del bucle WHILE.
~~~sql
-- Uses AdventureWorks  
  
WHILE ( SELECT AVG(ListPrice) FROM dbo.DimProduct) < $300  
BEGIN  
    UPDATE dbo.DimProduct  
        SET ListPrice = ListPrice * 2;  
    SELECT MAX ( ListPrice) FROM dbo.DimProduct  
    IF ( SELECT MAX (ListPrice) FROM dbo.DimProduct) > $500  
        BREAK;  
END
~~~

### 2.2   Operadores aritméticos y Comparaciones<a name="22"></a>
	- practicar en 2 (dos) Hojas máximo, ubicar y explicar los operadores aritméticos

	- Haga un ejemplo con cada una de las estructuras de control del servidor Sql entregar en un archivo .sql

#

### 2.3   Operadores Lógicos.<a name="23"></a>

#### Los operadores lógicos comprueban la veracidad de alguna condición. Al igual que los operadores de comparación, devuelven el tipo de datos Boolean con el valor TRUE, FALSE o UNKNOWN.

|Operator |	Significado |
|-----------------------|-----------------------------|
|ALL   | 	TRUE si el conjunto completo de comparaciones es TRUE.|
|AND|	TRUE si ambas expresiones booleanas son TRUE.|
|ANY|	TRUE si cualquier miembro del conjunto de comparaciones es TRUE.|
|BETWEEN|	TRUE si el operando está dentro de un intervalo.|
|EXISTS|	TRUE si una subconsulta contiene cualquiera de las filas.|
|IN |	TRUE si el operando es igual a uno de la lista de expresiones.|
|LIKE|	TRUE si el operando coincide con un patrón.|
|NOT|	Invierte el valor de cualquier otro operador booleano.|
|OR|	TRUE si cualquiera de las dos expresiones booleanas es TRUE.|
|SOME |	TRUE si alguna de las comparaciones de un conjunto es TRUE.|
Consulte también

## ALL
#### Es una subconsulta que devuelve un conjunto de resultados de una columna. El tipo de datos de la columna devuelta debe ser igual que el tipo de datos de scalar_expression.

#### Es una instrucción SELECT restringida en la que no se permiten la cláusula ORDER BY ni la palabra clave INTO.

## Ejemplos
#### En el ejemplo siguiente se crea un procedimiento almacenado que determina si todos los componentes de un objeto SalesOrderID especificado en la base de datos AdventureWorks2019 se pueden fabricar en el número de días especificado. En el ejemplo se usa una subconsulta para crear una lista del número del valor de DaysToManufacture para todos los componentes del SalesOrderID específico y, a continuación, confirma que todos los DaysToManufacture están dentro del número de días especificado.

~~~sql
-- Uses AdventureWorks

CREATE PROCEDURE DaysToBuild @OrderID INT, @NumberOfDays INT  
AS  
IF   
@NumberOfDays >= ALL  
   (  
    SELECT DaysToManufacture  
    FROM Sales.SalesOrderDetail  
    JOIN Production.Product   
    ON Sales.SalesOrderDetail.ProductID = Production.Product.ProductID   
    WHERE SalesOrderID = @OrderID  
   )  
PRINT 'All items for this order can be manufactured in specified number of days or less.'  
ELSE   
PRINT 'Some items for this order can''t be manufactured in specified number of days or less.' ;
~~~


#### Para probar el procedimiento, ejecútelo con SalesOrderID 49080, que tiene un componente que requiere 2 días y dos componentes que requieren 0 días. La primera instrucción que se indica a continuación cumple los criterios. La segunda consulta no.

~~~sql
EXECUTE DaysToBuild 49080, 2 ;
~~~

#### El conjunto de resultados es el siguiente:

    All items for this order can be manufactured in specified number of days or less.

~~~sql
EXECUTE DaysToBuild 49080, 1 ;  
~~~
#### El conjunto de resultados es el siguiente:

    Some items for this order can't be manufactured in specified number of days or less.
# 

## AND 
#### Combina dos expresiones booleanas y devuelve TRUE cuando ambas expresiones son TRUE. Cuando se usa más de un operador lógico en una instrucción, en primer lugar se evalúan los operadores AND. Puede cambiar el orden de evaluación gracias a los paréntesis.


## Ejemplos
#### A. Utilizar el operador AND
#### En el ejemplo siguiente se selecciona información sobre los empleados que tienen el cargo de Marketing Assistant y más de 41 horas de vacaciones disponibles.

~~~sql
-- Uses AdventureWorks  
  
SELECT  BusinessEntityID, LoginID, JobTitle, VacationHours   
FROM HumanResources.Employee  
WHERE JobTitle = 'Marketing Assistant'  
AND VacationHours > 41 ;
~~~

#### B. Utilizar el operador AND en una instrucción IF
#### En los ejemplos siguientes se muestra cómo utilizar AND en una instrucción IF. En la primera instrucción, 1 = 1 y 2 = 2 son true; por consiguiente, el resultado es true. En el segundo ejemplo, el argumento 2 = 17 es false; por consiguiente, el resultado es false.
~~~sql
IF 1 = 1 AND 2 = 2  
BEGIN  
   PRINT 'First Example is TRUE'  
END  
ELSE PRINT 'First Example is FALSE' ;  
GO  
  
IF 1 = 1 AND 2 = 17  
BEGIN  
   PRINT 'Second Example is TRUE'  
END  
ELSE PRINT 'Second Example is FALSE' ;  
GO
~~~

## ANY 
#### Compara un valor escalar con un conjunto de valores de una sola columna.

#### Ejemplos
#### A. Ejecutar un ejemplo sencillo
    Las instrucciones siguientes crean una tabla simple y agregan los valores 1, 2, 3 y 4 a la columna de ID.
~~~sql
CREATE TABLE T1  
(ID INT) ;  
GO  
INSERT T1 VALUES (1) ;  
INSERT T1 VALUES (2) ;  
INSERT T1 VALUES (3) ;  
INSERT T1 VALUES (4) ;
~~~
    La consulta siguiente devuelve TRUE porque 3 es menor que alguno de los valores de la tabla.

~~~sql
IF 3 < SOME (SELECT ID FROM T1)  
PRINT 'TRUE'   
ELSE  
PRINT 'FALSE' ;
~~~

    La consulta siguiente devuelve FALSE porque 3 no es menor que todos los valores de la tabla.

~~~sql
IF 3 < ALL (SELECT ID FROM T1)  
PRINT 'TRUE'   
ELSE  
PRINT 'FALSE' ;
~~~
#


## BETWEEN 

#### BETWEEN devuelve TRUE si el valor de test_expression es mayor o igual que el valor de begin_expression y menor o igual que el valor de end_expression.

#### NOT BETWEEN devuelve TRUE si el valor de test_expression es menor que el valor de begin_expression y mayor que el valor de end_expression.

## Ejemplos
#### A. Utilizar BETWEEN
#### En el ejemplo siguiente se devuelve información sobre los roles de base de datos de una de base de datos. La primera consulta devuelve todos los roles. En el segundo ejemplo se usa la cláusula BETWEEN para limitar los roles a los valores database_id especificados.
~~~sql
SELECT principal_id, name 
FROM sys.database_principals
WHERE type = 'R';

SELECT principal_id, name 
FROM sys.database_principals
WHERE type = 'R'
AND principal_id BETWEEN 16385 AND 16390;
GO  
~~~
#
#### B. Utilizar > y < en lugar de BETWEEN
#### En el siguiente ejemplo se utilizan los operadores mayor que (>) y menor que (<) y, puesto que dichos operadores no son inclusivos, se devuelven nueve filas en lugar de las diez devueltas en el ejemplo anterior.

~~~sql
-- Uses AdventureWorks  
  
SELECT e.FirstName, e.LastName, ep.Rate  
FROM HumanResources.vEmployee e   
JOIN HumanResources.EmployeePayHistory ep   
    ON e.BusinessEntityID = ep.BusinessEntityID  
WHERE ep.Rate > 27 AND ep.Rate < 30  
ORDER BY ep.Rate;  
GO  
~~~
#

## EXISTS 
#### Especifica una subconsulta para probar la existencia de filas.
 

##  Ejemplos
#### A. Utilizar NULL en una subconsulta para seguir devolviendo un conjunto de resultados
#### En el ejemplo siguiente se devuelve un conjunto de resultados con NULL especificado en la subconsulta, que se sigue evaluando como TRUE al utilizar EXISTS.
~~~sql
-- Uses AdventureWorks  
  
SELECT DepartmentID, Name   
FROM HumanResources.Department   
WHERE EXISTS (SELECT NULL)  
ORDER BY Name ASC ;  
~~~
# 
#### B. Comparar consultas mediante EXISTS e IN
#### En el ejemplo siguiente se comparan dos consultas que son semánticamente equivalentes. En la primera consulta se utiliza EXISTS y en la segunda IN.
~~~sql
-- Uses AdventureWorks  
  
SELECT a.FirstName, a.LastName  
FROM Person.Person AS a  
WHERE EXISTS  
(SELECT *   
    FROM HumanResources.Employee AS b  
    WHERE a.BusinessEntityID = b.BusinessEntityID  
    AND a.LastName = 'Johnson') ;  
GO  
~~~
#

## IN 
#### Si el valor de test_expression es igual a cualquier valor devuelto por subquery o si es igual a cualquier expression de la lista separada por comas, el valor devuelto es TRUE; en caso contrario, el valor del resultado es FALSE.

#### El uso de NOT IN niega el valor de subquery o de expression.


## Ejemplos
#### A. Comparar OR e IN
#### En el ejemplo siguiente se selecciona una lista con los nombres de los empleados que son ingenieros de diseño, ingenieros de herramientas o asistentes de marketing.

~~~sql
-- Uses AdventureWorks  
  
SELECT p.FirstName, p.LastName, e.JobTitle  
FROM Person.Person AS p  
JOIN HumanResources.Employee AS e  
    ON p.BusinessEntityID = e.BusinessEntityID  
WHERE e.JobTitle = 'Design Engineer'   
   OR e.JobTitle = 'Tool Designer'   
   OR e.JobTitle = 'Marketing Assistant';  
GO  
~~~
    No obstante, con IN se recuperan los mismos resultados.
~~~sql
-- Uses AdventureWorks  
  
SELECT p.FirstName, p.LastName, e.JobTitle  
FROM Person.Person AS p  
JOIN HumanResources.Employee AS e  
    ON p.BusinessEntityID = e.BusinessEntityID  
WHERE e.JobTitle IN ('Design Engineer', 'Tool Designer', 'Marketing Assistant');  
GO  
~~~
#

## LIKE 
#### Determina si una cadena de caracteres específica coincide con un patrón especificado. Un patrón puede contener caracteres normales y caracteres comodín. Durante la operación de búsqueda de coincidencias de patrón, los caracteres normales deben coincidir exactamente con los caracteres especificados en la cadena de caracteres. Sin embargo, los caracteres comodín pueden coincidir con fragmentos arbitrarios de la cadena. El uso de caracteres comodín hace que el operador LIKE sea más flexible que los operadores de comparación de cadenas = y !=. Si alguno de los argumentos no es del tipo de datos de cadena de caracteres, Motor de base de datos de SQL Server lo convierte al tipo de datos de cadena de caracteres, si es posible.

### Argumentos
# 
|Carácter comodín	|Descripción	| Ejemplo |
|----------------|----------------|-------------------|
|%|	|Cualquier cadena de cero o más caracteres.|	WHERE title LIKE '%computer%' busca todos los títulos de libros que contengan la palabra 'computer' en el título.|
|_ |(carácter de subrayado)	Cualquier carácter individual.|	WHERE au_fname LIKE ‘_ean’ busca todos los nombres de cuatro letras que terminen en ean (Dean, Sean, etc.)|
|[ ] |	Cualquier carácter individual del intervalo ([a-f]) o del conjunto ([abcdef]) que se ha especificado.|	WHERE au_lname LIKE ‘[C-P]arsen’ busca apellidos de autores que terminen en arsen y empiecen por cualquier carácter individual entre C y P, como Carsen, Larsen, Karsen, etc. En las búsquedas de intervalos, los caracteres incluidos en el intervalo pueden variar, dependiendo de las reglas de ordenación de la intercalación.|
|[^]|	Cualquier carácter individual que no se encuentre en el intervalo ([^a-f]) o el conjunto ([^abcdef]) que se ha especificado.|	WHERE au_lname LIKE ‘de[^l]%’ busca todos los apellidos de autores que empiecen por de y en los que la siguiente letra no sea l.|
#

## Observaciones
#### Cuando se realizan comparaciones de cadenas con LIKE, todos los caracteres de la cadena patrón son significativos, Los caracteres significativos incluyen los espacios iniciales o finales. Si una comparación de una consulta debe devolver todas las filas con una cadena LIKE 'abc ' (abc seguido de un espacio), no se devolverán las filas en las que el valor de esa columna sea abc (sin espacio al final). Sin embargo, no se tienen en cuenta los espacios en blanco finales de la expresión con la que se compara el patrón. Si la comparación de una consulta debe devolver todas las filas con la cadena LIKE 'abc' (abc sin espacio), se devolverán todas las filas que empiecen por abc y tengan cero o más espacios al final.

#### Una comparación de cadenas con un patrón que contenga datos de tipo char y varchar puede no pasar una comparación LIKE debido a la forma en que se han almacenado los datos para cada tipo de datos. En el siguiente ejemplo se pasa una variable local char a un procedimiento almacenado y luego se usa la coincidencia de patrones para encontrar todos los empleados cuyos apellidos empiecen por un juego de caracteres especificado.

~~~sql
-- Uses AdventureWorks  
  
CREATE PROCEDURE FindEmployee @EmpLName CHAR(20)  
AS  
SELECT @EmpLName = RTRIM(@EmpLName) + '%';  
SELECT p.FirstName, p.LastName, a.City  
FROM Person.Person p JOIN Person.Address a ON p.BusinessEntityID = a.AddressID  
WHERE p.LastName LIKE @EmpLName;  
GO  
EXEC FindEmployee @EmpLName = 'Barb';  
GO
~~~
#### En el procedimiento FindEmployee, no se devuelven filas porque la variable char (@EmpLName) contiene espacios al final cuando el nombre tiene menos de 20 caracteres. Debido a que la columna LastName es de tipo varchar, no hay espacios al final. Este procedimiento no funciona porque los espacios al final son significativos.

#### Pero el siguiente ejemplo funciona porque no se agregan espacios al final a una variable varchar.

~~~sql
-- Uses AdventureWorks  
  
CREATE PROCEDURE FindEmployee @EmpLName VARCHAR(20)  
AS  
SELECT @EmpLName = RTRIM(@EmpLName) + '%';  
SELECT p.FirstName, p.LastName, a.City  
FROM Person.Person p JOIN Person.Address a ON p.BusinessEntityID = a.AddressID  
WHERE p.LastName LIKE @EmpLName;  
GO  
EXEC FindEmployee @EmpLName = 'Barb';
~~~




#

### 2.4   Funciones de conversión.<a name="24"></a>
|Veremos en este capitulo|
|-------------------------|
|CAST y CONVERT (Transact-SQL)|
|PARSE (Transact-SQL)|
|TRY_CAST (Transact-SQL)|
|TRY_CONVERT (Transact-SQL)|
|TRY_PARSE (Transact-SQL)|

## CAST y CONVERT
#### Estas funciones convierten una expresión de un tipo de datos a otro.


## PARSE 
#### Devuelve el resultado de una expresión, traducido al tipo de datos solicitado en SQL Server.
#### ejemplos
~~~sql
SELECT PARSE('Monday, 13 December 2010' AS datetime2 USING 'en-US') AS Result;
~~~
#

## TRY_CAST
#### Devuelve una conversión de valor al tipo de datos especificado si la conversión se realiza correctamente; de lo contrario, devuelve NULL.

### Observaciones
#### TRY_CAST toma el valor que se le ha pasado e intenta convertirlo al data_type especificado. Si la conversión se realiza correctamente, TRY_CAST devuelve el valor como el data_type especificado; si se produce un error, se devuelve NULL. Pero si se solicita una conversión que no se permite explícitamente, TRY_CAST generará un error.

#### TRY_CAST no es una palabra clave reservada y está disponible en todos los niveles de compatibilidad. TRY_CAST tiene la misma semántica que TRY_CONVERT al conectarse a los servidores remotos.

## Ejemplos
#### A. TRY_CAST devuelve NULL
#### En el ejemplo siguiente se muestra que TRY_CAST devuelve NULL cuando se produce un error en la conversión.

~~~sql
SELECT   
    CASE WHEN TRY_CAST('test' AS float) IS NULL   
    THEN 'Cast failed'  
    ELSE 'Cast succeeded'  
END AS Result;  
GO  
~~~ 

## TRY_CONVERT
#### Devuelve una conversión de valor al tipo de datos especificado si la conversión se realiza correctamente; de lo contrario, devuelve NULL.

## Observaciones
#### TRY_CONVERT toma el valor que se le ha pasado e intenta convertirlo al data_type especificado. Si la conversión se realiza correctamente, TRY_CONVERT devuelve el valor como el data_type especificado; si se produce un error, se devuelve NULL. Pero si se solicita una conversión que no se permite explícitamente, TRY_CONVERT generará un error.

#### TRY_CONVERT es una palabra clave reservada en el nivel de compatibilidad 110 y posteriores.

#### Esta función se puede enviar de forma remota a servidores que tengan una versión de SQL Server 2012 (11.x) y superior. No se puede enviar de forma remota a servidores que tengan una versión inferior a SQL Server 2012 (11.x).


## Ejemplos
#### A. TRY_CONVERT devuelve NULL
#### En el ejemplo siguiente se muestra que TRY_CONVERT devuelve NULL cuando se produce un error en la conversión.
~~~sql
SELECT   
    CASE WHEN TRY_CONVERT(float, 'test') IS NULL   
    THEN 'Cast failed'  
    ELSE 'Cast succeeded'  
END AS Result;  
GO
~~~

## TRY_PARSE 
#### Devuelve el resultado de una expresión, traducido al tipo de datos solicitado, o NULL si se produce un error en la conversión en SQL Server. Use TRY_PARSE solo para convertir de tipos de cadena a tipos de fecha y hora y de número.


## Ejemplos
#### A. Ejemplo simple de TRY_PARSE
~~~sql
SELECT TRY_PARSE('Jabberwokkie' AS datetime2 USING 'en-US') AS Result;  
~~~ 

#

#### B. Detectar valores NULL con TRY_PARSE
~~~sql
SELECT  
    CASE WHEN TRY_PARSE('Aragorn' AS decimal USING 'sr-Latn-CS') IS NULL  
        THEN 'True'  
        ELSE 'False'  
END  
AS Result; 
~~~










## 2.5   Transacciones.<a name="25"></a>
## Transacciones
#### Se aplica a: SQL Server (todas las versiones admitidas)  Azure SQL Database  Azure SQL Managed Instance  Azure Synapse Analytics  Analytics Platform System (PDW)
#
#### Una transacción es una unidad única de trabajo. Si una transacción tiene éxito, todas las modificaciones de los datos realizadas durante la transacción se confirman y se convierten en una parte permanente de la base de datos. Si una transacción encuentra errores y debe cancelarse o revertirse, se borran todas las modificaciones de los datos.
#
## SQL Server funciona en los modos de transacción siguientes:

## Transacciones de confirmación automática
#### Cada instrucción individual es una transacción.

## Transacciones explícitas
#### Cada transacción se inicia explícitamente con la instrucción BEGIN TRANSACTION y se termina explícitamente con una instrucción COMMIT o ROLLBACK.

## Transacciones implícitas
#### Se inicia implícitamente una nueva transacción cuando se ha completado la anterior, pero cada transacción se completa explícitamente con una instrucción COMMIT o ROLLBACK.

## Transacciones de ámbito de lote
#### Una transacción implícita o explícita de Transact-SQL que se inicia en una sesión de MARS (conjuntos de resultados activos múltiples), que solo es aplicable a MARS, se convierte en una transacción de ámbito de lote. Si no se confirma o revierte una transacción de ámbito de lote cuando se completa el lote, SQL Server la revierte automáticamente.
#
## Practica
Realizar investigacion y colocar ejemplos de las siguientes transacciones

    BEGIN TRANSACTION
    ROLLBACK TRANSACTION
    COMMIT TRANSACTION
#



## 2.6   Funciones Definidas por el Usuario.<a name="26"></a>

#### Al igual que las funciones en lenguajes de programación, SQL Server funciones definidas por el usuario son rutinas que aceptan parámetros, realizan una acción, como un cálculo complejo, y devuelven el resultado de esa acción como valor. El valor devuelto puede ser un valor escalar único o un conjunto de resultados.

## Ventajas de las funciones definidas por el usuario

## ¿Por qué usar funciones definidas por el usuario (UDF)?

#### Programación modular. Puede crear la función una vez, almacenarla en la base de datos y llamarla desde el programa tantas veces como desee. Las funciones definidas por el usuario se pueden modificar, independientemente del código de origen del programa.

#### Ejecución más rápida. De forma similar a los procedimientos almacenados, las funciones definidas por el usuario de Transact-SQL reducen el costo de compilación del código de Transact-SQL almacenando en caché los planes y reutilizándolos para ejecuciones repetidas. Esto significa que la función definida por el usuario no necesita volver a analizarse y volver a personalizarse con cada uso, lo que da lugar a tiempos de ejecución mucho más rápidos.

#### Las funciones CLR ofrecen una ventaja de rendimiento significativa sobre las funciones de Transact-SQL para las tareas computacionales, la manipulación de cadenas y la lógica de negocios. Las funciones de Transact-SQL son más adecuadas para la lógica intensiva de acceso a datos.

#### Reduzca el tráfico de red. Una operación que filtra los datos en función de alguna restricción compleja que no se puede expresar en una sola expresión escalar se puede expresar como una función. La función se puede invocar luego en la cláusula WHERE para reducir el número de filas que se envían al cliente.

## Tipos de funciones
## Funciones escalares
#### Las funciones escalares definidas por el usuario devuelven un único valor de datos del tipo definido en la cláusula RETURNS. En una función escalar insertada, el valor escalar es el resultado de una sola instrucción. Para una función escalar de varios estados, el cuerpo de la función puede contener una serie de instrucciones Transact-SQL que devuelven el valor único. El tipo devuelto puede ser de cualquier tipo de datos excepto text, ntext, image, cursory timestamp. Para obtener ejemplos, consulte Creación de funciones definidas por el usuario (motor de base de datos).

## Funciones con valores de tabla
#### Las funciones con valores de tabla (TVF) definidas por el usuario devuelven un tipo de datos de tabla . Las funciones insertada con valores de tabla no tienen cuerpo; la tabla es el conjunto de resultados de una sola instrucción SELECT. Para obtener ejemplos, consulte Creación de funciones definidas por el usuario (motor de base de datos).

## Funciones del sistema
#### SQL Server proporciona muchas funciones del sistema que puede usar para realizar varias operaciones. No se pueden modificar. Para obtener más información, vea Funciones integradas (Transact-SQL),Funciones almacenadas del sistema (Transact-SQL) y Funciones y vistas y funciones de administración dinámica (Transact-SQL).


#
## 2.7   Practica #2<a name="27"></a> 

## Cree una consulta para cada uno de los conceptos tratados en este capítulo
#### 2.1 Estructuras de Control
#### 2.2 Operadores aritméticos y comparaciones
#### 2.3 Operadores Lógicos.
#### 2.4 Funciones de conversión.
#### 2.5 Transacciones.
#### 2.6 Funciones definidas por el usuario.



#

## UNIDAD III.-  Temporales  Vistas y triggers	
### 3.1   Tablas Temporales
### 3.2   Vistas
### 3.3   Triggers
### 3.4   Programando Stored Procedures de SELECT UPDATE y DELETE
### 3.5   Práctica#3.1
#



## UNIDAD IV.- SQL Server Administración

### 4.1    Backup y Restores Database
### 4.2    Schedule JOBS
### 4.3 Administración de Usuarios, Roles, Schemas y Permisos
### 4.4  Practica#4 
#

## UNIDAD V.- SQL Profiler y manipulación de registros externos
### 5.1   importación de registros SQL Server
### 5.2   exportación de Registros SQL Server
### 5.3   SQL Server Profiler
### 5.3   Data Visualización con Power BI
### 5.3   Practica#5.

