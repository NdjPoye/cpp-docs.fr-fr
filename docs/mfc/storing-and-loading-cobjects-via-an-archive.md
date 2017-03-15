---
title: "Stockage et chargement de CObjects via une archive | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchive (classe), stocker et charger des objets"
  - "CObject (classe), objets CArchive"
  - "CObjects"
  - "CObjects, charger via les archives"
  - "Serialize (méthode), différences par rapport aux opérateurs CArchive"
ms.assetid: a829b6dd-bc31-47e0-8108-fbb946722db9
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Stockage et chargement de CObjects via une archive
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le stockage et chargement de `CObject`s via une archive requiert une attention supplémentaire.  Dans certains cas, vous devez appeler la fonction `Serialize` de l'objet, où l'objet `CArchive` est un paramètre de l'appel `Serialize`, par opposition à utiliser l'opérateur **\<\<** ou **\>\>** de `CArchive`.  Le fait qu'il est important de prendre en compte est que l'opérateur `CArchive`**\>\>** construit le `CObject` en mémoire en fonction des informations `CRuntimeClass` précédemment écrites dans le fichier d'archive de journalisation.  
  
 Par conséquent, si vous utilisez les opérateurs `CArchive` **\<\<** et **\>\>**, plutôt qu'appeler `Serialize`, dépend de si vous *avez besoin* que l'archive de chargement reconstruise dynamiquement l'objet selon les informations `CRuntimeClass` préalablement stockées.  Utilisez la fonction `Serialize` dans les cas suivants :  
  
-   En désérialisant l'objet, vous connaissez la classe exacte de l'objet au préalable.  
  
-   En désérialisant l'objet, vous avez déjà de la mémoire allouée pour ce dernier.  
  
> [!CAUTION]
>  Si vous chargez l'objet à l'aide de la fonction `Serialize`, vous devez également stocker l'objet à l'aide de la fonction `Serialize`.  Ne stockez pas en utilisant l'opérateur `CArchive`**\<\<** puis en chargeant en utilisant la fonction `Serialize`, ou à l'aide de la fonction `Serialize` puis en chargeant en utilisant l'opérateur **CArchive \>\>**.  
  
 L'exemple de code suivant illustre le cas :  
  
 [!code-cpp[NVC_MFCSerialization#36](../mfc/codesnippet/CPP/storing-and-loading-cobjects-via-an-archive_1.h)]  
  
 [!code-cpp[NVC_MFCSerialization#37](../mfc/codesnippet/CPP/storing-and-loading-cobjects-via-an-archive_2.cpp)]  
  
 En résumé, si votre classe sérialisable définit **CObjec**t incorporé comme membre, vous ne devez *pas* utiliser `CArchive` **\<\<** et les opérateurs **\>\>** pour cet objet, mais vous devez appeler la fonction `Serialize` à la place.  En outre, si votre classe sérialisable définit un pointeur vers un `CObject` \(ou un objet dérivé de `CObject`\) en tant que membre, mais construit l'autre objet dans son propre constructeur, vous devez aussi appeler `Serialize`.  
  
## Voir aussi  
 [Sérialisation : sérialisation d'un objet](../mfc/serialization-serializing-an-object.md)