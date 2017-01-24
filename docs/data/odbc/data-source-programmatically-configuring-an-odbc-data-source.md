---
title: "Source de donn&#233;es&#160;: configuration d&#39;une source de donn&#233;es ODBC par programme | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SQLConfigDataSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "configurer les sources de données ODBC"
  - "ODBC (connexions), configurer"
  - "sources de données ODBC, configurer"
  - "SQLConfigDataSource (exemple de méthode)"
ms.assetid: b8cabe9b-9e12-4d73-ae36-7cb12dee3213
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Source de donn&#233;es&#160;: configuration d&#39;une source de donn&#233;es ODBC par programme
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique décrit comment configurer les noms de sources de données ODBC \(Open Database Connectivity\) par programmation.  Ainsi, vous avez la possibilité d'accéder aux données sans forcer l'utilisateur à recourir explicitement à l'Administrateur ODBC ou d'autres programmes pour spécifier les noms des sources de données.  
  
 Généralement, un utilisateur exécute l'Administrateur ODBC pour créer une source de données si le système de gestion de base de données \(SGBD\) associé prend en charge cette opération.  
  
 Lors de la création d'une source de données ODBC Microsoft Access à l'aide de l'Administrateur ODBC, vous avez le choix entre deux options : sélectionner un fichier .mdb existant ou en créer un nouveau.  Il n'existe aucun moyen de créer le fichier .mdb par programmation à partir de votre application ODBC MFC.  Par conséquent, si votre application nécessite de placer des données dans une source de données Microsoft Access \(fichier .mdb\), vous voulez probablement avoir un fichier .mdb vide que vous pourrez utiliser ou copier lorsque vous en aurez besoin.  
  
 Cependant, de nombreux systèmes de gestion de base de données permettent de créer une source de données par programmation.  Certaines sources de données conservent une spécification de répertoire pour les bases de données.  En d'autres termes, un répertoire est une source de données et chaque table de la source de données est stockée dans un fichier séparé \(dans le cas de dBASE, chaque table est un fichier .dbf\).  Les pilotes d'autres bases de données ODBC, telles que Microsoft Access et SQL Server, nécessitent que certains critères spécifiques soient remplis avant qu'une source de données ne soit établie.  Par exemple, lors de l'utilisation d'un pilote ODBC SQL Server, vous devez avoir établi un ordinateur SQL Server.  
  
##  <a name="_core_sqlconfigdatasource_example"></a> Exemple de SQLConfigDataSource  
 L'exemple suivant utilise la fonction API ODBC **::SQLConfigDataSource** pour créer une nouvelle source de données Excel intitulée « New Excel Data Source » :  
  
```  
SQLConfigDataSource(NULL,ODBC_ADD_DSN, "Excel Files (*.xls)",   
                   "DSN=New Excel Data Source\0"   
                   "Description=New Excel Data Source\0"   
                   "FileType=Excel\0"   
                   "DataDirectory=C:\\EXCELDIR\0"   
                   "MaxScanRows=20\0");  
```  
  
 Notez que la source de données est en réalité un répertoire \(C:\\EXCELDIR\) qui doit exister.  Le pilote Excel utilise les répertoires comme ses sources de données et les fichiers comme des tables individuelles \(une table par fichier .xls\).  
  
 Pour plus d'informations sur la création de tables, consultez [Source de données : création d'une table par programmation dans une source de données ODBC](../../data/odbc/data-source-programmatically-creating-a-table-in-an-odbc-data-source.md).  
  
 Les informations suivantes décrivent les paramètres que vous devez passer à la fonction API ODBC **::SQLConfigDataSource**.  Pour utiliser **::SQLConfigDataSource**, vous devez inclure le fichier d'en\-tête Odbcinst.h et utiliser la bibliothèque d'importation Odbcinst.lib.  De plus, Odbccp32.dll \(ou Odbcinst.dll pour les plateformes 16 bits\) doit se trouver dans le chemin d'accès lors de l'exécution.  
  
 Vous pouvez créer un nom de source de données ODBC à l'aide de l'Administrateur ODBC ou d'un utilitaire similaire.  Cependant, il est parfois préférable de créer un nom de source de données directement à partir de votre application pour obtenir l'accès sans que l'utilisateur ne doive exécuter un utilitaire distinct.  
  
 L'Administrateur ODBC \(installé généralement dans le Panneau de configuration\) crée une nouvelle source de données en ajoutant des entrées dans le Registre Windows \(ou pour les plateformes 16 bits, dans le fichier Odbc.ini\).  Le gestionnaire de pilote ODBC interroge ce fichier pour obtenir les informations requises sur la source de données.  Il est important de connaître les informations qui doivent être ajoutées au Registre, car vous devrez les spécifier lors de l'appel à **::SQLConfigDataSource**.  
  
 Bien qu'il soit possible d'écrire directement ces informations dans le Registre sans utiliser **::SQLConfigDataSource**, toute application qui procède de cette façon repose sur la technique actuelle utilisée par le gestionnaire de pilote pour conserver ses données.  Si une version ultérieure du gestionnaire de pilote ODBC implémente la maintenance d'enregistrements sur les sources de données d'une façon différente, toute application utilisant cette technique est interrompue.  Il est généralement conseillé d'utiliser une fonction API lorsqu'elle est fournie.  Par exemple, votre code est portable à partir de 16 bits jusqu'à 32 bits si vous utilisez la fonction **::SQLConfigDataSource**, car cette fonction écrit correctement dans le fichier Odbc.ini ou dans le Registre.  
  
##  <a name="_core_sqlconfigdatasource_parameters"></a> Paramètres de la fonction SQLConfigDataSource  
 Cette section décrit les paramètres de la fonction **::SQLConfigDataSource**.  La majorité des informations provient du *Guide de référence du programmeur* API ODBC livré avec la version 1.5 ou ultérieure de Visual C\+\+.  
  
###  <a name="_core_function_prototype"></a> Prototype de fonction  
  
```  
BOOL SQLConfigDataSource(HWND hwndParent,UINT fRequest, LPCSTR lpszDriver, LPCSTR lpszAttributes);  
```  
  
### Remarques  
  
####  <a name="_core_parameters_and_usage"></a> Paramètres et utilisation  
 *hwndParent*  
 Fenêtre spécifiée en tant que propriétaire de toute boîte de dialogue que le gestionnaire de pilote ODBC ou le pilote ODBC spécifique crée pour obtenir des informations supplémentaires de l'utilisateur sur la nouvelle source de données.  Si le paramètre `lpszAttributes` ne fournit pas assez d'informations, une boîte de dialogue s'affiche.  Le paramètre *hwndParent* peut être **NULL**.  
  
 `lpszDriver`  
 Description du pilote.  Il s'agit du nom présenté aux utilisateurs plutôt que du nom de pilote physique \(la DLL\).  
  
 `lpszAttributes`  
 Liste d'attributs sous format « keyname\=value ».  Ces chaînes sont séparées par des marques de fin null se terminant par deux marques de fin null consécutives à la fin de la liste.  Ces attributs représentent fondamentalement des entrées spécifiques au pilote par défaut, placés dans le Registre pour la nouvelle source de données.  Une clé importante, non mentionnée dans le guide de référence API ODBC, pour cette fonction est « DSN » \(Data Source Name\), qui spécifie le nom de la nouvelle source de données.  Les autres entrées sont spécifiques au pilote pour la nouvelle source de données.  Il n'est souvent pas nécessaire de fournir toutes les entrées, car le pilote peut inviter l'utilisateur à entrer les nouvelles valeurs dans des boîtes de dialogue \(lorsque la valeur de *hwndParent* est **NULL**\). Pour éviter que l'utilisateur ne soit obligé d'entrer ces valeurs, fournissez explicitement des valeurs par défaut.  
  
###### Pour déterminer la description d'un pilote pour le paramètre lpszDriver à l'aide de l'Administrateur ODBC  
  
1.  Exécutez l'Administrateur ODBC.  
  
2.  Cliquez sur **Ajouter**.  
  
 Vous obtenez une liste des pilotes installés et leurs descriptions.  Utilisez cette description comme paramètre `lpszDriver`.  Notez que vous utilisez la description complète, comme « Fichiers Excel \(\*.xls\) », comprenant l'extension du nom du fichier et les parenthèses s'ils existent dans la description.  
  
 Vous pouvez aussi analyser le Registre \(ou pour les plateformes 16 bits, le fichier Odbcinst.ini\), qui comprend une liste de toutes les entrées et descriptions de pilotes sous la clé de Registre « ODBC Drivers » \(ou la section \[ODBC Drivers\] dans le fichier Odbcinst.ini\).  
  
 Pour connaître les noms de clés et valeurs du paramètre `lpszAttributes`, vous pouvez analyser le fichier Odbc.ini d'une source de données déjà configurée \(peut\-être à l'aide de l'Administrateur ODBC\) :  
  
###### Pour connaître les noms de clés et les valeurs du paramètre lpszAttributes  
  
1.  Exécutez l'Éditeur du Registre Windows \(ou ouvrez le fichier Odbc.ini pour les plateformes 16 bits\).  
  
2.  Recherchez les informations de sources de données ODBC à l'aide de l'une des méthodes suivantes :  
  
    -   Pour les plateformes 32 bits, recherchez la clé **HKEY\_CURRENT\_USER\\Software\\ODBC\\ODBC.INI\\ODBC Data Sources** dans le volet gauche.  
  
         Le volet droit répertorie les entrées au format « pub: REG\_SZ:*\<nom de source de données\>*, où *\<nom de source de données\>* est la source de données déjà configurée avec les paramètres souhaités pour le pilote que vous voulez utiliser.  Sélectionnez la source de données souhaitée, par exemple, SQL Server.  Les éléments qui suivent la chaîne « pub: » sont, dans l'ordre, le nom de la clé et la valeur à utiliser dans votre paramètre `lpszAttributes`.  
  
    -   Pour les plateformes 16 bits, recherchez la section dans le fichier Odbc.ini marquée par \[*\<nom de source de données\>*\].  
  
         Les lignes suivant cette ligne se présentent sous la forme « keyname\=value ».  Elles représentent exactement les entrées à utiliser dans votre paramètre `lpszAttributes`.  
  
 Vous pouvez aussi lire la documentation relative au pilote que vous voulez utiliser.  Vous trouverez des informations utiles dans l'aide en ligne du pilote, à laquelle vous pouvez accéder en exécutant l'Administrateur ODBC.  Ces fichiers d'aide sont généralement placés dans le répertoire WINDOWS\\SYSTEM pour Windows NT, Windows 3.1 ou Windows 95.  
  
###### Pour obtenir de l'aide en ligne pour votre pilote ODBC  
  
1.  Exécutez l'Administrateur ODBC.  
  
2.  Cliquez sur **Ajouter**.  
  
3.  Sélectionnez le nom du pilote.  
  
4.  Cliquez sur **OK**.  
  
 Lorsque l'Administrateur ODBC affiche les informations pour créer une nouvelle source de données pour ce pilote spécifique, cliquez sur **Aide**.  Le fichier d'aide de ce pilote s'ouvre et comprend généralement des informations importantes sur l'utilisation du pilote.  
  
## Voir aussi  
 [Source de données \(ODBC\)](../../data/odbc/data-source-odbc.md)