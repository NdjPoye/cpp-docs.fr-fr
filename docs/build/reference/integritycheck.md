---
title: "/INTEGRITYCHECK | Microsoft Docs"
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
  - "/INTEGRITYCHECK"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/INTEGRITYCHECK (options editbin)"
  - "INTEGRITYCHECK (options editbin)"
  - "-INTEGRITYCHECK (options editbin)"
ms.assetid: 2a293705-4396-421b-a5a5-693b4b867a85
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /INTEGRITYCHECK
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie que la signature numérique de l'image binaire doit être vérifiée au moment du chargement.  
  
```  
  
/INTEGRITYCHECK[:NO]  
  
```  
  
## Notes  
 Dans l'en\-tête du fichier DLL ou du fichier exécutable, cette option définit un indicateur qui requiert un contrôle de signature numérique par le gestionnaire de mémoire pour charger l'image dans Windows.  Les versions de Windows antérieures à Windows Vista ignorent cet indicateur.  Cette option doit être définie pour les DLL 64 bits qui implémentent le code en mode noyau, et est recommandée pour tous les pilotes de périphérique.  Pour plus d'informations, consultez [Procédure de signature de code en mode noyau](http://go.microsoft.com/fwlink/?linkid=237093) sur le site Web MSDN.  
  
## Voir aussi  
 [Options EDITBIN](../../build/reference/editbin-options.md)