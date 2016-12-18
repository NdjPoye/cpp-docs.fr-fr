---
title: "Type, propri&#233;t&#233; d&#39;un acc&#233;l&#233;rateur | Microsoft Docs"
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
  - "Type (propriété)"
  - "VIRTKEY"
ms.assetid: 8c349bc4-e6ad-43fa-959e-f29168af35b8
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Type, propri&#233;t&#233; d&#39;un acc&#233;l&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La propriété **Type** d'un accélérateur détermine si la combinaison de touches de raccourci associée à l'ID de l'accélérateur est une combinaison de touches virtuelle ou une valeur de touche ASCII\/ANSI :  
  
-   Si la propriété **Type** est **ASCII**, la propriété [Modifier](../windows/accelerator-modifier-property.md) ne peut être que Aucun ou Alt, ou elle peut utiliser un accélérateur qui utilise la touche CTRL \(spécifié en faisant précéder la touche d'un ^\).  
  
-   Si la propriété **Type** est **VIRTKEY**, toutes les combinaisons des valeurs Modifier et Key sont valides.  
  
    > [!NOTE]
    >  Si vous souhaitez entrer une valeur dans la table d'accélérateurs et que les valeurs soient traitées comme ASCII\/ANSI, cliquez sur le Type pour l'entrée dans la table et sélectionnez ASCII dans la liste déroulante.  Cependant, si vous utilisez la commande **Touche enfoncée suivante** \(menu **Edition**\) pour spécifier la touche, vous devez changer la propriété **Type** de VIRTKEY en ASCII *avant* d'entrer le code de la touche.  
  
## Configuration requise  
 Win32  
  
## Voir aussi  
 [Setting Accelerator Properties](../windows/setting-accelerator-properties.md)   
 [Accelerator Editor](../mfc/accelerator-editor.md)