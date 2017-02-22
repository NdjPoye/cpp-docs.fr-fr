---
title: "Erreur RW2001 du compilateur de ressources  | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RW2001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RW2001"
ms.assetid: 963bdc7d-6ebe-4378-8bbc-47dfcf5d330c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur RW2001 du compilateur de ressources 
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Directive non valide dans le fichier RC prétraité  
  
 Le fichier RC contient une directive **\#pragma**.  
  
 Utilisez la directive de préprocesseur **\#ifndef** avec la constante **RC\_INVOKED** définie par le compilateur de ressources lors du traitement du fichier include.  Placez la directive **\#pragma** dans un bloc de code qui n'est pas traité lorsque la constante **RC\_INVOKED** est définie.  Le code situé dans le bloc est traité par le compilateur C\/C\+\+, mais pas par le compilateur de ressources.  L'exemple de code suivant illustre cette méthode :  
  
```  
#ifndef RC_INVOKED  
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler  
#endif  
```  
  
 La directive de préprocesseur **\#pragma** n'a aucune signification dans un fichier .RC.  La directive de préprocesseur **\#include** est fréquemment utilisée dans un fichier .RC pour inclure un fichier d'en\-tête \(un fichier d'en\-tête personnalisé d'un projet ou un fichier d'en\-tête standard fourni par Microsoft avec l'un de ses produits\).  Certains de ces fichiers include contiennent la directive **\#pragma**.  Un fichier d'en\-tête peut contenir un ou plusieurs autres fichiers d'en\-tête et il peut donc être difficile d'identifier le fichier contenant la directive **\#pragma** posant problème.  
  
 La méthode **\#ifndef RC\_INVOKED** permet de contrôler l'ajout de fichiers d'en\-tête dans des fichiers d'en\-tête de projet.