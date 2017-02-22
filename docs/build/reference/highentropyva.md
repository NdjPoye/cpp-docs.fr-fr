---
title: "/HIGHENTROPYVA | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/HIGHENTROPYVA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/HIGHENTROPYVA (option editbin)"
  - "HIGHENTROPYVA (option editbin)"
  - "-HIGHENTROPYVA (option editbin)"
ms.assetid: ef4b7c63-440d-40ca-b39d-edefb3217505
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /HIGHENTROPYVA
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie si l'image exécutable prend en charge la randomisation du format d'espace d'adresse \(ASLR\) 64 bits de forte entropie.  
  
```  
  
/HIGHENTROPYVA[:NO]  
  
```  
  
## Notes  
 Cette option modifie l'en\-tête d'un fichier .dll ou .exe pour indiquer si la fonctionnalité ASLR est prise en charge avec des adresses 64 bits.  Quand cette option est définie au niveau d'un fichier exécutable et de tous les modules dont il dépend, un système d'exploitation qui prend en charge l'ASLR 64 bits peut redéfinir les segments de l'image exécutable au moment du chargement en utilisant des adresses aléatoires tirées d'un espace d'adressage virtuel de 64 bits.  Devant ce grand espace d'adressage, il est plus difficile pour une personne malveillante de deviner l'emplacement d'une région de mémoire particulière.  
  
 Par défaut, l'éditeur de liens définit cette option pour les images exécutables 64 bits.  Pour définir cette option, l'option [\/DYNAMICBASE](../../build/reference/dynamicbase.md) doit également être définie.  
  
## Voir aussi  
 [Options EDITBIN](../../build/reference/editbin-options.md)   
 [\/DYNAMICBASE](../../build/reference/dynamicbase.md)   
 [Sécurité de Windows pour les éditeurs de logiciels](http://msdn.microsoft.com/library/bb430720.aspx)