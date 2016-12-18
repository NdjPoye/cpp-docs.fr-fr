---
title: "Cr&#233;ation du fournisseur | Microsoft Docs"
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
  - "fournisseurs OLE DB, créer"
ms.assetid: 2506ba8f-010d-4231-aac1-387432f7b6b9
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation du fournisseur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

#### Pour créer un fournisseur OLE DB par l'intermédiaire de l'Assistant Fournisseur OLE DB ATL  
  
1.  Cliquez avec le bouton droit sur le projet.  
  
2.  Dans le menu contextuel, cliquez sur **Ajouter**, puis sur **Ajouter une classe**.  
  
3.  Dans la boîte de dialogue **Ajouter une classe**, sélectionnez l'icône **Fournisseur OLE DB ATL**, puis cliquez sur **Ouvrir**.  
  
4.  Dans l'Assistant Fournisseur OLE DB ATL, entrez un nom court pour le fournisseur dans la zone **Nom court**.  Les rubriques suivantes utilisent le nom court « MyProvider », mais vous pouvez choisir un autre nom.  Les autres zones de nom sont renseignées selon le nom que vous entrez.  
  
5.  Modifiez éventuellement les autres zones de noms.  Outre les noms d'objets et de fichiers, vous pouvez modifier les éléments suivants :  
  
    -   **Coclasse** : nom utilisé par COM pour créer le fournisseur.  
  
    -   **ProgID** : identificateur \(ID\) programmatique ; une chaîne de texte qui peut être utilisée à la place d'un GUID.  
  
    -   **Version** : utilisée avec ProgID et coclasse pour générer un ID programmatique dépendant de la version.  
  
6.  Cliquez sur **Terminer**.  
  
## Voir aussi  
 [Création d'un fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md)