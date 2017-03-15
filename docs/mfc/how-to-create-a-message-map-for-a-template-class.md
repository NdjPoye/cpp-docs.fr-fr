---
title: "Comment&#160;: cr&#233;er une table des messages pour une classe de mod&#232;le | Microsoft Docs"
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
  - "tables des messages, classes de modèle"
  - "classes de modèle, créer des tables des messages"
ms.assetid: 4e7e24f8-06df-4b46-82aa-7435c8650de3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Comment&#160;: cr&#233;er une table des messages pour une classe de mod&#232;le
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le mappage de message dans MFC est un moyen efficace de diriger les messages Windows à une instance d'objet appropriée C\+\+.  Les exemples de cibles de table des messages MFC comprennent des classes d'application, des classes document et vue, des classes de contrôle, et ainsi de suite.  
  
 Les tables de messages traditionnelles MFC sont déclarées avec la macro [BEGIN\_MESSAGE\_MAP](../Topic/BEGIN_MESSAGE_MAP.md) pour déclarer le début de la table des messages, une entrée macro pour chaque méthode de la classe de gestionnaire de messages, et enfin la macro [END\_MESSAGE\_MAP](../Topic/END_MESSAGE_MAP.md) pour donner la fin de la carte du message.  
  
 Une limite avec la macro [BEGIN\_MESSAGE\_MAP](../Topic/BEGIN_MESSAGE_MAP.md) se produit lorsqu'elle est utilisée conjointement avec une classe qui contient les arguments de modèle.  Si elle est utilisée avec une classe de modèle, la macro entraînera une erreur de compilation en raison des paramètres de modèle manquants pendant l'expansion macro.  La macro [BEGIN\_TEMPLATE\_MESSAGE\_MAP](../Topic/BEGIN_TEMPLATE_MESSAGE_MAP.md) a été conçue pour autoriser les classes qui contient un seul argument de modèle pour déclarer leurs propres tables de messages.  
  
## Exemple  
 Prenons un exemple où la classe MFC [CListBox](../mfc/reference/clistbox-class.md) est étendue pour assurer la synchronisation avec une source de données externe.  La classe fictive **CSyncListBox** est déclarée comme suit :  
  
 [!code-cpp[NVC_MFC_CListBox#42](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_1.h)]  
  
 La classe **CSyncListBox** est basée sur des modèles sur un seul type qui décrit la source de données avec laquelle elle synchronisera.  Il déclare également trois méthodes qui participeront à la table des messages de la classe : **OnPaint**, **OnDestroy**, et **OnSynchronize**.  La méthode **OnSynchronize** est implémentée comme suit :  
  
 [!code-cpp[NVC_MFC_CListBox#43](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_2.cpp)]  
  
 L'implémentation ci\-dessus fournit la classe **CSyncListBox** à spécialiser sur n'importe quel type de classe qui implémente la méthode **GetCount**, telle que **CArray**, **CList**, et **CMap**.  La fonction de **StringizeElement** est une fonction de modèle prototype par ce qui suit :  
  
 [!code-cpp[NVC_MFC_CListBox#44](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_3.cpp)]  
  
 Normalement, la table des messages pour cette classe est définie comme suit :  
  
 `BEGIN_MESSAGE_MAP(CSyncListBox, CListBox)`  
  
 `ON_WM_PAINT()`  
  
 `ON_WM_DESTROY()`  
  
 `ON_MESSAGE(LBN_SYNCHRONIZE, OnSynchronize)`  
  
 `END_MESSAGE_MAP()`  
  
 où **LBN\_SYNCHRONIZE** est un message utilisateur personnalisé défini par l'application, par exemple :  
  
 [!code-cpp[NVC_MFC_CListBox#45](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_4.cpp)]  
  
 La carte de macro ci\-dessus ne compilera pas, en raison du fait que la spécification du modèle pour la classe **CSyncListBox** est absente pendant l'expansion macro.  La macro **BEGIN\_TEMPLATE\_MESSAGE\_MAP** résout ce problème en incorporant le paramètre de modèle dans la carte étendue de macro.  La table des messages pour cette classe est :  
  
 [!code-cpp[NVC_MFC_CListBox#46](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_5.cpp)]  
  
 L'exemple suivant illustre l'utilisation de l'exemple de la classe de **CSyncListBox** à l'aide d'un objet **CStringList**:  
  
 [!code-cpp[NVC_MFC_CListBox#47](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_6.cpp)]  
  
 Pour effectuer le test, la fonction **StringizeElement** doit être spécialisée pour fonctionner avec la classe **CStringList**:  
  
 [!code-cpp[NVC_MFC_CListBox#48](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_7.cpp)]  
  
## Voir aussi  
 [BEGIN\_TEMPLATE\_MESSAGE\_MAP](../Topic/BEGIN_TEMPLATE_MESSAGE_MAP.md)   
 [Gestion et mappage des messages](../mfc/message-handling-and-mapping.md)