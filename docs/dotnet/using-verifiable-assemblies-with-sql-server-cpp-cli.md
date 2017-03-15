---
title: "Utilisation d&#39;assemblys v&#233;rifiables avec SQL Server (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "assemblys vérifiables (C++), à SQL Server"
ms.assetid: 5248a60d-aa88-4ff3-b30a-b791c3ea2de9
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation d&#39;assemblys v&#233;rifiables avec SQL Server (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les procédures stockées étendues, empaquetées comme bibliothèques de liens dynamiques \(DLL\), permettent d'étendre les fonctionnalités de SQL Server à travers des fonctions développées à l'aide de [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)].  Les procédures stockées étendues sont implémentées en tant que fonctions à l'intérieur des DLL.  En plus des fonctions, les procédures stockées étendues peuvent définir également des [types définis par l'utilisateur](../cpp/classes-and-structs-cpp.md) et des [fonctions d'agrégation](http://msdn.microsoft.com/fr-fr/de255454-f45e-4281-81f9-bc61893ac5da), telles que SUM ou AVG.  
  
 Lorsqu'un client exécute une procédure stockée étendue, SQL Server recherche la DLL associée à la procédure stockée étendue et charge la DLL.  SQL Server appelle la procédure stockée étendue demandée et l'exécute sous un contexte de sécurité spécifié.  La procédure stockée étendue passe ensuite des jeux de résultats et retourne les paramètres au serveur.  
  
 [!INCLUDE[sqprsqlong](../dotnet/includes/sqprsqlong_md.md)] fournit des extensions à Transact\-SQL \(T\-SQL\) pour vous permettre d'installer des assemblys vérifiables dans SQL Server.  Le jeu d'autorisations SQL Server spécifie le contexte de sécurité, avec les niveaux de sécurité suivants :  
  
-   Mode non restreint : exécutez le code à votre propre risque ; le code ne doit pas être de type sécurisé vérifié.  
  
-   Mode sans échec : exécutez le code de type sécurisé vérifié ; compilé avec \/clr:safe.  
  
 Le mode sans échec nécessite que les assemblys exécutés soient de type sécurisé vérifié.  
  
 Pour créer et charger un assembly vérifiable dans SQL Server, utilisez les commandes Transact\-SQL CREATE ASSEMBLY et DÉPLACEMENT ASSEMBLY comme suit :  
  
```  
CREATE ASSEMBLY <assemblyName> FROM <'Assembly UNC Path'> WITH   
  PERMISSION_SET <permissions>  
DROP ASSEMBLY <assemblyName>  
```  
  
 La commande PERMISSION\_SET spécifie le contexte de sécurité et peut avoir les valeurs UNRESTRICTED, SAFE ou EXTENDED.  
  
 De plus, vous pouvez utiliser la commande CREATE FUNCTION pour lier aux noms de méthodes dans une classe :  
  
```  
CREATE FUNCTION <FunctionName>(<FunctionParams>)  
RETURNS returnType  
[EXTERNAL NAME <AssemblyName>:<ClassName>::<StaticMethodName>]  
```  
  
## Exemple  
 Le script SQL suivant \(par exemple, "MyScript.sql" nommé\) charge un assembly dans SQL Server et rend une méthode d'une classe disponible :  
  
```  
-- Create assembly without external access  
drop assembly stockNoEA  
go  
create assembly stockNoEA  
from   
'c:\stockNoEA.dll'  
with permission_set safe  
  
-- Create function on assembly with no external access  
drop function GetQuoteNoEA  
go  
create function GetQuoteNoEA(@sym nvarchar(10))  
returns real  
external name stockNoEA:StockQuotes::GetQuote  
go  
  
-- To call the function  
select dbo.GetQuoteNoEA('MSFT')  
go  
```  
  
 Les scripts SQL peuvent être exécutés de façon interactive dans l'Analyseur de requêtes SQL ou sur la ligne de commande avec l'utilitaire sqlcmd.exe.  La ligne de commande suivante se connecte à MyServer, utilise la base de données par défaut, utilise une connexion approuvée, entre MyScript.sql et renvoie MyResult.txt.  
  
```  
sqlcmd –S MyServer -E –i myScript.sql –o myResult.txt  
```  
  
## Voir aussi  
 [Comment : effectuer une migration vers \/clr:safe](../dotnet/how-to-migrate-to-clr-safe-cpp-cli.md)   
 [Classes et structs](../cpp/classes-and-structs-cpp.md)