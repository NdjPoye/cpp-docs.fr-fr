---
title: "Surcharge de l&#39;op&#233;rateur &gt;&gt; pour vos propres classes | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "opérateur >>, surcharge pour vos propres classes"
  - "opérateur >>"
  - "opérateur >>, surcharge pour vos propres classes"
ms.assetid: 40dab4e0-3f97-4745-9cc8-b86e740fa246
caps.latest.revision: 8
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Surcharge de l&#39;op&#233;rateur &gt;&gt; pour vos propres classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les flux d'entrée utilisent l'opérateur d'extraction \(`>>`\) pour les types standard.  Vous pouvez écrire des opérateurs d'extraction similaires pour vos propres types ; votre succès dépend de l'utilisation de l'espace blanc avec précision.  
  
 Voici un exemple d'un opérateur d'extraction pour la classe `Date` présentée précédemment :  
  
```  
istream& operator>> ( istream& is, Date& dt )  
{  
   is >> dt.mo >> dt.da >> dt.yr;  
   return is;  
}  
```  
  
## Voir aussi  
 [Flux d'entrée](../standard-library/input-streams.md)