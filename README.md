![](https://kimerikal.com/wp-content/uploads/2019/07/sql-server-php-kimerikal.png)

| Alejandro Jimenez | UCSD |
|---------------------|------------------------|
|![](https://avatars.githubusercontent.com/u/7384546?v=4)|![](https://pbs.twimg.com/profile_images/901546652091252736/6Clcdv1L_400x400.jpg)|


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
### 2.1   Estructuras de Control
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

### 2.2   Operadores aritméticos y Comparaciones
	- practicar en 2 (dos) Hojas máximo, ubicar y explicar los operadores aritméticos

	- Haga un ejemplo con cada una de las estructuras de control del servidor Sql entregar en un archivo .sql

#

### 2.3   Operadores Lógicos.

### 2.4   Funciones de conversión.
### 2.5   Transacciones.
### 2.6   Funciones Definidas por el Usuario.
### 2.7   Practica #2 

#

## UNIDAD III.-  Temporales  Vistas y triggers	3.1   Tablas Temporales
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

