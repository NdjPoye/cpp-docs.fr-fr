---
title: "Utilisation de CObject | Microsoft Docs"
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
  - "CObject (classe)"
  - "classes dérivées, de CObject"
  - "exemples (MFC), CObject"
  - "MFC, classe de base"
  - "classe de base racine pour MFC"
ms.assetid: d0cd19bb-2856-4b41-abbc-620fd64cb223
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Utilisation de CObject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CObject](../mfc/reference/cobject-class.md) est la classe racine de base pour la plupart des bibliothèques Microsoft Foundation Class \(MFC\).  La classe `CObject` contient de nombreuses fonctionnalités utiles que vous pourrez souhaiter incorporer dans vos propres objets de programme, notamment la prise en charge de sérialisation, les informations sur la classe de l'exécution, et de la sortie du diagnostic objet.  Si vous dérivez votre classe à partir de `CObject`, votre classe pourra alors exploiter ces fonctionnalités `CObject`.  
  
## Que voulez\-vous faire ?  
  
-   [Crée une classe dérivée à partir de CObject](../mfc/deriving-a-class-from-cobject.md)  
  
-   [Ajouter la prise en charge des informations sur la classe d'exécution, la création dynamique, et la sérialisation à mes classe dérivées](../mfc/specifying-levels-of-functionality.md)  
  
-   [Accès aux informations de la classe d'exécution courante](../mfc/accessing-run-time-class-information.md)  
  
-   [Crée des objets de manière dynamique](../mfc/dynamic-object-creation.md)  
  
-   [Décharge les données de l'objet afin d'effectuer un diagnostic](http://msdn.microsoft.com/fr-fr/727855b1-5a83-44bd-9fe3-f1d535584b59)  
  
-   Valide l'état interne de l'objet \(voir l' [MFC ASSERT\_VALID et CObject::AssertValid](http://msdn.microsoft.com/fr-fr/7654fb75-9e9a-499a-8165-0a96faf2d5e6)\)  
  
-   [Permet à la classe d'effectuer une sérialisation pour un stockage permanent](../mfc/serialization-in-mfc.md)  
  
-   Consultez la liste des [Forum Aux Questions de CObject](../mfc/cobject-class-frequently-asked-questions.md)  
  
## Voir aussi  
 [Concepts](../mfc/mfc-concepts.md)   
 [Rubriques MFC générales](../mfc/general-mfc-topics.md)   
 [CRuntimeClass Structure](../mfc/reference/cruntimeclass-structure.md)   
 [Fichiers](../mfc/files-in-mfc.md)   
 [Sérialisation](../mfc/serialization-in-mfc.md)