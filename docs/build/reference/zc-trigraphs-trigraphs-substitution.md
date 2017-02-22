---
title: "/Zc:, trigrammes (substitution de trigrammes) (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Zc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc (options du compilateur C++)"
  - "conformité des options du compilateur"
  - "Zc (options du compilateur C++)"
  - "-Zc (options du compilateur C++)"
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# /Zc:, trigrammes (substitution de trigrammes) (C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lorsque **\/Zc:trigraphs** est spécifié, le compilateur remplace une séquence de caractères trigrammes par le caractère de ponctuation correspondant.  Pour désactiver la substitution de trigrammes, spécifiez **\/Zc:trigraphs\-**.  Par défaut, **\/Zc:trigraphs** est désactivé.  
  
## Syntaxe  
  
```  
/Zc:trigraphs[-]  
```  
  
## Notes  
 Un trigraphe se compose de deux points d'interrogation consécutifs \(??\) suivis d'un troisième caractère unique.  Par exemple, le compilateur remplace le "??" \= " trigraph en utilisant le caractère "\#".  Utilisez des trigraphes dans les fichiers sources C qui utilisent un jeu de caractères qui ne contient pas de représentation graphique pour certains caractères de ponctuation.  
  
 Pour obtenir une liste des trigrammes de C\/C\+\+ et un exemple qui indique comment utiliser les trigrammes, consultez [Trigraphes](../../c-language/trigraphs.md).  
  
## Voir aussi  
 [\/Zc \(Conformité\)](../../build/reference/zc-conformance.md)   
 [Trigraphes](../../c-language/trigraphs.md)