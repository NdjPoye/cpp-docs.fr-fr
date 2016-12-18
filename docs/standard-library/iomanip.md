---
title: "&lt; iomanip &gt; | Microsoft Docs"
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
  - "iomanip/std::<iomanip>"
  - "std::<iomanip>"
  - "<iomanip>"
  - "std.<iomanip>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iomanip (en-tête)"
ms.assetid: 3681c346-4763-4037-bba4-cf0dc3447974
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt; iomanip &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Incluez l'en\-tête standard `iostreams``<iomanip>` pour définir plusieurs manipulateurs qui acceptent chacun un argument unique.  
  
## Syntaxe  
  
```  
  
#include <iomanip>  
  
```  
  
## Notes  
 Chacun de ces manipulateurs retourne un type non spécifié, appelé **T1** à **T10**, qui surcharge à la fois `basic_istream`\<**Elem**, **Tr**\>`::`[operator\>\>](../Topic/operator%3E%3E%20\(%3Cistream%3E\).md) et `basic_ostream`\<**Elem**, **Tr**\>`::`[operator\<\<](../Topic/operator%3C%3C%20\(%3Costream%3E\).md).  
  
### Manipulateurs  
  
|||  
|-|-|  
|[get\_money](../Topic/%3Ciomanip%3E%20get_money.md)|Obtient une valeur monétaire, éventuellement au format international.|  
|[get\_time](../Topic/%3Ciomanip%3E%20get_time.md)|Obtient une heure dans une structure d'heure à l'aide d'un format spécifié.|  
|[put\_money](../Topic/%3Ciomanip%3E%20put_money.md)|Fournit une valeur monétaire, éventuellement au format international.|  
|[put\_time](../Topic/%3Ciomanip%3E%20put_time.md)|Fournit une heure dans une structure d'heure et une chaîne de format à utiliser.|  
|[quoted](../Topic/quoted.md)|Autorise un aller\-retour pratique des chaînes avec des opérateurs d'insertion et d'extraction.|  
|[resetiosflags](../Topic/resetiosflags.md)|Efface les indicateurs spécifiés.|  
|[setbase](../Topic/setbase.md)|Définir la base pour les entiers.|  
|[setfill](../Topic/setfill.md)|Définit le caractère qui sera utilisé pour remplir les espaces dans un affichage aligné à droite.|  
|[setiosflags](../Topic/setiosflags.md)|Définit les indicateurs spécifiés.|  
|[setprecision](../Topic/setprecision.md)|Définit la précision des valeurs à virgule flottante.|  
|[setw](../Topic/setw.md)|Spécifie la largeur de la zone d'affichage.|  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)