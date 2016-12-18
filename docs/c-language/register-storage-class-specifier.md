---
title: "Sp&#233;cificateur register de classe de stockage | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "classe de stockage de registre"
  - "variables de registre"
ms.assetid: 7577bf48-88ec-4191-873c-ef4217a4034e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Sp&#233;cificateur register de classe de stockage
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Le compilateur Microsoft C\/C\+\+ n'honore pas les requêtes utilisateur pour les variables de registre.  Toutefois, pour la portabilité, toutes les autres sémantiques associées au mot clé **register** sont honorées par le compilateur.  Par exemple, vous ne pouvez pas appliquer l'opérateur unaire address\-of \(**&**\) pour enregistrer un objet. De la même manière, le mot clé **register** ne peut pas être utilisé sur les tableaux.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Spécificateurs de classe de stockage pour les déclarations de niveau interne](../c-language/storage-class-specifiers-for-internal-level-declarations.md)