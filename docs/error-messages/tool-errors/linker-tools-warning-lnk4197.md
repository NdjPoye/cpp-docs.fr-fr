---
title: "Avertissement des outils &#201;diteur de liens LNK4197 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4197"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4197"
ms.assetid: 8a976fd7-a74b-4c83-ab66-a9e7d7073c4a
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement des outils &#201;diteur de liens LNK4197
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

exportation 'NomExportation' spécifiée à plusieurs reprises ; première spécification utilisée  
  
 Une exportation est spécifiée de plusieurs façons différentes.  L'éditeur de liens utilise la première spécification et ignore les autres.  
  
 Si vous régénérez la bibliothèque runtime C, vous pouvez ignorer ce message.  
  
 Si une exportation est spécifiée plusieurs fois exactement de la même façon, l'éditeur de liens n'émet pas d'avertissement.  
  
 Par exemple, le contenu ci\-dessous d'un fichier .def peut causer cet avertissement :  
  
```  
EXPORTS  
   functioname      NONAME  
   functioname      @10  
```  
  
### Pour résoudre le problème en vérifiant les causes possibles suivantes  
  
1.  La même exportation est spécifiée à la fois sur la ligne de commande \(par export:\) et dans le fichier .def  
  
2.  La même exportation apparaît deux fois dans le fichier .def avec des attributs différents.