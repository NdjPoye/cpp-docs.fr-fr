---
title: "Mise &#224; jour de donn&#233;es avec le contr&#244;le de donn&#233;es ADO | Microsoft Docs"
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
  - "ADO (C++), liaison de données"
  - "ADO (C++), contrôles de données"
ms.assetid: 8bec34b9-93dd-4872-b023-55ac011ccff5
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Mise &#224; jour de donn&#233;es avec le contr&#244;le de donn&#233;es ADO
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les données du contrôle de données ADO peuvent être en lecture seule ou modifiables.  
  
### Pour créer une application qui modifie les données à l'aide du contrôle de données ADO  
  
1.  Définissez la propriété **CursorLocation** du contrôle de données ADO.  Les options sont les suivantes :  
  
    -   Server Side \(côté serveur\)  
  
    -   Client Side \(côté client\)  
  
2.  Définissez la propriété **LockType** du contrôle de données ADO.  L'utilisation de l'accès concurrentiel optimiste est recommandée.  
  
3.  Définissez la propriété **CursorType** du contrôle de données ADO.  Les options sont les suivantes :  
  
    -   Keyset Cursor \(curseur sur ensemble de valeurs clés\)  
  
    -   Dynamic Cursor \(curseur dynamique\)  
  
    -   Static Cursor \(curseur statique\)  
  
     Assurez\-vous que le fournisseur OLE DB prend en charge l'option sélectionnée.  
  
4.  Définissez, selon le cas, les propriétés du contrôle lié aux données de façon à tenir compte des possibilités de mise à jour.  Remarquez que certains contrôles ne permettent pas la mise à jour.  
  
 Pour plus d'informations sur ces propriétés, consultez la documentation ADO.  
  
## Voir aussi  
 [Liaison de données ADO](../../data/ado-rdo/ado-databinding.md)   
 [Utilisation de la liaison de données ADO dans Visual C\+\+](../../data/ado-rdo/using-ado-databinding-in-visual-cpp.md)