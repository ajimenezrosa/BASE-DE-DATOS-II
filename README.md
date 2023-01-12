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
### 2.2   Operadores aritméticos y Comparaciones
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

