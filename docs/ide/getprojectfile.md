---
title: "GetProjectFile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetProjectFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetProjectFile (méthode)"
ms.assetid: e5fdc468-755a-4b4e-81bd-e63881531bed
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# GetProjectFile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Retourne le type spécifié du nom de fichier.  
  
## Syntaxe  
  
```  
  
      function GetProjectFile(   
   oProj,   
   strType,   
   bFullPath,   
   bMFC    
);  
```  
  
#### Paramètres  
 oProj  
 Projet sélectionné.  
  
 `strType`  
 Type de fichier à récupérer tel que STDAFX, RC, IDL, CPP, H, ODL ou DEF.  
  
 *bFullPath*  
 Indicateur signalant si le nom de chemin complet doit être retourné.  
  
 *bMFC*  
 Indique si le projet est fondé sur MFC.  Si le paramètre `strType` est .cpp ou .h, le projet est considéré comme étant fondé sur MFC.  Si ce n'est pas le cas, le projet est considéré comme étant fondé sur ATL.  
  
## Valeur de retour  
 Retourne le nom de fichier du type des fichiers par projet.  
  
## Notes  
 Appelez cette fonction pour obtenir le nom de fichier du type spécifié dans le projet spécifié.  
  
## Exemple  
  
```  
// The selected MFC project's CPP file is retrieved and   
// assigned to strFileName.  
var strFileName = GetProjectFile(selProj, "CPP", false, true);  
```  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)   
 [GetProjectPath](../ide/getprojectpath.md)   
 [GetUniqueFileName](../ide/getuniquefilename.md)