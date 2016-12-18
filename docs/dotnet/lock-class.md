---
title: "lock, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "msclr::lock"
  - "msclr.lock"
  - "lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lock (classe)"
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# lock, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette classe automatise la prise d'un verrou pour synchroniser l'accès à un objet à partir de plusieurs threads.  Une fois construit, celui\-ci acquiert un verrou et une fois détruit, il libère le verrou.  
  
## Syntaxe  
  
```  
ref class lock;  
```  
  
## Notes  
 `lock` est disponible uniquement pour les objets CLR et peut être utilisé uniquement dans le code CLR.  
  
 En interne, la classe de verrou utilise <xref:System.Threading.Monitor> pour synchroniser l'accès.  Consultez cette rubrique pour plus d'informations détaillées sur la synchronisation.  
  
## Configuration requise  
 **Fichier d'en\-tête** \<msclr\\lock.h\>  
  
 **Espace de noms** msclr  
  
## Voir aussi  
 [verrou](../dotnet/lock.md)   
 [lock, membres](../dotnet/lock-members.md)