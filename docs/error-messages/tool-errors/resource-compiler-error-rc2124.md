---
title: "Erreur RC2124 du compilateur de ressources  | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC2124"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC2124"
ms.assetid: 4eb5c4ec-ca9b-46a0-805b-35e040e9ed41
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur RC2124 du compilateur de ressources 
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

menus vides non autorisés  
  
 Un mot clé **END** apparaît alors qu'aucun élément de menu n'a été défini dans l'instruction **MENU**.  Le compilateur de ressources n'autorise pas les menus vides.  Assurez\-vous que l'instruction **MENU** ne contient pas de guillemets ouvrants.