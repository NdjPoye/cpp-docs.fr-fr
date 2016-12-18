---
title: "D&#233;bogage de votre fournisseur | Microsoft Docs"
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
  - "déboguer (C++), fournisseurs"
  - "fournisseurs OLE DB, débogage"
  - "débogueur Visual C++"
  - "débogueur Visual C++, déboguer les fournisseurs"
ms.assetid: 90d4e7db-06ea-4de0-a7f4-4f3751d50d93
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;bogage de votre fournisseur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour déboguer votre fournisseur, deux méthodes s'offrent à vous :  
  
-   Dans la mesure où les fournisseurs sont créés in\-process, vous pouvez créer un code consommateur à l'aide des modèles du consommateur OLE DB et exécuter pas à pas le fournisseur normalement.  
  
-   Vous pouvez utiliser l'utilitaire ITEST fourni avec Visual C\+\+.  
  
### Pour utiliser l'utilitaire ITEST  
  
1.  Ouvrez le projet du fournisseur.  
  
2.  Dans le menu **Projets**, cliquez sur **Paramètres**.  
  
3.  Dans la boîte de dialogue **Pages de propriétés**, cliquez sur l'onglet **Déboguer**.  
  
4.  Dans la zone **Exécutable pour session de débogage**, sélectionnez l'application ITEST.  
  
5.  Définissez les points d'arrêt et procédez au débogage comme d'habitude.  
  
## Voir aussi  
 [Utilisation des modèles du fournisseur OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)