---
title: "G&#233;n&#233;ration d&#39;une biblioth&#232;que d&#39;importation et d&#39;un fichier d&#39;exportation | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLibrarianTool.ModuleDefinitionFile"
  - "VC.Project.VCLibrarianTool.ExportNamedFunctions"
  - "VC.Project.VCLibrarianTool.GenerateDebug"
  - "VC.Project.VCLibrarianTool.ForceSymbolReferences"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers .lib"
  - "/DEF (option du Gestionnaire de bibliothèque)"
  - "/EXPORT (option du Gestionnaire de bibliothèque)"
  - "/INCLUDE (option du Gestionnaire de bibliothèque)"
  - "/OUT (option du Gestionnaire de bibliothèque)"
  - "DEF (option du Gestionnaire de bibliothèque)"
  - "-DEF (option du Gestionnaire de bibliothèque)"
  - "fichiers EXP"
  - "EXPORT (option du Gestionnaire de bibliothèque)"
  - "-EXPORT (option du Gestionnaire de bibliothèque)"
  - "exporter les données"
  - "exporter les données, fichiers d'exportation (.exp)"
  - "bibliothèques d'importation, générer"
  - "INCLUDE (option du Gestionnaire de bibliothèque)"
  - "-INCLUDE (option du Gestionnaire de bibliothèque)"
  - "OUT (option du Gestionnaire de bibliothèque)"
  - "-OUT (option du Gestionnaire de bibliothèque)"
ms.assetid: 2fe4f30a-1dd6-4b05-84b5-0752e1dee354
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# G&#233;n&#233;ration d&#39;une biblioth&#232;que d&#39;importation et d&#39;un fichier d&#39;exportation
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour générer une bibliothèque d'importation et un fichier d'exportation, utilisez la syntaxe suivante :  
  
```  
LIB /DEF[:deffile] [options] [objfiles] [libraries]  
```  
  
 Quand l'option \/DEF est spécifiée, LIB crée les fichiers de sortie à partir des spécifications d'exportation qui sont passées dans la commande LIB.  Il existe trois méthodes de spécification des exportations, présentées dans l'ordre d'utilisation recommandé :  
  
1.  Une définition **\_\_declspec\(dllexport\)** dans l'un des *objfiles* ou l'une des *libraries*  
  
2.  Une spécification de l'option \/EXPORT:*name* sur la ligne de commande LIB  
  
3.  Une définition dans une instruction **EXPORTS** d'un `deffile`  
  
 Il s'agit des mêmes méthodes utilisées pour spécifier des exportations lors de la liaison d'un programme exportateur.  Un programme peut utiliser plusieurs méthodes.  Vous pouvez spécifier des portions de la commande LIB \(par exemple, des *objfiles* ou des spécifications \/EXPORT multiples\) au sein d'un fichier de commandes dans la commande LIB, tout comme vous pouvez le faire dans une commande LINK.  
  
 Les options suivantes s'appliquent à la génération d'une bibliothèque d'importation et d'un fichier d'exportation :  
  
 \/OUT:*import*  
 Substitue le nom du fichier de sortie par défaut pour la bibliothèque *import* en cours de création.  Quand l'option \/OUT n'est pas spécifiée, le nom par défaut correspond au nom de base du premier fichier objet ou bibliothèque dans la commande LIB et à l'extension .lib.  Le fichier d'exportation reçoit le même nom de base que la bibliothèque d'importation et l'extension .exp.  
  
 \/EXPORT:*entryname*\[\=*internalname*\]\[,@`ordinal`\[,**NONAME**\]\]\[,**DATA**\]  
 Exporte une fonction à partir de votre programme afin de permettre à d'autres programmes d'appeler la fonction.  Vous pouvez également exporter des données \(en utilisant le mot clé **DATA**\).  Les exportations sont généralement définies dans une DLL.  
  
 L'argument *entryname* est le nom de la fonction ou de l'élément de données tel qu'il doit être utilisé par le programme appelant.  Éventuellement, vous pouvez spécifier le *internalname* en tant que fonction connue dans le programme de définition ; par défaut, *internalname* est identique à *entryname*.  L'`ordinal` spécifie un index dans la table d'exportation dans une plage comprise entre 1 et 65 535 ; si vous ne spécifiez pas `ordinal`, LIB en assigne un.  Le mot clé **NONAME** exporte la fonction uniquement comme ordinal, sans *entryname*.  Le mot clé **DATA** est utilisé pour exporter des objets de type données seulement.  
  
 \/INCLUDE:`symbol`  
 Ajoute le symbole spécifié dans la table des symboles.  Cette option est utile pour forcer l'utilisation d'un objet bibliothèque, qui ne serait pas inclus autrement.  
  
 Notez que si vous créez votre bibliothèque d'importation lors d'une étape préliminaire, avant de créer votre fichier .dll, vous devez passer lors de la génération du fichier .dll le même jeu de fichiers objets que celui que vous avez passé lors de la génération de la bibliothèque d'importation.  
  
## Voir aussi  
 [Utilisation de bibliothèques d'importation et de fichiers d'exportation](../../build/reference/working-with-import-libraries-and-export-files.md)