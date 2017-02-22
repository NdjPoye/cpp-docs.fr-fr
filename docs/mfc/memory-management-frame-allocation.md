---
title: "Gestion de la m&#233;moire&#160;: allocation de frame | Microsoft Docs"
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
  - "détection des fuites de mémoire"
  - "allocation de frame"
  - "variables frame"
  - "variables frame, suppression automatique"
  - "allocation des tas, allocation de frame (différences)"
  - "allocation de mémoire, frames"
  - "fuites de mémoire, allocation d'objets sur le frame"
  - "fuites de mémoire, détecter"
  - "fuites de mémoire, allocation de frame"
  - "mémoire, détection des fuites"
  - "mémoire, récupération"
  - "mémoire, libération"
  - "portée, variables frame"
  - "frames de pile"
  - "variables, variables frame"
ms.assetid: 945a211a-6f4f-4679-bb6a-b0f2a0d4a6c1
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Gestion de la m&#233;moire&#160;: allocation de frame
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'allocation dans le cadre tient son nom de « frame de pile » installée lorsqu'une fonction est appelée.  Le frame de pile est une zone de la mémoire contenant temporairement les arguments à la fonction ainsi que toutes les variables qui sont des administrateurs locaux définis pour la fonction.  Les variables de la vue sont souvent appelées variables « automatique » puisque le compilateur alloue de l'espace pour eux.  
  
 Il existe deux principales caractéristiques des allocations de cadre.  D'abord, lorsque vous définissez une variable locale, suffisamment d'espace est alloué sur le frame de pile pour contenir la valeur entière, même s'il s'agit d'une grande table ou structure de données.  Ensuite, les variables du cadre sont automatiquement supprimées lorsqu'elles passent hors de portée :  
  
 [!code-cpp[NVC_MFC_Utilities#10](../mfc/codesnippet/CPP/memory-management-frame-allocation_1.cpp)]  
  
 Pour les variables de fonction locale, cette transition de portée se produit lorsque la fonction existe, mais l'étendue d'une variable de cadre peut être inférieur à la fonction si les accolades imbriquée sont utilisées.  L'effacement automatique des variables de ce cadre est essentiel.  Dans le cas de types primitifs simples \(par exemple `int` ou **byte**\), les tables, ou des structures de données, l'effacement automatique libère simplement la mémoire utilisée par la variable.  Dans la mesure où la variable est sortie de l'étendue, elle est inaccessible de toute façon.  Dans le cas des objets C\+\+, toutefois, le processus de l'effacement automatique est un peu plus compliqué.  
  
 Lorsqu'un objet est défini comme variable de cadre, le constructeur est appelé automatiquement au point où la définition est produite.  Lorsque l'objet sort de l'étendue, le destructeur est automatiquement appelée avant que la mémoire de l'objet soit diffusée.  Ces constructions et destructions automatiques peuvent être très pratiques, mais vous devez connaître les appels automatiques, notamment le destructeur.  
  
 Le principal avantage d'allouer des objets dans le cadre est qu'ils sont automatiquement supprimés.  Lorsque vous allouez vos objets dans le cadre, vous n'avez pas à vous soucier des objets oubliés provoquant des fuites de mémoire. \(Pour plus d'informations sur les fuites de mémoire, consultez l'article [Détection des fuites de mémoire de MFC](http://msdn.microsoft.com/fr-fr/29ee8909-96e9-4246-9332-d3a8aa8d4658).\) Un inconvénient d'allocation de cadre est que les variables du cadre ne peuvent pas être utilisées hors de portée.  Un autre facteur en choisissant l'allocation de cadre par rapport à l'allocation des segments est que pour les structures et les objets, il est souvent préférable d'utiliser le segment au lieu de la pile du stockage, l'espace de pile est généralement limitée.  
  
## Voir aussi  
 [Gestion de la mémoire](../mfc/memory-management.md)