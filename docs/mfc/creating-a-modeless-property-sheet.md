---
title: "Cr&#233;ation d&#39;une feuille de propri&#233;t&#233;s non modale | Microsoft Docs"
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
  - "Create (méthode) (C++), feuilles de propriétés"
  - "feuilles de propriétés non modales"
  - "feuilles de propriétés, non modales"
ms.assetid: eafd8a92-cc67-4a69-a5fb-742c920d1ae8
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation d&#39;une feuille de propri&#233;t&#233;s non modale
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Généralement, les feuilles de propriétés que vous créez seront modales.  Lorsque vous utilisez une feuille de propriétés modales, l'utilisateur doit fermer la feuille de propriétés avant d'utiliser une autre partie de l'application.  Cet article décrit les méthodes que vous pouvez utiliser pour créer une feuille de propriétés non modales qui permet à l'utilisateur de gérer la feuille de propriétés ouverte lors de l'utilisation d'autres parties de l'application.  
  
 Pour afficher une feuille de propriétés comme boîte de dialogue non modales et non comme une boîte de dialogue modale, appelez [CPropertySheet::Create](../Topic/CPropertySheet::Create.md) au lieu d'[DoModal](../Topic/CPropertySheet::DoModal.md).  Vous devez également implémenter certaines tâches supplémentaires pour prendre en charge une feuille de propriétés non modales.  
  
 L'une des autres tâches est d' échanger des données entre une feuille de propriétés et l'objet externe qu'elle modifie lorsque la feuille de propriétés est ouverte.  C'est généralement la même tâche que pour les boîtes de dialogue non modales standard.  Partie de cette tâche implémente un canal de communication entre la feuille de propriétés non modales et l'objet externe auquel les paramètres de propriété s'applique.  Cette implémentation est beaucoup plus facile si vous dérivez une classe d'[CPropertySheet](../mfc/reference/cpropertysheet-class.md) pour votre feuille de propriétés non modales.  Cet article suppose que vous avez fait.  
  
 Une méthode pour communiquer entre la feuille de propriétés non modales et l'objet externe \(la sélection actuelle dans une vue, par exemple\) consiste à définir un pointeur de la feuille de propriétés à l'objet externe.  Définissez une fonction \(appelée un problème comme `SetMyExternalObject`\) dans `CPropertySheet`\- classe dérivée pour modifier le pointeur chaque fois que le focus se transforme en un objet externe vers une autre.  La fonction d'`SetMyExternalObject` doit réinitialiser les paramètres de chaque page de propriétés reflète l'objet externe être sélectionné.  Pour ce faire, la fonction d'`SetMyExternalObject` doit pouvoir accéder aux objets d'[CPropertyPage](../mfc/reference/cpropertypage-class.md) appartenant à la classe d'`CPropertySheet`.  
  
 Le moyen le plus pratique pour permettre aux pages de propriétés dans une feuille de propriétés est d'inclure les objets d'`CPropertyPage` dans `CPropertySheet`\- objet dérivé.  L'incorporation `CPropertyPage` dans `CPropertySheet`\- objet dérivé diffère de la conception standard pour les boîtes de dialogue modales, où le propriétaire de la feuille de propriétés crée les objets d'`CPropertyPage` et les passe à la feuille de propriétés via [CPropertySheet::AddPage](../Topic/CPropertySheet::AddPage.md).  
  
 Il existe de nombreuses méthodes de l'interface utilisateur pour déterminer quand les paramètres de la feuille de propriétés non modales doivent être appliqués à un objet externe.  Une alternative consiste à appliquer les paramètres de la page de propriétés active lorsque l'utilisateur modifie une valeur.  Une autre solution consiste à fournir un bouton de l'application, qui permet à l'utilisateur pour accumuler les modifications des pages de propriétés avant de valider à l'objet externe.  Pour plus d'informations sur les moyens de gérer le bouton de l'application, consultez l'article [Gérer le bouton de l'application](../mfc/handling-the-apply-button.md).  
  
## Voir aussi  
 [Feuilles de propriétés](../mfc/property-sheets-mfc.md)   
 [Échange des données](../mfc/exchanging-data.md)   
 [Cycle de vie d'une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)