---
title: "Mise en forme de CString et affichage des bo&#238;tes de message | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.strings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "objets CString, boîtes de message et de mise en forme"
ms.assetid: d1068cf4-9cc5-4952-b9e7-d612c53cbc28
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# Mise en forme de CString et affichage des bo&#238;tes de message
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un nombre de fonctions sont fournies au format et analysent des objets `CString`.  Vous pouvez utiliser ces fonctions lorsque vous devez manipuler des objets `CString`, mais ils sont particulièrement utiles pour mettre en forme les chaînes qui apparaîtront dans le texte de la fenêtre de message.  
  
 Ce groupe de fonctions inclut également une routine globale pour afficher un message.  
  
### Fonctions CString  
  
|||  
|-|-|  
|[AfxExtractSubString](../Topic/AfxExtractSubString.md)|Extrait des sous\-chaînes séparées par un seul caractère à partir d'une chaîne source donnée.|  
|[AfxFormatString1](../Topic/AfxFormatString1.md)|Remplace une chaîne donnée pour les caractères de format « %1 " dans une chaîne contenue dans la table de chaînes.|  
|[AfxFormatString2](../Topic/AfxFormatString2.md)|Remplace deux chaînes pour les caractères de format " %1 " " and "%2" dans une chaîne contenue dans la table de chaînes.|  
|[AfxMessageBox](../Topic/AfxMessageBox.md)|Affiche une boîte de message.|  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)   
 [CStringT Class](../../atl-mfc-shared/reference/cstringt-class.md)