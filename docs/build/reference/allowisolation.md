---
title: "/ALLOWISOLATION | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/ALLOWISOLATION"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ALLOWISOLATION (option Editbin)"
  - "ALLOWISOLATION (option Editbin)"
  - "-ALLOWISOLATION (option Editbin)"
ms.assetid: 91430344-f64f-491a-a5a5-7ea3b21cbe68
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /ALLOWISOLATION
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie un comportement pour la recherche de manifeste.  
  
## Syntaxe  
  
```  
  
/ALLOWISOLATION[:NO]  
```  
  
## Notes  
 **\/ALLOWISOLATION** indique au système d'exploitation de rechercher et charger le fichier manifeste.  
  
 **\/ALLOWISOLATION** est la valeur par défaut.  
  
 **\/ALLOWISOLATION:NO** indique que les fichiers exécutables sont chargés comme s'il n'existait aucun manifeste, et indique à [Référence EDITBIN](../../build/reference/editbin-reference.md) de définir le bit `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` dans le champ `DllCharacteristics` de l'en\-tête facultatif.  
  
 Quand l'isolation est désactivée pour un fichier exécutable, le chargeur Windows ne tente pas de trouver un manifeste d'application pour le processus nouvellement créé.  Le nouveau processus n'a pas de contexte d'activation par défaut, même s'il existe un manifeste dans le fichier exécutable lui\-même ou s'il existe un manifeste qui porte le nom *nom\_fichier\_exécutable*.exe.manifest.  
  
## Voir aussi  
 [Options EDITBIN](../../build/reference/editbin-options.md)   
 [\/ALLOWISOLATION \(Recherche de manifeste\)](../../build/reference/allowisolation-manifest-lookup.md)   
 [Référence des fichiers manifeste](http://msdn.microsoft.com/library/aa375632.aspx)