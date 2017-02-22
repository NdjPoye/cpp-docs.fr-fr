---
title: "Classes de bases de donn&#233;es ATL (mod&#232;les OLE&#160;DB) | Microsoft Docs"
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
  - "classes de base de données (C++), ATL"
  - "classes de base de données (C++), OLE DB"
  - "modèles OLE DB (C++), classes de base de données ATL"
ms.assetid: 219766aa-e18a-405f-9e36-d7a0fdb31b2b
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Classes de bases de donn&#233;es ATL (mod&#232;les OLE&#160;DB)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft fournit plusieurs implémentations d'OLE DB, un jeu d'interfaces COM qui assurent un accès uniforme aux données dans divers formats et sources d'informations.  
  
 Les modèles OLE DB sont des modèles C\+\+ dans ATL ; ils facilitent l'utilisation de la technologie performante des bases de données OLE DB en fournissant des classes qui implémentent un grand nombre d'interfaces OLE DB courantes.  
  
 Cette bibliothèque de modèles se divise en deux parties :  
  
-   [Modèles du consommateur OLE DB](../data/oledb/ole-db-consumer-templates-cpp.md) Permettent d'implémenter une application de type client \(consommateur\) OLE DB.  
  
-   [Modèles du fournisseur OLE DB](../data/oledb/ole-db-provider-templates-cpp.md) Permettent d'implémenter une application de type serveur \(fournisseur\) OLE DB.  
  
 En outre, les [Attributs du consommateur OLE DB](../windows/ole-db-consumer-attributes.md) constituent un moyen commode pour créer des consommateurs OLE DB.  Les attributs OLE DB injectent un code basé sur les modèles du consommateur OLE DB pour créer des consommateurs OLE DB de travail.  
  
 Notez que la bibliothèque MFC contient une classe, [COleDBRecordView](../mfc/reference/coledbrecordview-class.md), qui affiche des enregistrements de base de données dans des contrôles.  La vue est une vue de type formulaire directement connectée à un objet `CRowset`, et affiche les champs de l'objet `CRowset` dans les contrôles du modèle de boîte de dialogue.  
  
 Pour plus d'informations, consultez l'[Programmation OLE DB](../data/oledb/ole-db-programming.md) et [Le guide de référence du programmeur OLE DB](http://go.microsoft.com/fwlink/?LinkId=121548).  
  
## Voir aussi  
 [Création d'un consommateur OLE DB](../data/oledb/creating-an-ole-db-consumer.md)   
 [Création d'un fournisseur OLE DB](../data/oledb/creating-an-ole-db-provider.md)   
 [Référence des modèles du consommateur OLE DB](../data/oledb/ole-db-consumer-templates-reference.md)   
 [Référence des modèles du fournisseur OLE DB](../data/oledb/ole-db-provider-templates-reference.md)   
 [OLE DB Templates Samples](http://msdn.microsoft.com/fr-fr/08958863-0b5f-41ad-ae99-fca7440c553c)