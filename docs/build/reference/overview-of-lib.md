---
title: "Vue d&#39;ensemble de LIB | Microsoft Docs"
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
  - "Lib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LIB (C++), modes"
ms.assetid: e997d423-f574-434f-8b56-25585d137ee0
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Vue d&#39;ensemble de LIB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LIB crée des bibliothèques standard, des bibliothèques d'importation et des fichiers d'exportation que vous pouvez utiliser avec [LINK](../../build/reference/linker-options.md) lors de la génération d'un programme.  LIB s'exécute à partir d'une invite de commandes.  
  
 Vous pouvez utiliser LIB dans les modes suivants :  
  
-   [Génération ou modification d'une bibliothèque COFF](../../build/reference/managing-a-library.md)  
  
-   [Extraction d'un objet membre dans un fichier](../../build/reference/extracting-a-library-member.md)  
  
-   [Création d'une bibliothèque d'importation et d'un fichier d'exportation](../../build/reference/working-with-import-libraries-and-export-files.md)  
  
 Ces modes s'excluent mutuellement ; vous pouvez utiliser LIB dans un seul de ces modes à la fois.  
  
## Options Lib  
 Le tableau suivant répertorie les options de lib.exe, avec un lien vers d'autres informations.  
  
 **\/DEF**  
 Crée une bibliothèque d'importation et un fichier d'exportation.  
  
 Pour plus d'informations, consultez [Génération d'une bibliothèque d'importation et d'un fichier d'exportation](../../build/reference/building-an-import-library-and-export-file.md).  
  
 **\/ERRORREPORT**  
 Envoie des informations à Microsoft sur les erreurs internes avec lib.exe.  
  
 Pour plus d'informations, consultez [Exécution de LIB](../../build/reference/running-lib.md).  
  
 **\/EXPORT**  
 Exporte une fonction de votre programme.  
  
 Pour plus d'informations, consultez [Génération d'une bibliothèque d'importation et d'un fichier d'exportation](../../build/reference/building-an-import-library-and-export-file.md).  
  
 **\/EXTRACT**  
 Crée un fichier objet \(.obj\) qui contient une copie d'un membre d'une bibliothèque existante.  
  
 Pour plus d'informations, consultez [Extraction d'un membre de bibliothèque](../../build/reference/extracting-a-library-member.md).  
  
 **\/INCLUDE**  
 Ajoute un symbole à la table des symboles.  
  
 Pour plus d'informations, consultez [Génération d'une bibliothèque d'importation et d'un fichier d'exportation](../../build/reference/building-an-import-library-and-export-file.md).  
  
 **\/LIBPATH**  
 Substitue le chemin de la bibliothèque d'environnement.  
  
 Pour plus d'informations, consultez [Gestion d'une bibliothèque](../../build/reference/managing-a-library.md).  
  
 **\/LIST**  
 Affiche les informations sur la bibliothèque de sortie dans la sortie standard.  
  
 Pour plus d'informations, consultez [Gestion d'une bibliothèque](../../build/reference/managing-a-library.md).  
  
 **\/LTCG**  
 Entraîne la génération de la bibliothèque à l'aide de la génération du code au moment de la liaison.  
  
 Pour plus d'informations, consultez [Exécution de LIB](../../build/reference/running-lib.md).  
  
 **\/MACHINE**  
 Spécifie la plateforme cible du programme.  
  
 Pour plus d'informations, consultez [Exécution de LIB](../../build/reference/running-lib.md).  
  
 **\/NAME**  
 Lors de la génération d'une bibliothèque d'importation, spécifie le nom de la DLL pour laquelle la bibliothèque d'importation est générée.  
  
 Pour plus d'informations, consultez [Gestion d'une bibliothèque](../../build/reference/managing-a-library.md).  
  
 **\/NODEFAULTLIB**  
 Supprime une ou plusieurs bibliothèques par défaut de la liste des bibliothèques qu'elle parcourt lors de la résolution de références externes.  
  
 Pour plus d'informations, consultez [Gestion d'une bibliothèque](../../build/reference/managing-a-library.md).  
  
 **\/NOLOGO**  
 Supprime l'affichage du message de copyright et du numéro de version de LIB, et empêche la reproduction par écho des fichiers de commandes.  
  
 Pour plus d'informations, consultez [Exécution de LIB](../../build/reference/running-lib.md).  
  
 **\/OUT**  
 Substitue le nom du fichier de sortie par défaut.  
  
 Pour plus d'informations, consultez [Gestion d'une bibliothèque](../../build/reference/managing-a-library.md).  
  
 **\/REMOVE**  
 Omet un objet de la bibliothèque de sortie.  
  
 Pour plus d'informations, consultez [Gestion d'une bibliothèque](../../build/reference/managing-a-library.md).  
  
 **\/SUBSYSTEM**  
 Indique au système d'exploitation comment exécuter un programme créé par l'établissement d'une liaison avec la bibliothèque de sortie.  
  
 Pour plus d'informations, consultez [Gestion d'une bibliothèque](../../build/reference/managing-a-library.md).  
  
 **\/VERBOSE**  
 Affiche des détails relatifs à la progression de la session, notamment les noms des fichiers .obj qui sont ajoutés.  
  
 Pour plus d'informations, consultez [Exécution de LIB](../../build/reference/running-lib.md).  
  
 **\/WX**  
 Considère les avertissements comme des erreurs.  
  
 Pour plus d'informations, consultez [Exécution de LIB](../../build/reference/running-lib.md).  
  
## Voir aussi  
 [Référence LIB](../../build/reference/lib-reference.md)   
 [Fichiers d'entrée LIB](../../build/reference/lib-input-files.md)   
 [Fichiers de sortie LIB](../../build/reference/lib-output-files.md)   
 [Autre sortie LIB](../../build/reference/other-lib-output.md)   
 [Structure d'une bibliothèque](../../build/reference/structure-of-a-library.md)