---
title: "/REBASE | Microsoft Docs"
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
  - "/rebase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/REBASE (option Editbin) (C++)"
  - "adresses de base (C++)"
  - "DLL (C++), lier"
  - "fichiers exécutables (C++), adresse de base"
  - "REBASE (option Editbin)"
  - "-REBASE (option Editbin)"
ms.assetid: 3f89d874-af5c-485b-974b-fd205f6e1a4b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /REBASE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/REBASE[:modifiers]  
```  
  
## Notes  
 Cette option définit les adresses de base des fichiers spécifiés.  EDITBIN assigne de nouvelles adresses de base dans un espace d'adressage contigu selon la taille de chaque fichier arrondie aux 64 Ko les plus proches.  Pour plus d'informations sur les adresses de base, consultez l'option [Adresse de base](../../build/reference/base-base-address.md) \(\/BASE\) de l'éditeur de liens.  
  
 Spécifiez les fichiers exécutables et les DLL du programme dans l'argument *files* sur la ligne de commande EDITBIN dans l'ordre où ils doivent être basés.  Vous pouvez éventuellement spécifier un ou plusieurs *modifiers*, séparés par une virgule \(**,**\) :  
  
|Modificateur|Action|  
|------------------|------------|  
|BASE**\=***adresse*|Fournit une adresse de départ pour la réassignation d'adresses de base aux fichiers.  Spécifiez *adresse* en notation décimale ou de langage C.  Si BASE n'est pas spécifié, l'adresse de base de départ par défaut est 0x400000.  Si DOWN est utilisé, BASE doit être spécifié, et *adresse* définit la fin de la plage des adresses de base.|  
|BASEFILE|Crée un fichier nommé COFFBASE.TXT, qui est un fichier texte dans le format attendu par l'option \/BASE de LINK.|  
|DOWN|Indique à EDITBIN de réassigner les adresses de base dans un ordre descendant à partir d'une adresse de fin.  Les fichiers sont réassignés dans l'ordre spécifié, avec le premier fichier situé dans la plus haute adresse possible en dessous la fin de la plage d'adresses.  BASE doit être utilisé avec DOWN afin de garantir un espace d'adressage suffisant pour baser les fichiers.  Pour déterminer l'espace d'adressage requis par les fichiers spécifiés, exécutez EDITBIN avec \/REBASE sur les fichiers et ajoutez 64 Ko à la taille totale affichée.|  
  
## Voir aussi  
 [Options EDITBIN](../../build/reference/editbin-options.md)