---
title: "Exceptions&#160;: lev&#233;e d&#39;exceptions &#224; partir de vos propres fonctions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exceptions, lever"
  - "fonctions (C++), lever des exceptions"
  - "lever des exceptions, à partir de fonctions"
ms.assetid: 492976e8-8804-4234-8e8f-30dffd0501be
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Exceptions&#160;: lev&#233;e d&#39;exceptions &#224; partir de vos propres fonctions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il est possible d'utiliser le paradigme de gestion des exceptions de MFC uniquement pour intercepter les exceptions levées par les fonctions de MFC ou d'autres bibliothèques.  En plus d'attraper les exceptions levées par le code de bibliothèque, vous pouvez lever des exceptions dans votre propre code lorsque vous entrez des fonctions qui peuvent rencontrer des conditions exceptionnelles.  
  
 Lorsqu'une exception est levée, l'exécution de la fonction en cours est arrêté et accède directement au bloc **catch** du cadre le plus interne de l'exception.  Le mécanisme d'exception ignore le chemin d'accès normal de résultat d'une fonction.  Par conséquent, vous devez vous assurer de supprimer ces blocs de mémoire qui seraient supprimés dans une sortie normale.  
  
#### Lever une exception.  
  
1.  Utilisez l'une des fonctions d'assistance de MFC, telles que `AfxThrowMemoryException`.  Ces fonctions lèvent un objet exception préaffecté du type approprié.  
  
     Dans l'exemple suivant, une fonction tente d'allouer deux blocs de mémoire et lève une exception si l'une des allocations échoue :  
  
     [!code-cpp[NVC_MFCExceptions#17](../mfc/codesnippet/CPP/exceptions-throwing-exceptions-from-your-own-functions_1.cpp)]  
  
     Si la première allocation échoue, vous pouvez simplement lever l'exception de mémoire.  Si la première allocation réussit mais la seconde échoue, vous devez libérer le premier bloc d'allocation avant de lever l'exception.  Si les deux allocations réussissent, vous pouvez continuer normalement et libérer les blocs en quittant la fonction.  
  
     \- ou \-  
  
2.  Utilisez une exception définie par l'utilisateur pour afficher l'état du problème.  Vous pouvez générer un élément de n'importe quel type, même une classe entière, comme exception.  
  
     L'exemple suivant tente de jouer un son via un périphérique et lève une exception si il y a un problème.  
  
     [!code-cpp[NVC_MFCExceptions#18](../mfc/codesnippet/CPP/exceptions-throwing-exceptions-from-your-own-functions_2.cpp)]  
  
> [!NOTE]
>  La gestion par défaut de MFC des exceptions s'applique uniquement aux pointeurs aux objets `CException` \(et aux objets de classes dérivées de `CException`\).  L'exemple ci\-dessus outrepasse le mécanisme d'exception MFC.  
  
## Voir aussi  
 [Gestion des exceptions](../mfc/exception-handling-in-mfc.md)