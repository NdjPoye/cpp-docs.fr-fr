---
title: "Gestion d&#39;une biblioth&#232;que | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLibrarianTool.IgnoreAllDefaultLibraries"
  - "VC.Project.VCLibrarianTool.AdditionalDependencies"
  - "VC.Project.VCLibrarianTool.RemoveObjects"
  - "VC.Project.VCLibrarianTool.LibraryPaths"
  - "VC.Project.VCLibrarianTool.OutputFile"
  - "VC.Project.VCLibrarianTool.IgnoreDefaultLibraryNames"
  - "VC.Project.VCLibrarianTool.AdditionalLibraryDirectories"
  - "VC.Project.VCLibrarianTool.ListContentsFile"
  - "VC.Project.VCLibrarianTool.ListContents"
  - "VC.Project.VCLibrarianTool.SubSystemVersion"
  - "VC.Project.VCLibrarianTool.IgnoreDefaultLibraryName"
  - "VC.Project.VCLibrarianTool.SubSystem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CONVERT (option du Gestionnaire de bibliothèque)"
  - "/LIBPATH (option du Gestionnaire de bibliothèque)"
  - "/LINK50COMPAT (option du Gestionnaire de bibliothèque)"
  - "/LIST (option du Gestionnaire de bibliothèque)"
  - "/OUT (option du Gestionnaire de bibliothèque)"
  - "/REMOVE (option du Gestionnaire de bibliothèque)"
  - "/SUBSYSTEM (option du Gestionnaire de bibliothèque)"
  - "CONVERT (option du Gestionnaire de bibliothèque)"
  - "-CONVERT (option du Gestionnaire de bibliothèque)"
  - "LIB (C++), gérer les bibliothèques COFF"
  - "LIBPATH (option du Gestionnaire de bibliothèque)"
  - "-LIBPATH (option du Gestionnaire de bibliothèque)"
  - "LINK50COMPAT (option du Gestionnaire de bibliothèque)"
  - "-LINK50COMPAT (option du Gestionnaire de bibliothèque)"
  - "LIST (option du Gestionnaire de bibliothèque)"
  - "-LIST (option du Gestionnaire de bibliothèque)"
  - "fichiers objets"
  - "fichiers objets, générer et modifier"
  - "OUT (option du Gestionnaire de bibliothèque)"
  - "-OUT (option du Gestionnaire de bibliothèque)"
  - "REMOVE (option du Gestionnaire de bibliothèque)"
  - "-REMOVE (option du Gestionnaire de bibliothèque)"
  - "SUBSYSTEM (option du Gestionnaire de bibliothèque)"
  - "-SUBSYSTEM (option du Gestionnaire de bibliothèque)"
ms.assetid: f56a8b85-fbdc-4c09-8d8e-00f0ffe1da53
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Gestion d&#39;une biblioth&#232;que
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dans le mode par défaut, LIB génère ou modifie une bibliothèque d'objets COFF.  LIB s'exécute dans ce mode lorsque vous ne spécifiez ni \/EXTRACT \(pour copier un objet dans un fichier\) ni \/DEF \(pour générer une bibliothèque d'importation\).  
  
 Pour générer une bibliothèque à partir d'objets et\/ou de bibliothèques, utilisez la syntaxe suivante :  
  
```  
LIB [options...] files...  
```  
  
 Cette commande crée une bibliothèque à partir d'un ou plusieurs *files* d'entrée.  Les *files* peuvent être des fichiers objets COFF, des fichiers objets OMF 32 bits ou des bibliothèques COFF existantes.  LIB crée une bibliothèque contenant tous les objets dans les fichiers spécifiés.  Si un fichier d'entrée est un fichier objet OMF 32 bits, LIB le convertit en COFF avant de générer la bibliothèque.  LIB n'accepte pas un objet OMF 32 bits qui se trouve dans une bibliothèque créée par la version 16 bits de LIB.  Vous devez d'abord utiliser la version 16 bits de LIB pour extraire l'objet ; ensuite, vous pouvez utiliser le fichier objet extrait comme entrée pour la version 32 bits de LIB.  
  
 Par défaut, LIB nomme le fichier de sortie en utilisant le nom de base du premier fichier objet ou bibliothèque et l'extension .lib.  Le fichier de sortie est mis dans le répertoire actif.  Si un fichier existe déjà sous le même nom, le fichier de sortie remplace le fichier existant.  Pour conserver une bibliothèque existante, utilisez l'option \/OUT pour donner un nom au fichier de sortie.  
  
 Les options suivantes s'appliquent à la génération et à la modification d'une bibliothèque :  
  
 \/LIBPATH: `dir`  
 Substitue le chemin de la bibliothèque d'environnement.  Pour plus d'informations, consultez la description de l'option [\/LIBPATH](../../build/reference/libpath-additional-libpath.md) de l'outil LINK.  
  
 \/LIST  
 Affiche les informations sur la bibliothèque de sortie dans la sortie standard.  La sortie peut être redirigée vers un fichier.  Vous pouvez utiliser \/LIST pour répertorier le contenu d'une bibliothèque existante sans le modifier.  
  
 \/NAME:*nom\_fichier*  
 Lors de la génération d'une bibliothèque d'importation, spécifie le nom de la DLL pour laquelle la bibliothèque d'importation est générée.  
  
 \/NODEFAULTLIB  
 Supprime une ou plusieurs bibliothèques par défaut de la liste des bibliothèques qu'elle parcourt lors de la résolution de références externes.  Pour plus d'informations, consultez [\/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md).  
  
 \/OUT:*nom\_fichier*  
 Substitue le nom du fichier de sortie par défaut.  La bibliothèque de sortie est créée par défaut dans le répertoire actif, avec le nom de base du premier fichier bibliothèque ou objet sur la ligne de commande et l'extension .lib.  
  
 \/REMOVE:*objet*  
 Omet l'*objet* spécifié dans la bibliothèque de sortie.  LIB crée une bibliothèque de sortie en combinant tous les objets \(dans des fichiers objets ou des bibliothèques\), puis en supprimant les objets spécifiés avec \/REMOVE.  
  
 \/SUBSYSTEM:{CONSOLE &#124; EFI\_APPLICATION &#124; EFI\_BOOT\_SERVICE\_DRIVER &#124; EFI\_ROM &#124; EFI\_RUNTIME\_DRIVER &#124; NATIVE &#124; POSIX &#124; WINDOWS &#124; WINDOWSCE}\[,\#\[.\#\#\]\]  
 Indique au système d'exploitation comment exécuter un programme créé par l'établissement d'une liaison avec la bibliothèque de sortie.  Pour plus d'informations, consultez la description de l'option [\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) de l'outil LINK.  
  
 Les options LIB spécifiées sur la ligne de commande ne respectent pas la casse.  
  
 Vous pouvez utiliser LIB pour accomplir les tâches de gestion de bibliothèque suivantes :  
  
-   Pour ajouter des objets à une bibliothèque, spécifiez le nom de fichier de la bibliothèque existante et les noms de fichiers des nouveaux objets.  
  
-   Pour combiner des bibliothèques, spécifiez les noms de fichiers bibliothèque.  Vous pouvez ajouter des objets et combiner des bibliothèques à l'aide d'une seule commande LIB.  
  
-   Pour remplacer un membre de bibliothèque par un nouvel objet, spécifiez la bibliothèque contenant l'objet membre à remplacer et le nom de fichier du nouvel objet \(ou la bibliothèque qui le contient\).  Quand un objet portant le même nom existe dans plusieurs fichiers d'entrée, LIB place le dernier objet spécifié dans la commande LIB au sein de la bibliothèque de sortie.  Quand vous remplacez un membre de bibliothèque, veillez à spécifier le nouvel objet ou la nouvelle bibliothèque après la bibliothèque contenant l'ancien objet.  
  
-   Pour supprimer un membre d'une bibliothèque, utilisez l'option \/REMOVE.  LIB traite les spécifications de l'option \/REMOVE après avoir combiné tous les objets en entrée, quel que soit l'ordre suivi sur la ligne de commande.  
  
> [!NOTE]
>  Vous ne pouvez pas à la fois supprimer un membre et l'extraire vers un fichier au cours de la même étape.  Vous devez d'abord extraire l'objet membre à l'aide de \/EXTRACT, puis réexécuter LIB au moyen de \/REMOVE.  Ce comportement diffère de celui de la version 16 bits de LIB \(pour les bibliothèques OMF\) fournie dans d'autres produits Microsoft.  
  
## Voir aussi  
 [Référence LIB](../../build/reference/lib-reference.md)