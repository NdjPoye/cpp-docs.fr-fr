---
title: "Erreur des outils &#201;diteur de liens LNK2039 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2039"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2039"
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK2039
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l'importation du '\<type\>' de la classe de référence qui est défini dans another.obj; il doit être soit importé soit défini, mais pas les deux  
  
 La classe '\<`type`\>' de référence est importée dans le fichier .obj spécifié mais est également définie dans un autre fichier .obj.  Cette condition peut provoquer l'échec de l'exécution ou un autre comportement inattendu.  
  
### Pour corriger cette erreur  
  
1.  Vérifiez si '`type`' doit être défini dans l'autre fichier .obj et contrôlez s'il doit être importé à partir du fichier .winmd.  
  
2.  Supprimez soit la définition soit l'importation.  
  
## Voir aussi  
 [Erreurs et avertissements des outils Éditeur de liens](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)   
 [Erreur des outils Éditeur de liens LNK1332](../../error-messages/tool-errors/linker-tools-error-lnk1332.md)