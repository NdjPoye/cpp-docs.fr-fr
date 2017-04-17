---
title: "Erreur du compilateur&#160;C2813 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2813"
ms.assetid: 6cf2135f-7b82-42d1-909a-5e864308a09c
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur&#160;C2813
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#import n'est pas pris en charge avec \/MP  
  
 L’erreur C2813 est émise si, dans une commande du compilateur, vous spécifiez l’option du compilateur **\/MP**, deux fichiers ou plus à compiler et qu’un ou plusieurs des fichiers contiennent la directive de préprocesseur [\#import](../../preprocessor/hash-import-directive-cpp.md). La directive [\#import](../../preprocessor/hash-import-directive-cpp.md) génère des classes C\+\+ à partir des types dans la bibliothèque de types spécifiée, puis écrit ces classes dans deux fichiers d’en\-tête. La directive [\#import](../../preprocessor/hash-import-directive-cpp.md) n’est pas prise en charge, car si plusieurs unités de compilation importent la même bibliothèque de types, ces unités sont en conflit quand elles essaient d’écrire les mêmes fichiers d’en\-tête en même temps.  
  
 Cette erreur du compilateur et l’option du compilateur **\/MP** sont nouvelles dans [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)].  
  
## Exemple  
 L’exemple suivant génère l’erreur C2813. La ligne de commande située dans le commentaire « compiler avec : » indique au compilateur d’utiliser les options **\/MP** et **\/c** pour compiler plusieurs fichiers. Au moins un des fichiers contient la directive [\#import](../../preprocessor/hash-import-directive-cpp.md). Nous utilisons le même fichier à deux reprises pour tester cet exemple.  
  
```  
// C2813.cpp // compile with: /MP /c C2813.cpp C2813.cpp #import "C:\windows\system32\stdole2.tlb"   // C2813 int main() { }  
```