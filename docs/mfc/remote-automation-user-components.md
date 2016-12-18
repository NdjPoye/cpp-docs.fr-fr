---
title: "Composants utilisateur d&#39;Automation &#224; distance | Microsoft Docs"
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
  - "DLL (C++), Automation"
  - "Automation à distance (C++), composants utilisateur"
ms.assetid: 601591cc-a442-440a-988e-baf3284b0d46
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Composants utilisateur d&#39;Automation &#224; distance
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous devez vous assurer que chaque ordinateur client contient votre programme client et les DLL de support dont il a besoin.  Vous devez également vérifier que l'application serveur et toutes les DLL de support qu'elle nécessite sont présents sur l'ordinateur serveur.  Enfin, vous devez vous assurer que votre programme serveur est inscrit sur chaque ordinateur client avant que le gestionnaire RAC peut être exécuté pour configurer la connexion.  Si le programme automatise les enregistrements \(comme la plupart sont\), vous devez exécuter que le programme serveur sur l'ordinateur client pour inscrire.  Manquant cela, vous devrez peut\-être effectuer un fichier Registre que vous fournissez, ou modifiez manuellement le Registre.  
  
## Voir aussi  
 [Gestionnaire d'Automation \(MFC\)](../mfc/automation-manager-mfc.md)   
 [Remote Automation Connection Manager \(gestionnaire de connexion d'Automation à distance\)](../mfc/remote-automation-connection-manager.md)   
 [Installation de l'Automation à distance](../mfc/remote-automation-installation.md)