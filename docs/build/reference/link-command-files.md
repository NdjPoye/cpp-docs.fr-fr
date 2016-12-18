---
title: "Fichiers de commandes LINK | Microsoft Docs"
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
  - "link"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers de commandes (C++)"
  - "fichiers de commandes (C++), LINK"
  - "LINK (outil C++)"
  - "LINK (outil C++), syntaxe de la ligne de commande"
  - "syntaxe, LINK (fichiers de commandes)"
  - "fichiers texte, passer des arguments aux fichiers LINK"
ms.assetid: 7154511c-32b9-4e5b-a515-3922fa9de48e
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Fichiers de commandes LINK
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous pouvez passer des arguments de ligne de commande à LINK sous la forme d'un fichier de commandes.  Pour spécifier un fichier de commandes pour l'éditeur de liens, utilisez la syntaxe suivante :  
  
```  
LINK @commandfile  
```  
  
 Le fichier `commandfile` est le nom d'un fichier texte.  Les espaces et les tabulations sont interdits entre le signe arobas \(@\) et le nom de fichier.  Il n'existe pas d'extension par défaut ; vous devez spécifier le nom de fichier complet, y compris l'extension éventuelle.  Les caractères génériques ne sont pas autorisés.  Vous pouvez spécifier un chemin d'accès absolu ou relatif avec le nom de fichier.  LINK n'utilise pas une variable d'environnement pour rechercher le fichier.  
  
 Dans le fichier de commandes, les arguments peuvent être séparés par des espaces ou des tabulations \(comme c'est le cas sur la ligne de commande\) et par des caractères de saut de ligne.  
  
 Vous pouvez spécifier tout ou partie de la ligne de commande dans un fichier de commandes.  Vous pouvez utiliser plusieurs fichiers de commandes dans une commande LINK.  LINK accepte l'entrée du fichier de commandes comme si elle était spécifiée à cet emplacement sur la ligne de commande.  Les fichiers de commandes ne peuvent pas être imbriqués.  LINK reproduit par écho le contenu des fichiers de commandes, sauf quand l'option [\/NOLOGO](../../build/reference/nologo-suppress-startup-banner-linker.md) est spécifiée.  
  
## Exemple  
 La commande suivante destinée à générer une DLL passe les noms des fichiers objets et des bibliothèques dans des fichiers de commandes séparés et utilise un troisième fichier de commandes pour la spécification de l'option \/EXPORTS :  
  
```  
link /dll @objlist.txt @liblist.txt @exports.txt  
```  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)