---
title: "/DYNAMICBASE | Microsoft Docs"
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
  - "/dynamicbase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DYNAMICBASE (option Editbin)"
  - "DYNAMICBASE (option Editbin)"
  - "-DYNAMICBASE (option Editbin)"
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /DYNAMICBASE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie si une image exécutable peut être redéfinie de façon aléatoire au moment du chargement en utilisant la randomisation du format d'espace d'adresse \(ASLR\).  
  
## Syntaxe  
  
```  
  
/DYNAMICBASE[:NO]  
```  
  
## Notes  
 Par défaut, l'éditeur de liens définit l'option **\/DYNAMICBASE**.  
  
 Cette option modifie l'en\-tête d'une image exécutable pour indiquer si le chargeur peut redéfinir aléatoirement l'image au moment du chargement.  
  
 La fonctionnalité ASLR est prise en charge sur Windows Vista, Windows Server 2008, Windows 7, Windows 8 et Windows Server 2012.  
  
## Voir aussi  
 [Options EDITBIN](../../build/reference/editbin-options.md)   
 [Sécurité de Windows pour les éditeurs de logiciels](http://msdn.microsoft.com/library/bb430720.aspx)