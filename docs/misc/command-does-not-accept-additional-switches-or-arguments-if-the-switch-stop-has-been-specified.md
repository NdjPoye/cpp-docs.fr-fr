---
title: "Command does not accept additional switches or arguments if the switch &quot;/stop&quot; has been specified. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.message.0x800A00CD"
  - "vs.message.VS_E_NOTVALIDWITHSTOP"
ms.assetid: 1dea2450-034e-4a7f-b959-2060811329b6
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Command does not accept additional switches or arguments if the switch &quot;/stop&quot; has been specified.
Cette erreur se produit généralement lorsque le commutateur `/stop` a été spécifié avec d'autres commutateurs pour les commandes **Rechercher dans les fichiers** ou **Remplacer dans les fichiers**.  
  
### Pour corriger cette erreur  
  
1.  Pour arrêter l'opération Rechercher dans les fichiers en cours, entrez :  
  
    ```  
    Edit.FindinFiles /stop.  
    ```  
  
2.  Pour arrêter l'opération Remplacer dans les fichiers en cours, entrez :  
  
    ```  
    Edit.ReplaceinFiles /stop  
    ```  
  
3.  Pour démarrer une nouvelle opération Rechercher dans les fichiers ou Remplacer dans les fichiers, entrez la commande sans `/stop`.  
  
## Voir aussi  
 [Remplacer dans les fichiers, commande](../Topic/Replace%20In%20Files%20Command.md)   
 [Rechercher dans les fichiers, commande](../Topic/Find%20in%20Files%20Command.md)   
 [Commandes Visual Studio](../Topic/Visual%20Studio%20Commands.md)