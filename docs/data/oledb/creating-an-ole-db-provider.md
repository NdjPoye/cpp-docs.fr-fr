---
title: "Cr&#233;ation d&#39;un fournisseur OLE&#160;DB | Microsoft Docs"
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
  - "modèles du fournisseur OLE DB, créer des fournisseurs"
  - "fournisseurs OLE DB, créer"
ms.assetid: f73017c3-c89f-41a6-a306-ea992cf6092c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Cr&#233;ation d&#39;un fournisseur OLE&#160;DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La méthode recommandée pour créer un fournisseur OLE DB est de recourir aux Assistants pour créer un projet COM ATL et un fournisseur, puis de modifier les fichiers à l'aide des modèles OLE DB.  Quand vous personnalisez votre fournisseur, vous pouvez mettre en commentaire les propriétés indésirables et ajouter des interfaces facultatives.  
  
 Les étapes de base sont les suivantes :  
  
1.  Utilisez l'Assistant Projet ATL pour créer les fichiers projet de base et l'Assistant Fournisseur OLE DB ATL pour créer le fournisseur \(sélectionnez **Fournisseur OLE DB ATL** à partir du dossier Visual C\+\+ dans **Ajouter une classe**\).  
  
2.  Modifiez le code dans la méthode `Execute` dans CMyProviderRS.h.  Pour obtenir un exemple, consultez [Lecture de chaînes dans le fournisseur OLE DB](../../data/oledb/reading-strings-into-the-ole-db-provider.md).  
  
3.  Modifiez les mappages de propriété dans MyProviderDS.h, MyProviderSess.h et MyProviderRS.h.  L'Assistant crée des mappages de propriété qui contiennent toutes les propriétés qu'un fournisseur peut implémenter.  Parcourez les mappages des propriétés et supprimez ou mettez en commentaire les propriétés que votre fournisseur n'a pas besoin de prendre en charge.  
  
4.  Mettez à jour PROVIDER\_COLUMN\_MA qui se trouve dans MyProviderRS.h.  Pour obtenir un exemple, consultez [Stockage de chaînes dans le fournisseur OLE DB](../../data/oledb/storing-strings-in-the-ole-db-provider.md) \(page éventuellement en anglais\).  
  
5.  Lorsque vous êtes prêt à tester votre fournisseur, commencez par essayer de le trouver dans une énumération de fournisseurs.  Pour des exemples de code de test qui retrouve un fournisseur dans une énumération, consultez les exemples [CatDB](http://msdn.microsoft.com/fr-fr/003d516b-2bf6-444e-8be5-4ebaa0b66046) et [DBVIEWER](http://msdn.microsoft.com/fr-fr/07620f99-c347-4d09-9ebc-2459e8049832) ou l'exemple fourni dans [Implémentation d'un consommateur simple](../../data/oledb/implementing-a-simple-consumer.md).  
  
6.  Ajoutez, le cas échéant, des interfaces supplémentaires de votre choix.  Pour voir un exemple, consultez [Amélioration du fournisseur simple accessible en lecture seule](../../data/oledb/enhancing-the-simple-read-only-provider.md).  
  
    > [!NOTE]
    >  Par défaut, les Assistants génèrent un code conforme au niveau 0 OLE DB.  Pour vous assurer que votre application conserve une conformité au niveau 0, ne supprimez dans le code aucune des interfaces générées par l'Assistant.  
  
## Voir aussi  
 [CATDB](http://msdn.microsoft.com/fr-fr/003d516b-2bf6-444e-8be5-4ebaa0b66046)   
 [DBVIEWER](http://msdn.microsoft.com/fr-fr/07620f99-c347-4d09-9ebc-2459e8049832)