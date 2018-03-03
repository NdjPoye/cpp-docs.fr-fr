---
title: Utilisation de CObject | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- examples [MFC], CObject
- root base class for MFC
- derived classes [MFC], from CObject
- MFC, base class
- CObject class [MFC]
ms.assetid: d0cd19bb-2856-4b41-abbc-620fd64cb223
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 17bffb412975cfc6a97eae8b30aff2514a2e1d93
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="using-cobject"></a>Utilisation de CObject
[CObject](../mfc/reference/cobject-class.md) est la classe de base racine pour la plupart de la bibliothèque Microsoft Foundation classe (MFC). La `CObject` classe contient de nombreuses fonctionnalités utiles que vous pouvez incorporer dans vos propres objets, y compris la prise en charge de la sérialisation, les informations de classe d’exécution et sortie de diagnostic d’objet. Si vous dérivez votre classe de `CObject`, votre classe peut exploiter ces `CObject` fonctionnalités.  
  
## <a name="what-do-you-want-to-do"></a>Tu veux faire quoi  
  
-   [Dérivez une classe de CObject](../mfc/deriving-a-class-from-cobject.md)  
  
-   [Ajouter la prise en charge des informations de classe d’exécution, la création dynamique et la sérialisation à ma classe dérivée](../mfc/specifying-levels-of-functionality.md)  
  
-   [Accéder aux informations de classe d’exécution](../mfc/accessing-run-time-class-information.md)  
  
-   [Créer des objets de manière dynamique](../mfc/dynamic-object-creation.md)  
  
-   [Vider les données de l’objet pour établir un diagnostic](http://msdn.microsoft.com/en-us/727855b1-5a83-44bd-9fe3-f1d535584b59)  
  
-   Valider l’état interne de l’objet (voir [MFC ASSERT_VALID et CObject::AssertValid](http://msdn.microsoft.com/en-us/7654fb75-9e9a-499a-8165-0a96faf2d5e6))  
  
-   [Que la classe se sérialiser vers le stockage persistant](../mfc/serialization-in-mfc.md)  
  
-   Afficher la liste des [CObject Forum aux Questions](../mfc/cobject-class-frequently-asked-questions.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Concepts](../mfc/mfc-concepts.md)   
 [Rubriques MFC générales](../mfc/general-mfc-topics.md)   
 [Structure de CRuntimeClass](../mfc/reference/cruntimeclass-structure.md)   
 [Fichiers](../mfc/files-in-mfc.md)   
 [Sérialisation](../mfc/serialization-in-mfc.md)

